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

Release date validation: Compare the Release Date in the release input file against the Release Date in the product file. If the release input date is newer, flag the discrepancy and stop. 
Do not generate the document until the user confirms the product file has been updated manually. Wait for explicit confirmation before proceeding.

OS Support Policy: Unless otherwise specified, supported OS versions default to the current release and two versions back for consumer apps, three versions back for enterprise tools.
Confirm with the product owner before documenting.

