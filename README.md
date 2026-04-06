# Shazam

A Claude Code plugin for planning, architecture, bug triage, and development workflows.

Type `/shazam-hub` to get started. Call it anytime for guidance on what to do next.

## Skills

```
--- Build a new feature ---
/write-a-prd                       Describe what to build
/prd-to-plan                       Break PRD into phases
/prd-to-issues                     Break PRD into GitHub Issues
/grill-me                          Stress-test any plan or design

--- Improve existing code ---
/improve-codebase-architecture     Find architectural improvements
/request-refactor-plan             Plan a refactor as tiny commits
/design-an-interface               Compare 3+ interface designs

--- Handle bugs & issues ---
/triage-issue                      Investigate a bug, file fix plan
/github-triage                     Batch triage GitHub Issues
/qa                                Report bugs conversationally

--- Domain & writing ---
/ubiquitous-language               Extract DDD glossary
/edit-article                      Tighten an article draft

--- Tooling ---
/git-guardrails-claude-code        Block dangerous git commands
/setup-pre-commit                  Husky + lint-staged + Prettier
```

## How It Works

Each skill is a prompt in `skills/<name>/SKILL.md`. After each skill completes, it suggests what to do next — soft suggestions, not forced steps. You're always in control.

## Credits

- Skills based on [mattpocock/skills](https://github.com/mattpocock/skills).
- Navigation and skill chaining inspired by [obra/superpowers](https://github.com/obra/superpowers), which enforces workflow via strict state-machine orchestration. Shazam takes a lighter approach: soft suggestions, no hooks, user stays in control.
