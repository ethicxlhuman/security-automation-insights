# Telegram Lead Alert Automation

Prototype: https://ai-website-cybersecurity-company.vercel.app/

Instant Telegram notifications when prospects submit inquiry forms — name, phone, and service interest delivered to your phone in seconds via n8n webhook.

## The Problem

Cybersecurity founders lose qualified leads to slow follow-up:
- Form submissions sit unread for hours (or days)
- No mobile alert means no immediate response window
- Manual inbox checks interrupt deep work
- Warm leads go cold before first contact

**Result:** You lose deals to faster-responding competitors.

## The Solution

n8n webhook workflow that fires on every form submission and sends a structured Telegram message instantly.

**How it works:**
1. Form submits a POST request to your n8n webhook URL
2. n8n parses name, phone, and service interest
3. Telegram bot sends formatted message to your channel/DM

**Key Features:**
- Sub-second notification delivery
- All lead fields included (name, phone, offer selected)
- Works across every form on the site
- Single `.env` variable to swap webhook URLs
- Zero polling, zero inbox dependency

## Target Audience

Security founders and CTOs at MDR, GRC, or consulting firms who handle their own sales pipeline and need instant lead visibility without a full CRM setup.

---
Built by Kunsh Tanwar | Founder of ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-02-25 190326.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/telegram-lead-alert-automation/Screenshot%202026-02-25%20190326.png" />
<img width="800" alt="Screenshot 2026-02-25 190535.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/telegram-lead-alert-automation/Screenshot%202026-02-25%20190535.png" />
<img width="800" alt="Screenshot 2026-02-25 190701.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/telegram-lead-alert-automation/Screenshot%202026-02-25%20190701.png" />
