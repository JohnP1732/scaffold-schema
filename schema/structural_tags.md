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

## [support-url] — Support Link
Renders the Support URL and Support URL Display Text from the 
product file as a single linked element.
Format: [Support URL Display Text](https://support-url)
Both fields must exist in the product file. If either is missing, ask.

---

## [release-url] — Release Notes Archive Link
Renders the Product Release URL and Product Release URL Display 
Text from the product file as a single linked element.
Format: [Product Release URL Display Text](https://release-url)
Both fields must exist in the product file. If either is missing, ask.

---

## [store-link-google] — Google Play Store URL  
Replaced with the Google Play URL from the product file.  
Format: [Google Play Store](https://full-url-from-product-file)  
If the URL is missing from the product file, ask before proceeding.  

---
  
## [store-link-apple] — Apple App Store URL  
Replaced with the Apple App Store URL from the product file.  
Format: [Apple App Store](https://full-url-from-product-file)  
If the URL is missing from the product file, ask before proceeding.  
  
---

## [about-url] — About Page Link
Renders the About URL from the product file as a linked element.
Display text is pulled from Product Name in the product file.
Format: [Product Name](https://about-url)
The About URL must exist in the product file. If missing, ask.

---

## [release-date] — Release Date
The date this version was released to the app stores.
Pulled from the Release Date field in the release input file.
Required field. If it is missing from the release input file, please ask before proceeding.

Validation rule: Compare against the Release Date in the product file.
If the release input date is newer than the product file date, stop.
Flag the discrepancy to the user and wait for confirmation that
the product file has been updated before proceeding.
Do not generate the document until explicit confirmation is received.

---

## [os-android] — Android OS Version
Pulls the Android OS version string from the Supported OS section of the product file.
Format: exactly as written in the product file.
If missing, ask before proceeding.

---

## [os-ios] — iOS Version
Pulls the iOS version string from the Supported OS section of the product file.
Format: exactly as written in the product file.
If missing, ask before proceeding.

---


## General Rules

- Tags are instructions to the AI, not to a browser.
- Every tag has a purpose. Do not skip tags because a field seems empty.
- If a field has no content, ask before leaving it blank.
- Do not invent tags not listed in this file.
- When in doubt, ask.

- 
