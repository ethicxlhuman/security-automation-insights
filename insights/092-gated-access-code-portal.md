# Gated Access Code Portal

Client-tier enforcement via local access code validation — no backend auth, 
no user accounts, no session management overhead.

## The Problem

MSSP and MDR firms often need to share tier-specific content with clients: 
onboarding materials, runbooks, VIP portal access, beta feature previews. 
The options are either a full authentication stack (weeks of dev work) or 
unprotected links that leak. Neither fits a lean security ops team moving fast.

Manual alternatives — emailing PDFs, Notion shares, password-protected zips — 
create audit gaps and version drift. There is no middle layer between 
"public page" and "full login system."

## The Solution

A client-side gated content system that validates access codes against a 
predefined tier list, unlocks content on match, and persists session state 
across refreshes. No database. No auth server. No cookies beyond localStorage.

**Key Features:**
- Code validation against tiered access list (VIP, Client, Early Access)
- Persistent session across page refreshes without re-entry
- Animated validation state with "Validating..." feedback loop
- Lock/unlock toggle so clients can clear access from the same UI
- Tier-aware content display — different codes unlock different content blocks

## Use Cases

**IAM/PAM — Client Portal Access:**
Security firms gate onboarding docs, SLA tiers, and runbooks behind codes 
issued per engagement. Clients access what they paid for, nothing more.

**MDR/SOC — Beta Feature Previews:**
SOC-as-a-Service operators give early access codes to pilot clients testing 
new alert triage workflows before general release.

**GRC — Compliance Document Delivery:**
Compliance teams distribute evidence packages and policy templates to 
auditors using single-use access codes tied to audit engagements.

## Impact

- Eliminates backend auth setup for content-tier use cases
- Reduces time-to-client-portal from weeks (auth stack) to hours (code deploy)
- Provides audit-trail-friendly access pattern — codes are logged, not credentials

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

[▶ Watch: 2026-05-06 13-42-40.mp4](https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/gated-access-code-portal/2026-05-06%2013-42-40.mp4)
