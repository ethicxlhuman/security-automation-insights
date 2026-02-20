# AI Image Generation Pipeline — Vertex AI + Supabase

Automated pipeline that writes its own image prompts, generates visuals via Google Vertex AI (Imagen 3), and stores them in Supabase Storage — zero manual steps.

## The Problem
Security founders waste hours sourcing, prompting, and organizing AI-generated visuals for content. Manual creative ops don't scale.

## The Solution
n8n workflow: AI Agent writes a detailed image prompt → Vertex AI Imagen 3 generates the image → base64 decoded and stored in Supabase Storage → metadata logged to Supabase DB.

## Use Cases
- Automated social media visual generation
- Threat report cover images on schedule
- Security awareness campaign assets
- Client-facing dashboard thumbnails

## Tech Stack
- n8n (orchestration)
- OpenAI GPT-4o (prompt writing agent)
- Google Vertex AI — Imagen 3 (`imagen-3.0-generate-002`)
- Supabase Storage + Database
- GCP Service Account (JWT auth)

## Target Audience
MDR founders, SOC-as-a-Service operators, GRC consultants automating content workflows

## Impact
Eliminates 2–4 hours/week of manual visual sourcing. Fully schedulable. 100% automated prompt-to-storage pipeline.

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com
