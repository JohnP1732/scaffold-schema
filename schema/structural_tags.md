# Scaffold — Structural Tags
## Minimum viable schema for AI document generation.
## Full tag library expanded as new document types are added.

---

## [h1] — Document Title
Primary document header. Product name, version, document type.
One per document. Always the first element.

---

## [h2] — Section Header
Major section divider. What's New, Fixes and Improvements, etc.
Multiple per document. Never nested inside another [h2].

---

## [body] — Body Text
Standard paragraph text. Introductory lines, single statements,
supporting information. Not for lists. Not for headers.

---

## [br] — Line Break
Intentional line break. Treat as a pause.
Do not merge the line before this tag with the line after it.
Do not remove. Placement is intentional.

---

## [ul] — Unordered List
Opens a bulleted list. Contains [li] items.
Close the list before starting a new [h2] section.

---

## [li] — List Item
Single item within a [ul] list.
Each [li] stands alone. Do not combine two [li] items into one.

---

## [footer] / [/footer] — Footer Block
Opens and closes the document footer.
Content inside is fixed governance text.
Do not paraphrase. Do not rewrite. reproduce exactly as written
with only the bracketed fields filled in.

---

## [store-link-google] — Google Play Store URL
Replaced with the Google Play URL from the product file.
Renders as the full URL or as "Google Play Store" depending
on audience tier. See voice/voice_constraints.md.

---

## [store-link-apple] — Apple App Store URL
Replaced with the Apple App Store URL from the product file.
Renders as the full URL or as "Apple App Store" depending
on audience tier. See voice/voice_constraints.md.

---

## ** ** — Bold
Used for UI elements, button names, field labels, and critical 
terms on first use. Example: Click **Save** to continue.
Do not use for general emphasis.

---

## _ _ — Italics
Used for the first introduction of a technical term, document title 
references, or deliberate mode shifts in narrative content.
Do not use for decoration.

---

## General Rules

- Tags are instructions to the AI, not to a browser.
- Every tag has a purpose. Do not skip tags because a field seems empty.
- If a field has no content, ask before leaving it blank.
- Do not invent tags not listed in this file.
- When in doubt, ask.

- 
