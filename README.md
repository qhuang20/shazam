# Shazam

A Claude Code plugin with 18 skills for planning, architecture, bug triage, and development workflows. Based on [mattpocock/skills](https://github.com/mattpocock/skills).

**New here? Type `/shazam` to get started.** It will guide you to the right skill based on what you want to do. You can call it anytime for suggestions on what to do next.

## Workflow Map

```
/shazam  (start here - call anytime for guidance)

--- Build a new feature ---
/write-a-prd             Write a PRD through interactive interview
    |
    v
/prd-to-plan             Break PRD into phased implementation plan
    |
    v
/prd-to-issues           Break PRD into GitHub Issues with dependencies
    |
    v
    Start coding!

--- Improve existing code ---
/improve-codebase-architecture   Find shallow modules, propose deepening
    |
    v
/request-refactor-plan           Plan refactor as tiny commits
    |
    v
/design-an-interface             "Design It Twice" - compare 3+ designs

--- Handle bugs & issues ---
/triage-issue            Investigate bug, find root cause, file fix plan
/github-triage           Batch triage GitHub Issues with label state machine
/qa                      Conversational QA session - describe bugs, auto-file

--- Think & stress-test ---
/grill-me                Get grilled on any plan or design

--- Domain & writing ---
/ubiquitous-language     Extract DDD glossary from conversation
/edit-article            Restructure and tighten an article draft

--- Tooling ---
/git-guardrails-claude-code   Block dangerous git commands via hooks
/setup-pre-commit             Husky + lint-staged + Prettier
```

## All Skills

### Planning & Design

| Skill | Command | Description |
|-------|---------|-------------|
| **write-a-prd** | `/write-a-prd` | Create a PRD through interactive interview and codebase exploration, filed as a GitHub Issue |
| **prd-to-plan** | `/prd-to-plan` | Break a PRD into phased vertical slices (tracer bullets), saved as Markdown |
| **prd-to-issues** | `/prd-to-issues` | Break a PRD into independently-grabbable GitHub Issues with acceptance criteria and dependencies |
| **grill-me** | `/grill-me` | Stress-test any plan or design by walking every branch of the decision tree |
| **design-an-interface** | `/design-an-interface` | "Design It Twice" - generate 3+ radically different module interface designs for comparison |

### Architecture & Refactoring

| Skill | Command | Description |
|-------|---------|-------------|
| **improve-codebase-architecture** | `/improve-codebase-architecture` | Explore codebase for shallow modules and propose architectural improvements |
| **request-refactor-plan** | `/request-refactor-plan` | Plan a refactor as tiny commits via interview, filed as a GitHub RFC Issue |
| **ubiquitous-language** | `/ubiquitous-language` | Extract a DDD-style glossary from conversation, saved to `UBIQUITOUS_LANGUAGE.md` |

### Bug Triage & QA

| Skill | Command | Description |
|-------|---------|-------------|
| **triage-issue** | `/triage-issue` | Investigate a bug, find root cause, file a GitHub Issue with TDD fix plan |
| **github-triage** | `/github-triage` | Batch triage GitHub Issues using a label-based state machine |
| **qa** | `/qa` | Conversational QA session - describe bugs, auto-explore codebase and file Issues |

### Writing

| Skill | Command | Description |
|-------|---------|-------------|
| **edit-article** | `/edit-article` | Restructure and tighten an article draft, section by section |

### Tooling & Setup

| Skill | Command | Description |
|-------|---------|-------------|
| **git-guardrails-claude-code** | `/git-guardrails-claude-code` | Install hooks to block dangerous git commands (push, reset --hard, etc.) |
| **setup-pre-commit** | `/setup-pre-commit` | Set up Husky + lint-staged + Prettier pre-commit hooks |

### Specialized

| Skill | Command | Description |
|-------|---------|-------------|
| **migrate-to-shoehorn** | `/migrate-to-shoehorn` | Replace `as` type assertions in tests with @total-typescript/shoehorn |
| **scaffold-exercises** | `/scaffold-exercises` | Create course exercise directory structures |
| **obsidian-vault** | `/obsidian-vault` | Manage notes in an Obsidian vault with wikilinks and index notes |

## How It Works

Each skill is a self-contained prompt in `skills/<name>/SKILL.md`. When you invoke a slash command, Claude follows the instructions in that skill file.

After each skill completes, it suggests what to do next - these are **soft suggestions**, not forced steps. You're always in control.

## Credits

- Skills based on [mattpocock/skills](https://github.com/mattpocock/skills).
- Navigation hub (`/shazam`) and skill chaining inspired by [obra/superpowers](https://github.com/obra/superpowers), which uses strict state-machine orchestration and mandatory hooks to enforce workflow discipline. Shazam takes a lighter approach: soft suggestions instead of hard gates, no session-start hooks, and the user stays in control at every step.
- Navigation and chaining added by Danny Huang.
