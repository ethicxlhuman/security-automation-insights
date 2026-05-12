# Threat Intelligence Region Mapper

Security operations teams often collect organization metadata without geopolitical context.
This creates blind spots in regional exposure analysis, threat modeling,
and executive reporting.

This n8n workflow enriches organization records with live country intelligence,
maps entities to regions, and generates clean operational summaries.

## Problem

Threat intelligence and security datasets frequently lack:
- standardized region classification
- geographic enrichment
- normalized reporting structures
- automated aggregation logic

Without enrichment:
- regional threat visibility becomes fragmented
- executive dashboards lose context
- geopolitical reporting requires manual analysis
- AI security pipelines receive incomplete metadata

## Solution

An n8n workflow that:
- Fetches live country intelligence from REST Countries API
- Uses mock security organization datasets
- Merges datasets using country names
- Cleans and transforms region metadata
- Counts organizations by geopolitical region
- Generates structured JSON summaries

## Workflow Pipeline

Trigger → Fetch Country Intelligence → Load Security Organizations → Merge Datasets → Transform Metadata → Aggregate Regions → Generate Summary

## Use Cases

- Threat intelligence enrichment
- AI SOC metadata pipelines
- Regional exposure dashboards
- Geopolitical cyber risk reporting
- Security data normalization
- Executive cyber operations summaries

## Example Output

```json
[
  {
    "regionCount": {
      "Europe": 2,
      "Americas": 2,
      "Asia": 1
    },
    "summary": "Threat Intelligence Region Summary\n\nEurope: 2\nAmericas: 2\nAsia: 1"
  }
]
```

## Impact

Automates regional threat enrichment.
Eliminates manual geographic mapping.
Improves AI security context generation.
Provides structured outputs ready for SIEMs, SOC dashboards, and executive reporting.

Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="Screenshot 2026-05-12 223853.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/threat-intelligence-region-mapper/Screenshot%202026-05-12%20223853.png" />
