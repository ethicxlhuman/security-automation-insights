# SOC incident intake wizard 

## The Problem

SOC teams lose 20–40 minutes per incident on unstructured intake:
- Analysts ask different follow-up questions every time
- Severity classification is inconsistent across team members  
- Incident summaries get written manually, introducing errors
- No branching logic = flat forms that collect irrelevant data

**Result:** Alert fatigue compounds because triage itself is manual work.

## The Solution

A smart branching wizard that:
- Asks only relevant follow-up questions based on prior answers
- Stores all answers in one unified state object
- Auto-classifies urgency (Critical / High / Medium / Low)
- Generates a pre-filled incident summary ready for ticket creation

## How It Works

```
Answer: "Endpoint affected"
  → Next Q: "Is the endpoint isolated?"
    → Yes → Medium priority + containment playbook
    → No  → Critical priority + immediate isolation runbook
```

## Best Fit For
- MDR providers standardizing analyst intake
- SOC-as-a-Service firms serving multiple clients
- MSSPs building consistent triage workflows

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

[▶ Watch: 2026-04-15 23-03-01.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/soc-incident-intake-wizard/2026-04-15%2023-03-01.mp4)
