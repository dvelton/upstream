# Engineering Example

## Prompt Corpus

> Role: Backend engineer at a mid-size SaaS company, mostly working on the payments service and internal APIs. These are from the past month. I use AI tools probably 15-20 times per week, split between Copilot in VS Code and ChatGPT.

---

1. Write a PR description for this diff. It adds exponential backoff retry logic to our Stripe webhook handler so transient failures don't drop events.

2. Why is my Postgres query slow even with an index on `created_at`? Here's the EXPLAIN ANALYZE output: [paste]

3. Help me explain to the PM why we can't just "add a field to the payments table" this sprint — there's a migration involved, we need to version the API response, and it touches the billing sync job.

4. Write a PR description for this change — it refactors subscription billing to pull pricing from the new plan-pricing service instead of hardcoding tier amounts.

5. I have a Redis SETNX being used as a distributed lock but it's not behaving correctly under concurrent load. The lock seems to be acquired twice sometimes. Here's the relevant code: [paste]

6. What's the difference between Bull and BullMQ for job queues in Node.js? We're already on Node 18 and Redis 7.

7. Write a commit message for this — it pulls the charge retry logic out of the billing controller into its own service class.

8. Help me respond to the PM asking why the invoice PDF feature can't ship this sprint. The real reason is that it depends on the document rendering service that's not done yet, but I also don't want to throw the other team under the bus.

9. Write a PR description for this — adds a compound index on (customer_id, status, created_at) to the subscriptions table to speed up the active subscription lookup query.

10. My async function isn't catching errors from a nested Promise. The outer try/catch doesn't fire. Here's the code: [paste]

11. Write tests for this payment processing function. It should cover: successful charge, card decline, network timeout, and idempotency key collision.

12. Help me explain to the PM why we need to finish the auth service refactor before we can ship SSO. She keeps asking if we can just "do SSO first and refactor later."

13. Our `/v1/charges` endpoint is throwing intermittent 504s under load. Here's the nginx access log and the Node process metrics during the spike: [paste]

14. Write a PR description for this change — it adds per-endpoint rate limiting to the public API using a sliding window counter in Redis.

15. Why would Stripe webhook signature verification fail intermittently? It works in dev and most of the time in prod, but we get occasional 400s from our own verification middleware.

16. Convert this SQL to use a CTE instead of the nested subquery. I want it to be more readable for the next person. [paste]

17. Help me write a runbook entry for the new "payment processor timeout" alert. What should on-call do when it fires, and what are the likely causes?

18. We have a scheduled billing job that runs at midnight UTC but it's charging some customers at the wrong local time for their invoice period. I think it's a timezone handling issue. Here's how we're constructing the billing date: [paste]

19. Write a PR description for this — it adds request ID propagation headers so we can trace a single transaction across the payments service, billing service, and notification service.

20. What are the actual tradeoffs between database transactions and the saga pattern for distributed payments? I know sagas are "the right answer" but I want to understand when a transaction across two services is genuinely acceptable vs. when it's going to bite us.

21. Help me write a message to the PM explaining why the "just add a retry" suggestion for the failed payment notification won't work without first fixing how we track notification state — right now there's no way to know if a notification was sent, so retrying would send duplicates.

22. Docker Compose config for local development — I need to run Postgres 15, Redis 7, and a mock Stripe server, with proper healthchecks so the app container waits for them.

23. Write a PR description for this diff — it switches our outbound HTTP client from `node-fetch` to `undici` and adds retry/timeout defaults so we stop getting hung connections to third-party APIs.

24. I keep getting `Cannot read properties of undefined (reading 'customerId')` in the charge handler but only for a specific webhook event type. How do I track this down systematically?

25. Help me write the architecture decision record for choosing Postgres over DynamoDB for the new audit log table. We evaluated both. Main factors were query flexibility and our team's existing expertise.

---

## Analysis Output

### Section 1: Clusters

---

**Cluster A: PR Descriptions**
Prompts 1, 4, 7, 9, 14, 19, 23 — 7 of 25 prompts, roughly 28%

Each of these starts cold. There's no template to fill in, so the engineer either writes something thin and feels bad about it, or delegates it to AI and gets something that vaguely describes what the diff does without explaining *why* the change was made. The outputs probably vary a lot in quality.

Upstream cause: No PR description template in the repo. Every PR starts from a blank box.

Fix: Add a `.github/PULL_REQUEST_TEMPLATE.md` with four fields — *What changed*, *Why*, *How to test*, *Anything reviewers should know*. This doesn't eliminate AI use here, but it changes the task from "write me a PR description" to "help me fill in this template," which produces better descriptions and takes less back-and-forth.

**This is legitimately recurring work.** Writing PR descriptions is part of the job. The issue isn't that you're doing it — it's that you're doing it in the most friction-heavy way possible every time.

Score: 7/25 prompts in this sample. At 15-20 queries/week over a month, that's probably 10-12 PR descriptions written this way. At 5-10 minutes per PR description session with AI, that's an hour or two a month on something a template would cut to under a minute per PR.

---

**Cluster B: Translating Technical Decisions for the PM**
Prompts 3, 8, 12, 21 — 4 of 25 prompts, roughly 16%

The pattern is consistent: PM asks why something is harder than it looks, engineer uses AI to draft a response that explains the technical reality in terms that won't alienate the relationship or cause a longer argument. The prompts themselves are a sign of real friction — you're spending mental energy managing the translation layer every time a technical constraint bumps into a business expectation.

Upstream cause: There's no shared reference document that describes how the payments service works, what its constraints are, or what the standing architectural decisions are. Every time a PM asks "can we just," the engineer has to reconstruct the explanation from scratch.

Fix: Write a one-page "How Payments Works" doc — not a spec, not an RFC, just a document written for non-engineers that explains the service's shape: what it owns, what it depends on, why certain changes are sequenced the way they are. Share it with the PM and reference it when these questions come up. This won't eliminate all of these conversations, but it moves the discussion from "let me explain this to you" to "let me point you to section 3."

Score: 4/25 in this sample. If this rate holds, you're writing PM-translation prompts 4-6 times a month, each taking 10-15 minutes to get right. That's an hour a month on what is fundamentally a documentation problem.

---

**Cluster C: Async, Distributed State, and Race Conditions**
Prompts 5, 10, 13, 15, 18 — 5 of 25 prompts, roughly 20%

These look like different problems — a Redis lock, an async try/catch, 504s under load, intermittent Stripe verification failures, a timezone bug — but they're all debugging distributed or asynchronous behavior where the failure is intermittent and the information available at debug time is insufficient. The common shape: "here's some logs and code, what's wrong?"

Upstream cause: The payments service has no distributed tracing. When something fails intermittently in a system with multiple async steps, network calls, and external dependencies, debugging from logs alone is slow and sometimes impossible. You're reconstructing the execution path by inference.

Fix: Add OpenTelemetry instrumentation to the payments service with traces exported to whatever your company is running (Datadog, Honeycomb, Jaeger). This is a real project — probably a few days of work — but it changes the debugging experience for every problem in this category. Instead of asking AI to interpret log fragments, you'd have spans showing exactly where the request spent its time and where it failed.

This cluster also includes two genuine one-offs that happen to fall in the same category (the timezone bug, the nested Promise issue). Those probably wouldn't recur even with better observability. Don't overfit the fix.

Score: 5/25. Intermittent distributed failures are inherently hard to debug. But the volume suggests this is costing 2-4 hours a month, most of which is information-gathering rather than actual problem-solving.

---

**Cluster D: Single-Query Knowledge Lookups**
Prompts 6, 16, 20, 25 — 4 of 25 prompts

Bull vs BullMQ, SQL CTEs, sagas vs transactions, Postgres vs DynamoDB for an audit log. These are legitimate one-offs — questions you'd look up once, probably never ask again, and the answers are genuinely useful. No structural fix needed here. This is AI being used correctly.

The saga/transaction question (prompt 20) is worth noting: the framing "I know sagas are the right answer but I want to understand when a transaction is acceptable" suggests you've absorbed received wisdom without the underlying model. That's normal and fine. The question is good.

---

### Section 2: The Pattern Tax

The PM-translation cluster and the PR-description cluster together account for 11 of 25 prompts — probably 40-50 minutes a week at your usage rate. Neither of these is deeply technical work. They're communication and documentation overhead that keeps landing in your AI queue because the right artifact (a PR template, a shared context document) doesn't exist. The observability gap in the debugging cluster is a different kind of tax: it doesn't show up as many prompts, but each debugging session takes significantly longer than it should, and the AI can only help you reason about incomplete information. It can't tell you what actually happened.

---

### Section 3: The One Thing

Add a PR description template this week. It takes 20 minutes, it's entirely in your control, and it will reduce the most frequent cluster immediately. The PM doc and the observability work are higher-leverage but harder to ship alone — the template you can just do.

---

### Section 4: The Diagnostic Question

Your PM-translation prompts are the most telling cluster, not because of the volume but because of the shape. You're drafting these carefully — "I don't want to throw the other team under the bus," "she keeps asking if we can do SSO first." That's not a writing problem; that's a structural problem where you're the only translator between how the system works and what the business expects.

The question worth sitting with: does your PM have any way to understand the payments service's constraints without asking you? If the answer is no, these prompts will keep coming no matter how good your AI responses are.

One last thing: the Docker Compose prompt (22) and the runbook prompt (17) are both setup and operational documentation tasks. They're not in a cluster, but taken with the ADR prompt (25), you're spending real time on documentation that probably lives in scattered places or doesn't exist yet. That's worth paying attention to separately.
