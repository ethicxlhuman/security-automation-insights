# Voice Booking Agent for Security Firm Intake

A voice-first scheduling agent for cybersecurity firms.
Handles inbound calls, collects engagement details, and
confirms bookings — without a human scheduler.

## The Problem

Security firms miss qualified leads after hours. Prospects
land on a website, want to book a pentest scoping call or
IR retainer intake, and hit a contact form. That form goes
cold. No booking. No revenue.

Human schedulers cost $40K-70K/year and don't work 24/7.

## The Solution

A Vapi voice agent with 3 structured tools:

- bookAppointment: Captures name, date, service type,
  contact info. Creates Cal.com event + Google Calendar
  entry via n8n.
- rescheduleAppointment: Validates reference ID, updates
  event in Cal.com, syncs new time to Google Calendar.
- cancelAppointment: Confirms identity, removes event,
  triggers CRM update via n8n.

Each tool fires a structured n8n webhook. n8n handles
calendar logic and returns a clean confirmation string.
Agent reads it back to the caller verbally.

## Use Cases

- MDR/SOC: IR retainer intake and scoping call booking
- Offensive Security: Pentest kickoff and recon briefings
- GRC: Compliance review intake and audit scheduling
- Cloud Security: CSPM assessment scoping calls

## Tech Stack

- Vapi (voice agent, tool calling)
- n8n (webhook orchestration, calendar logic)
- Cal.com (availability management)
- Google Calendar (event sync)
- OpenAI GPT-4o (model)

## Target Audience

Security founders and ops managers at $1M-$50M firms
running outbound or inbound sales motions who need
intake automation without hiring SDRs.

## Impact

- 24/7 booking coverage: 0 SDR hours required
- Structured data captured on every call
- Average scheduling cycle reduced from 2 days to 4 min

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-04-04 232114.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/voice-booking-agent-for-security-firm-intake/Screenshot%202026-04-04%20232114.png" />
<img width="800" alt="Screenshot 2026-04-04 232530.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/voice-booking-agent-for-security-firm-intake/Screenshot%202026-04-04%20232530.png" />
