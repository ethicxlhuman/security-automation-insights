# Error Tracking System for Security Tooling Reliability

An incident-style error collector that groups repeated failures by message, tracks occurrence
counts, and surfaces critical/high severity errors before they become client-facing outages.

## The Problem

Security automation tools fail silently more often than anyone admits. A SOAR playbook throws
an unhandled exception at 3 AM. A compliance evidence collector hits a malformed API response
and stops mid-run. A client-facing dashboard breaks on a null value nobody tested for.

Most teams find out from a support ticket, not from the system itself. By the time a client
reports the bug, the same error has already happened 300 times and the audit trail is whatever
scattered console logs are left in a server that already restarted.

For platforms that handle security operations, an unmonitored error in the automation layer
is itself a risk: a missed alert, a skipped compliance check, a silent gap in coverage.

## The Solution

A lightweight error tracker treating every failure as an incident, not a log line. Errors are
ingested via a single POST endpoint, automatically grouped by message so repeated failures
collapse into one trackable record, and triaged through a status workflow (New, Investigating,
Resolved, Ignored) instead of disappearing into a log stream.

**Key Features:**
- Single POST endpoint accepts message, stack trace, URL, browser, severity, and timestamp
- Automatic grouping by error message with running occurrence count and first/last seen timestamps
- Four-stage triage workflow: New, Investigating, Resolved, Ignored
- Severity classification: Critical, High, Medium, Low, Info, with visual highlighting on the table
- Trend sparklines on stat cards showing 7-day movement for total, new, critical, and resolved counts
- Errors by Severity and Errors by Status donut charts for instant triage prioritization
- Full detail panel per error: stack trace, user agent, browser/OS, occurrence count, and notes field
- Filter and search by severity, status, time range, and free-text message search

## Use Cases

**MDR / SOC-as-a-Service platforms:**
Track failures in your own alert enrichment and triage pipeline. An unhandled error in the
triage automation is an undetected gap in client coverage. Surface it before a client does.

**GRC compliance tools:**
Evidence collection scripts that silently fail mean missing compliance documentation. Group
errors by message so a single API change that breaks ten client integrations shows up as one
high-occurrence incident, not ten separate mysteries.

**MSSP operators:**
Multi-tenant automation surfaces different failure modes per client environment. Severity-based
triage means a critical failure affecting billing or alert delivery gets attention before a
cosmetic dashboard glitch.

**Offensive Security / Pentest platforms:**
Report generation and scan orchestration tools fail on edge-case target environments. Stack
trace capture with URL and browser context speeds up reproduction without re-running engagements.

## Impact

- Repeated failures collapse into one incident instead of flooding logs with duplicate noise
- Critical and High severity errors are visually impossible to miss on the dashboard
- Mean time to detection drops from "client reported it" to "dashboard flagged it"
- Full stack trace and environment context eliminates back-and-forth reproduction requests

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
