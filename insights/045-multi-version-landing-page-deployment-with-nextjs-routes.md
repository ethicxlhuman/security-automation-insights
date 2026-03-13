# Multi-Version Landing Page Deployment with NextJS Routes

Three distinct landing page variants served from a single NextJS repository using route-based versioning (/v2, /v3). Each version uses a different design system, font stack, and hero copy while sharing the same underlying infrastructure.

## The Problem

Security founders testing positioning and messaging typically spin up separate repos or duplicate entire sites. This creates maintenance overhead, inconsistent deployments, and no clean way to share the same tooling across variants.

## The Solution

Route-based versioning in a single NextJS repo:

- `/` serves the default dark/teal variant
- `/v2` and `/v2/*` serve a white editorial variant with different fonts and hero copy
- `/v3` and `/v3/*` serve a luxury dark variant with a different accent palette
- All inner pages (Solutions, ROI Calculator, Blog, etc.) inherit their version's theme via a shared layout wrapper
- Zero duplication of inner page logic; only hero copy and theme tokens change per version

## Use Cases

- A/B testing hero messaging with security decision-makers (CISOs, SOC managers, founders)
- Testing dark vs. light vs. editorial aesthetics on the same domain without separate deploys
- Validating which positioning resonates before committing to a full redesign

## Impact

- Single deployment for 3 audience experiments
- All inner pages automatically themed via layout wrapper; no per-page changes required
- Version-aware routing keeps URLs clean and shareable for stakeholder review

Built by Kunsh Tanwar | ETXcyberops | [kunsh@etxhuman.com](mailto:kunsh@etxhuman.com)

<img width="800" alt="brave_screenshot_bolt.new (1).png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/multi-version-landing-page-deployment-with-nextjs-routes/brave_screenshot_bolt.new%20(1).png" />
<img width="800" alt="brave_screenshot_bolt.new (2).png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/multi-version-landing-page-deployment-with-nextjs-routes/brave_screenshot_bolt.new%20(2).png" />
<img width="800" alt="brave_screenshot_bolt.new.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/multi-version-landing-page-deployment-with-nextjs-routes/brave_screenshot_bolt.new.png" />
[▶ Watch: Recording 2026-03-13 194231.mp4](https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/multi-version-landing-page-deployment-with-nextjs-routes/Recording%202026-03-13%20194231.mp4)
