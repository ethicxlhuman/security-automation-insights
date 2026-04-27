# SOC Platform Changelog Viewer

Versioned release notes viewer with category filtering and persistent read acknowledgment, 
built for security teams that need traceable awareness of tooling changes.

## The Problem

Security platforms update constantly. Detection rules change, integrations break, 
new triage logic ships. But awareness of those changes is informal. Most SOC teams 
find out through a Slack message or a Monday morning incident. There is no structured 
record of who reviewed what, when.

When compliance auditors ask "did your team review the detection engine update before 
the breach window?" there is no answer. 53% of MSSPs report operational workflow gaps 
as their top time drain. Untracked tooling changes sit at the center of that.

## The Solution

A changelog viewer that groups updates by version and date, filters by category 
(Features, Fixes, Security, UI, Integrations), highlights the newest release, and 
persists read acknowledgment per update ID in localStorage. Analysts mark updates as 
read. That state survives page reloads.

**Key Features:**
- Version-grouped release entries with timestamps and category badges
- Category filter tabs that derive results from state without re-fetching
- Newest release pinned and visually distinguished from reviewed history
- Per-update read state persisted in localStorage, survives session reloads

## Use Cases

**Mid-Market MDR - SOC Analyst Teams:**
Analysts acknowledge detection logic updates and rule changes before shifts, 
creating an informal but structured awareness trail.

**GRC-Adjacent SOC Teams:**
Change acknowledgment doubles as lightweight evidence that platform updates were 
reviewed before the next audit period, supporting SOC 2 change management controls.

**MSSP Operators:**
Client-facing changelog attached to managed service portals so customers see exactly 
what changed in their security stack without a support ticket.

## Impact

- Replaces untracked Slack update culture with structured per-analyst acknowledgment
- Supports SOC 2 change management evidence without a separate ticketing workflow
- Reduces "what changed?" support noise by surfacing versioned history on demand

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_ai-website-cybersecurity-company.vercel.app (1).png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/brave_screenshot_ai-website-cybersecurity-company.vercel.app%20(1).png" />
<img width="800" alt="brave_screenshot_ai-website-cybersecurity-company.vercel.app.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/brave_screenshot_ai-website-cybersecurity-company.vercel.app.png" />
