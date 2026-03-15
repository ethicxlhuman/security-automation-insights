# Interactive Buttons and Service Carousels

Extension of Puzzle 52. Adds quick-reply buttons and a service module carousel to the AI chat agent landing page — no changes to the n8n workflow required.

## The Problem

A text-only chat interface puts all the burden on the visitor. They have to know what to ask, how to phrase it, and why it matters. Most don't. They bounce.

For a cybersecurity firm selling technical services to CISOs and security founders, that friction kills conversions before the conversation starts.

## The Solution

Two UI layers on top of the existing n8n chat backend:

**Quick-reply buttons:** Pre-built prompts the visitor can click instead of type. Each button submits a message directly to the AI agent — same as typing it manually. Lowers the barrier to engagement, guides intent, and surfaces the questions prospects actually have.

**Service carousel:** A browsable panel showing each ETXcyberops service module (MDR/SOC, GRC, Cloud Security, IAM/PAM, Offensive Security). Each card has a CTA button that fires a targeted question into the chat — turning passive browsing into an active conversation.

No changes needed to the n8n workflow. The frontend does the rendering; the agent handles the responses.

## Use Cases

- Security founders who want prospects to self-qualify before a discovery call
- MDR/SOC firms showcasing multiple service lines without a complex nav structure
- Any cybersecurity company where the sales cycle starts with "what do you actually do?"

## Tech Stack

- Lovable.dev (frontend, carousel + button components)
- n8n Chat Trigger + AI Agent (unchanged from Puzzle 52)
- Azure OpenAI (model backend)
- n8n Simple Memory (session continuity)

## Target Audience

Security founders and CTOs at mid-market cybersecurity firms who need a lead-capture layer that does more than just sit there.

## Impact

Quick-reply buttons reduce drop-off from blank-canvas friction. The carousel replaces a static services page with an interactive demo. Together they turn a single-page site into a guided product tour backed by a live AI agent.

---

Built by Kunsh Tanwar | Founder of ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_lovable.dev.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/interactive-buttons-and-service-carousels/brave_screenshot_lovable.dev.png" />
