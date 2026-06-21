# QR Phishing Awareness Campaign Generator

A no-auth console that turns an awareness drill into a printable QR code. Security teams create a campaign, the QR lands employees on a training page, and the human gap gets measured and closed.

## The Problem

Human error is the single biggest concern for most CISOs, and QR phishing (quishing) is the fastest-growing version of it. A poster in a break room, a fake parking notice, a sticker over a real menu QR: attackers moved the phishing link off the screen and onto a wall, where email filters cannot see it.

Running an authorized awareness drill to test for this is awkward. Teams either buy a heavy phishing-simulation platform or hand-build landing pages and QR codes per campaign. Both are slow, and neither makes it trivial to spin up a one-off poster test, measure who scanned, and route them straight into training.

## The Solution

A single-page console with no login. You enter a campaign title, an awareness message, CTA text, and a training link. The tool generates a QR code that encodes the entire campaign in the URL itself, so the public landing page renders on any device that scans it with no backend to stand up.

The scan lands on an educational page, not a credential trap. It tells the employee they engaged with a simulated phishing QR, shows them how to spot the next one, and pushes them toward a single training CTA. The QR is the bridge from offline attention to one clear online action.

**Key Features:**
- No authentication, no server: the campaign payload travels inside the QR URL, so the public page works cross-device with zero backend
- Live landing preview that updates as you type, so what you print is what the employee sees
- One-click QR download (PNG) and copy-link for posters, flyers, and badge inserts
- Educational landing by design: awareness messaging and quishing tips, never credential capture
- Saved-campaign history in the browser for quick reuse and teardown

## Use Cases

**Offensive Security, social engineering and red team drills:**
Spin up authorized quishing tests for physical-premises engagements without provisioning landing infrastructure for each campaign.

**Security Awareness and human-risk teams:**
Run recurring poster-based drills tied to training modules, then measure scan-through as a human-risk signal over time.

**GRC teams, awareness as a control:**
Produce evidence of routine phishing-awareness testing for SOC 2, ISO 27001, and HIPAA control requirements with a repeatable, documented campaign artifact.

## Impact

- Collapses campaign setup from a platform rollout to a 60-second form fill and QR download
- Removes all backend and hosting work by encoding the campaign in the QR itself, so there is nothing to patch or breach
- Turns a physical attack vector into a measurable training touchpoint that targets the 74 percent of risk that is human
- Keeps every drill ethical by default, landing scans on education rather than data capture

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
