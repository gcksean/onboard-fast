---
name: searching-answers
description: Use when a user asks a question and the agent should retrieve and synthesize answers from existing knowledge buckets.
---

# Searching Answers

## Overview
Handle question requests as retrieval-first: search all buckets, synthesize an answer, and cite sources.

## When to Use
- User input is a question, not a note to store.
- User asks "how", "where", "what", "who", or "why" about known onboarding topics.

## Quick Reference
1. Parse the question intent and key terms.
2. Search in this order:
   - `procedures` for executable steps,
   - `concepts` for explanation/context,
   - `resources` for links/systems/access pointers,
   - `questions` for prior unresolved/partial context.
3. Synthesize a concise answer with file links.
4. If confidence is low or data conflicts, say what is uncertain.
5. If no answer exists, propose creating/updating a `questions` entry.

## Common Mistakes
- Treating every question as new capture input.
- Answering without searching all relevant buckets.
- Returning an answer without citing where it came from.
