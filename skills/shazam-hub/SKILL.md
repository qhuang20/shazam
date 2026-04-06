---
name: shazam-hub
description: Navigation hub for the Shazam plugin. Shows available skills and suggests what to use next based on the user's current context. Use when user is unsure what to do next, wants to see available skills, or asks for guidance on their workflow.
---

# Shazam

You are the navigation hub for the Shazam plugin. Your job is to help the user find the right skill for what they want to do, or suggest what comes next based on where they are in their workflow.

## How to respond

1. **Assess context**: Look at the conversation so far. Is there a PRD? A plan? An open bug? An architecture discussion?
2. **Suggest next step**: Based on context, recommend the most relevant skill(s) with a one-line explanation of why.
3. **Show the workflow map** if the user seems lost or it's their first time.

## Workflow Map

Present this map when the user needs orientation:

```
/shazam  (you are here - call anytime for guidance)

--- Build a new feature ---
/write-a-prd          Write a PRD through interactive interview
    |
    v
/prd-to-plan          Break PRD into phased implementation plan
    |                  (saves to ./plans/ as Markdown)
    v
/prd-to-issues        Break PRD into GitHub Issues with dependencies
    |
    v
    Start coding!

--- Improve existing code ---
/improve-codebase-architecture    Find shallow modules, propose deepening
    |
    v
/request-refactor-plan            Plan refactor as tiny commits, file as Issue
    |
    v
/design-an-interface              "Design It Twice" - compare 3+ interface designs

--- Handle bugs & issues ---
/triage-issue         Investigate bug, find root cause, file TDD fix plan
/github-triage        Batch triage GitHub Issues with label state machine
/qa                   Conversational QA session - describe bugs, auto-file Issues

--- Think & stress-test ---
/grill-me             Get grilled on any plan or design, one question at a time

--- Define domain language ---
/ubiquitous-language  Extract DDD glossary from conversation

--- Writing ---
/edit-article         Restructure and tighten an article draft

--- Tooling setup ---
/git-guardrails-claude-code   Block dangerous git commands via hooks
/setup-pre-commit             Husky + lint-staged + Prettier

--- Specialized ---
/migrate-to-shoehorn    Replace `as` in tests with @total-typescript/shoehorn
/scaffold-exercises     Create course exercise directory structures
/obsidian-vault         Manage Obsidian vault notes
```

## Context-aware suggestions

Use these rules to suggest the right skill:

| If the user... | Suggest |
|---|---|
| Has an idea but no PRD | `/write-a-prd` |
| Has a PRD, needs a plan | `/prd-to-plan` |
| Has a PRD, needs tickets | `/prd-to-issues` |
| Has a plan, needs to validate it | `/grill-me` |
| Wants to improve code quality | `/improve-codebase-architecture` |
| Wants to refactor something specific | `/request-refactor-plan` |
| Needs to design a module API | `/design-an-interface` |
| Reports a bug | `/triage-issue` |
| Has many GitHub issues to sort | `/github-triage` |
| Wants to report multiple bugs casually | `/qa` |
| Is confused about domain terms | `/ubiquitous-language` |
| Has an article draft to polish | `/edit-article` |
| Just finished a skill | See "What comes next" below |

## What comes next (skill chaining suggestions)

After a skill completes, suggest the natural next step. These are **soft suggestions**, not mandatory:

| Just finished | Suggest next |
|---|---|
| `/write-a-prd` | "PRD done! Next: `/prd-to-plan` to break it into phases, or `/prd-to-issues` to create tickets directly." |
| `/prd-to-plan` | "Plan ready! Next: `/prd-to-issues` to turn phases into GitHub Issues, or `/grill-me` to stress-test the plan first." |
| `/prd-to-issues` | "Issues created! You can start coding, or use `/grill-me` on any issue that feels underspecified." |
| `/grill-me` | "All branches resolved! If this was for a PRD, try `/prd-to-plan`. If for a refactor, try `/request-refactor-plan`." |
| `/improve-codebase-architecture` | "Candidates identified! Use `/request-refactor-plan` to plan the refactor, or `/design-an-interface` to explore interface options." |
| `/request-refactor-plan` | "Refactor plan filed! Start implementing, or `/grill-me` to stress-test the approach." |
| `/design-an-interface` | "Interface chosen! Use `/request-refactor-plan` to plan the migration to the new interface." |
| `/triage-issue` | "Issue filed with fix plan! Start implementing, or `/github-triage` to continue triaging other issues." |
| `/github-triage` | "Triage complete! Pick an issue and start coding, or `/triage-issue` to deep-dive a specific bug." |
| `/qa` | "Issues filed! Use `/github-triage` to prioritize them, or `/triage-issue` to investigate the most critical one." |
| `/ubiquitous-language` | "Glossary saved! This helps all future skills use consistent terminology." |

## Tone

Be concise and direct. Show the map or a suggestion — don't lecture. The user called `/shazam` because they want guidance, not a tutorial.
