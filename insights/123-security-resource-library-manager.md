# Security Resource Library Manager

Managed downloadable asset library for cybersecurity firm websites. Operators upload PDFs, DOCX templates, XLSX tools, PPTX slide decks, and ZIP packages to a Supabase Storage bucket, then publish and feature them from the admin dashboard. Visitors browse the public resource library, filter by category, search by title, and download directly from Supabase Storage. Download counts are tracked per resource. No developer required to add, update, or remove a resource.

## The Problem

Security firms produce intellectual property constantly — pentest checklists, IR playbook templates, SOC 2 evidence spreadsheets, threat reports, compliance guides. These assets demonstrate expertise more effectively than any landing page paragraph. They are also lead magnets: a GRC prospect who downloads a "SOC 2 Readiness Checklist" has told you exactly what they need before they ever send an email.

The current state: these assets sit in Google Drive, are emailed to prospects on request, or are linked from blog posts using static URL strings that break when the file moves. There is no centralized library, no visibility into what is being downloaded, and no way for the content or operations team to add a new resource without asking a developer to update the website.

The second failure: no featured tier. A 2026 Threat Landscape Report that took three weeks to write is presented with the same weight as a basic checklist. There is no mechanism to surface the highest-value proof-of-expertise content above the fold.

## The Solution

A single `resources` table with file metadata, a `status` field (`published`, `draft`, `archived`), and a boolean `is_featured` flag. Files upload to a `resource-files` Supabase Storage public bucket from the admin form. File type is derived from the uploaded MIME type. File size is captured from the File object at upload time and stored as a formatted string (`"2.4 MB"`). The download button increments a `download_count` field on click, giving operators a lightweight analytics signal on which assets drive the most engagement.

**Key Features:**
- Admin resource CRUD with file upload (PDF, DOCX, XLSX, PPTX, ZIP — up to 20MB)
- Status management: Draft, Published, Archived
- Featured toggle: highlighted resources appear in a dedicated hero section
- Public library with featured section, category sidebar with counts, search, and sort
- Download button on every published resource with count tracking
- File type badge derived from MIME type (PDF / DOCX / XLSX / PPTX / ZIP)
- File size stored as human-readable string at upload time
- Admin stat cards: Total, Published, Draft, Archived, Featured

## Why Security Resources Are Different From Generic Files

A security firm's downloadable assets are credentialing documents. A "Web Application Pentest Methodology" PDF tells a prospect how thorough the assessment process is before they commit. A "HIPAA Security Rule Compliance Checklist" tells a healthcare CISO that this firm understands their specific regulatory context. The resource library is not a file dump — it is a structured demonstration of the firm's intellectual depth across every subsegment they serve.

Featured resources are the most powerful of these. A 48-page Red Team TTP Playbook surfaced in the featured section at the top of the page communicates more about offensive security capability than any copywritten claim below the fold.

## Use Cases

**GRC Advisory Practices:**
SOC 2 checklists, ISO 27001 gap assessment templates, HIPAA compliance guides, and evidence collection spreadsheets are the content that GRC-seeking prospects search for before they look for a vendor. A public resource library indexed by category surfaces these assets to the right audience.

**Offensive Security Firms:**
Pentest checklists, red team rules-of-engagement templates, and assessment report formats published as free downloads demonstrate methodology depth. Prospects who download the checklist arrive at the scoping call knowing what to expect.

**MDR Providers:**
Alert triage runbooks, incident response playbooks, and threat hunting hypothesis workbooks are the evidence that an MDR provider has operational depth, not just tooling. Publishing these (appropriately redacted) builds the kind of trust that security buyers need before committing to a managed detection contract.

## Impact

- Centralizes all downloadable security assets in one operator-managed location
- Download counts create a lightweight content analytics signal without a third-party tool
- Featured section surfaces highest-value assets above the fold for maximum prospect impact
- Draft status holds work-in-progress assets off the public library until they are ready

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
