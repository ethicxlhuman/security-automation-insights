# Security Engagement Quote Estimator

Configurable pricing engine for cybersecurity firms. Operators set base prices for assessment types and optional scope add-ons from the admin dashboard. Prospects visit the public estimator, pick an assessment, stack add-ons, fill in basic engagement details, and get an instant price estimate — then submit for follow-up. Three Supabase tables. No pricing logic hardcoded in the frontend.

## The Problem

Security firm pricing lives in a salesperson's head, a spreadsheet, or a rate card PDF that is always one version out of date. When a prospect asks "how much does a pentest cost?", the answer depends on who they ask, when they ask, and how good that person is at scoping. Pricing inconsistency is a trust issue and a qualification issue simultaneously.

The second failure: there is no self-serve way for a prospect to explore pricing before scheduling a call. The call happens, someone creates a quote from memory, and the prospect either accepts it, haggles, or goes quiet. There is no audit trail of what they selected, what they were quoted, or whether the scope changed between the first conversation and the proposal.

The third failure: when the firm changes a price — adds a new add-on, retires a service, adjusts the base rate — updating the website requires a developer. So the website stays wrong for weeks.

## The Solution

Three tables with a clean separation of concerns. `services` holds the assessment catalog with base prices. `addons` holds optional scope additions with extra prices. Both are operator-controlled from the admin dashboard. `quote_requests` stores the full snapshot of what the prospect selected — service name, selected add-ons with prices, estimated total, and engagement details — at the moment of submission. The public estimator fetches live prices from Supabase, calculates the estimate client-side on every selection change, and saves the complete snapshot on submit.

**Key Features:**
- Admin service management: add, edit, publish, archive assessments with base prices
- Admin add-on management: add, edit, publish, archive optional scope additions with prices
- Three-step public estimator: Assessment Selection → Add-ons + Engagement Details → Review & Submit
- Live price calculation: base price + selected add-ons, recalculates on every change
- JSONB snapshot of selected add-ons stored on quote request for historical accuracy
- Admin quote dashboard with Pending / Approved / Declined status pipeline
- "Get a Quote" CTA button in the main public navigation

## The Pricing Logic Insight

Pricing logic as configurable database records means the firm controls pricing from a dashboard, not a codebase. When a senior penetration tester raises the Red Team Engagement base price from $25K to $30K after winning three enterprise clients, an operator makes one admin update. The public estimator reflects the new price immediately. No pull request. No deployment. No one on the website seeing a price that does not match the proposal.

## Use Cases

**Offensive Security Firms:**
Web app pentest and red team engagement pricing varies by scope, but a base price with configurable add-ons (retesting, executive report, compliance mapping) covers 80% of prospect inquiries without a scoping call. Prospects arrive at the call already understanding roughly what they will pay and what is included.

**GRC Advisory Practices:**
SOC 2 and ISO 27001 readiness pricing is particularly opaque. A base price for the advisory engagement with add-ons for evidence automation, auditor liaison, and compliance framework mapping lets GRC prospects scope their own engagement before the first conversation.

**MDR Providers:**
MDR onboarding base price with add-ons for extended coverage, threat hunting hours, and quarterly business reviews gives prospects a transparent starting point. The submitted quote request includes their environment details, which pre-populates the actual scoping worksheet.

## Impact

- Eliminates pricing inconsistency across sales conversations — every prospect sees the same live rates from the same source of truth
- Converts website visitors into identified prospects with a named company, email, and stated scope before any human interaction
- Full snapshot storage means the firm can audit what a client was quoted versus what they were charged, even if prices changed in between
- Admin status pipeline (Pending → Approved → Declined) creates a lightweight CRM for inbound quote follow-up

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
