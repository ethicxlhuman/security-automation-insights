# Hero Image Swapper

Automated hero section image updates through a form submission that writes 
directly to a GitHub repo and triggers a live site redeploy on Vercel. 
No code editor, no FTP, no deployment dashboard needed.

## Problem

Security company websites go stale because non-technical team members 
can't update hero images without developer help. Every visual change 
becomes a ticket, a blocker, or a context-switch for the engineer.

## Solution

n8n workflow triggered by a form upload that:
- Accepts an image file via web form
- Commits the image to GitHub under a timestamped path
- Fetches the live HTML file from the repo
- Finds and replaces the hero image src reference
- Pushes the updated HTML back to GitHub
- Vercel auto-deploys the change within seconds

## Use Cases

- Security founders updating site visuals without dev involvement
- SOC-as-a-Service firms rotating client-facing landing page assets
- GRC consultancies refreshing trust page imagery pre-audit
- Offensive security shops updating campaign landing pages quickly

## Impact

Reduces hero image update time from 30 minutes (dev ticket) to under 
60 seconds. Zero code access required for the person making the update.

---
ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_etxn8n.etxhuman.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/hero-image-swapper/brave_screenshot_etxn8n.etxhuman.com.png" />
<img width="800" alt="brave_screenshot_vercel.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/hero-image-swapper/brave_screenshot_vercel.com.png" />
<img width="800" alt="Screenshot 2026-03-15 004343.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/hero-image-swapper/Screenshot%202026-03-15%20004343.png" />
<img width="800" alt="Screenshot 2026-03-15 004506.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/hero-image-swapper/Screenshot%202026-03-15%20004506.png" />
<img width="800" alt="Screenshot 2026-03-15 011141.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/hero-image-swapper/Screenshot%202026-03-15%20011141.png" />
