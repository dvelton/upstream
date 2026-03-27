# Legal Example

## Prompt Corpus

Role: Associate at a mid-size commercial law firm, focusing on technology transactions (SaaS, cloud, data licensing). These are from the past 6 weeks. I use AI tools maybe 8-12 times per week, split across ChatGPT, Copilot, and occasionally our firm's internal contract review tool.

1. Draft a mutual limitation of liability clause for a SaaS agreement where the customer is pushing for uncapped liability on IP indemnification and data breach. We've agreed to cap general liability at 12 months of fees but need carve-outs for IP infringement, confidentiality breach, and data protection violations.

2. The vendor came back rejecting our liability cap structure. They want consequential damages excluded entirely, no carve-outs. Draft fallback language that preserves our position on direct damages but concedes on consequential, with a super-cap on the carve-out items at 2x fees.

3. Compare these two indemnification provisions and tell me which is more favorable to the customer. [pasted two clauses from competing vendor forms]

4. Redline this limitation of liability section. The vendor's form uses a single aggregate cap with no carve-outs. We need IP indemnification and confidentiality breaches carved out, and I want the cap tied to fees paid in the prior 12-month period, not total contract value.

5. I need to explain to a client why they shouldn't accept unlimited liability for data breaches in a cloud services agreement. Their CEO thinks the vendor's cyber insurance covers the exposure. Short email, non-technical language.

6. Draft a status update email to the general counsel at Meridian Health. We've been negotiating their MSA with CloudServe for three weeks. Key open issues are the liability cap, data processing terms, and the SLA credit mechanism. We sent our last redline Tuesday and are waiting on their revised markup.

7. Write a short update for Linden Capital on the three contracts we're working in parallel. The data licensing agreement is in final redline and should close this week. The MSA is stalled because the vendor won't move on indemnity. The third contract (staff augmentation) just came in yesterday and we haven't started substantive review.

8. Draft a note to the procurement VP at TechPoint explaining that their vendor's data processing addendum doesn't meet GDPR requirements. Specifically, the sub-processor notification provision is missing, and the data transfer mechanism relies on Privacy Shield which is dead. Keep it plain English.

9. Help me write a billing summary email to the partner on the Meridian matter. The vendor changed their form agreement mid-negotiation after we'd already done a full redline, and we had to substantially re-do the markup. That's why the matter went over the original budget estimate by about 15 hours.

10. Explain what "consequential damages" means in a way that a product manager would understand. I'm on a call with a client's product team tomorrow and they keep asking why we care about this clause. They think it's boilerplate.

11. Draft talking points for a call with TechPoint's CTO. We need to explain why the vendor's limitation of liability clause is a problem for them, but in business risk terms, not legal terms. Focus on what happens if the vendor's platform goes down for an extended period and TechPoint's losses exceed the cap.

12. The business team at Linden wants to know what a "most favored customer" pricing provision actually commits them to operationally. What are the practical implications? Will they actually have to track and compare pricing across all their customers? A few bullet points.

13. Write a one-page risk summary of the CloudServe MSA for Meridian Health's board. Focus on data handling obligations, liability exposure, and termination rights. Assume a non-legal audience. Keep it under 500 words.

14. What's the current state of play on the FTC's non-compete rulemaking? I have a client asking whether they should still include non-competes in executive employment agreements or shift to a garden leave / PIIA approach. What's defensible right now?

15. Draft an assignment clause that requires consent for assignment but carves out assignments to affiliates and in connection with a merger, acquisition, or sale of substantially all assets. Governing law is Delaware. Include an anti-assignment provision that makes any prohibited assignment void.

16. Is there a standard market position on audit rights in enterprise SaaS agreements? Specifically, how often can the customer audit, what's a reasonable notice period, and is it typical to limit audits to once per 12-month period?

17. Draft a data retention and deletion clause for a SaaS agreement. The vendor wants to retain de-identified and aggregated data after termination for product improvement. What's a reasonable position that protects the customer but doesn't blow up the deal?

18. Summarize the key differences between SOC 2 Type I and Type II reports. A client's CISO is asking which they should require from their SaaS vendors, and I need to give a practical recommendation, not just a definitional comparison.

19. Draft a force majeure clause that explicitly addresses pandemics and government-mandated shutdowns. Standard commercial contract. Include a termination right if the force majeure event continues beyond 90 days. Don't make it look like it was written in response to COVID even though it obviously was.

20. Review this termination for convenience provision. The vendor is asking for 90 days' notice but our standard is 30. Is 90 days commercially reasonable for an enterprise SaaS agreement, or should we push back? What's the argument either way?

21. Help me draft a negotiation playbook for SaaS agreements. I want to document our standard positions on the 10 most commonly contested provisions: liability caps, indemnification, data protection, termination, SLAs, IP ownership, confidentiality, assignment, force majeure, and governing law. For each one, list our preferred position, the typical vendor pushback, and our fallback.

## Analysis Output

### Clusters

**1. Limitation of liability and indemnification rework**

Prompts 1, 2, 3, 4, 5, 11, and 20 all involve drafting, redlining, comparing, or explaining limitation of liability and indemnification provisions. This is the dominant pattern in the sample, accounting for roughly a third of all prompts.

The upstream cause is straightforward: you don't have a clause library or documented standard positions for your most-negotiated provisions. Every deal starts with a fresh drafting exercise or a redline against a vendor's form, and every round of pushback generates another drafting request. You're re-deriving your firm's position on liability caps, carve-out structures, super-caps, and consequential damages exclusions on a per-matter basis.

The fix is the artifact you actually started building in prompt 21: a negotiation playbook for your standard provisions. But the version that matters here is narrower and more immediately useful than a full playbook. Start with a one-page clause library covering just liability caps and indemnification. Include your preferred structure (tiered cap with carve-outs, 12-month fee basis), your standard fallback (super-cap at 2x for carved-out items, concede on consequential with floor protections), and annotated model language you can drop into any redline. If this document existed three weeks ago, prompts 1, 2, and 4 are copy-paste jobs instead of drafting exercises.

Rough score: roughly 30-35% of your recurring AI usage, or about 3-4 queries per week based on your stated frequency. This is the largest cluster by a wide margin.

**2. Client status communications**

Prompts 6, 7, 8, 9, and 13 are all client-facing communications: status updates, risk summaries, billing explanations. Different clients, different deal stages, but the underlying task is the same each time. You're composing a short professional email that summarizes where things stand and what's outstanding.

The upstream cause here is less about a missing artifact and more about a missing template structure for recurring communications. You write status updates frequently enough that the format and content categories are predictable (open issues, last action taken, next step, timeline), but each one starts from a blank page.

The fix is a set of 2-3 lightweight email templates: one for deal status updates, one for risk/issue escalation to a non-legal audience, and one for billing explanations. These aren't form letters. They're structured outlines with placeholders for the matter-specific details. The status update template might be five lines: client name, counterparty, open issues (bulleted), last action and date, next expected milestone. That's enough scaffolding that you'd fill it in directly rather than asking an AI to compose the whole email.

That said, I want to be honest about this cluster: some of these communications genuinely benefit from AI drafting assistance even with templates, particularly the ones aimed at non-legal audiences (prompts 8 and 13) where tone calibration matters. A template reduces the frequency, but it won't eliminate the need entirely.

Rough score: roughly 20-25% of your recurring usage, or about 2-3 queries per week.

**3. Translating legal concepts for business stakeholders**

Prompts 5, 10, 11, 12, and 18 all involve the same core task: taking a legal concept (consequential damages, liability cap mechanics, MFN pricing obligations, SOC 2 report types) and restating it for a non-lawyer audience. The audience varies (CEOs, product managers, CTOs, CISOs), but the translation job is the same.

The upstream cause is that your practice group doesn't have shared reference material for the business-facing explanations of concepts that come up in every technology transaction. You're rebuilding these explanations from scratch each time because there's no internal document that says "here's how we explain consequential damages to a business audience" or "here's the two-paragraph version of why liability caps matter."

The fix is a short internal reference document, maybe titled something like "Tech Transactions Concepts for Client Conversations," covering the 8-10 legal concepts you most frequently translate. For each one, write a two-to-three sentence plain-English explanation and a practical example. This doesn't need to be polished client-facing material. It's a cheat sheet for you and anyone else on your team who gets asked these questions. Once it exists, you can send the relevant excerpt directly or adapt it in two minutes instead of prompting an AI to generate the explanation fresh.

Rough score: roughly 20-25% of your recurring usage, or about 2 queries per week. The per-query time cost is moderate (these prompts are faster than drafting exercises), but the repetition is clear.

**4. Contract drafting one-offs**

Prompts 14, 15, 16, 17, and 19 are genuinely non-repeating tasks: a regulatory research question about FTC non-compete rulemaking, drafting an assignment clause with specific governing law requirements, market-standard audit rights, data retention positions, and a pandemic-aware force majeure clause.

These don't form a pattern that warrants an upstream fix. They're the kind of discrete, context-specific work that AI tools handle well. The variation in subject matter is real, and the specificity of each question (Delaware governing law, SOC 2 practical recommendations, 90-day force majeure termination trigger) suggests you're using AI appropriately here: as a first-draft or research accelerator for tasks that don't repeat enough to justify templating.

No intervention recommended. If anything, the existence of this cluster is a sign that your AI usage isn't uniformly a crutch. About a quarter of your prompts are well-calibrated to what AI is actually good at.

Rough score: roughly 20-25% of your usage. This is the baseline that would remain even if you addressed every other cluster.

**5. Prompt 21: the playbook attempt**

This one is worth flagging separately. Prompt 21 is you asking AI to help build a SaaS negotiation playbook, which is precisely the upstream artifact that would address Cluster 1 (and partially Cluster 3). You've already identified the need. The question is whether the AI-generated version is good enough to actually use, or whether it's a starting point that needs substantial rework based on your firm's actual positions and deal experience.

My guess is that an AI-generated playbook gives you a reasonable market-standard skeleton, but it won't reflect your specific practice's preferred positions, your clients' typical risk tolerances, or the firm's institutional knowledge about which fallbacks actually work in negotiation. The playbook is worth building, but build it from your own deal files, not from AI output. Use your last five or six completed SaaS deals as source material. Extract the positions you actually took, the concessions you actually made, and the language that actually closed.

No score assigned. This is a single prompt, not a recurring pattern.

### The Pattern Tax

Based on your stated usage of 8-12 AI queries per week, the three actionable clusters (liability language, client communications, and concept translation) account for roughly 70-75% of your recurring usage, or somewhere around 6-8 queries per week. At a conservative estimate of 10-15 minutes per prompt cycle (composing the prompt, reviewing the output, editing it into usable form), that's roughly 60-120 minutes per week spent on work that has a structural fix. Over the next quarter, that's somewhere in the range of 12-25 hours.

The time cost isn't catastrophic on its own. But the compounding cost is harder to see: every time you re-derive your standard position on liability caps, you're making a micro-judgment call that may or may not be consistent with what you did last month on a similar deal. The risk isn't just wasted time. It's inconsistency across matters and across attorneys if anyone else on your team is doing the same thing. The clause library and the negotiation playbook aren't just efficiency tools. They're quality control.

### The One Thing

Build the clause library for limitation of liability and indemnification. Not the full ten-provision playbook from prompt 21. Just the liability and indemnification sections, covering your preferred position, your standard fallback, and annotated model language for each. Pull it from your last five completed deals, not from AI output.

This addresses the largest cluster directly, partially reduces the concept-translation cluster (because the annotations serve as a reference for business-audience explanations), and it's a concrete artifact you can finish in a focused afternoon. The full playbook is a good idea, but starting with the highest-frequency provisions gets you the fastest return and builds momentum for the rest.

### The Diagnostic Question to Carry Forward

The next time you open ChatGPT to draft or redline a limitation of liability clause, ask yourself: am I generating new language for a new situation, or am I reconstructing the same position I took two deals ago because I don't have it written down anywhere?

If the answer is the second one more than occasionally, that's your signal to stop and spend the time on the clause library instead of the current prompt. This analysis is designed to make itself unnecessary. If the recurring clusters shrink and your AI usage shifts toward the one-off research and drafting work in Cluster 4, the upstream fixes did their job.
