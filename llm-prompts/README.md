# LLM Prompts

System prompts for using LLMs as a sparring partner. These prompts are designed to push back on weak reasoning, spot gaps you missed, and force you to articulate why your idea is actually good.

## Available Prompts

### Product Management

| Prompt | Description |
|--------|-------------|
| [ask-a-pm.md](ask-a-pm.md) | General-purpose PM sparring partner for thinking through tradeoffs, preparing for meetings, and sanity-checking reasoning |
| [draft-review-okrs.md](draft-review-okrs.md) | Review OKRs with strict outcomes-over-outputs enforcement |
| [draft-review-prd.md](draft-review-prd.md) | Stress-test PRDs based on Marty Cagan's Product Opportunity Assessment |
| [debate-product-idea.md](debate-product-idea.md) | Simulates a Visionary vs. Skeptic debate to stress-test product ideas |

### Technical

| Prompt | Description |
|--------|-------------|
| [ask-a-dev.md](ask-a-dev.md) | Staff Engineer assistant for understanding systems and navigating codebases |
| [eli5-devtools.md](eli5-devtools.md) | "Explain Like I'm 5" for CI/CD, build systems, and SDLC concepts |
| [cloudflare-explainer.md](cloudflare-explainer.md) | Explains Cloudflare products in PM-friendly language |

## Philosophy

These prompts are built around a core belief: **the goal isn't to have AI write things for you—it's to have a thinking partner that:**

- Challenges weak problem statements before you waste time on solutions
- Spots missing success criteria you forgot to define
- Asks "why?" when your reasoning gets hand-wavy
- Points out when you're jumping to solutions before understanding the problem

I'd rather have an assistant that pushes back on bad ideas than one that says "Great idea!" to everything.

## How to Use

### File Structure

Set up a folder structure like this:

```
llm-prompts/
├── prompts/           # System prompts (this repo)
│   ├── pm/
│   └── technical/
├── context/           # Personal context files
│   ├── about-me.md
│   ├── product-philosophy.md
│   └── manager-readme.md
├── reference/         # Syntax guides, style guides
└── work/              # Saved feedback and refined docs
```

The key is the `context/` folder—files that describe who you are, how you work, and what you value. These get referenced alongside prompts to give the model background on you. Examples:

- **About you** — Your role, responsibilities, and what you're working on
- **Your product philosophy** — How you approach decisions and communication
- **Style preferences** — Tone, structure, and formatting you prefer

### In an IDE (Windsurf, Cursor, etc.)

If you're using an IDE with AI chat, you can reference files directly using `@` mentions:

- `@prompts/pm/ask-a-pm.md` — References a specific prompt
- `@context/about-me.md` — References a context file
- `@docs/project-brief.md` — References whatever you're working on

A typical message might look like:

> Using @prompts/pm/draft-review-prd.md and @context/product-philosophy.md, review the attached PRD and give me feedback on the problem statement and success metrics.

Or:

> Use @prompts/pm/ask-a-pm.md to help me prepare for tomorrow's brainstorming session. Here's the structure I'm thinking of. Help me poke holes in it and suggest improvements: [paste content]

### Composing Multiple Prompts

You can stack prompts for specific needs:

> Using @prompts/pm/debate-product-idea.md and @context/about-me.md, run a Pro vs. Skeptic debate on this feature idea: [describe idea]

> With @prompts/pm/ask-a-pm.md and @prompts/technical/eli5-devtools.md, I wrote this technical approach section for a PRD. Is my understanding correct? What am I oversimplifying or getting wrong?

### MCP Servers

If your IDE supports MCP (Model Context Protocol) servers, you can connect the AI to external data sources—internal wikis, documentation sites, code repositories, APIs. This grounds responses in actual information rather than just training data.

In prompts, you can tell the model which MCP servers are available and when to use them:

- Search official documentation first to ground answers in verified information
- Check internal wikis for known issues, edge cases, and workarounds
- Look at code repositories when documentation is incomplete
- Always cite sources with links

This turns a general-purpose assistant into something more like an expert with access to your company's actual knowledge base.

### Tips

- **Context files are worth the investment.** Files that describe who you are, how you work, and what you value pay off in every conversation.
- **Push back is a feature, not a bug.** If the model is challenging your approach, consider that it might be right.
- **Iterate on the prompts.** Update them based on what works and what doesn't.
- **Don't over-@ mention.** Start with the minimum context you need, add more if the model seems confused.

