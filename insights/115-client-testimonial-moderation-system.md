# Client Testimonial Moderation System

Status-gated content pipeline for security firm client reviews. Approved testimonials render on the public trust page. Pending and rejected records stay in the admin queue. The gate exists for quality control and for client information security review before quotes go live.

## The Problem

Security firms collect post-engagement feedback from clients who just had their systems broken into. Those reviews can be extraordinarily candid. A client describing how "three chained CVEs breached our Azure AD in under 4 hours" is good social proof and a confidentiality incident at the same time. Security firm testimonial pages fail in one of two ways: nothing gets published because every review needs legal sign-off, or everything gets published because there is no review process at all.

The secondary failure: marketing teams push reviews live manually via CMS. One approval email from the wrong person and an unvetted quote is visible to every prospect, competitor, and threat actor reading the firm's trust page.

## The Solution

Single `testimonials` table with a `status` field as the publish gate. The admin dashboard controls status transitions (pending, approved, rejected) without authentication overhead. The public page queries only `status = 'approved'` records. No approved means no render. Status change is instant. No CMS, no deploy pipeline, no email chain.

**Key Features:**
- Admin moderation queue showing all testimonials with current status and one-click state transitions
- Approve, reject, and mark-pending actions per record with instant Supabase update
- Status filter tabs on admin dashboard (All, Approved, Pending, Rejected) with live counts
- Public testimonials page fetching only approved records in real time
- Star rating display, service type badge, company name, and role per testimonial card
- Search across customer name, company, and review text in admin view

## Use Cases

**Offensive Security Firms:**
Pentest and red team client quotes frequently contain details that should not be public. A moderation queue gives the ops or marketing lead a checkpoint before social proof becomes a disclosure event. Rejected records stay in the database for reference without going live.

**MDR Providers:**
Client success stories take weeks to get legal approval. A pending status keeps the review captured from the post-engagement survey without forcing a binary approved/deleted decision. The queue accumulates, approvals happen in batches, the trust page stays current.

**GRC Advisory Practices:**
SOC 2 and ISO 27001 advisory clients often mention specific audit timelines, auditor names, or gap counts in their reviews. A rejection with note capability lets the team flag which quotes need client re-consent before publishing.

## Impact

- Eliminates manual CMS-based testimonial publishing, which typically requires 3-5 touchpoints per review
- Creates an audit trail of every moderation decision without a separate logging tool
- Public trust page updates in real time from database state, no redeploy required
- Confidentiality risk from unvetted client quotes goes from a process gap to a solved workflow

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com