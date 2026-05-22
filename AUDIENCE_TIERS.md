# Audience Tiers
## Scaffold voice framework — five-tier audience definitions

Tier 1 is the most constrained. Each tier below it relaxes specific 
constraints. Tier 5 is the baseline — if the content doesn't work at 
Tier 5, it doesn't work anywhere.

---

## Tier 1 — Executive (CEO, C-Suite, Board)

### Who they are
Decision makers with no time and high stakes. They are not reading 
your document. They are scanning it for one thing: does this matter 
to me, and what do I do about it.

### What they are trying to accomplish
Confirm that something is worth their attention. Understand the 
outcome or impact without needing to understand the mechanism.

### What they will tolerate
- A single clear statement of impact
- One or two supporting facts if they are numbers
- A direct ask or next step if one exists

### What they will not tolerate
- Steps, instructions, or process detail
- Jargon, acronyms, or technical terms without immediate plain-language 
  translation
- Anything that requires them to already know something to understand it
- Documents longer than they need to be

### Words and phrases that work
- Revenue, risk, customers, growth, outcome, decision, impact
- Numbers with context ("3% drop in retention" not "retention metrics")
- Active voice, short sentences

### Words and phrases that don't
- "In order to," "utilize," "leverage" (as a verb), "synergy"
- Version numbers, build numbers, patch notes
- Any acronym not spelled out on first use

### What a failed document looks like
A Tier 1 reader puts it down after the first paragraph because 
nothing in it told them why they should keep reading.

### Reference
My Kind of Chaos release notes and compatibility matrix are not 
written for Tier 1. The Advocate section of the About content 
(test_product.md) approaches Tier 1 language at its opening line.

Tier 1 document generation requires a metrics file. 
See data/metrics/[ProductName]_metrics_[YYYY_MM].md for 
current period data. Monthly files roll up to quarterly 
on request, based on company's fiscal calendar.

---

## Tier 2 — Manager (Team Lead, Director, Program Manager)

### Who they are
Accountable for outcomes they don't always control directly. They 
need enough technical context to make decisions and communicate 
upward and downward. They are readers, not skimmers — but only if 
the document earns it in the first paragraph.

### What they are trying to accomplish
Understand what changed, what it means for their team or process, 
and whether any action is required from them.

### What they will tolerate
- Process and workflow context
- Selective technical detail where it affects decisions
- Moderate document length if the structure is clear
- Lists and tables

### What they will not tolerate
- Deep technical implementation detail with no "so what"
- Unexplained acronyms or version strings
- Documents that bury the action item at the end

### Words and phrases that work
- Impact, timeline, dependency, owner, action required, rollout
- "This affects X" before explaining how
- Numbers with units and context

### Words and phrases that don't
- Raw code, command-line syntax, build logs
- "Simply" or "just" — implies the reader should already know
- Passive voice when ownership matters ("the issue was resolved" 
  vs "the team resolved the issue")

### What a failed document looks like
A Tier 2 reader finishes the document and still has to ask someone 
what it means for their team.

### Reference
My Kind of Chaos About — Advocate section (test_product.md) is 
written at Tier 2 voice. Release notes versions 01.00.00.05 and 
01.00.00.10 touch Tier 2 in the Fixes and Improvements section.

Tier 2 documents may reference metrics data for rollout 
and impact context. See data/metrics/[ProductName]_metrics_[YYYY_MM].md. 
Static fields (subscription tiers, support model) live in 
the product file.

---

## Tier 3 — Individual Contributor (Engineer, Support, Marketing IC)

### Who they are
Domain experts are doing the work. They read for precision, not 
context. They already know the background — they need the specific 
details that affect what they do next.

### What they are trying to accomplish
Find the exact information they need as fast as possible. Confirm 
that nothing broke their workflow. Know what changed and where.

### What they will tolerate
- Dense, precise language
- Technical terms without definition
- Long documents if they are well structured and scannable
- Version numbers, build strings, dependency lists
- Tables, code blocks, command-line examples

### What they will not tolerate
- Padding, preamble, or restating what they already know
- Vague language where precision is possible ("some improvements" vs specific items)
- Marketing language in technical documents
- Missing details that require a follow-up question

### Words and phrases that work
- Specific version numbers, exact field names, precise error states
- "Fixed," "updated," "deprecated," "removed," "added"
- Active voice, imperative where applicable

### Words and phrases that don't
- "Exciting new features," "seamless experience," "powerful"
- Hedging language where a direct statement is possible
- "etc." — either list it or don't

### What a failed document looks like
A Tier 3 reader has to open a second document, file a ticket, or 
ask a colleague to find the information they needed from the first one.

### Reference
My Kind of Chaos release notes are written primarily for Tier 3 
and Tier 4. The Fixes and Improvements section targets Tier 3 
precision expectations.

---

## Tier 4 — Experienced User / Informed New Visitor

### Who they are
People who use the product or are evaluating it. They may not know 
this specific product yet, but they know how software works. They 
do not need hand-holding — they need clear, honest information 
delivered efficiently.

### What they are trying to accomplish
Understand what the product does, what changed, or whether it 
works for them. They are making a decision — to download, to 
update, to recommend, to keep using.

### What they will tolerate
- Conversational but efficient language
- Feature descriptions without over-explanation
- Some personality if it fits the product voice
- Moderate length if content is relevant throughout

### What they will not tolerate
- Condescension or over-explanation of obvious things
- Marketing language that doesn't say anything
- Steps written as if they've never used a phone before
- Buried key information

### Words and phrases that work
- Plain descriptions of what the feature does
- "Now you can," "added," "fixed," "works with"
- Product voice where it exists — match it

### Words and phrases that don't
- "Innovative," "best-in-class," "revolutionary"
- "Simply tap the button" — they know how buttons work
- Anything that talks down to the reader

### What a failed document looks like
A Tier 4 reader rolls their eyes halfway through and closes the 
document because it was written for someone who has never used 
a smartphone.

### Reference
My Kind of Chaos release notes (01.00.00.05, 01.00.00.10, 
01.00.00.13) and the About — Self and About — Other sections 
in test_product.md are written at Tier 4 voice.

---

## Tier 5 — Grandma (General Public, First-Time User, Non-Technical Reader)

### Who they are
Anyone for whom no prior knowledge can be assumed. Not a 
pejorative — this is the hardest tier to write for and the most 
important one to get right. If the content works here, it works 
everywhere.

### What they are trying to accomplish
Understand whether this thing is for them and what it will do 
for them. They are not reading to learn — they are reading to 
decide if they need to learn.

### What they will tolerate
- Plain language, short sentences
- Analogies to familiar things
- Repetition of key points if it aids understanding
- Patience — they will read carefully if the document respects them

### What they will not tolerate
- Jargon of any kind without an immediate plain-language explanation
- Assumed knowledge — of technology, of the product, of the category
- Long paragraphs without a clear point
- Anything that makes them feel stupid for not already knowing

### Words and phrases that work
- Everyday language — the words people actually use out loud
- Concrete examples over abstract descriptions
- "This means," "in other words," "for example"
- Short sentences. One idea at a time.

### Words and phrases that don't
- Any acronym not spelled out
- "Intuitive," "seamless," "frictionless" — these are meaningless 
  to someone who hasn't used the product
- Technical comparisons ("unlike other apps that use X protocol")
- Anything that requires the reader to already know something

### What a failed document looks like
A Tier 5 reader finishes the document and still has to call 
someone to ask what it means or whether it applies to them.

### Reference
Tier 5 is the baseline for all Scaffold content. No document 
passes go/no-go if it fails at Tier 5 clarity, regardless of 
the target tier. The About — Self section in test_product.md 
approaches Tier 5 in its opening paragraphs.

---

## General Rules

- Every document has a target tier. The target tier is set in the 
  wireframe or specified at generation time.
- A document written for Tier 3 does not need to pass Tier 5 
  clarity at the detail level — but its structure and purpose 
  must still be clear to a first-time reader.
- Tier is not a quality setting. A Tier 1 document is not better 
  than a Tier 5 document. They are different tools for different 
  readers.
- When in doubt about the target tier, ask before generating.

- 
