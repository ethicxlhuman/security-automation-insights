# Security Engagement Intake Form

Multi-step client intake form for cybersecurity firms that captures scoping data
before an engagement begins. Validates required fields per step, preserves state
on back-navigation, and outputs a structured brief ready for handoff.

## The Problem

Security firms lose hours before an engagement even starts:
- Scoping questions scattered across email threads
- Clients submit incomplete info, requiring multiple follow-ups
- No standard data format means each PM re-asks the same questions
- Sales-to-delivery handoff breaks because context lives in someone's inbox

Result: 2-5 days of pre-engagement friction before actual work begins.

## The Solution

A 3-step validated intake form:
- Step 1: Contact Info (company, role, decision-maker confirmation)
- Step 2: Engagement Details (type: pentest/GRC/MDR, scope, existing stack)
- Step 3: Budget and Timeline (range, urgency, compliance deadline if applicable)

Key behaviors:
- Cannot advance without completing required fields per step
- All entered data preserved when navigating back
- Single state object drives the entire form (one source of truth)
- Output: structured JSON brief ready for CRM or ticketing ingestion

## Use Cases

- Pentest firms: capture scope, target environment, rules of engagement
- GRC consultancies: capture framework (SOC 2 / ISO 27001 / HIPAA), current posture
- MDR providers: capture existing SIEM, alert volume, SLA expectations

## Tech Stack

- React (state management via single form object)
- Tailwind CSS (dark enterprise theme)
- Field-level validation before step progression
- JSON output on submission

## Target Audience

Security firm founders and ops managers running 10-500 person teams who
close 3-20 engagements per month and lose hours per deal to pre-sales friction.

## Impact

- Cuts scoping intake from 3-5 days to under 10 minutes
- Eliminates incomplete submissions (validation gates)
- Standardizes data format across all incoming engagements
- Direct pipeline into CRM, n8n workflow, or ticketing system

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-04-02 223522.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/security-engagement-intake-form/Screenshot%202026-04-02%20223522.png" />
<img width="800" alt="Screenshot 2026-04-02 223606.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/security-engagement-intake-form/Screenshot%202026-04-02%20223606.png" />
<img width="800" alt="Screenshot 2026-04-02 223621.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/security-engagement-intake-form/Screenshot%202026-04-02%20223621.png" />
<img width="800" alt="Screenshot 2026-04-02 223633.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/security-engagement-intake-form/Screenshot%202026-04-02%20223633.png" />
