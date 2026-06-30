# Scheduled Jobs Manager for Security Operations Automation

A cron-based job scheduler with a full execution audit trail, per-job history, failure alerting,
and a dashboard that makes background security operations visible without touching server logs.

## The Problem

Security operations run on schedules. IOC enrichment runs at midnight. Compliance evidence gets
collected every Sunday. Client risk reports generate on the first of each month. Vulnerability
scans kick off at 03:00 UTC.

Most teams manage this through external cron services, cloud scheduler functions, or manually
triggered scripts. When a job silently fails, nobody knows until a deadline is missed, a report
is empty, or an auditor asks for evidence that was never collected.

"It ran fine last week" is not an audit trail.

## The Solution

A self-contained scheduler where every job is a record and every execution leaves a permanent
history. Jobs are defined with cron schedules, tracked for run count and failure rate, and their
most recent execution status is visible at a glance. Failed jobs surface immediately in the
dashboard without requiring anyone to check external logs or cloud provider consoles.

**Key Features:**
- Job registry with cron schedule, description, timezone, enable/disable toggle
- Human-readable schedule display alongside the raw cron expression
- Per-job execution history: status, duration, started/finished timestamps, error output
- Failed job flagging in the stats row: "X Requires Attention" with danger styling
- Next 5 Executions preview across all enabled jobs for operational awareness
- Job Executions bar chart (Last 7 Days) showing success/failed breakdown per day
- Right-panel execution timeline per job with direct access to recent run details
- Vercel Cron trigger endpoint: runs every minute, checks due jobs, records all outcomes

## Use Cases

**GRC compliance automation:**
Schedule SOC 2 evidence collection, ISO 27001 control verification, and HIPAA audit log
aggregation as named jobs. Every execution is self-documenting. When an auditor asks if the
weekly access review ran, the answer is a timestamp and a duration, not a guess.

**MDR / SOC-as-a-Service platforms:**
Daily IOC enrichment scans, threat intel feed ingestion, and automated alert aging all run
as registered jobs. When the MDR team onboards a new SIEM feed, it becomes a named job with
visible history, not a cron entry buried in a VM.

**MSSP operators:**
Client report generation, SLA compliance checks, and multi-tenant health monitoring run on
individual schedules per client. Failed report jobs surface in the dashboard before the client
notices the report is missing.

**Cloud Security / CSPM:**
Scheduled posture checks against AWS Config, Azure Policy, and GCP Security Command Center
run as registered jobs. Drift detection and misconfiguration alerts are tied to specific
execution records, not floating log entries.

## Impact

- Silent job failure eliminated: every failed execution surfaces immediately in the dashboard
- Audit trail for scheduled operations requires no external logging infrastructure
- Operations team sees the next 5 upcoming executions without accessing cloud scheduler consoles
- GRC evidence collection becomes traceable: each compliance check has a run record with timestamp

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
