# Operations Example (Sparse Input)

## Prompt Corpus

Role: Program manager in business operations at a mid-size company. These are from the past two weeks — I just started tracking. I probably use AI 5-8 times per week.

1. Turn these ticket notes into a proper handoff summary for the overnight team. I need the open items, current status, and who to contact if something breaks. [pasted notes from Jira]

2. Draft a follow-up email to our logistics vendor about the SLA reporting delay. We've asked twice already. Needs to be professional but noticeably less patient than the first two.

3. What's the difference between a RACI and a DACI, and when would you actually use one over the other?

4. This project is transitioning from my team to the vendor-managed phase next week. Write me a handoff document: open items, decisions still pending, key contacts, and what they should not change without looping us back in.

5. Summarize these status updates from five different people into one paragraph I can paste into the exec report. [pasted Slack threads]

6. Help me write an agenda for a kickoff meeting for a new vendor onboarding process — 30 minutes, cross-functional attendees.

7. We got a revised contract from the vendor that changed payment terms without flagging it. Help me write a note to our procurement contact that documents what changed and asks them to explain the rationale.

8. I need to write an OOO message for next week but I also want to make sure the right people know who to go to for each thing I own. Can you help me draft both the OOO and a brief internal coverage note?

---

## Analysis Output (Preliminary)

**Note:** Eight prompts is below the threshold for a full analysis. At your stated usage rate of 5-8 queries per week, this covers roughly two weeks — enough to spot tendencies, not enough to confirm patterns with confidence. What follows is a preliminary read. Score estimates and a Pattern Tax calculation are omitted; both would be fabricated from too little data.

---

### What the Sample Suggests

Two tendencies stand out, though neither is confirmed.

**Handoff and coverage writing.** Three of eight prompts involve writing something down so work can continue without you — an overnight handoff, a project transition document, and an OOO coverage note. That's a high concentration for a two-week window. The cause is almost certainly the same regardless of which specific handoff it is: no standard template, so you're constructing the output from scratch each time. The fix would be a single handoff template that covers the variables common across your handoff types (open items, current owner, escalation path, what shouldn't change without a check-in). One well-built template would handle most of what you're currently prompting for here.

**Vendor communication under friction.** Two prompts involve writing to vendors in situations where the normal register isn't quite right — the SLA follow-up that needs more weight behind it, and the undisclosed contract change. These aren't exactly the same task, but they share a shape: you're managing a relationship tension in writing and calibrating tone carefully. Whether this is a genuine recurring pattern or just a rough two weeks with vendors is impossible to say from two data points. Worth watching.

---

### What Can't Be Said Yet

The one-offs here — the RACI/DACI question, the exec status summary, the meeting agenda — don't point to anything structural on their own. They might represent genuine one-time needs, or they might be the visible edge of patterns that would show up in a larger sample. The status summary prompt (five threads → one paragraph) is the one I'd watch most closely; that kind of reconciliation task tends to recur more than people initially think.

---

### What Would Make a Full Analysis Useful

A month's worth of prompts, ideally 25-35, would support the full output. Specifically:

- More examples of your handoff work, across different contexts if possible. If the handoff pattern is real, the next month will show it clearly.
- Any additional vendor communications — not just the friction cases but the routine ones. That would clarify whether vendor writing is a recurring coordination cost or just noise from a difficult stretch.
- A few examples from your meeting and stakeholder management work. The kickoff agenda prompt hints at that load but there's not enough to say anything about it.

If you primarily use one AI tool, note that in the role context next time — it occasionally matters for diagnosing workflow fragmentation.

---

*This analysis is designed to become unnecessary. If recurring queries drop after you've addressed the upstream fixes, the tool did its job.*
