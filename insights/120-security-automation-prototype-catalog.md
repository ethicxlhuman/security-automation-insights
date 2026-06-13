# Security Automation Prototype Catalog

Public-facing showcase for cybersecurity automation prototypes. Each prototype is a listing with subsegment, category, starting price, integration count, workflow count, and delivery type. Featured prototypes surface in a dedicated hero section. Operators publish, draft, and archive entries from the admin dashboard. Visitors filter by subsegment, price range, integration count, and delivery type. Images upload directly to Supabase Storage.

## The Problem

A security automation firm's prototypes are its primary sales asset. The competency proof strategy — build 15 prototypes across 5 subsegments, publish them publicly — only works if prospects can browse the catalog before a discovery call. GitHub profile links and YouTube demo playlists are not a browsable catalog. They require the prospect to know what to look for. Most don't.

The current state for most security automation firms: the prototypes exist, the demos exist, and the proof of work exists — but it is scattered across platforms with no unified, filterable interface. A SOC manager looking for alert triage automation cannot immediately tell if a firm has solved their specific problem.

The second failure is maintenance. When a prototype gets superseded by a newer version, the old one should be archived, not deleted. When a new build goes live, it should be publishable instantly without a developer or a deployment. The content lifecycle has to be operator-controlled.

## The Solution

A single `prototypes` table with status (`published`, `draft`, `archived`) and a boolean `is_featured` flag. The dashboard controls the full lifecycle. The public showcase page fetches only published records and filters client-side across four dimensions simultaneously: subsegment, price range, integration count, and delivery type. Featured items render in a highlighted hero grid above the filterable catalog. Images upload to a Supabase Storage public bucket from the admin form.

**Key Features:**
- Admin dashboard with prototype CRUD, image upload, status management, and featured toggle
- Public catalog with four simultaneous client-side filters and two sort options
- Featured hero section showing is_featured + published prototypes
- Search by title and description on the public page
- Stat cards: Total, Published, Featured, Archived
- Image fallback using subsegment label when no image is uploaded

## This Is the Prototype Strategy Made Searchable

ETXcyberops' 15 prototypes across MDR/SOC, GRC/Compliance, Cloud Security, IAM/PAM, and Offensive Security are the seed data for this catalog. The 7 completed prototypes are seeded as published with featured flags. The 8 in-progress prototypes are seeded as draft. Two legacy versions are seeded as archived. This means the catalog goes live with real content the moment the SQL runs.

**Subsegment coverage:**
- MDR/SOC: Alert Triage, SOC Automation, Multi-Client Management
- GRC/Compliance: SOC 2, ISO 27001, HIPAA, Evidence Collection
- Cloud Security: CSPM, CWPP, SSPM
- IAM/PAM: Adaptive Auth, PAM Session Recording, Zero Trust
- Offensive Security: Pentest Report Gen, Cloud Pentesting, Red Team Simulation

## Use Cases

**Security Automation Firms:**
The prototype catalog IS the sales deck. A prospect who can filter by subsegment, see the integration count, check the starting price, and watch the demo video before a call arrives prequalified. The discovery call starts at "how do we customize this?" not "what do you actually do?"

**MDR Providers and MSSPs:**
A filterable tool catalog allows operator-facing buyers (SOC managers, CISOs) to identify which automation tools are already built and available for custom deployment. Featured placements direct attention to the highest-ROI offerings.

**GRC Advisory Practices:**
Compliance automation tools need a clear subsegment label, integration list, and outcome description. A managed catalog with rich filtering lets GRC prospects self-identify before reaching out.

## Impact

- GitHub profiles and YouTube channels become supplementary, not primary, for prospect discovery
- Subsegment filtering converts a generic "we do automation" message into a targeted match for each prospect's specific problem
- Draft status holds in-progress prototypes off the public catalog without deleting them
- Archive status preserves deprecated builds for internal reference while removing them from the prospect view

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
