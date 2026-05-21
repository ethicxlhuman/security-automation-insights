# SOC AI alert triage pipeline

A production-structured Python script that sends a security alert to an LLM API, parses the AI response, and handles failures. Built as the foundational pattern for AI-assisted SOC triage workflows.

## Problem

SOC analysts manually query AI tools mid-investigation: open browser, paste alert details, copy response, switch context. This breaks flow, introduces delay, and does not scale across multi-client MDR environments.

Inline AI calls inside scripts eliminate the context switch and make enrichment composable into larger pipelines.

## Solution

A single Python script implementing a clean triage pipeline:

1. Configuration loading via `.env`
2. Client initialization (MiniMax via OpenAI-compatible endpoint)
3. Security prompt execution
4. Response parsing
5. Error handling with labeled terminal output

## Use Cases

- Enrich a suspicious IP, hash, or domain with an inline AI severity assessment
- Summarize a SIEM alert payload before escalation
- Generate first-pass triage notes from raw log data
- Pipe output into ticket creation, Slack alerts, or pentest report builders

## Impact

- Removes manual AI lookups from analyst workflow
- Pattern reusable across MDR triage, GRC policy drafting, pentest report generation
- Composable: output feeds directly into n8n, SOAR, or any downstream automation

## Implementation Notes

- API key stored in `.env`, never hardcoded
- Prompt structured as a function to accept dynamic alert inputs
- Wraps request in try/except for auth errors, rate limits, and timeouts
- MiniMax uses OpenAI-compatible endpoint: `https://api.minimax.io/v1`

---

Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/soc-ai-alert-triage-pipeline/image.png" />
