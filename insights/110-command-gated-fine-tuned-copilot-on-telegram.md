# Command-Gated Fine-Tuned Copilot on Telegram

A fine-tuned AI agent that only activates on structured commands,
deployed via Telegram. Built as a copywriter copilot. Directly
applicable to SOC analyst tools, MSSP reporting bots, and GRC
documentation assistants.

## The Problem

Security teams adopting AI tools face two failure modes: open-chat
LLMs that respond to anything (including off-task or manipulated
prompts), and generic models with no knowledge of internal playbooks
or procedures.

Both kill reliability. A SOC analyst bot that answers anything is
a liability. A generic model that does not know your alert taxonomy
or client escalation logic produces outputs no one trusts.

The result: analysts stop using the tools, or worse, trust outputs
they should not.

## The Solution

A layered bot architecture: fine-tuned model first, Telegram trigger
second, command filter third, response generation last. The bot
listens on Telegram, filters all messages that do not begin with
/ask, and routes qualifying commands through a trained model
with persistent memory.

**Key Features:**
- Command gate enforces structured interaction, no freeform chat abuse
- Fine-tuned base model trained on role-specific data (190K tokens)
  produces consistent, on-pattern outputs
- Simple Memory node maintains session context across multi-turn
  analyst queries
- Code node normalizes response before delivery, no raw model
  output sent directly to users
- Drop-in replaceable for Slack or Teams with trigger node swap

## Use Cases

**Mid-Market MDR, Alert Triage Teams:**
Deploy a /triage command bot trained on your alert taxonomy and
escalation playbooks. Analysts type /ask investigate this IP with
context, receive structured triage notes, not freeform LLM output.

**MSSP Operators, Client Reporting:**
Train the model on your report templates and SLA language. Analysts
run /ask generate weekly summary for client X, output goes directly
into the client portal workflow.

**GRC Teams, Evidence Documentation:**
Fine-tune on your control framework language (SOC 2, ISO 27001).
Auditors run /ask map this log entry to CC6.1, receive a
pre-formatted evidence statement.

## Impact

- Eliminates prompt drift: fine-tuned models produce stable,
  auditable outputs vs. prompt-engineered generics
- Reduces attack surface: command gate blocks off-task usage and
  prompt injection via messaging platform
- Cuts documentation time 60-70% for repetitive structured outputs
  (reports, summaries, evidence statements)

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/command-gated-fine-tuned-copilot-on-telegram/image.png" />
