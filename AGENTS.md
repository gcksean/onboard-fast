# AGENTS

This repository is a **personal onboarding knowledge base**.  
When new content is pasted to an agent, the agent must classify and store it in one of four buckets:

1. `resources` — links, tools, pages, systems, credentials metadata, and access pointers.
2. `concepts` — durable knowledge (technical, tribal, organizational) by topic.
3. `procedures` — repeatable step-by-step task guides.
4. `questions` — unresolved or exploratory items.

## Core Operating Rules

1. **Classify first, then write.** If classification is ambiguous, ask one focused clarification.
2. **Update existing entries when possible.** Do not create duplicates when an existing entry can be merged.
3. **Use frontmatter metadata** so entries remain searchable and maintainable.
4. **Questions are temporary.** If a question gets answered:
   - update the question entry with the answer and status,
   - propagate durable details into `resources`, `concepts`, and/or `procedures`,
   - link all related updates.
5. **Always refresh bucket indexes** after create/update actions.
6. **Credentials policy:** encrypted credential blobs are allowed; plaintext credentials are not.

## Repository Shape

Each bucket uses:
- `entries/` for atomic notes
- `INDEX.md` for curated navigation

Entry file naming:
- `YYYY-MM-DD-short-kebab-title.md`

## Bucket Decision Guide

- Put in **resources** when the content is primarily a pointer to a system/tool/page/secret artifact.
- Put in **concepts** when it explains how something works or why it is done.
- Put in **procedures** when it is a sequence someone can execute.
- Put in **questions** when uncertainty remains or there is no stable answer yet.

If content includes multiple types, split into multiple entries and cross-link.

## Metadata Contract

Common frontmatter fields for all entries:
- `id`
- `title`
- `status` (`draft`, `active`, `deprecated`, `answered` where relevant)
- `tags`
- `updated`
- `source`

Bucket-specific fields:
- `resources`: `resource_type`, `system`, `access_level`, `credential_mode`
- `concepts`: `domain`, `audience`, `related_procedures`
- `procedures`: `owner`, `prerequisites`, `systems`, `validation`
- `questions`: `asked_by`, `answer_status`, `answered_on`, `linked_updates`

## Ingestion Flow (for Copilot/Claude CLI usage)

When a user pastes content:
1. Parse intent and classify to a bucket.
2. Locate related entry candidates in that bucket.
3. Merge or create entry with correct metadata.
4. If unresolved, write/update under `questions`.
5. If answered, propagate durable learnings into other buckets.
6. Update relevant `INDEX.md` files.

## Suggested Skill Usage

- `skills/classifying-intake/SKILL.md`
- `skills/updating-indexes/SKILL.md`
- `skills/resolving-questions/SKILL.md`

These skills define repeatable behavior so every ingestion pass stays consistent.

## Claude Code Compatibility

Claude Code should use root `CLAUDE.md`, which references this file via:
- `@AGENTS.md`
