# Exit-Intent Lead Capture for Security Websites

Interactive exit-intent detection system that triggers targeted offers when visitors attempt to leave, built for cybersecurity company websites.

## The Problem

Cybersecurity company websites lose qualified visitors silently:
- Prospects research 5–7 vendors before deciding
- 70–80% of visitors leave without any engagement signal
- No second chance once they bounce to a competitor
- Sales team never knows a decision-maker visited

**Result:** High-intent traffic evaporates with zero pipeline impact.

## The Solution

Exit-intent detection that triggers a targeted modal when:
- **Cursor exits** the viewport toward the browser chrome (desktop)
- **Idle timeout** fires after 30 seconds of inactivity (mobile + desktop)
- **Tab blur** detected on mobile when user switches apps

Session-scoped dismissal via sessionStorage prevents repeat triggers in the same visit. One clean prompt per session, then silence.

## Use Cases

- MDR/SOC firms capturing trial requests from analysts comparing vendors
- GRC platforms offering free compliance gap assessments
- IAM/PAM vendors triggering a demo booking before bounce
- Pentest firms surfacing a free scope call offer

## Impact

- Captures intent signals from visitors who would otherwise leave silently
- One-time trigger per session: no annoyance, no repeat interruptions
- Works on mobile via idle detection fallback
- Deployable in under 30 minutes on any existing site

---
Built by Kunsh Tanwar | kunsh@etxhuman.com | ETXcyberops

[▶ Watch: 2.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/exit-intent-lead-capture-for-security-websites/2.mp4)
