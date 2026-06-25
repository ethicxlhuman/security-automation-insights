# Security Asset Expiry Tracker

Deadline-aware asset dashboard for security operations teams. Every SSL certificate, tool license, compliance certification, cloud subscription, and security contract has an expiry date. This tracker surfaces which assets are active, which are coming up for renewal within 30 days, and which have already expired — before a certificate outage, a lapsed license, or a missed compliance renewal causes an incident or a gap in coverage.

## The Pattern

The vehicle fleet management model maps directly to security asset management:

| Fleet Manager         | Security Asset Tracker                          |
|-----------------------|-------------------------------------------------|
| Registration number   | Asset ID (cert serial, license key, contract #) |
| Make / Model          | Vendor / Asset type                             |
| Year acquired         | Acquisition year                                |
| Mileage               | Usage count (scans, incidents, API calls)       |
| MOT expiry date       | Primary expiry date (hard deadline)             |
| Next service date     | Next review date (soft deadline)                |
| Active / Overdue      | Active / Due Soon / Overdue / Inactive          |

A car with an expired MOT cannot legally be driven. An SSL certificate that expires brings down every HTTPS service it protects. The stakes are different but the data model — assets with named deadlines, status derived from dates, and a dashboard that surfaces what needs attention before it becomes a problem — is identical.

## The Problem

Security teams manage dozens of time-bounded assets across certificates, licenses, certifications, and contracts. SSL certificates expire silently at 03:00 UTC on a Sunday. Tool licenses lapse mid-incident when nobody checked the renewal date. ISO 27001 certifications drift past their surveillance audit window. Cloud subscription contracts auto-renew at the wrong tier because nobody reviewed the terms at the 30-day mark.

The current state: these deadlines live in calendar invites, renewal emails, and the memory of whoever set up the asset. When that person leaves, the institutional knowledge goes with them. The first sign of a problem is the outage, the service disruption, or the auditor noting a lapsed certification.

## The Solution

A single `security_assets` table with two date fields per record: `primary_expiry_date` (the hard deadline — cert expires, license ends) and `next_review_date` (the soft deadline — when you should review before the expiry). Status is computed dynamically from both dates: Overdue when the primary expiry has passed, Due Soon when either deadline falls within 30 days, Active otherwise. The dashboard surfaces overdue and due-soon assets in a dedicated attention panel above the full asset table so the most urgent items are never buried.

**Key Features:**
- Two-deadline model per asset: hard expiry + soft review date
- Computed status from both dates: Active / Due Soon / Overdue / Inactive
- "Needs Attention" panel showing overdue and due-soon assets at the top of the dashboard
- Days-until-expiry countdown on due-soon and overdue asset rows
- Filter by status, asset type, and environment (production / staging / internal)
- Stat cards: Total Assets, Active, Due Soon, Overdue
- Add, edit, archive asset records
- Asset types: SSL/TLS Certificate, Tool License, Compliance Certification, Security Contract, Pentest Certification, Cloud Subscription, Domain Registration

## Use Cases

**Security Operations Teams:**
SSL certificates across production, staging, and API environments tracked with primary expiry dates and 30-day review alerts. The dashboard shows which certs are expiring before on-call rotation begins.

**GRC Advisory Practices:**
ISO 27001 certifications have three-year validity with annual surveillance audits. SOC 2 Type II reports expire after 12 months. HIPAA assessments require periodic review. Each certification is an asset with a primary expiry (certification end) and a next review date (surveillance audit due). The dashboard surfaces which client certifications need attention this quarter.

**MDR Providers:**
Tool licenses for EDR, SIEM, and threat intel feeds are the operational foundation of the service. A lapsed CrowdStrike license at 3am removes endpoint visibility across all clients. An expiry tracker with 30-day alerts gives the ops team time to renew before coverage gaps open.

## Impact

- Converts reactive certificate/license management into a proactive workflow
- Eliminates the institutional knowledge problem — expiry dates are in a database, not someone's head
- Overdue panel provides immediate visibility on what is already broken
- Soft review date gives teams time to act before the hard expiry forces them to

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="01KVY6V4HWMDCN5TTVRHY68ERW.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-asset-expiry-tracker/01KVY6V4HWMDCN5TTVRHY68ERW.png" />
<img width="800" alt="01KVY6V4HWMDCN5TTVRHY68ERN.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-asset-expiry-tracker/01KVY6V4HWMDCN5TTVRHY68ERN.png" />
