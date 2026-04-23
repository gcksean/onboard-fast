---
name: classifying-intake
description: Use when new onboarding notes are pasted and they need bucket classification, deduplication, and storage updates.
---

# Classifying Intake

## Overview
Classify each pasted note into one primary bucket, then merge or create entries with consistent metadata.

## When to Use
- New note arrives from chat/CLI paste.
- Existing entries might overlap.
- Destination bucket is uncertain.

## Quick Reference
1. Identify dominant intent.
2. Pick one primary bucket (`resources`, `concepts`, `procedures`, `questions`).
3. Check `*/entries/` for near-duplicate entries.
4. Merge when overlap is high; otherwise create a new file.
5. Preserve metadata contract from `AGENTS.md`.
6. Trigger `updating-indexes`.

## Common Mistakes
- Creating duplicate entries instead of merging.
- Storing unresolved content outside `questions`.
- Breaking credential policy (plaintext secrets).
