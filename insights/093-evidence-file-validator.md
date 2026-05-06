# Evidence File Validator

Client-side file validation engine that separates accepted from rejected 
submissions before anything touches your backend — built for security 
teams that cannot afford garbage-in on compliance workflows.

## The Problem

GRC and audit teams receive evidence files from clients and internal teams 
constantly: screenshots, exports, signed policies, scan reports. Without 
upfront validation, the wrong file types and oversized uploads clog 
pipelines, break downstream automation, and create manual cleanup work.

SOC 2 and ISO 27001 evidence collection is already one of the highest 
time-drain workflows in a GRC practice — surveys show manual compliance 
processes consume 14+ hours per assessment. Bad file submissions multiply 
that number.

## The Solution

A multi-file upload validator that checks type and size rules on the client 
before any upload is processed. Accepted and rejected files are separated 
instantly with clear feedback. Users remove bad files and resubmit, clean.

**Key Features:**
- Multi-file drag-and-drop intake with browse fallback
- Per-file type and size validation against configurable rule sets
- Split accepted/rejected display with rejection reason per file
- Remove-before-submit for both accepted and rejected queues
- Submission gated until queue is clean — no partial uploads

## Use Cases

**GRC — SOC 2 / ISO 27001 Evidence Collection:**
Evidence portals enforce file type rules (PDF, PNG, JPG only) and size 
limits upfront, so auditors receive clean submissions without back-and-forth.

**MDR/SOC — Incident Artifact Ingestion:**
SOC teams collecting PCAP files, memory dumps, and log exports gate 
uploads by type before routing to analysis pipelines, preventing 
parser failures downstream.

**Offensive Security — Pentest Report Delivery:**
Red team operators submit final deliverables through validated upload 
flows that reject wrong formats before reports reach client portals.

## Impact

- Eliminates manual file cleanup from compliance evidence queues
- Reduces evidence collection round-trips by catching bad submissions at intake
- Prevents downstream automation failures caused by unsupported file types

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

[▶ Watch: 2026-05-06 22-57-49 - Trim.mp4](https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/evidence-file-validator/2026-05-06%2022-57-49%20-%20Trim.mp4)
