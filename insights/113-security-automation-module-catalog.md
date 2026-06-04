# Security Automation Module Catalog

Prototype → https://security-automation-module-catalog.vercel.app/

A Supabase-powered control room and public storefront for cybersecurity automation firms.
Manage your service modules from a private dashboard. Show prospects a live, browsable catalog of your capabilities.

---

## Problem

Security firms list their automation capabilities in PDFs, slide decks, and static pages that go stale the moment they are published. Prospects receive outdated information. Operators waste time updating documents instead of building.

There is no live, structured, centralized view of what a firm actually delivers.

---

## Solution

A two-surface application backed by Supabase:

**Control Room (private dashboard)**
Add, update, and archive automation modules. Upload demo screenshots to Supabase Storage. Assign each module to a segment, tier, and status. No authentication required for the operator.

**Public Storefront**
A landing page showing featured modules and a full catalog page showing all active modules. Data renders dynamically from Supabase. Images serve from Supabase Storage. Updates in the control room appear on the storefront immediately.

---

## Database Schema

**Table: `modules`**

| Field | Type | Notes |
|---|---|---|
| id | uuid | Primary key |
| name | text | Module display name |
| segment | text | MDR/SOC, GRC, Cloud Security, IAM/PAM, Offensive Security |
| tier | text | Starter, Professional, Enterprise |
| price | numeric | Base engagement price |
| description | text | One-paragraph capability summary |
| features | text[] | Array of bullet-point capabilities |
| image_url | text | Public URL from Supabase Storage |
| status | text | active, draft, archived |
| featured | boolean | Appears on landing page if true |
| created_at | timestamp | Auto-generated |

**Storage Bucket: `module-screenshots`**
Public bucket. Stores PNG/JPG demo screenshots per module.

---

## Use Cases

- MSSP listing detection and response playbooks for prospective clients
- GRC firms showcasing SOC 2, ISO 27001, and HIPAA automation modules
- MDR operators displaying triage and enrichment capabilities per client tier
- Offensive security teams presenting pentest report automation services
- Any security firm replacing static capability decks with a live catalog

---

## Impact

Prospects see live capabilities, not stale slide decks.
Updates happen from the control room, not from a designer or developer.
The same infrastructure used to manage an e-commerce storefront manages a security service catalog.
The architecture pattern is identical. The domain context is what creates the value.

---

Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-automation-module-catalog/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-automation-module-catalog/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-automation-module-catalog/image.png" />
