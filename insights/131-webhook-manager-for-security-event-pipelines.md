# Webhook Manager for Security Event Pipelines

A multi-endpoint webhook manager that receives, stores, and audits inbound security events,
with delivery history, payload inspection, and replay for dropped or failed deliveries.

## The Problem

Security platforms integrate with dozens of tools via webhooks: SIEMs, EDRs, threat intel feeds,
ticketing systems, and client notification services. Every one of those integrations is a
fire-and-forget pipe with no audit trail.

When an alert webhook fails, no one knows. When a SOAR integration drops an event during
maintenance, the alert is gone. When a compliance audit asks "did you receive this notification?",
the answer is usually a spreadsheet guess.

Silent event loss in webhook pipelines is a documented gap in MDR operations. You cannot replay
what you never stored.

## The Solution

A webhook endpoint manager that treats every inbound request as a first-class record. Webhooks
are received, stored in full (payload, headers, status, timing), and held for inspection or
replay. Each endpoint has a unique URL and HMAC secret for validation. Deliveries can be
replayed to a configured forward URL when downstream processing fails.

**Key Features:**
- Auto-generated unique webhook URLs with HMAC signing secrets per endpoint
- Per-endpoint enable/disable toggle (disabled endpoints still log, but return 200 without forwarding)
- Every inbound request stored before processing: payload, headers, response, duration
- Success rate tracking per endpoint for integration health monitoring
- Delivery history per endpoint with full payload and header inspection
- Replay: re-POST any stored delivery to the endpoint's configured forward URL
- Log deletion with confirmation for housekeeping and compliance scope management
- JSON/Raw toggle on payload viewer for structured and unstructured event inspection

## Use Cases

**MDR / SOC-as-a-Service platforms:**
Ingest alerts from client EDR and SIEM tools via dedicated per-client webhook endpoints.
Every alert is stored before it touches the triage pipeline. Dropped alerts during SOAR
downtime can be replayed in order once the integration recovers.

**MSSP operators:**
Route client notification events (incidents, policy violations, patch failures) through
named webhook endpoints. Audit trail satisfies client SLA reporting without manual logging.

**GRC compliance tools:**
Receive compliance events from cloud posture tools, identity providers, and audit systems.
Full delivery log with timestamps satisfies SOC 2 CC7.2 and ISO 27001 A.12.4 logging
requirements with no additional tooling.

**Offensive Security / Red Team platforms:**
Receive callback notifications from out-of-band payloads and exfiltration probes.
Replay functionality lets operators re-examine captured payloads during post-engagement review.

## Impact

- Silent alert loss eliminated: every inbound event is persisted before any processing occurs
- Integration health visible at a glance: per-endpoint success rate with delivery counts
- Replay capability reduces mean time to recovery when downstream systems drop events
- Full audit trail of received events satisfies external audit requirements out of the box

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
