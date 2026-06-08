# Security Knowledge Base Manager

CMS-lite FAQ system for cybersecurity firm websites. Operators draft, stage, and publish answers to prospect and client questions. The public help centre renders only published content, searchable by category, with per-answer helpfulness voting. Unpublished drafts and pending items stay in the admin queue.

## The Problem

Security firms field the same pre-sales questions repeatedly across email, LinkedIn, and discovery calls. What's included in the pentest report? Which compliance frameworks do you support? What's your IR SLA? These answers exist somewhere in a slide deck, a Notion page, or a salesperson's memory. They are not on the website. Prospects who cannot find answers drop off before booking a call.

The secondary failure: when a firm does have a FAQ page, it is HTML hardcoded by a developer. Updating an answer requires a code change, a pull request, and a deployment. The content team gives up and the page goes stale.

## The Solution

A `faqs` table with a `status` column as the publish gate. Operators draft answers in the admin dashboard, mark them pending for review, and publish when ready. Published items appear on the public help centre immediately. Drafts never surface publicly. The public page fetches only published records, filters by category client-side, and supports keyword search without a backend query. No developer involvement needed after the initial deploy.

**Key Features:**
- Admin dashboard with status management (draft, pending, published) per FAQ item
- Category tagging across five security-relevant groups: Engagements, Pricing, Compliance, Incident Response, MDR Coverage
- Public accordion FAQ with client-side search and category filter
- Helpfulness voting (yes/no) per FAQ item, stored in Supabase with no authentication required from the visitor
- Edit and delete operations from the admin table with immediate local state sync
- Status counts shown as filter tabs in admin: Total, Published, Draft, Pending

## Use Cases

**MSSP Operators:**
Pre-sales FAQ answers about MDR coverage, alert SLAs, and escalation paths reduce the number of repetitive discovery call minutes. Published answers on the public page handle basic qualification before a prospect books a call.

**Offensive Security Firms:**
Pentest scope questions, retesting policies, NDA handling, and deliverable format are asked by every new prospect. A published knowledge base article answers these in context without the prospect needing to email.

**GRC Advisory Practices:**
Compliance framework coverage, evidence collection process, and audit readiness timelines are questions that lose or win deals. A staged draft process lets the compliance team review the answer before it goes live.

## Impact

- Removes developer dependency from FAQ content updates, cutting update cycle from days to minutes
- Reduces repetitive pre-sales inquiry volume by surfacing answers that currently exist only in email threads
- Draft and pending statuses give non-technical operators a review gate, preventing unvetted answers from going public

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
