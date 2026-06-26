# API Key Manager for Security Service Platforms

Lifecycle management for machine identities: generate, store, rotate, revoke, and audit API keys
tied to named applications, with a protected endpoint that validates key status before serving data.

## The Problem

Security platforms expose APIs to clients, integrations, and internal services. Those connections
run on API keys. Most teams manage them in spreadsheets, Notion docs, or environment variable
files scattered across repos.

When a key is compromised, there is no audit trail of when it was last used or which system it
touched. When an integration breaks, no one knows which application it belonged to. Manual key
management creates the exact gap that attackers exploit in service account abuse scenarios.

Unmanaged machine identities are a silent attack surface. Service account abuse accounts for
a growing share of post-exploitation lateral movement in MDR incident reports.

## The Solution

A dashboard-integrated key manager with backend enforcement. Each API key is treated as a machine
identity: issued with a named application context, hashed at rest, tracked for last-use, and
revocable in one click without touching environment variables or redeploying services.

**Key Features:**
- Cryptographically secure key generation with visible prefix for visual identification
- Keys stored as SHA-256 hashes, never in plaintext, never retrievable after creation
- Per-key enable/disable toggle for instant revocation without deletion or key rotation
- Last-used timestamp and request count updated asynchronously on every valid request
- Protected API endpoint that rejects invalid or disabled keys with a 401 before any logic runs
- Admin dashboard with full key lifecycle: create, inspect, regenerate, revoke
- Usage log panel showing recent requests per key with endpoint, status, and response time
- Inline RLS editor for managing Supabase Row Level Security policies without leaving the dashboard

## Use Cases

**MDR / SOC-as-a-Service platforms:**
Each client integration runs on a scoped API key. When a client offboards, their key is revoked
in seconds with a full request history preserved. No shared secrets, no key recycling across tenants.

**GRC compliance tools:**
Evidence ingestion APIs accept keys from auditor systems and external scanners. Usage audit trails
satisfy SOC 2 CC6.1 logical access controls with zero additional logging tooling.

**IAM/PAM service providers:**
Demonstrate machine identity governance to enterprise buyers. Every integration in your own
platform runs this pattern before you sell it to clients. Credibility through proof of work.

**Offensive Security / Red Team platforms:**
Scope API access per engagement. Revoke keys when the engagement closes. Audit exactly which
endpoints were called and when, satisfying rules of engagement documentation requirements.

## Impact

- Revocation time drops from "find the key, update env vars, redeploy" to one click
- Full usage audit trail satisfies SOC 2 and ISO 27001 access logging requirements without
  additional tooling
- Plaintext key storage eliminated across dev and production environments
- Compromised key blast radius contained to a single named application, not the whole platform

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
