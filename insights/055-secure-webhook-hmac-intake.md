# Secure Webhook - HMAC Intake

# Secure Webhook Intake System with HMAC Verification

A production-grade n8n workflow that validates inbound webhook events
before accepting them: header auth blocks unknown callers, HMAC
signature verification confirms payload integrity, and timestamp
validation prevents replay attacks.

## The Problem

Security firms and SOC teams receive events from external sources:
SIEMs, threat feeds, ticketing systems, and custom scripts. Without
a verified intake gate, any caller can push malicious or spoofed
data into your automation pipeline.

Manual verification is not scalable. One misconfigured endpoint is
all it takes.

## The Solution

A layered webhook intake system with three enforcement points:

1. Header Auth blocks any request without the pre-shared API key
2. HMAC-SHA256 signature check verifies the payload was signed by
   the correct sender using a shared secret
3. Timestamp window (plus/minus 5 minutes) eliminates replay attacks

Accepted requests return 202. Signature failures return 401.
Stale or invalid timestamps return 403. The workflow fails closed
by design.

## Use Cases

- Inbound event intake for MDR alert pipelines
- Verified webhook receivers for GRC compliance triggers
- Secure API gateway layer for SOC-as-a-Service platforms
- Threat intel feed ingestion with integrity enforcement

## Impact

Eliminates blind webhook trust. Adds cryptographic verification and
replay protection to any inbound automation endpoint without custom
code or external services.

Built by Kunsh Tanwar | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-03-23 200427.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/secure-webhook-hmac-intake/Screenshot%202026-03-23%20200427.png" />
<img width="800" alt="Screenshot 2026-03-23 200457.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/secure-webhook-hmac-intake/Screenshot%202026-03-23%20200457.png" />
<img width="800" alt="Screenshot 2026-03-23 200516.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/secure-webhook-hmac-intake/Screenshot%202026-03-23%20200516.png" />
