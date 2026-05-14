# AI Security Incident Routing Pipeline

Modern SOC environments generate incidents with different risk levels.
Without automated routing, analysts manually separate low priority alerts from critical escalations, slowing response operations and increasing alert fatigue.

This n8n workflow automatically classifies security incidents into Low, Medium, and High severity buckets, formats each branch independently, merges all escalation streams, and generates one operational report.

## Problem

Security operations teams often struggle with:
- inconsistent incident prioritization
- manual triage workflows
- fragmented escalation reporting
- noisy low priority alerts mixed with critical incidents
- inefficient analyst handoffs

Without structured routing:
- SOC teams lose visibility into critical threats
- escalation workflows become delayed
- executive summaries require manual formatting
- AI automation pipelines receive inconsistent severity metadata

## Solution

An n8n workflow that:
- Ingests security incident records
- Calculates incident severity using risk scores
- Routes incidents into Low, Medium, and High severity branches
- Formats each branch independently
- Merges all escalation streams back together
- Sends a unified SOC report through Telegram

## Workflow Pipeline

Trigger → Incident Input → Severity Classification → Switch Routing → Branch Formatting → Merge → SOC Report → Telegram Alert

## Severity Buckets

### Low Severity
Risk score under 250

### Medium Severity
Risk score between 250 and 999

### High Severity
Risk score 1000 and above

## Example Output

```text
Security Incident Report

Low Severity Incidents:
- INC-9001 | Luna SOC | £120
- INC-9004 | UrbanSec Labs | £80

Medium Severity Incidents:
- INC-9002 | Northline Systems | £450
- INC-9005 | GreenFix CyberOps | £700

High Severity Incidents:
- INC-9003 | Prime Dental Secure | £1,250
- INC-9006 | Vertex Legal AI | £2,200
```

## Use Cases

- SOC incident routing
- AI assisted alert triage
- MDR escalation pipelines
- Threat prioritization automation
- Executive cyber reporting
- SIEM enrichment workflows

## Impact

Reduces manual SOC triage effort.
Improves escalation visibility.
Standardizes incident severity reporting.
Accelerates AI driven cyber operations.

Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-05-14 232023.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/ai-security-incident-routing-pipeline/Screenshot%202026-05-14%20232023.png" />
