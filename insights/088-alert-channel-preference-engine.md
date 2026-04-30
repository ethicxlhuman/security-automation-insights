# Alert Channel Preference Engine

A granular notification routing interface that lets each alert type define its own delivery channel
independently, with a master mute-all for maintenance windows and persistent state across sessions.

## The Problem

SOC and MDR teams run on alerts. But most platforms give two options: everything on, or everything off.

The result:
- Critical system alerts buried next to weekly digest emails
- Analysts toggling off notifications entirely during noise spikes
- No way to silence low-priority channels without killing high-priority ones
- Preferences reset every session, so nothing sticks

**Alert fatigue is not a volume problem. It is a routing problem.**

## The Solution

A nested preference model where each notification type carries its own channel state independently.

Key behaviors:
- Per-type toggles for email, push, and in-app delivery
- Master mute-all that overrides all channels without destroying individual settings
- State persists across sessions via localStorage
- Visual muted state so analysts always know their current config

Applied to security operations, this pattern powers:
- Different routing rules for critical vs. informational alerts
- Analyst-level preference overrides without touching SIEM config
- Maintenance window muting that restores all prior settings on unmute

## Use Cases

**MDR Alert Triage:** Route P1 critical alerts to push only. Weekly threat digests to email only.
Analysts control their own signal-to-noise ratio without admin intervention.

**SOC-as-a-Service Multi-Client:** Each client's alert stream gets its own channel preference profile.
One analyst handles 10 clients without cross-channel contamination.

**GRC Compliance Notifications:** Audit deadlines hit email. Daily evidence collection reminders
stay in-app. No compliance notification ever gets lost in push notification noise.

**IAM/PAM Access Alerts:** Just-in-time access requests route to push for immediate response.
Session recording summaries route to email for weekly review.

## Impact

- Eliminates manual alert reconfiguration during high-volume incidents
- Reduces analyst time spent triaging misrouted low-priority notifications
- Restores full alert coverage after maintenance windows automatically
- Scales preference management across multi-analyst, multi-client SOC environments

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

[▶ Watch: 2026-05-01 00-14-40.mp4](https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/alert-channel-preference-engine/2026-05-01%2000-14-40.mp4)
