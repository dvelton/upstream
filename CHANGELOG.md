# Changelog

## v1.1.0

- Revised core prompt to use conversation history directly instead of requiring manual prompt collection. The prompt now tells the AI to analyze the current session (and cross-session memory if available), with optional additional prompts pasted below.
- Shortened README significantly.

## v1.0.0

Initial release.

- Core prompt (`prompt.md`) with four-section analysis format: Clusters, Pattern Tax, The One Thing, Diagnostic Question
- Role preambles for legal, engineering, management, operations, and writing
- Examples for all five roles, including a sparse-input demonstration
- Input quality handling for thin, ambiguous, or pattern-less prompt histories
- Score calibration anchored to stated or inferred usage frequency
