# Discovery call scarcity engine

Persistent countdown timer + live availability tracker for cybersecurity company offer pages.
Built to convert warm website visitors into booked discovery calls — without manual updates or dev overhead.

---

## The Problem

Security firms spend weeks generating qualified leads through content, cold outreach, and demos.
Then prospects land on the website and bounce — no urgency, no scarcity, no reason to act now.

Manual workarounds are broken:
- Updating "X spots left" copy by hand → always stale or forgotten
- Countdown timers that reset on refresh → destroys credibility instantly
- No offer mechanics at all → warm leads go cold overnight

**Result:** Pipeline leaks at the final conversion step.

---

## The Solution

A lightweight, self-contained scarcity engine that:

- **Countdown timer** — anchored to a fixed end timestamp, survives refreshes
- **Live slot counter** — decrements dynamically, persists in localStorage
- **Zero-reset architecture** — derived from stored start state, not session memory
- **Drop-in ready** — no backend, no dependencies, pure HTML/CSS/JS

---

## How It Works

```js
// On load: check localStorage for existing session
const startTime = localStorage.getItem('offer_start') || Date.now();
const slotsLeft = localStorage.getItem('slots_left') || 7;

// Derive remaining time from anchored start — not from when page opened
const elapsed = Date.now() - startTime;
const remaining = OFFER_DURATION_MS - elapsed;
```

Timer loop updates the UI every second. Slots decrement on CTA click and persist immediately.

---

## Use Cases for Security Firms

| Scenario | Implementation |
|---|---|
| Limited discovery call slots (MDR/GRC firms) | Set slots to 5–10, reset monthly |
| Time-boxed assessment offer | 72-hour countdown, anchored to campaign launch |
| Early-access beta for new automation tooling | Combine countdown + waitlist form |
| Pentest retainer availability | Real scarcity, not manufactured — just displayed clearly |

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com