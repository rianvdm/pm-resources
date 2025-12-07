# LLM Prompts

System prompts for working with LLMs on common product management tasks. These are designed to be used as custom instructions or system prompts in tools like Claude, ChatGPT, or other LLM interfaces.

## How to Use

1. Copy the contents of a prompt file
2. Paste it into your LLM's system prompt or custom instructions
3. For best results, add your own context files covering:
   - **About you** — Your role, responsibilities, and what you're working on
   - **Your leadership/product philosophy** — How you approach decisions, collaboration, and communication
   - **Style preferences** — Tone, structure, and formatting you prefer in responses

## Available Prompts

### Product Management (`pm/`)

| Prompt | Description |
|--------|-------------|
| [ask-a-pm.md](pm/ask-a-pm.md) | General-purpose PM assistant for drafting docs, thinking through problems, and day-to-day tasks |
| [draft-okrs.md](pm/draft-okrs.md) | Structured guide for drafting outcome-focused OKRs with anti-patterns to avoid |
| [draft-prd.md](pm/draft-prd.md) | PRD framework based on Marty Cagan's Product Opportunity Assessment |
| [draft-feedback.md](pm/draft-feedback.md) | Structured feedback drafting assistant |
| [debate-product-idea.md](pm/debate-product-idea.md) | Structured debate partner for stress-testing and refining product ideas |
| [summarize-interview.md](pm/summarize-interview.md) | Summarize interview notes |

### Technical (`technical/`)

| Prompt | Description |
|--------|-------------|
| [ask-an-se.md](technical/ask-an-se.md) | Technical Q&A assistant using official Cloudflare documentation |
| [eli5-devtools.md](technical/eli5-devtools.md) | Explains technical DevTools/infrastructure concepts for PMs |
| [cloudflare-explainer.md](technical/cloudflare-explainer.md) | Explains Cloudflare products in clear, PM-friendly language |

### Development (`dev/`)

| Prompt | Description |
|--------|-------------|
| [brainstorming_planning.md](dev/brainstorming_planning.md) | Brainstorming and planning sessions |
| [claude.md](dev/claude.md) | Claude-specific coding instructions |
| [code-review.md](dev/code-review.md) | Code review assistant |
| [development_session.md](dev/development_session.md) | Development session helper |

## Philosophy

These prompts are built around a few core principles:

- **Outcomes over outputs** — Focus on the change you want to see, not activities
- **Problem-first thinking** — Understand the problem before jumping to solutions
- **Clarity over comprehensiveness** — Short, direct, high-signal communication
- **Empowered teams** — Provide context and goals, trust teams to find the best approach

