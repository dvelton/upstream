[ROLE CONTEXT, IF ANY, GOES ABOVE THIS LINE]

Analyze my recent AI usage for recurring patterns and identify the upstream structural fixes that would eliminate the recurrence.

Look at our conversation history in this session. If this tool has memory of past conversations, use that too. You're looking for the things I keep asking AI to help with. If I've also pasted additional prompts or notes below, include those in the analysis.

This is not a prompt engineering review. Don't optimize my prompts. The goal is to find the repeating queries that signal a missing artifact, an unresolved process gap, a skills deficit, or some other structural condition, and then recommend the one-time fix that makes those queries unnecessary.

## What I'm Providing

**Primary input:** The conversation history already available to you in this session (and across sessions, if your memory allows). This is the main source material.

**Additional input (optional):** I may paste extra prompts below — from other AI tools, rough notes, or paraphrased summaries of things I've asked elsewhere. Fold these into the analysis alongside the conversation history.

**Optional:** A one-sentence description of my role or professional context. If I don't include one, infer it from the content and flag the uncertainty in your analysis.

**Optional:** My approximate AI usage frequency and the timeframe these prompts cover (e.g., "these are from the past two months, I use AI 5-10 times a day"). If I don't include this, make a cautious inference from what's visible and state your assumption explicitly.

## Handling Varying Input Quality

Apply these rules before producing output:

- **Fewer than ~10 prompts:** Produce a shortened preliminary analysis. Identify one or two strongest tendencies. Skip the Pattern Tax section and any score estimates. End with specific guidance on what additional input would sharpen the analysis.
- **All one-offs, no visible patterns:** Say so directly. That's a valid finding. Distinguish between two possibilities: the user's AI usage is already well-calibrated (queries are genuinely non-repeating), or the sample isn't representative of actual usage.
- **Single cluster dominates:** Don't manufacture additional clusters to fill a quota. One well-diagnosed cluster is more useful than three padded ones.
- **Ambiguous or context-free prompts:** Note what's missing. Ask for clarification or suggest that a role sentence would help.
- **Mixed roles or workstreams:** Either split the analysis by workstream or note that the mix is reducing analytical clarity. Don't force disparate patterns into a single framework.
- **Never produce confident analysis from insufficient data.**

## Output Format

Produce four sections in this order. Use markdown headers and short paragraphs. Tables are fine for structured comparisons, but prose should carry the reasoning.

### Section 1: Clusters

Group the prompts into 3-6 recurring pattern types. Fewer if the sample supports fewer. Zero if there are no real patterns (see input quality rules above).

Give each cluster a plain-English label the user would immediately recognize from their own experience.

For each cluster, provide:

1. **What the pattern is.** One sentence.
2. **Why it recurs.** The upstream structural condition causing repetition. Be specific: a missing artifact, an unresolved process ambiguity, a skills gap, a relationship friction point, a standards vacuum, missing shared language, unclear authority. "You're busy" is not a cause. Name something the user can actually address.
3. **The one-time fix.** A concrete artifact or action, specified with enough detail to act on. Name the form it should take: "a one-page decision framework covering X," "a clause library for your 10 most contested provisions," "a 30-minute conversation with Y to align on Z." If no good fix exists because the work is legitimately non-repeating, say that plainly.
4. **Rough score.** Anchored to stated or inferred usage frequency. Use both proportional and absolute framing together: "roughly 15-20% of your recurring AI usage, or about 3-4 queries per week." If frequency wasn't provided, state the inference assumption. Label all estimates as rough.

Format as short paragraphs with reasoning, a summary table for at-a-glance comparison, or both.

### Section 2: The Pattern Tax

Write a short paragraph (not a list) synthesizing the cumulative cost across all clusters. Express the cost in time, not tokens or credits. Anchor it to stated or inferred usage frequency.

Frame it around loss aversion: what does continuing to handle these instance-by-instance actually cost over the next month and quarter, versus fixing the upstream cause once? Acknowledge uncertainty where it exists.

### Section 3: The One Thing

One recommendation. The single cluster fix with the highest return on effort. Make a call. Don't hedge.

If two clusters are genuinely close in impact, acknowledge it and explain why, but still pick one. "Both are strong candidates. I'd start with X because it's faster to implement and unblocks Y" is an acceptable form.

### Section 4: The Diagnostic Question to Carry Forward

Write one question, personalized to my dominant pattern. It should be specific enough that it would only make sense for this particular analysis, not a generic metacognitive prompt you could hand to anyone.

Target shape: "The next time you're [specific recurring task from the analysis], ask yourself whether [the upstream fix you identified] would make this query unnecessary."

The purpose is to give the user a habit: notice recurrence, trace it to the structural root, fix the root.

Close with a brief note that this analysis is designed to make itself unnecessary over time. If recurring AI queries drop after addressing the upstream fixes, the tool did its job.

## Additional Rules

**Multi-tool patterns:** If the history shows different AI tools used for different tasks, note it. Sometimes that reflects legitimate specialization. Sometimes it signals a fragmented workflow. Observe and note it, but don't turn the analysis into a tool comparison.

**Tone:** Be concrete and role-aware. Generic observations are worthless here. You're working from symptoms, not full context. Be confident about what patterns suggest, honest about what you can't see. Frame recommendations as strong starting points, not definitive prescriptions.

**Hard constraints:**

- Never suggest "use AI to automate this" as an intervention. The point is structural reduction of the need, not layering more AI on top of AI usage.
- Never rewrite or optimize my prompts. This is not about prompt craft.
- Don't recommend productivity tools, apps, or platforms unless genuinely necessary and no simpler alternative exists.
- Prefer artifacts the user can create themselves (a document, a template, a one-page reference, a conversation with a colleague) over systems they'd have to purchase or maintain.
- Be honest about limitations. If something specific would make a follow-up analysis more useful, say what it is.

---

**Additional prompts or notes, if any, follow below.**
