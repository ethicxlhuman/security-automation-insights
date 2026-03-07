# Automated Lead Personalization Pipeline

## The Problem

Cybersecurity firms doing outbound sales face a brutal tradeoff: personalized cold emails convert 3–5x better than generic ones, but manual research per prospect takes 15–20 minutes each. At scale, that's not a sales process : it's a full-time job.

**Result:** Teams either send generic emails that get ignored, or burn hours researching leads they'll never close.

## The Solution

An n8n workflow that turns a raw lead list into outreach-ready, personalized emails automatically:

- **Email verification** via NeverBounce: no bounces, no deliverability damage
- **Company research** via Perplexity API: pulls real context on what the prospect's firm actually does
- **Dual icebreaker generation**: produces two personalized openers per lead (company insight + pain-point hook), so you A/B test without extra work
- **Direct push to Instantly**: leads land in your outreach sequence with personalization pre-loaded

## Use Cases

- MDR/SOC firms prospecting other security companies for partnerships
- GRC consultancies reaching out to compliance-heavy verticals
- Security founders doing founder-led outbound at scale
- Any cybersecurity team replacing manual research with automated context

## Tech Stack

- **n8n** : workflow orchestration
- **NeverBounce** : email verification
- **Perplexity API** : live company research
- **OpenAI / Azure OpenAI** : icebreaker generation
- **Google Sheets** : lead input + personalization output
- **Instantly** : outreach delivery

## Target Audience

Founders and sales leads at mid-market cybersecurity firms ($1M–$50M revenue) who are doing outbound but losing time to manual research and generic messaging.

## Impact

- Cuts per-lead research time from ~15 minutes to under 60 seconds
- Two icebreaker variants per lead enable built-in A/B testing
- Clean email list before sending protects sender reputation
- Personalization at scale without hiring SDRs

## Contact

Built by Kunsh Tanwar | Founder, ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_docs.google.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/automated-lead-personalization-pipeline/brave_screenshot_docs.google.com.png" />
<img width="800" alt="brave_screenshot_etxn8n.etxhuman.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/automated-lead-personalization-pipeline/brave_screenshot_etxn8n.etxhuman.com.png" />
