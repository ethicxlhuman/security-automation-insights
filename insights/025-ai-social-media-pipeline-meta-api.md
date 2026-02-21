# AI Social Media Pipeline - Imagen + Meta Graph API

Automated pipeline that takes an AI-generated cybersecurity image from Supabase, writes platform-specific captions via two AI agents, and posts to Facebook and Instagram using the Meta Graph API.

## The Problem
Security founders spend hours writing captions and manually posting content across platforms. It doesn't scale.

## The Solution
n8n workflow: Fetch image from Supabase → Agent 1 writes IG caption → Agent 2 writes FB caption → Post to Instagram via container flow → Post to Facebook directly.

## Use Cases
- Automated cybersecurity brand content
- Daily social media posting without manual work
- Multi-platform content distribution from one pipeline

## Tech Stack
- n8n (orchestration)
- Supabase Storage (image source)
- OpenAI GPT-4o (caption agents)
- Meta Graph API (Facebook + Instagram)
- Vertex AI Imagen 4 (image source from puzzle #37)

## Target Audience
MDR founders, GRC consultants, security company operators running lean marketing

## Impact
Eliminates 1-2 hours daily of manual social posting. Fully automated end to end.

<img width="1161" height="708" alt="image" src="https://github.com/user-attachments/assets/0482097e-5588-4305-a497-85f886642a25" />
<img width="1493" height="275" alt="brave_screenshot_etxn8n etxhuman com" src="https://github.com/user-attachments/assets/e53d5328-afa1-4ffa-8999-c390686a2488" />

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com
