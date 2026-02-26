# Supabase Storage AI Agent (n8n)

An AI agent that reads files from Supabase storage buckets using S3 configuration — enabling on-demand retrieval of security playbooks, compliance evidence, and threat intel docs via natural language chat.

## The Problem

MDR and GRC teams store critical files (playbooks, SOC 2 evidence, IR runbooks) in cloud storage — but retrieval is manual. Analysts waste time locating and reading files instead of acting on them.

## The Solution

AI agent connected to Supabase storage via S3 protocol. Ask it a question → it fetches the right file → returns actionable content.

**Key Features:**
- Natural language file retrieval from Supabase buckets
- S3-compatible config (no custom Supabase SDK needed)
- Deployable as internal SOC assistant or GRC evidence fetcher
- Extensible: swap bucket for any S3-compatible store (AWS, R2, MinIO)

## Use Cases

| Role | Query | File Retrieved |
|------|-------|----------------|
| SOC Analyst | "Get IR playbook for ransomware" | `ransomware-ir.pdf` |
| GRC Lead | "Fetch SOC 2 CC6.1 evidence" | `cc6.1-access-logs.csv` |
| CISO | "List all compliance docs" | Bucket index |

## Tech Stack
- n8n (AI Agent + S3 tool)
- Supabase Storage (S3-compatible)
- OpenAI GPT-4o (reasoning)

## Target Audience
MDR firms, GRC teams, SOC-as-a-Service providers ($1M–$50M revenue)

## Impact
- Eliminates manual file hunting (~15 min/query → seconds)
- Enables AI-assisted evidence collection for audits
- Foundation for fully automated compliance workflows

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_zp1v56uxy8rdx5ypatb0ockcb9tr6a-oci3--5173--d7bdb599.local-credentialless.webcontainer-api.io.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/supabase-storage-ai-agent-n8n/brave_screenshot_zp1v56uxy8rdx5ypatb0ockcb9tr6a-oci3--5173--d7bdb599.local-credentialless.webcontainer-api.io.png" />
<img width="800" alt="brave_screenshot_zp1v56uxy8rdx5ypatb0ockcb9tr6a-oci3--5173--d7bdb599.local-credentialless.webcontainer-api.io (1).png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/supabase-storage-ai-agent-n8n/brave_screenshot_zp1v56uxy8rdx5ypatb0ockcb9tr6a-oci3--5173--d7bdb599.local-credentialless.webcontainer-api.io%20(1).png" />
<img width="800" alt="brave_screenshot_supabase.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/supabase-storage-ai-agent-n8n/brave_screenshot_supabase.com.png" />
<img width="800" alt="brave_screenshot_etxn8n.etxhuman.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/supabase-storage-ai-agent-n8n/brave_screenshot_etxn8n.etxhuman.com.png" />
