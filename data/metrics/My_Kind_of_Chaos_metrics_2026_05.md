# Scaffold — Metrics Data
## Source file for Tier 1 and Tier 2 document generation.
## Data is version-agnostic. Tracked by month, not by release.

---

## Field Definitions

### Period
The month and year this file covers.
Format: YYYY_MM (matches filename)
Example: 2026_05

### Delimiter
CSV fields in this file use the pipe character as a delimiter: |
Example: 2026_05 | 10000 | 12000

### Fields — in order as they appear in data rows
1. Period — YYYY_MM
2. Downloads — total cumulative downloads to date
3. Active Users — monthly active users for the period
4. New Installs — new installs during the period
5. Uninstalls — uninstalls during the period
6. Subscription Conversions — free to paid conversions during the period
7. Retention Rate — percentage of users active from the prior month
8. Ad Impressions — total ad impressions during the period (if applicable)
9. Notes — any context relevant to the numbers for this period

---

## Data

### Headers
Period | Downloads | Active Users | New Installs | Uninstalls | 
Subscription Conversions | Retention Rate | Ad Impressions | Notes

### Rows
2026_05 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | Initial stub. No data yet.

---

## Usage Notes
- One file per month per product.
- File naming convention: [ProductName]_metrics_[YYYY_MM].md
- Example: My_Kind_of_Chaos_metrics_2026_05.md
- For quarterly rollups, ask Claude to combine the relevant monthly 
  files based on the company's fiscal calendar.
- Metrics files live in data/metrics/ — present but out of the way.
