# Contact Form Lead Alert Pipeline

Real-time notification system that captures inbound leads from a cybersecurity landing page, stores them in Supabase, and delivers an instant Telegram alert via n8n webhook.

## Problem

Security founders miss inbound leads because contact forms dump data into an inbox nobody monitors. By the time you respond, the prospect has moved on.

## Solution

Form submission triggers a three-step pipeline:

1. Frontend POSTs structured lead data to an n8n webhook
2. n8n stores the record in Supabase with a timestamp
3. n8n sends a formatted Telegram alert with full lead details

Response time drops from hours to seconds. Every lead has a persistent database record.

## Use Cases

- MDR/SOC firms capturing threat assessment requests
- GRC consultancies tracking compliance inquiry volume
- Any security founder running a lean GTM operation without a CRM team

## Tech Stack

- Bolt.new (frontend form with POST request)
- n8n (webhook receiver, Supabase insert, Telegram message node)
- Supabase (lead storage with pgvector-ready schema)
- Telegram Bot API (instant founder alert)

## Impact

Zero missed leads. Full audit trail. Founder notified before the prospect closes the tab.

---

Built by Kunsh Tanwar | kunsh@etxhuman.com

<img width="800" alt="01KKVXVBW35D25WSYEVT0EP8M6.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/contact-form-lead-alert-pipeline/01KKVXVBW35D25WSYEVT0EP8M6.png" />
<img width="800" alt="brave_screenshot_bolt.new (1).png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/contact-form-lead-alert-pipeline/brave_screenshot_bolt.new%20(1).png" />
<img width="800" alt="brave_screenshot_supabase.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/contact-form-lead-alert-pipeline/brave_screenshot_supabase.com.png" />
<img width="800" alt="brave_screenshot_web.telegram.org.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/contact-form-lead-alert-pipeline/brave_screenshot_web.telegram.org.png" />
