# Scaffold — README
### A structured content schema for AI-assisted technical documentation

---

## What this is

This is not a formatting tool.
This is not a style guide.
This is not a template library.

It is all three — and the system that connects them.

**Scaffold** is a collection of files that, taken together, tell an AI:

- What kind of document will be made
- Who (the audience) is supposed to read it
- How the reader expects to experience the content
- What words and phrases to use — and which to avoid
- What the finished document should look like before a single word is written

The goal is simple: a technical writer, or a team, should be able to say "make a compatibility matrix for Product X" and get back a document that is accurate, readable, correctly structured, and written for the right audience — ready for human review, not human reconstruction.

---

## Why this exists

AI editors and generators fail at technical documentation for one primary reason:

**They cannot see structure. They see text.**

Paste a published compatibility matrix into an AI, and it reads a wall of words. It does not know which words are column headers, which are product names, which are version numbers, and which are support status flags. It cannot distinguish between numbered steps and bulleted lists. It does not know that a Note is not the same as a Warning.

This system solves that by giving AI a reading guide — a schema — that communicates structure, hierarchy, and intent before content is generated or edited.

The same schema works in both directions:

- **Forward:** AI receives a template and generates a correctly structured document
- **Reverse:** AI receives tagged existing content and edits or reviews it accurately

---

## Origin

This system began as a Google Docs add-on built to solve a different problem entirely.

A writer needed an AI editor to understand the cadence and rhythm of a memoir — where line breaks were intentional, where fragmented sentences carried weight, where a single word on its own line meant something different than the same word buried in a paragraph.

The add-on inserted lightweight tags (`[br]` for line breaks, Markdown for emphasis) so the AI could read the document as the author intended.

The insight that followed: **the same problem exists in technical documentation.** A compatibility matrix has structure. A numbered procedure has structure. A release note has a structure. And AI flattens all of it the same way it flattened the memoir — unless it is told otherwise.

Version 1 of the Google Docs add-on solved cadence for human writing.
This system solves the structure for technical documentation.

---

## The five files you need to understand first

Before anything else, read these in order:

1. **README.md** — this file. What the system is and why.
2. **voice/audience_tiers.md** — the five audience levels every document must be assigned to before generation begins.
3. **HOW_NOT_TO_AI.md** — the voice constraints. What AI reaches for by default, and what to use instead. Modulated by audience tier.
4. **schema/structural_tags.md** — the tag schema. What each tag means, how to use it, and what it tells the AI.
5. **wireframes/** — the document templates. One file per document type.

---

## The five audience tiers

Every document in this system is written for one of five audiences.
Full definitions are in AUDIENCE_TIERS.md. Brief version:

| Tier | Audience | Plain description |
|------|----------|-------------------|
| 1 | CEO | Outcome and impact. No steps. No jargon. |
| 2 | Manager | Process and accountability. Some technical context. |
| 3 | IC (Engineer, Support, Marketing) | Precise and dense. Assumes domain knowledge. |
| 4 | Experienced user / new visitor | Clear and efficient. No hand-holding. |
| 5 | Grandma | If you cannot explain it to Grandma, you cannot explain it to anyone. |

**Tier 5 is the baseline.** If content passes the Grandma test, it works at every level above it. Each tier above 5 relaxes specific voice constraints and permits progressively more technical language.

---

## File structure

```
/docs-os
│
├── README.md                         ← you are here
├── HOW_NOT_TO_AI.md                  ← voice constraints by tier
├── AUDIENCE_TIERS.md                 ← full tier definitions
│
├── /schema
│   └── structural_tags.md            ← the tag schema
│
├── /voice
│   └── voice_constraints.md          ← field-level voice rules
│   └── audience_tiers.md             ← full tier definitions
│
├── /governance
│   └── content_governance.md          ← rules for content generation
│   └── governance.md                  ← other rules
|
├── /release_input
│   └── ProductName_Version.md         ← template for content that is used for doc creation
|
├── /wireframes
│   ├── compatibility_matrix.md       ← template: compatibility matrix
│   └── release_notes.md              ← template: release notes
│
├── /data
│   ├── product_collection.md         ← master product list
│   └── compatibility_data.md         ← compatibility reference data
│
└── /test
    ├── test_product.md               ← sample product for testing
    ├── test_compatibility_matrix.md  ← proof of concept output
    └── test_release_notes.md         ← proof of concept output
```

Files marked as templates or test files are stubs until built.
Each stub contains a single line describing what goes there.

---

## How a document gets made

1. User states document type and product name:
   *"Make a compatibility matrix for Product X"*

2. AI identifies the wireframe for that document type.

3. AI checks the data layer for product information.
   If not found, AI asks for it before proceeding.

4. AI identifies the audience tier for this document.
   If not specified, AI asks before proceeding.

5. AI generates the document using the wireframe, schema tags, product data, and voice constraints for the assigned tier.

6. AI presents the completed MD file for human review.

7. Human gives go/no-go.
   - Go: file is saved, logged, next file proceeds.
   - No-go: human provides feedback, AI revises.

8. At the end of the session (or end of the week): AI produces a list of all files created or edited.

---

## What this is not

This is not a finished product.
This is a proof of concept and a working framework.

It is designed to grow. New wireframes can be added for new document types. New products can be added to the data layer. Voice constraints can be refined over time.

The system is only as good as the files that feed it.
Those files are only as good as the humans who build and maintain them.

That part does not change.

---

## Status

| Component | Status |
|-----------|--------|
| README | ✅ First draft complete |
| AUDIENCE_TIERS.md | 🔲 moved, Stub needed |
| HOW_NOT_TO_AI.md | 🔲 Stub needed |
| schema/structural_tags.md | 🔲 Stub needed |
| voice/voice_constraints.md | 🔲 Stub needed |
| wireframes/compatibility_matrix.md | 🔲 Stub needed |
| wireframes/release_notes.md | 🔲 Stub needed |
| data/product_collection.md | 🔲 Stub needed |
| data/compatibility_data.md | 🔲 Stub needed |
| test files | 🔲 Stub needed |

---

*Built from a conversation. Origin: a memoir, a cemetery, and a line break that needed to land.*

