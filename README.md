# upstream

Most people use AI to handle each instance of a recurring problem. Often the higher-return move is to fix the condition that creates the recurrence. One approach clears the task in front of you; the other reduces how often the task shows up at all. This repo is a tool for finding which of your recurring AI queries could be eliminated with a one-time structural fix.

## What's here

A prompt you paste into whatever AI tool you use, along with your recent prompt history. It analyzes your history for recurring patterns, identifies the upstream structural condition behind each one, and recommends specific one-time fixes. The output tells you what to build, write, or resolve so those queries stop coming back. If you want role-specific analysis, paste one of the included role preambles above the core prompt before adding your history.

## Why a prompt and not an app

This was a design decision. A standalone prompt is tool-agnostic. No account, no API key, no deployment, no dependencies. It works inside whatever AI environment you already use and trust. You paste it, you get results, you're done.

Building an app to tell people to use less AI would also be somewhat absurd.

## Collecting your prompt history

This is the main friction point, and there's no way around it. You need a sample of your recent AI prompts to feed to the analysis. The good news: it doesn't need to be perfect. Paraphrased prompts, rough notes, and partial histories all work. A messy but honest sample is better than waiting for a perfect export.

Here's what the collection process looks like for specific tools:

- **ChatGPT:** Go to Settings > Data Controls > Export. You'll get an email with a data dump. Alternatively, just scroll through recent conversations and copy your prompts manually. The export is cleaner; scrolling is faster.
- **Claude:** No bulk export option exists yet. Scroll through recent conversations and copy your prompts by hand. Focus on the last few weeks of regular use.
- **Copilot Chat / Cursor / IDE tools:** These often don't persist conversation history well across sessions. If this is your primary AI tool, keep a running note for a week or two where you jot down what you asked. Even shorthand is fine.
- **Gemini:** Google's Activity page at myactivity.google.com includes your Gemini queries. You can filter by product and date range.
- **Other tools or no export available:** Rough notes work. Spend 15 minutes writing down what you remember asking AI tools over the past month. Paraphrased prompts are fine. The analysis is looking for recurring patterns, not exact wording.

The whole collection step takes 15-30 minutes and it's the only real friction in this process. Twenty to fifty prompts is ideal, but work with what you have.

## Examples

**Lawyer:** A litigation attorney pastes six weeks of AI prompts and finds that about a quarter of them are variations on "draft a response explaining our position on limitation of liability." The queries span different deals but the arguments are the same three or four positions recycled each time. Upstream diagnosis: there's no clause library or standard position memo for commonly contested provisions. The fix is a one-page reference document covering the firm's standard positions on the ten most frequently negotiated points, with approved fallback language for each.

**Software engineer:** A backend developer's prompt history is heavy with "how do I set up X locally" and "why is this test failing with error Y." The setup questions repeat because onboarding docs are stale and the test failures trace to a flaky integration environment that everyone works around individually. Upstream diagnosis: missing or outdated runbook for local development setup, plus an unresolved environment reliability issue that the team has normalized. The fix is an afternoon spent updating the setup guide and filing (or fixing) the known flaky test.

**Engineering manager:** A team lead's prompts cluster around "summarize what happened this sprint" and "draft a status update for leadership." Each time, the manager is gathering the same information from the same sources and asking AI to structure it the same way. Upstream diagnosis: there's no reporting template or regular cadence that captures this information as work happens. The fix is a lightweight weekly template the team fills in as they go, so the summary writes itself by Friday.

**Content writer:** A marketing writer keeps asking AI to "rewrite this in our brand voice" and "restructure this blog post to match our usual format." The voice corrections and structural edits are consistent across pieces, which means the standards exist in the writer's head but nowhere else. Upstream diagnosis: missing voice guide and format template. The fix is a one-page brand voice reference (with before/after examples) and a structural template for the two or three content types the team publishes most often.

**Ops person:** An operations coordinator's prompts are full of "who owns this process" and "what's the handoff procedure for X." The questions come up when things fall between teams or when a process that normally runs on autopilot hits an exception. Upstream diagnosis: missing ownership map and incomplete handoff documentation. The fix is a simple intake form or checklist for the three or four handoff points that cause the most confusion, plus a one-page responsibility matrix that answers the "who owns this" question before it gets asked.

## Philosophy

Each individual AI query feels cheap. A minute of typing, a few seconds of waiting, a decent answer. But the aggregate cost of handling the same type of query repeatedly is not cheap, and the real issue goes beyond time. Tactical AI use, query by query, doesn't build anything. You handle the instance and the underlying condition remains. Next week, the same question comes back wearing different clothes.

There are two legitimate ways to use AI: as a recurring tool for ongoing tasks, and as a one-time intervention that eliminates a category of work. Most AI tooling is optimized for the first mode. This project is optimized for the second. The goal is to use AI once to diagnose a structural gap, fix the gap with a non-AI artifact (a document, a template, a conversation, a decision), and then never need AI for that particular problem again.

The prompt intentionally does not suggest "use more AI" as a fix for any pattern it identifies. This constraint is deliberate. The most common failure mode of AI-assisted diagnosis is recommending AI-assisted solutions, which converts a one-time analysis into a permanent dependency. Every recommended fix is something you can build, write, or resolve yourself.

## Limitations

The analysis works from symptoms alone. It can see your prompts but not your org chart, your existing tools, your team dynamics, or the political constraints that might make a "simple" fix complicated in practice. It doesn't know whether you've already tried the thing it's recommending, or whether your organization would actually adopt a new template if you created one.

Recommended interventions assume you have the authority and capacity to implement them. In practice, some fixes require buy-in from colleagues, changes to team process, or time you may not have. Treat the output as a starting point for your own reflection, not a consultant's report.

## The diagnostic question

The static, universal version:

> "The next time you notice you're asking AI the same thing twice, stop and ask: what upstream condition is making this keep coming back?"

When you run the prompt with your own history, it generates a personalized version of this question tailored to your dominant pattern. That personalized version is more useful because it names the specific recurring task and the specific structural gap.

The goal, eventually, is to make both versions unnecessary. Once you internalize the habit of tracing recurrence to root cause, you don't need a prompt to do it for you.

## How to use it

1. Open your AI tool of choice. Paste the contents of `prompt.md` into a new conversation. If you want role-specific analysis, paste the relevant file from `prompts/` above the core prompt.
2. Below the prompt, paste your recent AI prompt history. Raw transcripts, rough notes, or paraphrased summaries all work. Aim for 20-50 prompts from the last few weeks, but anything is better than nothing.
3. Read the analysis. Pick one fix and do it. You can rerun the analysis in a month or two to see if the patterns have shifted.

## What this is not

This is not a prompt optimizer. It won't make your AI queries better. It's not a productivity multiplier or an AI agent or assistant. It's not a critique of AI tools, which are genuinely useful for plenty of things. And it's not a full organizational assessment.

It's a periodic diagnostic. Run it occasionally when your AI usage starts feeling repetitive, see what it finds, and act on one thing. Then put it away until next time.

## Contributing

**Welcome:** Improvements to the core prompt, new role preambles, realistic examples, domain-specific corrections. If you work in a field not covered by the existing role variants and the generic prompt misses important context, a new preamble would be a genuinely useful contribution.

**Potentially welcome:** Lightweight helpers for collecting prompt history. The line here is about user agency. A script that exports your ChatGPT history into a text file you then paste manually is welcome. An app that watches your AI usage and sends you weekly reports is not. The distinction is whether the user stays in control of when and how the analysis runs.

**Not welcome:** App wrappers, dashboards, full automation, or features that encourage repeated use. The friction in this tool is somewhat intentional. If it were effortless to run constantly, it would become the kind of habitual AI dependency it's designed to diagnose.

## License

MIT
