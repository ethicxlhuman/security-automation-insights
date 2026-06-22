# Security Retainer Client Manager

Time-based access tracker for cybersecurity retainer programs. Operators manage client organizations on active MDR and GRC advisory retainers — tracking start dates, renewal dates, and coverage status across the client base. Active retainers are covered. Expiring-soon retainers trigger renewal conversations before the detection gap opens. Lapsed retainers are flagged and removed from coverage. The public retainer plans page shows available tiers with benefits and pricing so prospects can compare before reaching out.

## The Problem

MDR and GRC advisory retainers are time-bounded contracts. When a retainer expires and the client does not renew, their detection coverage ends — and if the ops team does not catch it within days, there is a window where incidents go undetected and the client may not know. At scale, tracking 50+ active retainer clients with expiry dates in a spreadsheet or a CRM not designed for this creates predictable failures: renewals missed, coverage gaps unnoticed, and clients lapsing without a proactive conversation.

The second failure: no self-serve way for prospects to compare retainer tiers before scheduling a call. A prospect who cannot evaluate the difference between MDR Starter and MDR Enterprise coverage without booking 30 minutes with a sales rep is a prospect who goes to a competitor with a public pricing page.

## The Solution

Two tables with a foreign key relationship. `retainer_plans` defines the tier catalog — name, monthly price, benefit list, active status, and a featured flag for "Most Popular." `retainer_clients` records each client organization, their assigned plan, start date, expiry date, and a manual deactivation flag. Status is computed dynamically from the expiry date: active when coverage extends beyond 30 days, expiring soon within the 30-day window, lapsed when the expiry has passed or the client has been manually deactivated. The admin dashboard surfaces expiring-soon clients in a dedicated panel for proactive renewal outreach. The public plans page shows only active tiers with full benefits for self-serve comparison.

**Key Features:**
- Admin client table with company name, contact, assigned plan, start/expiry dates, computed status, and deactivate action
- Color-coded status: Active (teal), Expiring Soon (amber), Lapsed (red/muted)
- "Expiring Soon" panel on admin overview showing clients renewing within 30 days
- Days-until-expiry countdown on expiring-soon client rows
- Plan management: add, edit, and toggle plan active status
- Public plans page with tier cards, benefit checklists, pricing, and "Most Popular" badge
- Filter clients by plan type and status in the admin table
- Stat cards: Total Clients, Active, Expiring Soon, Lapsed

## The Gym Membership Analogy Applied to Security

A gym membership is time-based access to a facility. An MDR retainer is time-based access to a security operations center. When a gym membership expires, the member cannot enter. When an MDR retainer lapses, the client's environment is no longer monitored. The stakes are orders of magnitude higher for the security retainer — but the underlying data model is identical. Both need a start date, an expiry date, a status derived from those dates, and a proactive renewal system. The gym puzzle maps directly.

## Use Cases

**MDR Providers:**
Track all active client engagements, surface which retainers are within 30 days of renewal, and use the expiring-soon panel as a daily ops briefing for account managers. Prevent detection coverage gaps by catching renewals before they lapse.

**GRC Advisory Practices:**
Ongoing GRC advisory retainers — SOC 2 evidence collection, ISO 27001 maintenance, quarterly compliance reviews — have annual renewal cycles. The dashboard gives the operations team a single view of the full advisory client base with renewal timeline visibility.

**Offensive Security Firms:**
Annual pentest retainers (quarterly assessments, priority scheduling, reduced rates) can be tracked against start and expiry dates. Expiring retainers trigger a conversation about the next annual engagement before the relationship goes cold.

## Impact

- Eliminates spreadsheet-based retainer tracking, which fails silently when renewals are missed
- Expiring-soon panel creates a proactive renewal workflow instead of a reactive one
- Public plans page converts comparison-shopping prospects without a sales call
- Computed status removes manual status updates — expiry date is the source of truth

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
