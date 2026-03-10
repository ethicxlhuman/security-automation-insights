# ETX Google Places n8n Community Node

**Package:** `n8n-nodes-etx-google-places`

Custom n8n community node that integrates the Google Places API (New) Text Search endpoint into automation workflows. Built for security and intelligence workflows that need structured location data without manual API wiring.

## The Problem

Security teams and ops workflows that need location-based intelligence - client site lookups, physical threat assessment, recon automation - have no native Google Places node in n8n. The workaround is a generic HTTP Request node with manual header configs, credential juggling, and zero reusability across workflows.

## The Solution

A packaged, installable n8n community node that:
- Accepts a Google Places API key via n8n's credential system (secure, reusable)
- Exposes a `textQuery` input for flexible search
- Supports `fieldMask` configuration to control exactly which place fields are returned
- Outputs structured place results (name, address, coordinates, rating, Maps URL) directly into the workflow

## Use Cases

- **Recon automation** - enrich targets with physical location data during OSINT workflows
- **Client intelligence** - auto-lookup vendor or client sites during onboarding pipelines
- **GRC workflows** - verify third-party physical locations against compliance records
- **MDR enrichment** - correlate IP geolocation with real-world business context

## Impact

Replaces 5-step manual HTTP Request setup with a single, reusable node. Plugs directly into existing n8n workflows - no code, no credential re-entry, no field parsing.

---

Built by Kunsh Tanwar | Founder of ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_etxn8n.etxhuman.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/etx-google-places-n8n-community-node/brave_screenshot_etxn8n.etxhuman.com.png" />
<img width="800" alt="brave_screenshot_www.npmjs.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/etx-google-places-n8n-community-node/brave_screenshot_www.npmjs.com.png" />
