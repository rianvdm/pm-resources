**(Note: this is the README from my private Product AI repo. Adjust as needed for your own use.)**

# Product AI Second Brain

*Last updated: 2026-02-02*

A personal knowledge system for product management work, optimized for [OpenCode](https://opencode.ai) and other AI chat tools (Claude.ai, ChatGPT).

## What This Is

This repo serves as my "second brain" for product work at Cloudflare. It contains:

- **Context files** that teach AI assistants how I think and write
- **Prompts** for common PM tasks (PRDs, OKRs, feedback, etc.)
- **Skills** that apply my methodology to conversations
- **Slash commands** for quick workflows in OpenCode
- **Project brains** for deep work on specific initiatives
- **Work artifacts** organized by team and category

## Quick Start

**For OpenCode users:**
Use slash commands like `/prd`, `/okr`, `/debate` to trigger workflows.

**For other AI tools:**
Copy the relevant prompt from `prompts/` into your conversation, or upload context files to your AI project.

## Repository Structure

```
.opencode/
├── agent/          # Subagents (e.g., cloudflare-research)
├── command/        # Slash commands for OpenCode
└── skills/         # On-demand methodology and context

context/            # Personal context files (philosophy, writing style, etc.)

prompts/
├── pm/             # Product management prompts
├── dev/            # Development and debugging prompts
├── hr/             # Feedback and interview prompts
└── meta/           # Prompts for creating/improving prompts

work/
└── cloudflare/     # Cloudflare work artifacts
    ├── product/    # PRDs, OKRs, strategies by team
    ├── projects/   # Project brains with dedicated context
    ├── briefings/  # Calendar briefings (generated)
    ├── weeknotes/  # Daily and weekly summaries (generated)
    ├── hiring/     # Interview notes, job descriptions
    ├── support/    # Customer support research
    └── team/       # Team-related docs

personal/           # Side projects and blog posts

reference/          # Syntax guides, recipes, quick reference

scripts/            # Python scripts (calendar briefing, etc.)
.venv/              # Python 3.12 virtual environment (gitignored)

chat/               # Second Brain Chat app (beta) - conversational interface
docs/               # Planning docs, audit reports, technical references

AGENTS.md           # Main instructions (auto-loaded by OpenCode via opencode.jsonc)
opencode.jsonc      # OpenCode config (MCP servers, instructions reference)
```

## Agents

Agents are specialized subagents that can be invoked directly with `@` or via the Task tool.

| Agent | Purpose |
|-------|---------|
| `cloudflare-research` | Research Cloudflare topics across docs, wiki, gitlab, jira, graphql, and backstage. Returns structured JSON with findings and sources. |

**Location:** `.opencode/agent/`

## Skills

Skills are methodology files that OpenCode loads on-demand when relevant. They inject my product philosophy into conversations.

| Skill | What It Does |
|-------|--------------|
| `pm-thinking` | Applies problem-first thinking, outcomes over outputs, empowered teams philosophy |
| `cloudflare-context` | Loads Cloudflare knowledge, triggers proactive use of internal MCP servers |
| `data-team-context` | Loads Data team strategy, priorities, and constraints |

For writing style guidance, reference these context files on demand:
- `context/writing-style-work.md` - Professional writing style
- `context/writing-style-personal.md` - Personal/blog writing style

## Slash Commands

Quick workflows for OpenCode. Run these by typing the command in your conversation.

| Command | Purpose |
|---------|---------|
| `/prd` | Write or review a PRD (problem-first, Confluence Wiki Markup) |
| `/okr` | Draft or review OKRs |
| `/debate` | Stress-test a product idea with pro vs skeptic simulation |
| `/retro` | Facilitate or document a retrospective |
| `/feedback` | Draft colleague feedback |
| `/new-project` | Scaffold a new project brain folder |
| `/ask-se` | Get help understanding technical concepts |
| `/today` | Generate end-of-day summary from file activity |
| `/weekly` | Generate manager-ready weekly summary from weeknotes |
| `/context-check` | Show current context window usage and loaded skills |
| `/briefing` | Generate calendar briefing for today, tomorrow, or the week |
| `/extract-pdf` | Extract PDF content to well-formatted Markdown |
| `/blog-summary` | Generate newsletter-ready summary of recent blog posts |
| `/link-post` | Create a short link post for personal blog |
| `/share-prompt` | Convert prompt to shareable Confluence format |
| `/tasks` | Query or manage OmniFocus tasks using natural language |
| `/gmail` | Search and summarize Gmail emails |
| `/docs` | Read and write Google Docs, Sheets, and Slides |
| `/wiki` | Read and write Confluence wiki pages |
| `/surf` | Open a file in Windsurf IDE |

### Daily and Weekly Summaries

The `/today` and `/weekly` commands automate work journaling based on file activity.

**`/today`** generates an end-of-day summary:
- Finds files modified on the target date using filesystem timestamps
- Groups related work into meaningful categories
- Focuses on outcomes, not just tasks completed
- Saves to `work/cloudflare/weeknotes/YYYY/MM/week-WW/YYYY-MM-DD.md`

```bash
/today                    # Summarize today's work
/today yesterday          # Summarize yesterday
/today 2025-12-16         # Summarize a specific date
/today "focused on PRD work"  # Add context to include
```

**`/weekly`** synthesizes daily notes into a manager-appropriate summary:
- Reads daily weeknotes for the date range
- Falls back to filesystem timestamps if dailies are sparse
- Frames work in terms of business impact (VP-level appropriate)
- Saves to `work/cloudflare/weeknotes/YYYY/MM/week-WW/week-WW-summary.md`

```bash
/weekly                   # Current week (Monday through today)
/weekly last week         # Previous Monday-Sunday
/weekly dec 9-13          # Specific date range
```

**Workflow:** Run `/today` at the end of each day to capture work while it's fresh. Run `/weekly` on Friday (or Monday for the prior week) to generate a summary ready for 1:1s or status updates.

### Calendar Briefings

The `/briefing` command generates AI-powered calendar summaries that highlight what's important, flag meetings that could be async, and suggest prep work.

```bash
/briefing today           # Brief on today's calendar
/briefing tomorrow        # Brief on tomorrow (default)
/briefing week            # Brief on the next 7 days
```

Briefings are saved to `work/cloudflare/briefings/` and use your personal context from `context/about-me.md` to personalize recommendations.

**Setup:** Requires one-time Google Calendar OAuth setup. Run `python scripts/setup_google_oauth.py` to configure.

### OmniFocus Integration

The `/tasks` command provides natural language access to OmniFocus tasks via the `scripts/omnifocus.py` script.

```bash
/tasks what's due today?
/tasks cloudflare tasks due this week
/tasks what's in my inbox?
/tasks add "Review PR" to cloudflare due friday
/tasks complete the review PR task
```

The script can also be used directly:

```bash
# List tasks
.venv/bin/python scripts/omnifocus.py inbox
.venv/bin/python scripts/omnifocus.py due today
.venv/bin/python scripts/omnifocus.py project "Cloudflare"

# Add and manage tasks
.venv/bin/python scripts/omnifocus.py add "Task name" --project "Work" --due "2026-01-15"
.venv/bin/python scripts/omnifocus.py complete "Task name"

# Output as JSON for scripting
.venv/bin/python scripts/omnifocus.py inbox --json
```

**Requirements:** macOS with OmniFocus installed. The script uses AppleScript for integration.

### Gmail Integration

The `/gmail` command searches and summarizes Gmail emails using the `scripts/gmail_reader.py` script.

```bash
/gmail summarize emails from Matt about docs
/gmail unread emails this week
/gmail what did Sarah send me about the project?
/gmail emails with attachments about Q4
```

The script can also be used directly:

```bash
# Search emails
.venv/bin/python scripts/gmail_reader.py "quarterly review"
.venv/bin/python scripts/gmail_reader.py --from "boss@company.com"
.venv/bin/python scripts/gmail_reader.py --after 2025-01-01 --unread

# Get AI summary
.venv/bin/python scripts/gmail_reader.py --summarize "project update"

# Output as JSON for scripting
.venv/bin/python scripts/gmail_reader.py --json "OKR"
```

**Setup:** Requires Google OAuth credentials. Run `python scripts/setup_google_oauth.py` to configure, then add the credentials to your environment.

### Google Docs, Sheets & Slides Integration

The `/docs` command reads Google Docs, Sheets, and Slides as Markdown. It auto-detects the type from the URL.

```bash
/docs https://docs.google.com/document/d/1ABC123xyz/edit
/docs https://docs.google.com/spreadsheets/d/1ABC123xyz/edit
/docs https://docs.google.com/presentation/d/1ABC123xyz/edit
```

The scripts can also be used directly:

```bash
# Google Docs
.venv/bin/python scripts/google_docs_reader.py "https://docs.google.com/document/d/1ABC123xyz/edit"
.venv/bin/python scripts/google_docs_reader.py --comments "1ABC123xyz"  # Include comments
.venv/bin/python scripts/google_docs_reader.py --json "1ABC123xyz"     # JSON output

# Google Sheets
.venv/bin/python scripts/google_sheets_reader.py "https://docs.google.com/spreadsheets/d/1ABC123xyz/edit"
.venv/bin/python scripts/google_sheets_reader.py --sheet "Q1 Roadmap" "1ABC123xyz"  # Specific sheet
.venv/bin/python scripts/google_sheets_reader.py --all "1ABC123xyz"    # All sheets
.venv/bin/python scripts/google_sheets_reader.py --list "1ABC123xyz"   # List sheet names

# Google Slides
.venv/bin/python scripts/google_slides_reader.py "https://docs.google.com/presentation/d/1ABC123xyz/edit"
.venv/bin/python scripts/google_slides_reader.py --notes "1ABC123xyz"     # Include speaker notes
.venv/bin/python scripts/google_slides_reader.py --comments "1ABC123xyz"  # Include comments
```

**Setup:** Requires Google OAuth with Drive, Docs, and Slides API access. If you already have Gmail/Calendar OAuth configured, you'll need to:
1. Enable "Google Drive API", "Google Docs API", and "Google Slides API" in Google Cloud Console
2. Re-run `python scripts/setup_google_oauth.py` to get a new token with expanded scopes
3. Update `GOOGLE_REFRESH_TOKEN` in your `.env` file

## Prompts

Standalone prompts that work in any AI tool. Copy the content into your conversation or upload to your AI project.

**Product Management:**
- `prompts/pm/review-prd.md` - Write or review PRDs
- `prompts/pm/review-okrs.md` - Write or review OKRs
- `prompts/pm/debate-product-idea.md` - Product idea stress-testing
- `prompts/pm/decision-log.md` - Document decisions with context
- `prompts/pm/retrospective.md` - Facilitate retrospectives
- `prompts/pm/stakeholder-map.md` - Map stakeholders and engagement strategies
- `prompts/pm/competitive-analysis.md` - Analyze competitors
- `prompts/pm/draft-review-devdocs.md` - Review Cloudflare developer documentation
- `prompts/pm/eli5-cloudflare.md` - Explain Cloudflare concepts simply
- `prompts/pm/eli5-devtools.md` - Explain DevTools concepts simply
- `prompts/pm/ask-dev.md` - Role-play conversation with a developer
- `prompts/pm/ask-se.md` - Role-play conversation with a solutions engineer
- `prompts/pm/review-smashing-article.md` - Review Smashing Magazine article drafts

**Development:**
- `prompts/dev/code-review.md` - Code review guidance
- `prompts/dev/systematic-debugging.md` - Structured debugging approach
- `prompts/dev/brainstorming-planning.md` - Project brainstorming and spec creation
- `prompts/dev/development-session.md` - Development session instructions
- `prompts/dev/general-dev-guidance.md` - General development guidance

**HR:**
- `prompts/hr/draft-colleague-feedback.md` - Write performance feedback
- `prompts/hr/annual-review-synthesis.md` - Synthesize annual review feedback
- `prompts/hr/summarize-interview.md` - Summarize interview notes
- `prompts/hr/summarize-pm-intern-screen.md` - Summarize PM intern screen interviews

**Meta:**
- `prompts/meta/create-prompt.md` - Generate new prompts
- `prompts/meta/improve-prompt.md` - Refine existing prompts
- `prompts/meta/clean-transcript.md` - Clean up raw transcripts
- `prompts/meta/clean-dictation.md` - Clean up dictation text
- `prompts/meta/second-brain-audit.md` - Full repo health check and innovation scan

## Project Brains

For deep work on specific initiatives, I use dedicated project folders that serve as self-contained AI contexts:

```
work/cloudflare/projects/[project-name]/
├── CONTEXT.md        # Project brief, goals, stakeholders
├── artifacts/        # PRDs, specs, designs
├── decisions/        # Decision logs
├── research/         # Customer feedback, data analysis
└── meetings/         # Meeting notes
```

**The CONTEXT.md file** is the project's source of truth. It contains:
- Quick reference (status, team, links)
- Problem statement and target users
- Success metrics with baselines and targets
- Key stakeholders and their interests
- Current status with recent updates and next steps
- Key decisions made (summary table)
- Open questions

**Day-to-day workflow:**
1. When starting work on a project, point the assistant at the project folder: "Read the CONTEXT.md in backstage-data-quality and help me draft a stakeholder update"
2. As decisions get made, add them to the decisions table in CONTEXT.md (detailed logs go in `decisions/`)
3. Drop meeting notes, research docs, and artifacts into their respective folders
4. Keep CONTEXT.md current—it's what OpenCode reads to understand the project state

Use `/new-project` to scaffold a new project folder, or see `context/project-template.md` for the full template.

## Context Files

These files teach AI assistants about me and how I work:

| File | Purpose |
|------|---------|
| `context/about-me.md` | Personal background and role |
| `context/product-philosophy.md` | My beliefs about product work |
| `context/writing-style-work.md` | Professional writing style guide |
| `context/writing-style-personal.md` | Personal/blog writing style |
| `context/avoid-ai-patterns.md` | Language patterns to avoid |
| `context/project-template.md` | Template for project brains |
| `context/manager-readme.md` | Manager README / working with me guide |
| `context/personalization-instructions.md` | Instructions for personalizing AI outputs |
| `context/opencode-global-system.md` | Global OpenCode system prompt template |
| `context/respecttables-commands.md` | RespectTables commands reference |

## MCP Servers

When using OpenCode with MCP servers configured in `opencode.jsonc`, the assistant can proactively search:

- **cloudflare-docs** - Public Cloudflare documentation
- **wiki** - Internal wiki for prior decisions and context
- **graphql** - Analytics API schema exploration
- **gitlab** - Internal code repositories
- **jira** - Ticket lookup and project status
- **backstage** - Service catalog, team ownership, developer portal

## OpenCode Setup

This repo uses [OpenCode](https://opencode.ai) as the primary AI coding assistant.

| Component | Location |
|-----------|----------|
| Instructions | `AGENTS.md` (loaded via `opencode.jsonc`) |
| Slash commands | `.opencode/command/` |
| Skills | `.opencode/skills/` (loaded on-demand) |
| MCP servers | Configured in `opencode.jsonc` |

**How it works:**
- `AGENTS.md` contains all instructions for the AI assistant
- OpenCode loads it via the `instructions` array in `opencode.jsonc`
- Skills are loaded on-demand when relevant to the task at hand

## Adding New Components

### Slash Commands
Create `.opencode/command/[name].md` with frontmatter:
```markdown
---
description: Short description of what the command does
---
# Command Title

Instructions...

$ARGUMENTS
```

### Skills
Create `.opencode/skills/[name]/SKILL.md` including:
- When to invoke (triggers)
- Core context or methodology
- How to apply it
- Anti-patterns to flag

### Prompts
Create `prompts/[category]/[name].md`. Include clear structure and examples.

### Context Files
Add to `context/[name].md`. Reference documents about preferences or methodology.

### Scripts
Add Python scripts to `scripts/`. Include docstring with usage examples. Update `requirements.txt` if adding dependencies.

## File Naming Conventions

**Always use descriptive names.** Never name a file with just a date.

| Type | Format | Example |
|------|--------|---------|
| Meeting notes | `YYYY-MM-DD-meeting-topic.md` | `2026-01-05-devtools-leads-sync.md` |
| Decision logs | `YYYY-MM-DD-decision-topic.md` | `2026-01-05-bazel-migration-approach.md` |
| PRDs | `descriptive-name-prd.md` | `okr-tracker-v2-prd.md` |
| Research | `YYYY-MM-DD-research-topic.md` | `2026-01-05-customer-feedback-d1.md` |
| Weeknotes | `YYYY-MM-DD.md` (exception: dailies in weeknotes folder) | `2026-01-05.md` |

**Key rules:**
* Use lowercase with hyphens (kebab-case)
* Date prefix for time-sensitive artifacts (meetings, decisions, research)
* Descriptive suffix that explains what the file contains
* No spaces, no underscores

## Setup

### Git Aliases

This repo uses custom Git aliases for quick commits and maintenance. To set them up on a new machine:

```bash
git config --global alias.up '!git add -A && git commit -m "Updates" && git push'
git config --global alias.cleanup '!$(git rev-parse --show-toplevel)/scripts/archive-old-files.sh'
```

**What they do:**
- `git up` — Stages all changes, commits with message "Updates", and pushes
- `git cleanup` — Runs the archive script to move old files to `_ARCHIVE/` folders

## License

Personal use. Feel free to fork and adapt for your own second brain.
