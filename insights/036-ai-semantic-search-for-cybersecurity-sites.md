# AI Semantic Search for Cybersecurity Sites

Prototype: https://ai-website-cybersecurity-company.vercel.app/

## The Problem

Keyword search fails security buyers. A CISO typing "cloud misconfiguration risk" 
gets zero results if your page says "CSPM posture drift." Same intent, different words.

## The Solution

- Convert all site content into vector embeddings via OpenAI
- Store vectors in Supabase using pgvector extension
- On search: embed the query → find nearest vectors via cosine similarity
- Return results ranked by semantic relevance, not keyword match

## Use Cases

- "Broken API" → surfaces webhook, integration, GraphQL docs
- "Compliance audit" → finds SOC 2, ISO 27001, HIPAA pages
- "Who monitors my cloud?" → returns CSPM and MDR service pages

## Tech Stack

- OpenAI Embeddings API (`text-embedding-3-small`)
- Supabase + pgvector extension
- n8n (optional: automate re-indexing on content updates)

## Target Audience

Security founders running content-heavy sites with 10+ service/blog pages

## Impact

Prospects find the exact service they need in one query. Reduces bounce rate 
from navigation confusion - especially critical when pitching GRC or MDR services 
to time-poor CISOs.

Built by Kunsh Tanwar - ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_ai-website-cybersecurity-company.vercel.app.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/ai-semantic-search-for-cybersecurity-sites/brave_screenshot_ai-website-cybersecurity-company.vercel.app.png" />
[▶ Watch: Screen Recording 2026-03-06 002136.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/ai-semantic-search-for-cybersecurity-sites/Screen%20Recording%202026-03-06%20002136.mp4)
