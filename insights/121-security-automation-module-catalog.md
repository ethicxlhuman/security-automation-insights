# Security Automation Module Catalog

Live-inventory service menu for cybersecurity automation firms. Operators control which modules are active, at capacity, or in draft from the admin dashboard. Featured modules surface in a dedicated hero section. Visitors browse and filter by category — Detection, Response, Compliance, Integrations, Premium — and see capacity status in real time. No developer required to update what is live on the site.

## The Problem

Security automation firms manage a shifting portfolio of modules — detection rules, IR playbooks, compliance automations, integration connectors. Some are live and available for new clients. Some are fully deployed across existing engagements and cannot take new clients until capacity frees up. Some are in development and not ready to advertise. Most firms treat all of these the same way on their website: a static services page that a developer has to update.

The result: prospects call about a module that is actually at capacity. The sales team wastes 30 minutes on a discovery call before the capacity issue surfaces. Meanwhile, a module that just cleared capacity is not reflected on the site because no developer has pushed the update yet.

The second problem: no featured tier. A ransomware containment playbook that saved a client $2M in breach costs is buried in the same flat list as a basic Slack alerting connector. The highest-value proof points are invisible.

## The Solution

A single `automation_modules` table with a `status` field (`active`, `at_capacity`, `draft`) and a boolean `is_featured` flag. The dashboard controls both. The public module catalog shows all non-draft modules — active ones invite inquiry, at-capacity ones show a clear capacity badge that pre-empts unqualified calls. Featured modules with active or at-capacity status appear in a highlighted hero section. All filtering is client-side with no re-fetches on category change.

**Key Features:**
- Admin dashboard with full module CRUD, image upload, status management, and featured toggle
- Four status dimensions in the admin: Active, At Capacity, Draft, Featured (toggle)
- Public module catalog with category filter tabs (Detection, Response, Compliance, Integrations, Premium)
- Featured hero section showing is_featured modules
- At-capacity badge on the public card prevents unqualified inquiry for full-capacity services
- Image upload to Supabase Storage with preview before save
- Stat cards: Total, Published (live), Active, At Capacity

## The Inventory Insight

A restaurant marks a dish as sold out when they run out of ingredients. A security automation firm should mark a module as at-capacity when they cannot take new client engagements for that specific service. The underlying pattern is identical: live inventory status that customers see before they engage, not after. The only difference is what "inventory" means — lobster supply versus senior detection engineer availability.

## Use Cases

**MDR Providers:**
Detection modules at full deployment capacity across the client base should show "At Capacity" publicly. New prospects see the badge and self-select into a waitlist inquiry rather than expecting immediate deployment. Featured detection modules with real client outcome data drive inbound from the right buyers.

**Offensive Security Firms:**
A red team simulation module that is currently fully booked should not imply availability. Marking it at capacity on the public page is more honest and more efficient than fielding calls about a service that cannot start for 90 days.

**GRC Advisory Practices:**
Compliance automation modules vary wildly in complexity and capacity. A HIPAA audit trail automation running for 4 clients might have room for 2 more. A SOC 2 evidence collector at maximum deployment shows at-capacity. The catalog reflects the true state of the firm's service availability at any moment.

## Impact

- Pre-qualifies prospects on capacity before the discovery call, reducing unqualified pipeline by eliminating the "actually we're full right now" conversation
- Featured tier surfaces highest-value proof-of-work above the fold without developer intervention
- Draft status holds modules in development off the public catalog until they are ready to advertise
- Category filtering lets the right buyer find the right module without reading every entry

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-automation-module-catalog/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-automation-module-catalog/image.png" />
