# Security Event & Registration Manager

Seat-limited event registration pipeline for cybersecurity firm websites. Operators publish upcoming workshops, webinars, labs, and briefings with hard capacity limits. Visitors register directly on the public events page. The system enforces capacity before saving an attendee record — no overbooking, no manual seat tracking, no "is there still space?" email chain.

## The Problem

Security firms that run training events, threat intelligence briefings, and hands-on labs manage registration manually. A workshop announcement goes out on LinkedIn. Replies come in via DM. Someone keeps a spreadsheet. The spreadsheet is wrong. The room has 12 seats and 17 people confirmed.

The second failure: no public-facing event calendar means prospective clients and candidates never discover the firm is running events at all. Events are a top-of-funnel trust signal — seeing a firm run a 10-seat hands-on web app hacking lab communicates competency better than a landing page copy paragraph. If the event is not on the website, it does not build brand.

The third failure: once a hands-on lab fills, there is no mechanism to tell latecomers it is full. The registration email keeps going to the organizer. The organizer manually replies to decline. This is unbillable overhead.

## The Solution

Two tables with a foreign key relationship. `events` is the inventory layer — each row has a `capacity` field and a `registered_count` maintained by a database trigger. `event_registrations` is the demand layer — each confirmed registration increments the count. Before any registration is saved, the handler re-fetches the event to confirm `registered_count < capacity`. If the event is full, the insert is blocked and the visitor sees a clear "Event Full" state. The public page derives remaining seats from `capacity - registered_count` and updates the UI immediately after a successful registration.

**Key Features:**
- Admin dashboard with tabbed views: Overview, Events, Registrations
- Event CRUD with publish, draft, and cancel status transitions and capacity setting
- Public events page showing only published upcoming events, ordered by date
- Per-event registration form with name, email, and optional company
- Hard capacity enforcement: client-side disabled state + server-side re-check before insert
- Live remaining seat display: green when seats available, amber when under 5, red "Event Full" when full
- Trigger-maintained `registered_count` on the events table — no aggregation queries on every page load
- Admin registrations view filterable by event and status

## Use Cases

**MDR Providers:**
Quarterly threat intelligence briefings for client security teams are typically limited to 15-20 attendees per session. A seat-limited registration system removes the manual RSVP process and gives the ops team a confirmed attendee list automatically.

**Offensive Security Firms:**
Hands-on web app hacking workshops and red team labs have hard physical limits. A cohort of 10 cannot become 14 because the tools, VMs, and instructor time do not scale on the day. Capacity enforcement is not a nice-to-have — it is operational safety.

**GRC Advisory Practices:**
SOC 2 and ISO 27001 readiness webinars are a top-of-funnel content channel. A public event calendar with a one-click registration form converts casual visitors into registered prospects whose name and company are now in the database.

## The Technical Insight

Seats are inventory with an expiry date. The capacity enforcement pattern — check before insert, decrement on registration, block when full — is identical to the stock-check pattern in e-commerce. The constraint lives in the database trigger, not in the application layer. Frontend race conditions are mitigated by the server-side re-check immediately before insert.

## Impact

- Eliminates manual RSVP tracking for all event types
- Capacity enforcement runs at the database level, making overbooking structurally impossible once the trigger is in place
- Public event calendar surfaces firm activity to prospects and candidates without marketing overhead
- Registered attendee list is available instantly in the admin dashboard — no spreadsheet export required

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
