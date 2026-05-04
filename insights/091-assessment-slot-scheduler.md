# Assessment Slot Scheduler

Self-serve time-slot booking for cybersecurity firms running recurring assessments, audits, or scoping calls.

## The Problem

Security firms waste hours per engagement on scheduling before billable work begins:
- Pentest scoping calls coordinated over 3-5 email threads
- GRC assessment kickoffs delayed by calendar availability conflicts
- Booked slots manually tracked in spreadsheets or CRM notes
- No visibility into what is open vs. committed until someone checks manually

**Result:** Admin overhead eats pre-engagement time, slows pipeline velocity, and signals operational immaturity to prospects.

## The Solution

A slot availability engine built on a simple status-flagged data array:
- Each slot carries a status: `available` or `booked`
- UI renders only what is open, greyed-out slots are non-selectable
- Selection updates state in real time, CTA reflects the confirmed slot
- No manual cross-checking, no confirmation email chains

**Key Features:**
- Multi-day availability view (configurable day range)
- Status-driven slot rendering (available / booked / selected)
- CTA dynamically updates to confirm selected time
- Easily wired to a backend or n8n webhook for calendar sync

## Use Cases

- **Pentest firms:** Let prospects self-select scoping call slots from a live availability window
- **GRC consultants:** Automate kickoff scheduling for SOC 2 and ISO 27001 engagements
- **MDR providers:** Schedule QBRs and threat review calls without coordinator overhead
- **Offensive Security teams:** Manage red team engagement windows across multiple clients

## Impact

- Eliminates 2-4 hours of scheduling coordination per engagement
- Removes a common drop-off point between prospect interest and first call
- Signals operational maturity: prospects see a firm that runs its own processes cleanly

