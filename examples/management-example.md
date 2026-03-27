# Management Example

## Prompt Corpus

Role: Engineering manager, team of 7, at a Series C company. These prompts are from the past 5 weeks. I use AI a few times most days, maybe 25-30 queries per week total across ChatGPT and Claude.

1. Help me write this week's engineering update for my VP. We shipped the payments API refactor, missed our sprint goal by about 20%, one engineer is out sick. Keep it short, focus on progress.

2. 1:1 tomorrow with my most senior engineer. He's been quiet lately and I think he might be job hunting. Help me prep some questions that don't feel like an interrogation.

3. Write a performance review comment for an engineer who delivers consistently but never volunteers for anything, never speaks up in meetings, just does his work and goes home. Technically solid, not growing.

4. Weekly status to my VP: data pipeline work is on track, we had a production incident Tuesday that we resolved in 3 hours, overall morale seems good.

5. My VP asked why we're behind on Q3 commitments. I need a response that acknowledges the delay but frames it around the scope changes product pushed in August, not engineering velocity.

6. What's the DACI framework and when do you actually use it instead of RACI?

7. I need to ask for a senior backend engineer headcount. Help me write something that ties the ask to our Q4 roadmap, not just "the team is stretched."

8. Weekly update: shipped user dashboard v2, still blocked on the infra team for the DB migration. Nothing dramatic to report.

9. Talking points for a 1:1 with a junior engineer who's missed his sprint goals two weeks in a row. I want to be direct without making it feel like we're starting a formal performance process.

10. Same headcount justification I wrote last week, but now I need to present it to our CFO. She doesn't care about sprint capacity -- she cares about ARR and revenue risk.

11. Weekly status: DB migration finally unblocked, started it this week. Sprint is otherwise on track. Two engineers are at a conference next week so capacity will be light.

12. Performance review language for an engineer who is technically excellent but doesn't communicate blockers. She works around problems silently until they become incidents.

13. We're doing a small structural change next week: I'm taking on the notifications service from another team. Help me write the announcement to my team. I want it to feel like a clean handoff, not like we're absorbing someone else's technical debt.

14. Skip-level with my VP's boss next week. What should I prepare? I want to highlight what the team has shipped without it reading like a status report.

15. Weekly update: conference week, low output by design. Need to frame this for a VP who expects consistent delivery and I don't want it to read as "we did nothing for a week."

16. Following up with the junior engineer from a few weeks ago. Second sprint was better but not great. Help me prep the 1:1.

17. Product is pushing 3 new features into our Q4 roadmap. I need to write a capacity analysis explaining why we can't take all three without dropping existing commitments or adding headcount.

18. Same capacity argument but for the product lead, not leadership. She's more receptive to specific tradeoffs than to abstract capacity models.

19. Performance review for another engineer: mid-level, always delivers, technically solid, but I honestly can't tell if she's growing or just coasting. Review cycle is in two weeks.

20. Talking points for a feedback conversation with my most senior engineer. He's more engaged than I thought back in week 1, but he's started blocking junior engineers without realizing it -- answering questions in ways that shut down thinking rather than opening it up. Need to deliver this feedback carefully.

21. Weekly status: one engineer has given notice, transition plan in progress, Q4 commitments still on track.

22. Product is asking for a fourth feature on top of the three I already pushed back on. Help me write the response. I've already explained our capacity twice.

---

## Analysis Output

### Section 1: Clusters

**Weekly status drafting**

Once a week, the manager opens a new AI conversation and writes a status update from scratch. Six of the 22 prompts follow this pattern, one per week with a slight variation in week 5 (the conference framing) and week 5 again for the departure news. The audience is the same. The format is the same. The only variable is the week's actual content.

The upstream cause is the absence of a standing document template. The status update has stable structure: what shipped or progressed, what's at risk or blocked, what the team needs from leadership, one flag if there's anything unusual. Those fields don't change. What changes is what goes inside them. Right now the manager is treating the whole thing as a blank page, including the parts that never change.

Fix: Draft a four-field status template and keep it somewhere you'll open it directly -- not in a chat window, not in Notion three clicks deep. Fill it in yourself; use AI for weeks where something genuinely unusual needs framing, like the departure announcement. One hour to build, indefinite payoff.

Rough score: Six instances in five weeks, or roughly one per week indefinitely. At 25-30 queries per week, this cluster is running at about 20% of total weekly AI usage. Over the next year, that's 50-plus queries that a template would nearly eliminate.

---

**The same capacity argument, rebuilt for each audience**

Five prompts across the five weeks are variations on the same underlying claim: the team is at capacity, taking on more work requires a visible tradeoff. The VP version, the CFO version, the product lead version, the written headcount ask, the second capacity response after product came back with a fourth feature request. Each one rebuilds the argument from scratch.

The cause isn't that different audiences need different framings -- they do, and that part is legitimate. The problem is that there is no persistent model underneath the framings. Nothing written down that captures team headcount, current allocations, existing Q4 commitments, and what specifically trades off with any new request. Without that baseline document, every conversation requires the manager to reconstruct the facts from memory before they can frame them for the audience in front of them.

Fix: A one-page team capacity document. Current headcount, rough allocation by workstream, Q4 commitments mapped out, and a clear row for "what adding X costs." Update it once a quarter. Share it proactively with product before roadmap discussions start, not after features are already on the table. The audience-specific framings still require judgment, but the facts stop requiring reconstruction each time.

Rough score: Five instances in five weeks, not at a clean cadence. Probably 2-3 per month ongoing as the company scales and pressure on the roadmap increases. The cost compounds: repeatedly re-arguing the same constraint to the same stakeholders starts to read as a manager who doesn't have a clear view of their own team, which is a credibility problem independent of the time cost.

---

**Performance review language**

Three prompts involve writing formal feedback for direct reports. Two capture real behavioral observations that needed precise, defensible language. The third is for an engineer the manager genuinely isn't sure how to read -- whether she's growing or coasting. That ambiguity shows up in the prompt itself.

This is legitimately recurring work. Performance cycles happen on a fixed cadence. The language ends up in permanent records, gets read above the manager's level, and shapes how engineers are perceived in future promotion conversations. Getting it right takes thought, and translating a behavioral observation into language that is accurate, fair, and legally considered is a real skill that takes time to develop. Using AI as a thought partner here is a reasonable, ongoing use.

The minor fix: keep a personal reference of phrasings you've used that were accurate and defensible. Over time this builds a working vocabulary for the behavioral patterns you encounter most often -- the strong-but-doesn't-communicate-blockers profile, the solid-but-not-growing profile. That reduces blank-page cost slightly. But the core work here is real. This cluster isn't a structural problem.

Rough score: Three instances in five weeks, concentrated around review season. Not worth optimizing heavily.

---

**1:1 prep for difficult conversations**

Four prompts involve preparing for specific 1:1s: the potentially-departing senior engineer in week 1, the junior engineer's first underperformance conversation in week 3, the follow-up with that same engineer in week 5, and the feedback conversation about the senior engineer blocking his junior colleagues in week 5.

These are not all the same kind of work. The first underperformance conversation (prompt 9) and the blocking-behavior feedback (prompt 20) are genuinely hard. The framing matters because the wrong approach can damage trust or miss the point. Preparation there is real work, and using AI to think through it is a reasonable use.

The follow-up conversation (prompt 16) is different. By the second conversation about the same situation, the manager already knows what was said the first time, what they committed to check in on, and what they've observed since. The prep question should not require reconstructing any of that from memory. This one prompt points to a simple gap: no running notes from the previous conversation.

Fix: A private per-report log. One short paragraph per 1:1: what came up, what you said, what you're watching for next time. Three sentences is enough. The follow-up prep largely writes itself when that paragraph exists. The genuinely hard first-time conversations -- the ones with real stakes and ambiguous framing -- still benefit from preparation and that use is worth keeping.

Rough score: Two of the four prompts here are addressable with basic note-keeping. The other two are legitimate prep work. Net addressable: roughly one query per month. Low priority on its own, but the habit compounds if the team grows or the manager is carrying more difficult dynamics at once.

---

**Summary**

| Cluster | Prompts | Upstream cause | Fix | Rough weekly cost |
|---|---|---|---|---|
| Weekly status drafting | 6 | No standing template | Four-field status doc | ~1/week |
| Capacity argument reconstruction | 5 | No persistent capacity model | One-page team capacity doc | ~2-3/month |
| Performance review language | 3 | Legitimately recurring | Minor: personal phrasings log | Seasonal; healthy use |
| 1:1 follow-up prep | 2 of 4 | No per-report running notes | One paragraph of notes per 1:1 | ~1/month |

---

### Section 2: The Pattern Tax

At 25-30 queries per week, this corpus represents roughly 125-150 total queries over five weeks. The 22 prompts here are a curated slice of that, which means the real cost across the two addressable clusters is probably higher than the sample shows.

Within what's visible: the status habit alone will generate around 50 queries over the next year, most of which would stop with a template built in an hour. The capacity argument cluster is less predictable in cadence, but it grows as the company scales and stakeholder pressure on roadmaps increases. Today it's three audiences; in six months it may be five. Without a capacity document, every new audience is a new reconstruction. Combined, the two primary clusters account for roughly 35-40% of the pattern-driven queries in this sample, or about 3-4 queries per week that don't need to exist.

The non-time cost is worth naming. The capacity argument cluster isn't just burning queries -- it's putting the manager in a reactive position in every roadmap conversation. Sharing a capacity document proactively changes that dynamic. The status template matters for similar reasons: the manager who shows up with a formatted update rather than a freshly written paragraph every week presents differently to their VP, even if the content is identical.

---

### Section 3: The One Thing

Build the status template.

The capacity document has a higher strategic ceiling -- it changes the dynamic in roadmap conversations rather than just reducing friction in a weekly routine. But it takes longer to build well. It requires headcount data, honest allocation estimates, and some judgment about how to represent uncertainty. The status template can be drafted in an hour today from two or three updates already written. The gains start next week.

Once the template exists, the status prompts drop out of the queue entirely. More importantly, it breaks the habit of treating AI as the writing environment for tasks that already have stable structure. That shift in how the manager relates to the tool is worth as much as the template itself.

After the template: build the capacity document. Both are worth having, and neither is complicated.

---

### Section 4: The Diagnostic Question to Carry Forward

The next time you open a new conversation to draft the weekly VP update, ask yourself whether a four-field template you already have would have gotten you to the same place in ten minutes without the conversation.

---

*This analysis is designed to make itself unnecessary. If the recurring clusters drop after the fixes are in place, the tool did its job.*
