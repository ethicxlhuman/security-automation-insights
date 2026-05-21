# AI SOC Meeting Summarizer Pipeline

Security teams run fast moving standups, incident reviews, threat briefings, and remediation meetings filled with scattered updates, ownership changes, deadlines, and operational decisions.

Without structured extraction, important actions disappear into meeting notes, Slack threads, or analyst memory.

This n8n workflow converts messy cybersecurity conversations into structured operational summaries using AI extraction.

## Problem

Security meetings often contain:

- fragmented incident updates
- mixed remediation discussions
- unclear task ownership
- buried deadlines
- undocumented operational decisions
- inconsistent reporting

Without extraction pipelines:

- SOC actions get missed
- remediation deadlines slip
- ownership becomes unclear
- executive summaries require manual effort
- AI operations lack structured memory

## Solution

An n8n workflow that:

- Accepts a messy cybersecurity transcript
- Sends the transcript to OpenAI
- Extracts discussion points
- Identifies action items
- Maps owners to tasks
- Detects deadlines
- Captures operational decisions
- Produces a structured summary
- Sends the result to Telegram

## Workflow Pipeline

Trigger → Input Transcript → AI Extraction → JSON Parsing → Structured Summary → Telegram

## Example Cybersecurity Transcript

Topics include:

- phishing investigation updates
- SIEM tuning changes
- vulnerability remediation
- ransomware containment planning
- EDR deployment blockers
- executive reporting deadlines

## Example Structured Output

```text
SOC Meeting Summary

Key Discussion Points
• Active phishing investigation expanded to 18 affected mailboxes
• EDR rollout blocked by legacy endpoint compatibility issue
• Critical VPN vulnerability patch scheduled for Thursday deployment

Decisions
• Increase phishing monitoring rules immediately
• Delay endpoint rollout until validation testing completes

Action Items

1. Expand phishing IOC hunt
Owner: James
Deadline: Tomorrow morning

2. Finalize VPN patch deployment
Owner: Maya
Deadline: Thursday 3PM

3. Validate EDR compatibility fixes
Owner: Tom
Deadline: End of day
```

## Use Cases

- SOC standup summarization
- Incident response retrospectives
- Threat intel briefings
- Vulnerability review meetings
- MDR operations summaries
- AI security knowledge extraction

## Impact

Reduces manual note taking.
Improves operational accountability.
Creates structured AI friendly security memory.
Accelerates cyber operations reporting.

Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
