# AGENTS

This repository is a **personal onboarding knowledge base**.  
When content is sent to an agent, it must first detect intent:

1. **Ask mode** (user is asking a question): search and answer from existing knowledge.
2. **Capture mode** (user is providing notes/info): classify and store in one of four buckets.

In Capture mode, classify into:

1. `resources` — links, tools, pages, systems, credentials metadata, and access pointers.
2. `concepts` — durable knowledge (technical, tribal, organizational) by topic.
3. `procedures` — repeatable step-by-step task guides.
4. `questions` — unresolved or exploratory items.

## Core Operating Rules

1. **Detect intent first.** Decide Ask mode vs Capture mode before any write action.
2. **Ask mode is read-first.** Search relevant buckets and answer from existing entries when possible.
3. **Capture mode writes.** Classify first, then write/update.
4. If classification is ambiguous, ask one focused clarification.
5. **Update existing entries when possible.** Do not create duplicates when an existing entry can be merged.
6. **Use frontmatter metadata** so entries remain searchable and maintainable.
7. **Questions are temporary.** If a question gets answered:
   - update the question entry with the answer and status,
   - propagate durable details into `resources`, `concepts`, and/or `procedures`,
   - link all related updates.
8. **Always refresh bucket indexes** after create/update actions.
9. **Credentials policy:** encrypted credential blobs are allowed; plaintext credentials are not.

## Ask Mode (Search + Answer)

When the user asks a question:
1. Parse the question and extract key terms.
2. Search across all four buckets (`resources`, `concepts`, `procedures`, `questions`) and their indexes.
3. Prioritize direct procedural answers from `procedures`, then explanatory support from `concepts`, then pointers from `resources`.
4. Include unresolved context from `questions` only when relevant.
5. Return the best answer with links to source entries.
6. If no reliable answer exists, say so clearly and suggest capturing it as a new question entry.

## Capture Mode (Classify + Store)

When the user pastes new information:
1. Parse intent and classify to a bucket.
2. Locate related entry candidates in that bucket.
3. Merge or create entry with correct metadata.
4. If unresolved, write/update under `questions`.
5. If answered, propagate durable learnings into other buckets.
6. Update relevant `INDEX.md` files.

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

## Suggested Skill Usage

- `skills/classifying-intake/SKILL.md`
- `skills/searching-answers/SKILL.md`
- `skills/updating-indexes/SKILL.md`
- `skills/resolving-questions/SKILL.md`

These skills define repeatable behavior so every ingestion pass stays consistent.

## Claude Code Compatibility

Claude Code should use root `CLAUDE.md`, which references this file via:
- `@AGENTS.md`
