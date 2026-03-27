# upstream

A prompt that analyzes your AI usage patterns, finds the recurring ones, and tells you what to fix so they stop recurring. You paste it into whatever AI tool you already use. It looks at your conversation history and produces a structured diagnosis.

## How to use it

1. Copy the contents of [`prompt.md`](prompt.md) into your AI tool. If you want role-specific analysis, paste a preamble from [`prompts/`](prompts/) above it.
2. That's it. The prompt tells the AI to analyze your conversation history in the current session. If your tool has cross-session memory, it'll use that too. You can also paste in prompts from other tools below the prompt if you want a broader picture.
3. Read the output. Pick one fix. Do it.

## What it produces

The analysis groups your prompts into recurring clusters, identifies the structural condition behind each one (a missing template, an undocumented process, a standards gap), and recommends a specific one-time fix. It also tells you which fix has the highest return if you only act on one thing.

The prompt won't suggest "use more AI" as a fix. Every recommendation is something you can build, write, or resolve without AI.

## Role preambles

Optional. Paste one above the core prompt to sharpen the analysis for your domain. Available for: [legal](prompts/legal.md), [engineering](prompts/engineering.md), [management](prompts/management.md), [operations](prompts/ops.md), [writing](prompts/writing.md).

## Examples

The [`examples/`](examples/) directory has full sample analyses for each role, including one that shows how the prompt handles a small sample size.

## Contributing

Improvements to the prompt, new role preambles, and realistic examples are welcome.  

## License

MIT
