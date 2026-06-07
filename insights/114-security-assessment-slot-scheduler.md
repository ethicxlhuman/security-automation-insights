# Security Assessment Slot Scheduler

Availability and bookings as separate Supabase entities, wired into a public-facing assessment booking page and an operator dashboard. Built so security firms can expose their assessment calendar without double-booking senior engineers.

## The Problem

Security firms running pentests, SOC 2 advisory, and MDR onboarding calls manage capacity manually. Engineers handle availability over email or shared spreadsheets. Prospects land on a site with no self-serve booking, so a salesperson is required for every single slot confirmation. Concurrent engagements create double-booking. Senior engineers get interrupted.

The structural failure: availability and bookings are treated as one thing. When a slot gets consumed, nothing updates the source record. The next prospect sees the same slot as open.

## The Solution

Two-table separation. The `assessment_slots` table is the capacity layer (operator-controlled). The `assessment_bookings` table is the consumption layer (prospect-facing). A booking inserts a record into `assessment_bookings` and flips the slot's status to `booked` in a single transaction. The public page only reads `available` slots. The same slot cannot be booked twice.

**Key Features:**
- Admin dashboard for operators to add, view, and manage assessment slots by service type
- Public booking page with service filter, date display, and slot selection
- Atomic status update: booking insert and slot status flip happen together, no race condition
- Booking confirmation view delivered immediately after submission
- Operator overview with today's count, upcoming count, total bookings, and pending confirmations

## Use Cases

**Offensive Security Firms (Pentest / Red Team):**
Expose Web App Pentest, API Assessment, and Red Team Engagement slots to prospects directly. No sales call required to reserve capacity. Senior engineers see confirmed bookings, not email threads.

**GRC Advisory Practices:**
SOC 2 advisory and compliance readiness sessions can be self-scheduled by client security teams. The operator controls how many slots are available per week without touching code.

**MDR Providers:**
MDR onboarding calls are high-friction to schedule. A public slot picker reduces the onboarding cycle from 3-5 email exchanges to a single form submission.

## Impact

- Eliminates manual slot coordination for assessment scheduling, typically 2-4 hours per week per operator
- Prevents double-booked engagements through atomic slot locking, a failure mode that costs firms senior engineer time and client trust
- Converts website visitors into booked prospects without a sales intermediary in the loop

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-assessment-slot-scheduler/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-assessment-slot-scheduler/image.png" />
