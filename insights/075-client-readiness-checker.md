# Client Readiness Checker 

An interactive pre-engagement checklist for cybersecurity firm websites.
Scores prospect readiness in real time and gates the discovery call CTA
until minimum requirements are met.

## The Problem

GRC consultancies, MDR providers, and pentest firms run discovery calls
where prospects arrive unprepared:

- No asset inventory completed
- Compliance scope undefined
- Stakeholder sign-off not confirmed
- Technical access credentials unavailable

Result: 30-45 min calls produce no actionable output. Analyst time wasted.
Pipeline velocity drops.

## The Solution

A client-side readiness checker that:
- Presents a checklist of engagement prerequisites
- Tracks completion state per item in a local array of objects
- Calculates a live readiness score (0-100%)
- Renders three states: Not Ready / Nearly Ready / Ready to Proceed
- Gates the "Book a Call" CTA until score threshold is met

## Use Cases

- GRC firms pre-qualifying clients before SOC 2 or ISO 27001 engagements
- MDR providers confirming SIEM access and log source readiness before onboarding
- Pentest firms scoping web/API assessments (scope doc, test credentials, written auth)
- MSSPs validating client environment before managed service kickoff

## Impact

- Eliminates unqualified discovery calls before they hit the calendar
- Reduces average pre-sales cycle by 1-2 touchpoints
- Surfaces scope gaps early so analysts arrive prepared

---

Built by Kunsh Tanwar | kunsh@etxhuman.com | ETXcyberops