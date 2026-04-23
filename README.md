# Onboard-Fast

Personal onboarding knowledge base for capturing what you learn when joining any new context—new jobs, role switches, team transfers, or new projects—and making it easy to retrieve later.

## Purpose

This repo is a living system for storing notes in four buckets, so you can onboard faster whenever your scope changes:
- `resources` — links, tools, systems, access pointers, credential metadata
- `concepts` — technical/tribal/domain understanding
- `procedures` — repeatable step-by-step guides
- `questions` — unresolved or exploratory items

Core behavior and routing rules are defined in:
- [`AGENTS.md`](AGENTS.md)

Claude Code root convention:
- [`CLAUDE.md`](CLAUDE.md) includes `@AGENTS.md`

## Repository Layout

```text
.
├── AGENTS.md
├── CLAUDE.md
├── README.md
├── resources/
│   ├── INDEX.md
│   └── entries/
├── concepts/
│   ├── INDEX.md
│   └── entries/
├── procedures/
│   ├── INDEX.md
│   └── entries/
├── questions/
│   ├── INDEX.md
│   └── entries/
└── skills/
    ├── classifying-intake/SKILL.md
    ├── updating-indexes/SKILL.md
    └── resolving-questions/SKILL.md
```

## Daily Workflow

1. Ask a question **or** paste new info into your agent (Copilot/Claude CLI).
2. Agent detects intent:
   - **Ask mode:** search relevant bucket entries and answer from existing knowledge.
   - **Capture mode:** classify and merge/create an entry in the best-fit bucket.
3. For Capture mode, agent updates the relevant `INDEX.md`.
4. If unresolved, it goes to `questions`.
5. When answered, the question is updated and durable details are propagated to `resources`, `concepts`, and/or `procedures`.

## Entry Conventions

- Store atomic notes in `<bucket>/entries/`.
- Use file name format: `YYYY-MM-DD-short-kebab-title.md`.
- Keep frontmatter fields aligned with `AGENTS.md`.
- For templates, start from:
  - `resources/entries/README.md`
  - `concepts/entries/README.md`
  - `procedures/entries/README.md`
  - `questions/entries/README.md`

## Credentials Policy

- Encrypted credential blobs are allowed.
- Plaintext credentials are not allowed.
- Include metadata so future-you can retrieve/decrypt/rotate safely.

## Skills

Use these project skills to keep ingestion consistent:
- [`skills/classifying-intake/SKILL.md`](skills/classifying-intake/SKILL.md)
- [`skills/searching-answers/SKILL.md`](skills/searching-answers/SKILL.md)
- [`skills/updating-indexes/SKILL.md`](skills/updating-indexes/SKILL.md)
- [`skills/resolving-questions/SKILL.md`](skills/resolving-questions/SKILL.md)
