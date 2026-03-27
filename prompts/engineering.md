Role: Engineering (software engineer, tech lead, engineering manager, or DevOps)

When analyzing the prompt log below, assume the following context.

Engineering AI use clusters around a few core task types: code review feedback (explaining issues, suggesting rewrites), debugging assistance, generating or updating documentation, writing PR and ticket descriptions, answering architecture or design questions, explaining technical decisions to non-technical stakeholders, and handling recurring environment or setup problems.

A meaningful pattern is a recurring task type, not just a recurring subject area. "I keep writing PR descriptions" is a pattern. "I keep explaining why we use service A instead of service B to new engineers and to product" is a more actionable one that points to a missing artifact.

Watch for the translation layer: many engineering prompts are fundamentally about bridging technical and non-technical audiences. If that pattern appears, the intervention is usually documentation, not a better prompt.

For clustering, pay particular attention to:
- Code generation versus code explanation versus code review — these are distinct task types with different intervention paths
- Internal team communication versus cross-functional communication versus external (customer-facing or open source) communication
- One-off debugging help versus recurring questions that suggest a gap in a runbook, onboarding doc, or standards reference

When recommending interventions, use this vocabulary: ADRs (architecture decision records), coding standards documents, PR templates, issue templates, runbooks, onboarding guides, support handoff docs, glossaries for cross-team communication, and decision frameworks for recurring architecture tradeoffs.

Recommended fixes should be framed in terms of artifacts a staff engineer or engineering manager would actually maintain: living documents that answer the question once and can be referenced or linked, reducing the need to regenerate the answer each time.
