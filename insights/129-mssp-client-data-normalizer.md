# MSSP Client Data Normalizer

n8n workflow that ingests a messy client-submitted xlsx via email, detects and separates
embedded data tables, normalizes each category independently, and outputs clean structured
rows to a new Google Sheet.

## The Problem

MSSP operators receive client data exports that are not clean spreadsheets. They are
accumulated chaos: multiple unrelated tables crammed into one file, inconsistent date formats,
mixed currencies, junk rows used as commentary, negative values where none belong, and
column names that change mid-sheet.

Feeding this directly into a reporting pipeline breaks aggregation, corrupts dashboards,
and wastes analyst time on manual cleanup that should not exist.

53% of MSSPs report client reporting and onboarding as their top operational time drain.
The bottleneck is not detection. It is normalization before data ever reaches a tool.

## The Solution

Workflow treats the incoming xlsx as a damaged source, not a structured input. It inspects
every row first, classifies it by table membership, routes each category through its own
normalization branch, then merges the output into a single clean schema.

The original file is never modified. The output is rebuilt from scratch.

**Key Features:**
- Gmail trigger fires on email with xlsx attachment, no manual upload required
- Row-level classification detects which embedded table each row belongs to by column signature
- Per-category normalization branches handle dates, currency strings, nulls, and negatives independently
- Junk rows (metadata, comments, empty rows) are routed to a separate audit log, not dropped silently
- Merge node appends all clean branches before final deduplication and column standardization
- Output writes to a timestamped new Google Sheet, source data untouched

## Use Cases

**MSSP Operators - Multi-Client Reporting:**
Clients send evidence exports in whatever format they have. This workflow normalizes on
ingest so the reporting pipeline always receives a consistent schema regardless of client.

**GRC Teams - Compliance Evidence Ingestion:**
Auditors submit bulk control evidence as mixed xlsx exports. Workflow separates asset data,
access records, and control test results into clean tables ready for a compliance dashboard.

**MDR Teams - Enrichment Pre-Processing:**
Threat data aggregated from multiple sources arrives in inconsistent column formats.
Normalize before feeding into triage or SIEM ingestion to prevent enrichment failures.

## Impact

- Eliminates manual xlsx cleanup before every client reporting cycle
- Normalizes multi-table source files in under 60 seconds vs. 45-90 minutes by hand
- Audit log preserves every discarded row with reason, satisfying evidence trail requirements
- Clean output feeds directly into dashboards with zero schema rework

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
