# Dynamic Sticky CTA Trust Bar

A sticky CTA + trust bar component for cybersecurity company websites that updates
its call-to-action message based on which section the visitor is currently viewing,
using Intersection Observer. No frameworks required.

## The Problem

Security company websites use one static CTA across every section:
- "Book a Demo" appears on the hero, pricing page, and case studies identically
- Trust signals (ratings, testimonials, guarantees) are buried at the bottom
- High-intent visitors scrolling through pricing see the same copy as cold visitors

**Result:** Missed conversions because the CTA doesn't match visitor intent.

## The Solution

A sticky container fixed to the viewport bottom that:
- Tracks visible sections via Intersection Observer API
- Swaps CTA text dynamically: "See It In Action" on hero → "Talk To Our Team" on pricing
- Shows 3 persistent trust signals: star rating, testimonial snippet, guarantee badge
- Works on desktop and mobile without JavaScript frameworks

## Use Cases

**MDR/SOC Firms:** Swap CTA from "Get a Threat Assessment" on services → "Start Free Trial" on pricing  
**GRC Platforms:** "View Compliance Templates" on features → "Schedule Audit Review" on contact  
**IAM/PAM Vendors:** "See Access Controls" on product → "Book Architecture Review" on enterprise tier  

## Impact

- Section-aware CTAs increase click-through by matching copy to visitor intent
- Persistent trust bar keeps social proof visible without scrolling back to hero
- Eliminates the "one CTA fits all" problem on security product websites

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-04-08 125424.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/draft/Screenshot%202026-04-08%20125424.png" />
[▶ Watch: 2026-04-07 12-16-29.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/draft/2026-04-07%2012-16-29.mp4)
