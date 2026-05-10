# Active Entity Normalizer

Raw user feeds contain noise. Inactive accounts, inconsistent formatting, unsorted identifiers.
This workflow filters, extracts, sorts, and formats active user entities into a clean,
normalized string ready for downstream ingestion.

## Problem

SOC pipelines and IAM access review tools frequently receive raw user datasets with mixed
statuses, unordered records, and no standardized output format. Passing dirty data to a
SIEM or identity governance tool causes false positives, missed correlations, and manual
cleanup overhead.

## Solution

An n8n workflow that:
- Filters only active user entities from a raw input
- Extracts usernames and sorts them alphabetically
- Wraps each identifier in double quotes
- Outputs a single formatted string ready for API injection or report use

## Use Cases

- IAM access review: compile active user lists before quarterly entitlement audits
- MDR triage: normalize user entity identifiers before enrichment against threat intel feeds
- GRC compliance: extract active accounts for SOC 2 user access evidence packages
- SSPM: pull active SaaS user lists for access governance checks

## Impact

Eliminates manual copy-paste normalization of user records before ingestion.
Removes formatting errors that break downstream API calls or audit evidence submissions.
Runs in seconds on datasets of any size.

Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/active-entity-normalizer/brave_screenshot.png" />
