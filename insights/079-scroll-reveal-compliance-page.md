# Scroll Reveal Compliance Page

## Problem

Security company websites overwhelm prospects with information density.
Compliance pages list every framework simultaneously -- SOC 2, ISO 27001,
HIPAA, NIST, PCI DSS, GDPR -- forcing the visitor to self-sort relevance
at the exact moment you need their attention most.

The result: CISOs bounce before reaching the CTA that applies to them.

## Solution

A scroll-based content reveal system using Intersection Observer API that:

- Detects which section the visitor is actively viewing
- Reveals framework content progressively as they scroll
- Highlights the active section in a side navigation indicator
- Updates the CTA contextually per section (e.g., "Book SOC 2 Assessment"
  vs "Start ISO 27001 Gap Analysis")

Content is gated behind scroll position -- not all dumped at load.
The visitor is guided, not overwhelmed.

## Use Cases

**GRC firms** -- Sequence SOC 2, ISO 27001, HIPAA, NIST sections with
framework-specific CTAs. A healthcare prospect scrolling to HIPAA sees
"Assess PHI Risk" not a generic "Contact Us."

**MDR/SOC providers** -- Reveal threat detection capabilities section by
section: detection, triage, response, reporting. Each section surfaces the
metric most relevant to that stage.

**Compliance SaaS** -- Progressive feature reveals tied to buyer journey
stages: awareness, evaluation, decision. Side nav gives the buyer a sense
of progress, reducing abandonment.

## Impact

- Increases time-on-page by reducing cognitive load at entry
- Surfaces the highest-relevance CTA per prospect segment
- Side navigation doubles as a trust signal -- structured firms
  feel credible to security-conscious buyers
- Zero framework dependency -- Intersection Observer is native browser API

## Implementation Notes

Track section visibility with `IntersectionObserver`. Map visible section
IDs to component state. Drive CTA text, side nav active state, and content
animation classes from that single state value. Each section entering the
viewport triggers its reveal independently.

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

[▶ Watch: 2026-04-17 19-28-32.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/scroll-reveal-compliance-page/2026-04-17%2019-28-32.mp4)
