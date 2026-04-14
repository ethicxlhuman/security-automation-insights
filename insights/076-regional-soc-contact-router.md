# Regional SOC Contact Router

> Instant contact switching for MSSPs and MDR providers operating across multiple locations or time zones.

---

## The Problem

When a client calls at 2 AM during an active incident, they shouldn't be hunting for the right SOC team's number.

Most MSSP and MDR providers operate across multiple offices or regional SOCs — but their contact pages are static, outdated, or force the client to read through all locations to find the relevant one. During high-pressure incidents, this friction costs time that directly affects breach response.

**The result:** Wrong team gets called. Escalation is delayed. SLA windows close.

---

## The Solution

A persistent, location-aware contact switcher that:

- Lets clients select their assigned SOC region in one click
- Instantly surfaces the correct address, phone, operating hours, and escalation CTA
- Remembers the selected location across page refreshes (localStorage persistence)
- Shows a region-specific call-to-action — so the button says "Speak to EMEA SOC" not a generic "Contact Us"

**Key Outcome:** Zero cognitive load during incident escalation. The right team's details are always one click away.

---

## Use Cases

- **MDR providers** with regional coverage (US, EMEA, APAC)
- **SOC-as-a-Service** vendors managing multi-timezone operations
- **MSSPs** with distributed analyst teams
- **Incident response firms** with on-call rotations by region

---

## Tech Stack

- Vanilla HTML/CSS/JS (zero framework dependency)
- localStorage for persistent state
- Component-driven architecture (branch data object → UI state)

---

## Cybersecurity Service provider Context

This pattern directly addresses the **client communication bottleneck** identified across MSSP operations — where over 50% of providers report that client onboarding and coordination consume excessive time (CyberRisk Alliance, 2024).

A contact router won't replace a full client portal, but as a website component it eliminates one of the most common friction points in incident escalation: *"I don't know which number to call."*

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-04-15 002226.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/regional-soc-contact-router/Screenshot%202026-04-15%20002226.png" />
<img width="800" alt="Screenshot 2026-04-15 002249.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/regional-soc-contact-router/Screenshot%202026-04-15%20002249.png" />
<img width="800" alt="Screenshot 2026-04-15 002305.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/regional-soc-contact-router/Screenshot%202026-04-15%20002305.png" />
