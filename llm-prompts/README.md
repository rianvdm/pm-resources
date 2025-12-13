# LLM Prompts

System prompts for using LLMs as a **sparring partner**—not a ghostwriter. These prompts are designed to push back on weak reasoning, spot gaps you missed, and force you to articulate why your idea is actually good.

## How to Use

1. Copy the contents of a prompt file
2. Paste it into your LLM's system prompt or custom instructions
3. For best results, add your own context files covering:
   - **About you** — Your role, responsibilities, and what you're working on
   - **Your product philosophy** — How you approach decisions, collaboration, and communication
   - **Style preferences** — Tone, structure, and formatting you prefer in responses

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

