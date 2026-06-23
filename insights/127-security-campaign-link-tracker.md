# Security Campaign Link Tracker

Tracked redirect system for cybersecurity firm campaigns. Each campaign link is a short code stored in Supabase that maps to a destination URL, logs every click with a timestamp, and can be deactivated instantly from the admin dashboard. Categories cover phishing simulations, security awareness training, threat reports, client portals, demos, and proposals. The admin dashboard shows total clicks, top performing links, last clicked timestamps, and a ranked leaderboard.

## The Pattern

A URL shortener is a threat detection system in miniature. The data model is identical:

1. A code (short slug, IP address, domain hash) is received
2. It is looked up in a database
3. An action is taken based on the result (redirect, block, alert, allow)
4. The event is logged

Phishing simulation platforms use this exact model. When a simulated phishing link fires, the tracker service receives the click, looks up the campaign code in a database, records the employee's click event, then redirects them to a phishing awareness training page. The redirect route in this spec does the same thing: receives the code, looks up the destination, increments the click count atomically via a PostgreSQL function, then fires the redirect.

## The Problem

Security firms send dozens of tracked links every month — phishing simulation payloads, proposal links sent to prospects, client portal access links, threat report distributions, demo environment access. These all get sent as full untracked URLs or via third-party link services (Bitly, Short.io) with no integration into the firm's own data. There is no visibility into which proposal link a prospect opened, which client read the threat report, or how many people clicked the phishing simulation before the training page appeared.

## The Solution

A single `campaign_links` table with a unique short code, destination URL, category, active flag, click count, and last clicked timestamp. A PostgreSQL function handles atomic click increment so concurrent redirects never produce a race condition. The redirect route at `/r/:code` fetches the link, fires the increment, and redirects — the entire operation is sub-200ms. The admin dashboard creates new links, copies the short URL to clipboard, views analytics, and deactivates links without touching code.

**Key Features:**
- Short code generation with uniqueness check before insert
- Atomic click increment via Supabase RPC function
- Redirect route at `/r/:code` — fetch, increment, redirect in a single flow
- Deactivate/reactivate links without deleting them
- Copy-to-clipboard for the full short URL from the dashboard
- Campaign categories: Phishing Simulation, Awareness Training, Threat Report, Client Portal, Demo, Proposal
- Stat cards: Total Links, Total Clicks, Active Links, Top Link Clicks
- Top performing links ranked by click count
- Created date and last clicked timestamp per link

## Cybersecurity Use Cases

**Phishing Simulation:**
Create a tracked campaign link for each phishing simulation payload. When the target clicks, the redirect logs the event and forwards them to an awareness training page. Every click is timestamped. The admin dashboard shows total clicks per simulation, giving the security awareness program measurable data without a third-party SaaS tool.

**Client Portal Access:**
Short-coded links to client-specific MDR portals, evidence submission forms, or debrief recordings give the firm visibility into whether clients are actually accessing their deliverables. A debrief recording with zero clicks after two weeks is an account health signal.

**Proposal and Demo Tracking:**
Short-coded links to pentest proposals and demo environments tell the sales team whether a prospect opened the proposal at all. Last clicked timestamp tells them exactly when the prospect was reviewing it — useful context before a follow-up call.

**Threat Intelligence Distribution:**
Track how many recipients click through to a threat report or advisory bulletin. Identify which threat intelligence content drives the most engagement.

## Impact

- Replaces third-party link shorteners with a self-hosted, owned analytics system
- Atomic click counting via RPC function prevents race conditions under concurrent traffic
- Deactivate action immediately stops a link without a code change or deployment
- Category tagging creates a lightweight campaign attribution system

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
