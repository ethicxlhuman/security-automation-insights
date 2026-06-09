# Security Engagement Portfolio Manager

Three-status proof asset pipeline for cybersecurity firm websites. Featured engagements surface in a dedicated hero section. Published engagements populate the full portfolio. Drafts stay in the admin queue until client consent is confirmed and the write-up is approved for public disclosure. Images upload directly to Supabase Storage and render dynamically with no developer involvement after initial deploy.

## The Problem

Security firms close deals on proof. A prospect evaluating a pentest vendor wants to know you have found the same class of vulnerability their environment probably has. A CISO evaluating an MDR provider wants to see a real detection story. This proof lives in engagement reports, in email threads with former clients, in a slide deck with "CONFIDENTIAL" on every page. It does not live on the website.

When security firms do publish case studies, the content lifecycle is broken. Engagements finish. The write-up sits in a Google Doc. The client approval email gets lost in a thread. The developer gets asked to add it to the hardcoded case studies section six weeks later. By then the window to use it in an active sales cycle has passed.

The second failure: treating all case studies as equal. A red team engagement that compromised a Fortune 500's domain in four hours closes deals differently than a routine web app scan. There is no way to surface that distinction without a featured tier.

## The Solution

A `case_studies` table with three status levels: `draft` (internal), `published` (live on portfolio page), and `featured` (live and highlighted in the hero section). Operators control the entire lifecycle from the admin dashboard — draft new write-ups, stage them for review, publish, and promote to featured — without touching code or a deployment pipeline. Images upload directly to a Supabase Storage public bucket from the admin form. The public portfolio page fetches only non-draft records and renders featured items in a separate highlighted grid above the full portfolio.

**Key Features:**
- Admin dashboard with total, published, draft, and featured stat cards
- Full case study form: title, client industry, service type, result headline, description, and image upload
- Direct-to-Supabase Storage image upload with preview before save
- Three-status management with inline status updates from the admin table
- Public portfolio page with featured hero section and filterable full portfolio
- Service type filter tabs on public page derived dynamically from live case studies
- Image fallback rendering when no image has been uploaded

## Use Cases

**Offensive Security Firms:**
A red team engagement that demonstrates lateral movement and domain compromise is a feature-worthy proof asset. A routine OWASP Top 10 scan is a published case study. The distinction matters for how prospects evaluate the firm. Featured status gives operators a way to surface the most compelling proof without rebuilding the page.

**MDR Providers:**
Detection case studies (real threat actor TTPs caught, response time metrics, client environment context) need client consent before going public. Draft status holds the write-up safely while consent is in progress. The engagement result does not expire from the CRM before the asset gets published.

**GRC Advisory Practices:**
SOC 2 and ISO 27001 readiness case studies quantify the outcome (weeks to readiness, audit results, controls automated). These convert at the bottom of the sales funnel. A managed portfolio ensures the most recent and most quantified outcomes are always live on the site.

## Impact

- Eliminates developer dependency on case study publication, cutting update cycle from weeks to minutes
- Draft status captures engagement outcomes immediately post-close, before client approval is finalized, preventing proof assets from being lost
- Featured tier surfaces highest-converting proof without restructuring the page
- Image upload to Supabase Storage removes external hosting dependency from the content workflow

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
