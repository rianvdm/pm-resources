# LLM Prompts

System prompts for working with LLMs on common product management tasks. These are designed to be used as custom instructions or system prompts in tools like Claude, ChatGPT, or other LLM interfaces.

## How to Use

1. Copy the contents of a prompt file
2. Paste it into your LLM's system prompt or custom instructions
3. For best results, also include the relevant context files from `general-context/` (available in the [source repo](https://github.com/rianvdm/llm-prompts))

## Available Prompts

| Prompt | Description |
|--------|-------------|
| [ask-a-pm.md](ask-a-pm.md) | General-purpose PM assistant for drafting docs, thinking through problems, and day-to-day tasks |
| [ask-an-se.md](ask-an-se.md) | Technical Q&A assistant that answers questions using official Cloudflare documentation |
| [draft-okrs.md](draft-okrs.md) | Structured guide for drafting outcome-focused OKRs with anti-patterns to avoid |
| [draft-prd.md](draft-prd.md) | PRD framework based on Marty Cagan's Product Opportunity Assessment |
| [eli5-devtools.md](eli5-devtools.md) | Explains technical DevTools/infrastructure concepts in accessible language for PMs |

## Philosophy

These prompts are built around a few core principles:

- **Outcomes over outputs** — Focus on the change you want to see, not activities
- **Problem-first thinking** — Understand the problem before jumping to solutions
- **Clarity over comprehensiveness** — Short, direct, high-signal communication
- **Empowered teams** — Provide context and goals, trust teams to find the best approach

## Source

These prompts are synced from [rianvdm/llm-prompts](https://github.com/rianvdm/llm-prompts). For the full set of prompts and context files, see the source repo.
