# Security Talent Pipeline Manager

Full hiring pipeline for cybersecurity firm websites. Operators publish open roles and manage candidate status across five stages: New, Reviewed, Shortlisted, Rejected, Hired. Visitors apply directly on the public careers page and upload their CV to Supabase Storage. The admin dashboard tracks every application from submission to close without a third-party ATS or email thread.

## The Problem

Cybersecurity firms operate inside the largest talent shortage in the industry's history — 4.76 million unfilled positions globally, a 19% increase year over year. Firms that manage hiring through email and LinkedIn DMs lose candidates in the handoffs. A resume arrives by email, gets forwarded, gets lost in a thread, and the candidate accepts an offer from a competitor before anyone follows up.

The structural failure is the same one as every other content lifecycle problem: there is no single source of truth for candidate status. One recruiter marks someone as "interesting," another schedules a call, and there is no record in one place. The application pipeline — which is just a state machine — is managed in people's heads instead of a database.

The second failure is the careers page itself. Security firms with no public-facing open roles list lose passive candidates who visit the site. A developer is required to add a new role. The job sits in a Notion doc for two weeks waiting for someone to push code.

## The Solution

Two tables with a foreign key relationship. `job_listings` controls which roles are public (open), hidden (draft), or historical (closed). `job_applications` holds every candidate record linked to a role, with status as the pipeline state. CV files upload directly to a Supabase Storage bucket from the public application form. The admin dashboard surfaces the full pipeline: stat cards, a stage-by-stage count strip, recent applications, and a filterable applications table.

**Key Features:**
- Admin dashboard with tabbed views: Overview, Job Listings, Applications
- Job CRUD with publish, draft, and close status transitions
- Application pipeline with five stages: New, Reviewed, Shortlisted, Rejected, Hired
- Public careers page with department filter and per-job application form with CV upload
- CV upload to Supabase Storage with file type and size validation
- Pipeline count strip on admin dashboard showing candidates at each stage
- Application table with CV link, status badge, and inline status updates
- "Don't see the right role?" fallback section on public page

## Use Cases

**MDR Providers:**
SOC Analyst and detection engineer roles are perpetually open at growing MDR firms. A managed careers page means candidates can apply at any time without a sales or ops person manually routing the inquiry. The pipeline tracks each applicant from initial screen to offer.

**Offensive Security Firms:**
Pentest and red team roles require highly specific qualifications. A published job description with requirements filters out unqualified applicants before they reach the admin queue. The Shortlisted stage gives the technical team a clear view of who passed the initial recruiter screen.

**GRC Advisory Practices:**
Contract GRC consultants are often hired on a project basis. Closing a job listing when a position fills and reopening it for the next engagement cycle takes one click in the admin dashboard instead of a GitHub pull request.

## The Security Analogy

Treat the hiring pipeline like SOC alert triage. A new application is an unreviewed alert. Reviewed is acknowledged. Shortlisted is escalated to Tier 2. Rejected is a closed false positive. Hired is a resolved true positive. The same state-machine pattern that runs SOC operations also runs a hiring pipeline — the data model is identical, only the domain changes.

## Impact

- Removes developer dependency from job posting, cutting time-to-publish from days to minutes
- Centralizes candidate tracking across all roles in a single admin view with no external ATS cost
- CV upload to Supabase Storage eliminates email attachment management
- Five-stage pipeline creates a shared state across everyone involved in hiring

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/security-talent-pipeline-manager/image.png" />
