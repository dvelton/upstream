# Writing Example

## Prompt Corpus

**Role:** Senior content strategist at a B2B SaaS company. I manage the blog, monthly newsletter, and occasional whitepapers. These are from the past 6 weeks, maybe 10-15 AI queries per week, mostly Claude.

---

**1** — Here are five bullet points from a product launch meeting. Turn these into a 600-word blog post for a developer audience. Tone should be practical, not salesy. [paste]

**2** — I have a draft from a contributor. It's solid but it doesn't match our style. [paste] Rewrite to match our voice — shorter paragraphs, active voice, fewer buzzwords. Keep all the ideas, just clean the presentation.

**3** — Give me 8 headline options for this post about API security. Audience is engineering managers, not developers.

**4** — The headline we went with isn't landing. [paste post + headline] Give me 10 more. Push harder on the business case angle, the risk framing isn't working.

**5** — Talking points from our CMO about our Series B. [paste] Blog post, 500 words, audience is customers and prospects. Should feel genuine — excited but not breathless.

**6** — This newsletter intro feels too stiff. [paste] Loosen it up — we're not a law firm. The content is fine, just the register is off.

**7** — Another contributor draft. [paste] Same issues as the last one: passive constructions throughout, lede buried in paragraph three, conclusion just trails off. Fix it.

**8** — I'm writing the intro to a whitepaper on zero-trust architecture for a non-technical audience. Before I start: what are the standard framings people use, what do they usually get wrong, and is there a smarter angle that's underused right now?

**9** — Headlines for the zero-trust piece. Audience is CISOs and security buyers — not engineers, not IT generalists. The piece argues that most companies are doing zero-trust backwards.

**10** — Executive talking points, conference recap version. [paste] 400 words, we were a sponsor, don't make it sound like a press release. The sponsorship shouldn't be the story.

**11** — Contributor draft, different contributor. [paste] This one is tighter than usual but the tone is too academic. We're a Series C company, not a research institution.

**12** — We're seeing developer readers bounce off our security content. [paste post] Reframe this piece — same information, but written for someone who owns the problem, not someone who has to comply with a policy.

**13** — Newsletter subject lines for this month's issue. Ten options. The issue covers a product update and a featured customer interview. Our open rate is fine, click-through is the problem.

**14** — Campaign brainstorm: we want to run a Q4 content series around the idea that security debt is like technical debt. What's the editorial angle? What would 4-6 pieces look like, and what's the through-line that makes it a campaign rather than just a list of posts?

**15** — CEO posted this on LinkedIn yesterday. [paste] He's making three good points but they're buried. Turn it into a blog post that lets those points breathe. Keep his voice.

**16** — Two versions of this paragraph. [paste] Which one lands better for a CFO audience and why? Then revise the weaker one.

**17** — Our CSO gave me talking points for a year-in-review post. [paste] Blog post, feel genuine — readers can smell the PR version of these.

**18** — Meta descriptions for five posts that went live this month. [paste titles and first paragraphs] Keep them under 155 characters, don't start with the company name.

**19** — I need to figure out whether our developer content problem is distribution or quality. Here's what we published in the last 90 days. [paste titles] Here's the engagement data. [paste] Help me think through this.

**20** — Headlines for the year-in-review. Can't be a listicle, can't be vague. Has to feel earned — the year was actually hard and the post should acknowledge that.

**21** — Contributor draft. [paste] Good research, but she writes like she's pitching a dissertation committee. We need it for the blog, not an academic journal. Restructure and rewrite the voice throughout.

---

## Analysis Output

### Section 1: Clusters

---

**Cluster A: Contributor Draft Reformatting**
Prompts 2, 7, 11, 21 — four instances in six weeks, different contributors, same underlying problems each time.

*Pattern:* A draft arrives. The ideas are there. The execution isn't — buried ledes, passive constructions, wrong register, conclusions that stop instead of land. You paste it into Claude and talk it through.

*Upstream cause:* There's no contributor brief. Contributors are receiving a topic, a deadline, and an audience description. That's not enough. They're writing to a standard they've never seen, so each draft is a negotiation instead of a revision.

*Fix:* A two-page contributor brief that goes out when you assign the piece. It should include your lede philosophy, a note on register (with a before/after example), paragraph length expectations, and the three things that will get a draft kicked back. The brief doesn't eliminate Claude from this workflow — it changes your role in it. Instead of reconstructing the piece, you're making smaller calls.

*Score:* 4 of your last 6 weeks. Probably 25-40 minutes per instance. This is your highest-frequency recurring cost.

---

**Cluster B: Executive Content Translation**
Prompts 1, 5, 10, 15, 17 — five instances. Different executives, different formats, always the same move: take points that were written for a meeting and make them work for readers who weren't there.

*Pattern:* The raw material is bullet points, a LinkedIn post, or a conference debrief. The output is a blog post that sounds like a person said it, not like someone approved it.

*Upstream cause:* There's no intake template for exec content. Every piece starts from a blank briefing. Executives are handing you their thinking in whatever form it happened to take that week, and you're doing the translation from scratch each time.

*Fix:* A one-page exec content brief. The exec (or their EA) fills it out before the conversation: intended audience, three things you want readers to understand, one thing you want to avoid, anything that's off-limits. That document becomes your prompt and your contract. Output quality goes up; back-and-forth goes down. You'll still use Claude for the drafting — the brief just means you're not also doing archaeology.

*Score:* Weekly pattern, roughly. High frequency, moderate time per instance.

---

**Cluster C: Audience Tone Adjustments**
Prompts 6, 12, 16, 19 — recalibrating voice or angle for a specific audience: developers, CFOs, security buyers, newsletter readers.

*Pattern:* Good content, wrong register. Or content that was written for one audience and needs to be adapted for another. The adjustment is always ad hoc — you describe the audience each time and ask Claude to recalibrate.

*Upstream cause:* Possible, but not certain. You could write three short audience guides (developer voice, security executive, financial buyer) and reference them in prompts instead of redescribing from scratch. That would make the prompts faster and the outputs more consistent.

*The complication:* Some of these adjustments are not infrastructure problems. Prompt 16 — which version lands better for a CFO — is editorial judgment. There's no document that makes that question easier to answer; it requires reading two pieces of writing and making a call. The right question for this cluster is whether the inconsistency is in your prompts or in the actual judgment required. If you're redescribing the same audience in the same words every time, that's a gap. If you're making genuinely different calls based on context, that's the job.

*Fix (partial):* Write the audience guides. See if it helps. Keep the judgment-call prompts — those are working correctly.

*Score:* Medium. Worth addressing, but some of this is not a gap.

---

**Cluster D: Headline Generation**
Prompts 3, 4, 9, 13, 20 — five headline sessions across six weeks. One of them (prompt 4) is a second pass on the same post.

*Pattern:* You generate a round of headlines, pick one or don't, come back for more, or refine based on what the piece became in editing.

*What this is not:* A sign of missing infrastructure.

Headline brainstorming is collaborative by nature. It requires iteration. The first round gives you material to react to; the second round reflects what you learned from the first. A better brief might get you closer on round one, but it won't make round two unnecessary — that second pass in prompt 4 happened because the first headline wasn't working on the page, not because the brief was vague.

Claude is a reasonable tool for this. The recurrence here is the nature of the work, not a signal that something is broken upstream. Headline iteration showing up five times in six weeks, at your publishing volume, is exactly what you'd expect.

*Fix:* None needed. This is appropriate recurrence.

*Score:* Not a pattern tax. Flag and move on.

---

**Cluster E: One-Off Strategic Work**
Prompts 8, 14, 19 — zero-trust research, Q4 campaign brainstorm, developer content diagnosis.

These are single-use, high-value, and the right kind of thing to bring to an AI. The research in prompt 8 informed a whitepaper; the diagnosis in prompt 19 is the kind of thinking that's useful to do out loud. None of these will recur in the same form.

*Score:* Not a pattern. No action required.

---

### Section 2: Pattern Tax

Two clusters are costing you real time on a recurring basis: contributor reformatting and exec content translation.

If each contributor reformat takes 30 minutes and you're doing it four times in six weeks, that's two hours. If exec translation takes 20 minutes a session and happens five times, that's another hour and a half. Neither number is alarming on its own, but the work is the same work each time — same diagnosis, same fix, same output. That's the sign of a missing document, not a hard problem.

A contributor brief and an exec content template together would probably cut that combined time by half. Not because you'd stop using Claude for drafts, but because you'd start from a better place each time.

The audience tone adjustments are worth watching. If the same five phrases keep showing up in how you describe your developer audience to Claude, that's a sign a short doc would pay off. If the context varies enough that the descriptions are genuinely different each time, then it's probably just the editorial texture of a multi-audience publication.

---

### Section 3: The One Thing

Write the contributor brief.

Not because it's the most intellectually interesting fix, but because it touches the highest-frequency pattern, it changes the contributor relationship in a way that scales, and it takes two hours to write once. Every contributor reformat you're doing right now is a version of the same conversation you haven't had with contributors yet. The brief has that conversation in advance.

The exec template is worth doing too, but the contributor brief should come first. Contributor volume is harder to control than exec volume, and the problems are more consistent across contributors.

---

### Section 4: Diagnostic Question

When a contributor draft lands in your inbox, what do you know about it before you open it?

If the answer is the topic and the deadline, that's the gap. The brief exists to make the answer: the audience, the intended argument, the structure they're working toward, and the register they've been asked to hit. With that in hand, your Claude prompt changes from "fix this" to "this needs work in the second half — here's the brief they were given, here's what they submitted."

That's a different conversation, and it produces a better draft faster.
