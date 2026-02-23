# Mega Dropdown Navigation

Prototype: [your-bolt-link]

Pure Tailwind CSS mega dropdown for cybersecurity company websites — 
no JavaScript required. Keeps dropdown active when cursor moves into it 
using group-hover utilities, organized in 2-3 columns for service 
categorization.

## The Problem

Security company websites bury their services:
- Flat navbars hide service depth
- Hover dropdowns close before users reach them
- Single-column dropdowns feel cheap for B2B buyers
- JS-dependent menus break on some enterprise browsers

**Result:** Prospects can't find your MDR vs. GRC vs. pentesting offerings 
fast enough — and leave.

## The Solution

Mega dropdown with persistent hover using Tailwind group-hover:

**Key Features:**
- Stays open when cursor moves into dropdown (no accidental closes)
- 2-3 column layout: Browse by Type + Featured/Highlighted services
- Pure CSS — no JavaScript, no dependencies
- Mobile-friendly with fallback patterns
- B2B-appropriate visual weight and spacing

## Core Pattern
```html
<div class="group relative">
  <button>Services</button>
  <div class="hidden group-hover:block absolute ...">
    <!-- 2-3 column grid content -->
  </div>
</div>
```

## Use Cases
- MDR firm: Columns for Threat Detection / Response / Reporting
- GRC firm: Columns for SOC2 / ISO27001 / HIPAA
- Full-service: Columns by segment with featured case study

## Tech Stack
- Tailwind CSS (group-hover utility)
- HTML5
- Zero JavaScript

Built by Kunsh Tanwar | Founder of ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_ai-website-cybersecurity-company.vercel.app.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/draft/brave_screenshot_ai-website-cybersecurity-company.vercel.app.png" />
[▶ Watch: Recording 2026-02-23 231342.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/draft/Recording%202026-02-23%20231342.mp4)
