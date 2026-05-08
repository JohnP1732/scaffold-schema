# Scaffold — Project Handoff Document
### Context for continuing development in a new session
### Last updated: May 8, 2026

---

## What Scaffold is

Scaffold is a structured content schema for AI-assisted technical documentation.

It is a collection of plain-text .md files that tell an AI:
- What kind of document it is making
- Who is supposed to read it
- How the reader expects to experience the content
- What words and phrases to use — and which to avoid
- What the finished document should look like before a single word is written

It is platform agnostic. It works on free-tier AI tools. It lives in a folder. No SaaS, no login, no black box.

GitHub repo: https://github.com/JohnP1732/scaffold-schema

---

## Current State — What's Built

### Files that exist and are functional:

**Root:**
- `README.md` — complete, explains the system
- `HOW_NOT_TO_AI.md` — stub only
- `PUBLISHING.md` — does not exist yet, next major build item

**schema/**
- `structural_tags.md` — functional, minimum viable, tested

**voice/**
- `audience_tiers.md` — stub only
- `voice_constraints.md` — stub only

**governance/**
- `content_governance.md` — functional, core rules in place

**wireframes/**
- `release_notes.md` — built and tested, two successful runs
- `compatibility_matrix.md` — built and tested, one successful run

**data/**
- `product_collection.md` — contains My Kind of Chaos test product
- `compatibility_data.md` — stub only

**release_input/**
- `My_Kind_of_Chaos_01.00.00.05.md` — complete
- `My_Kind_of_Chaos_01.00.00.10.md` — complete

**test/**
- `test_product.md` — same as product_collection for now
- `test_compatibility_matrix.md` — stub only
- `test_release_notes.md` — stub only

---

## What Was Tested This Session

### Release Notes — Two successful runs:

**Run 1:** My Kind of Chaos 01.00.00.05
- All fields populated correctly from product and release input files
- Publish date generated at creation time
- Store links rendered as Markdown linked display text
- Footer filled correctly with version and date
- List items stayed separate

**Run 2:** My Kind of Chaos 01.00.00.10
- Same results
- Em dash in h1 confirmed clean
- support-url and release-url both resolved correctly

### Compatibility Matrix — One successful run:

**Run 1:** My Kind of Chaos
- Product name pulled correctly throughout
- about-url rendered with Product Name as display text
- OS versions pulled from the product file exactly as written
- Store links are rendering correctly in the table
- language-list rendered as separate list items
- No footer — correct, wireframe doesn't include one
- Governance is working as intended

---

## Known Issues / Next Fixes

**Structural tags file:**
- `[about-url]` may still have a duplicate entry — verify and remove if present
- Display text simplification pending: support-url, release-url display text fields 
  could default to Product Name instead of requiring separate display text fields.
  Deferred — fix after publishing the layer is built.

**Product file:**
- Support URL Display Text and Product Release URL Display Text fields exist
  But it may be simplified later to use Product Name as the default.

**Release input files:**
- Both need the Release Date field added and validated against the product file date.
  `My_Kind_of_Chaos_01.00.00.05.md` — Release Date: April 2026
  `My_Kind_of_Chaos_01.00.00.10.md` — Release Date: May 2026
  May 2026 is newer than the product file date — validation rule should flag this.
  Test this before moving to the publishing layer.

---

## What Needs to Be Built Next

### Priority 1 — Publishing Layer

This is the next major component. Not started yet.

The concept: after go/no-go approval, Claude strips Scaffold tags from the generated output and formats it for the target publishing platform.

Two new fields needed in product_collection.md:
```markdown
## Publishing Platform
Confluence

## Publishing Notes
on
```

A new file needed: `PUBLISHING.md`
- Lists supported platforms
- Defines formatting rules per platform
- Defines what "stripping Scaffold tags" means for each platform

Supported platforms to define initially:
- Confluence
- SharePoint  
- MkDocs / static site generators
- Plain Markdown (no stripping needed)
- Word document (via Pandoc note)

Publishing Notes flag behavior:
- `on` — Claude appends a "next steps" note to the generated file
- `off` — Claude generates the file silently, no note appended

### Priority 2 — Stub files that need content

In order:
1. `voice/audience_tiers.md` — five-tier definitions, full detail
2. `HOW_NOT_TO_AI.md` — voice constraints by tier and field type
3. `voice/voice_constraints.md` — field-level rules
4. `data/compatibility_data.md` — structure definition

### Priority 3 — Test files

Once a publishing layer exists:
- `test/test_compatibility_matrix.md` — full end-to-end output
- `test/test_release_notes.md` — full end-to-end output

---

## The Tag Schema — Current State

All tags defined in `schema/structural_tags.md`:

| Tag | Purpose | Source |
|-----|---------|--------|
| `[h1]` | Document title | Wireframe |
| `[h2]` | Section header | Wireframe |
| `[body]` | Paragraph text | Wireframe |
| `[br]` | Line break | Wireframe |
| `[ul]` | Unordered list | Wireframe |
| `[li]` | List item | Wireframe |
| `[footer]/[/footer]` | Footer block | Wireframe |
| `[store-link-google]` | Google Play URL | Product file |
| `[store-link-apple]` | Apple App Store URL | Product file |
| `[support-url]` | Support link | Product file |
| `[release-url]` | Release archive link | Product file |
| `[about-url]` | About page link | Product file |
| `[release-date]` | Version release date | Release input file |
| `[os-android]` | Android OS version | Product file |
| `[os-ios]` | iOS version | Product file |
| `[language-list]` | Supported languages | Product file |
| `** **` | Bold | Wireframe |
| `_ _` | Italics | Wireframe |

---

## The Five Audience Tiers

| Tier | Audience | Voice |
|------|----------|-------|
| 1 | CEO | Outcome and impact. No steps. No jargon. |
| 2 | Manager | Process and accountability. Some technical context. |
| 3 | IC (Engineer, Support, Marketing) | Precise and dense. Assumes domain knowledge. |
| 4 | Experienced user / new visitor | Clear and efficient. No hand-holding. |
| 5 | Grandma | If you can't explain it to Grandma, you can't explain it to anyone. |

Tier 5 is the baseline. Each tier above relaxes specific voice constraints.
Full definitions pending in `voice/audience_tiers.md`.

---

## Core Governance Rules (current)

1. The wireframe defines what a document type requires. If it's in the 
   template, it's required. If it's not, it doesn't exist for that document type.

2. Trailing spaces at the end of lines in wireframe files are intentional 
   Markdown syntax. Do not remove them.

3. Publish date is generated at document creation time. 
   It is not stored in the product file.

4. For published apps, replace placeholders with actual store URLs 
   copied directly from the store listing. Do not construct URLs manually.

5. Version numbers always follow the padding standard with leading zeros. 
   No exceptions, including in release input files.

6. Release date validation: Compare the Release Date in the release input file 
   against the Release Date in the product file. If newer, stop and flag. 
   Wait for the user confirmation that the product file has been updated manually.

7. Source file integrity: Scaffold does not modify, overwrite, or update 
   any source file autonomously. Claude generates output files only. 
   When a source file requires updating, flag it and wait for user confirmation.

8. OS Support Policy: Unless otherwise specified, supported OS versions 
   default to the current release and two versions back for consumer apps, 
   three versions back for enterprise tools. Confirm with the product owner 
   before documenting.

---

## The Service Model

**Base license** — Annual or monthly. Core files, all updates, self-serve.

**Support tier** — Base license plus business hours contact (CST).

**Custom schema / wireframe work** — Separate engagement, scoped and quoted.

**Onboarding / live working session** — Discounted from hourly rate. 
Client team participates and leaves self-sufficient.

**Bundle** — Base license + onboarding + one custom wireframe.

Key differentiator: Lives in a folder. No IT required. Every rule is 
readable. Platform agnostic. Self-serve after onboarding.

---

## How to Run a Document Generation Session

Minimum files needed for a release note:
1. `schema/structural_tags.md`
2. `wireframes/release_notes.md`
3. `data/product_collection.md`
4. `release_input/[ProductName_Version].md`
5. `governance/content_governance.md`

Minimum files needed for a compatibility matrix:
1. `schema/structural_tags.md`
2. `wireframes/compatibility_matrix.md`
3. `data/product_collection.md`
4. `governance/content_governance.md`

Prompt to trigger generation:
*"Create a [document type] for [Product Name] version [version number]."*

Claude will:
- Pull data from the correct source files
- Flag any missing fields before generating
- Generate the document using the wireframe structure
- Present for human review
- Wait for go / no-go before proceeding

---

## Context About the Person Building This

John Prill. Senior Technical Writer. Cypress TX.
10+ years of documentation experience across SaaS, enterprise, and infrastructure.
Currently available — contract or full-time.
LinkedIn: linkedin.com/in/johnprill
GitHub: github.com/JohnP1732/scaffold-schema

ADHD pattern recognition in the brain. Builds systems while solving smaller problems.
Scaffold started as a demo explanation for a job interview.

When continuing this work: be direct, skip hand-holding, challenge assumptions 
when something doesn't hold up. He will push back if he disagrees. That's useful.

---

## One Sentence to Remember

*"I'm not writing HTML for browsers. I'm writing structure tags so AI 
understands how a human reader is supposed to experience the content."*

That's the whole thing.
