---
name: resolving-questions
description: Use when a question gains new evidence and needs status updates plus propagation into durable knowledge buckets.
---

# Resolving Questions

## Overview
When a question is answered, close the loop in `questions` and copy durable knowledge into `resources`, `concepts`, or `procedures`.

## When to Use
- A question has full or partial answer.
- New facts should be preserved outside the question record.

## Quick Reference
1. Update question frontmatter (`answer_status`, `answered_on`, `linked_updates`).
2. Add concise answer summary in the question body.
3. Determine propagation target(s):
   - pointer/access -> `resources`
   - understanding/explanation -> `concepts`
   - executable steps -> `procedures`
4. Create or update propagated entries.
5. Cross-link all touched files.
6. Trigger `updating-indexes`.

## Common Mistakes
- Marking a question answered without propagating learnings.
- Leaving related entries unlinked.
- Treating temporary investigation notes as final concepts.
