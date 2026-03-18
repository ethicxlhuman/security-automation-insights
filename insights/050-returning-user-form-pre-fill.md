# Returning User Form Pre-Fill

A client intake form that detects returning visitors and pre-fills their 
data automatically using localStorage. No backend, no auth required.

## Problem

Security firms lose repeat prospects at the intake form:
- Visitors abandon re-entry when forced to retype details
- No memory between sessions means friction on every return
- Manual follow-up can't tell if a prospect has engaged before

## Solution

On first submit, store form data (name, email, phone, service interest, 
message) to localStorage. On return visits, detect existing data and 
inject it back into fields automatically. Users can overwrite and resubmit 
to update their stored profile.

## Use Cases

- MDR/SOC firms collecting repeat assessment requests
- GRC consultants with multi-step onboarding forms
- Offensive security teams booking pentest scopes across sessions

## Impact

- Zero backend dependency for session memory
- Reduces form abandonment on repeat visits
- Works as a drop-in upgrade to any existing intake page

Built by Kunsh Tanwar | kunsh@etxhuman.com

[▶ Watch: Recording 2026-03-18 200801.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/returning-user-form-pre-fill/Recording%202026-03-18%20200801.mp4)
