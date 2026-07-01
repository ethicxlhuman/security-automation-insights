# AI Code Reviewer (n8n)

## Problem
Manual code review is slow and inconsistent. Reviewers miss injection risks, unsafe async patterns, and logic bugs under time pressure, and free-text AI output is unreliable to parse into anything actionable.

## Solution
An n8n workflow that accepts raw code, sends it to a model with a forced JSON schema, parses the structured response, and renders a clean scored report covering security, performance, and readability. No manual triage of AI prose, just a consistent output format every run.

## Use Cases

**MDR/SOC-as-a-Service**
Screen client-submitted scripts and integration code for injection flaws before they touch production pipelines.

**GRC Compliance**
Generate consistent, auditable review artifacts that map directly to secure coding control evidence.

**MSSP Operators**
Run the same review workflow across every client engagement without depending on reviewer availability or skill variance.

**Offensive Security/Red Team**
Rapidly triage third-party or client code for exploitable patterns like SQL injection and hardcoded credentials during engagement scoping.

## Impact
Cuts manual review time on routine code checks, standardizes severity scoring across engagements, and produces a structured record instead of an ad hoc text summary.

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
