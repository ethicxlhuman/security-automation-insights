# AI Image Generation Pipeline - Vertex AI + Supabase

Automated pipeline that writes its own image prompts, generates visuals via Google Vertex AI (Imagen 3), and stores them in Supabase Storage - zero manual steps.

## The Problem
Security founders waste hours sourcing, prompting, and organizing AI-generated visuals for content. Manual creative ops don't scale.

## The Solution
n8n workflow: AI Agent writes a detailed image prompt → Vertex AI Imagen 3 generates the image → base64 decoded and stored in Supabase Storage → metadata logged to Supabase DB.

## Use Cases
- Automated social media visual generation
- Threat report cover images on schedule
- Security awareness campaign assets
- Client-facing dashboard thumbnails

## Impact
Eliminates 2–4 hours/week of manual visual sourcing. Fully schedulable. 100% automated prompt-to-storage pipeline.

<img width="613" height="611" alt="image" src="https://github.com/user-attachments/assets/56d99e97-9fbe-4314-b6f0-85778f3b5af0" />
<img width="1366" height="379" alt="image" src="https://github.com/user-attachments/assets/d560f651-346a-4fc3-80f6-22d4f809f9db" />

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com
