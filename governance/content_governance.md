Source file integrity: Scaffold does not autonomously modify, overwrite, or update any source file. Product files, release input files, and all schema files are maintained by the user. Claude generates output files only. When a source file requires updating, flag it, explain what needs to change, and wait for the user to confirm the update before proceeding.

The wireframe defines what a document type requires. If it's in the template, it's required. If it's not, it doesn't exist for that document type.  

Trailing spaces at the end of lines in wireframe files are intentional Markdown syntax. Do not remove them.  

The publish date is generated at the time of document creation. It is not stored in the product file.  

For published apps, replace the placeholder with the actual store URL copied directly from the store listing. Do not construct URLs manually.  

## Version Number Format

Version numbers use a four-segment format with two digits per segment, 
zero-padded. No exceptions.

Standard: 01.00.00.00

Examples:
- Correct: 01.00.00.05
- Correct: 01.00.00.13
- Incorrect: 1.0.0.5
- Incorrect: 1.00.00.13

This applies to:
- Product file (Current Version, Release Version)
- Release input files (Version)
- All generated output documents
- File naming (My_Kind_of_Chaos_01.00.00.13.md)

Validation rule: If any version number in any source file does not match 
the 00.00.00.00 pattern exactly, stop and flag before generating.

## Release Date Validation

Release date validation:
The release input file stores the full date  (Month DD, YYYY — example: May 22, 2026).
The product file stores only the month and year (Month YYYY — example: May 2026).

Validation compares only the month and year. Day is ignored.

Rule: Any mismatch between the release input date and the product file date 
stops generation. Do not proceed until the user explicitly confirms 
the discrepancy has been resolved.

If the release input is newer than the product file:
Flag — "Release input date is newer than product file. The product file 
may not have been updated. Confirm product file is current before 
proceeding."

If the release input is older than the product file:
Flag — "Release input date is older than product file. An undocumented 
release may exist. Confirm all releases are documented before proceeding."

If the month and year match, proceed without flagging.

Examples:
- Release input: May 22, 2026 / Product file: May 2026 — match, proceed
- Release input: May 22, 2026 / Product file: April 2026 — newer, flag, and stop
- Release input: April 15, 2026 / Product file: May 2026 — older, flag, and stop


OS Support Policy: Unless otherwise specified, supported OS versions default to the current release and two versions back for consumer apps, three versions back for enterprise tools.
Confirm with the product owner before documenting.

## File Naming Convention

All Scaffold files follow a product-first naming standard.

Format: [ProductName]_[DocType]_[Version or Period].md

Document type identifiers:
- RelNote — Release notes
- CompatMatrix — Compatibility matrix
- Metrics — Monthly metrics file
- About — About page content

Examples:
- My_Kind_of_Chaos_RelNote_01.00.00.13.md
- My_Kind_of_Chaos_CompatMatrix_01.00.00.13.md
- My_Kind_of_Chaos_Metrics_2026_05.md
- My_Kind_of_Chaos_About.md

Rules:
- Product name matches exactly as written in the product file,
  spaces replaced with underscores
- Document type identifier is always the second segment
- Version numbers follow the 00.00.00.00 standard
- Metrics files use YYYY_MM for the period segment, no version number
- New document types get a short identifier defined here before
  the first file is created
