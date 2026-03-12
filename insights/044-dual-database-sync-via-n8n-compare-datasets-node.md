# Dual Database Sync via n8n Compare Datasets Node

Automates synchronization between a Primary and Secondary database using n8n's
Compare Datasets node. Only creates, updates, or deletes rows where data has
actually changed, preventing duplicate writes and stale records.

## The Problem

Security operations teams manage data across multiple systems:
- Asset inventories drift between your CMDB and your SIEM
- Alert records in your ticketing system go stale when source data updates
- Manual reconciliation between client databases takes hours per week
- Duplicate or outdated records cause missed detections and false positives

## The Solution

An n8n workflow that runs on a schedule (or trigger), pulls records from both
databases, compares them field by field, then only acts on what changed.

## Workflow Logic

1. Fetch all records from Primary DB (source of truth)
2. Fetch all records from Secondary DB (sync target)
3. Compare Datasets node identifies: new rows, updated rows, deleted rows
4. Create/Replace rows in Secondary DB for new or changed records
5. Delete rows in Secondary DB that no longer exist in Primary

## Security Use Cases

- Sync asset inventory between your CMDB and vulnerability scanner
- Keep client contact records consistent across CRM and ticketing system
- Mirror alert data from primary SIEM into a reporting database
- Replicate user access records from IAM into a compliance audit table

## Stack

- n8n (self-hosted)
- Supabase (Primary + Secondary DB via REST API nodes)
- Compare Datasets node (built-in n8n)

Built by Kunsh Tanwar | Contact: kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_etxn8n.etxhuman.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/dual-database-sync-via-n8n-compare-datasets-node/brave_screenshot_etxn8n.etxhuman.com.png" />
<img width="800" alt="brave_screenshot_supabase.com (1).png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/dual-database-sync-via-n8n-compare-datasets-node/brave_screenshot_supabase.com%20(1).png" />
<img width="800" alt="brave_screenshot_supabase.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/dual-database-sync-via-n8n-compare-datasets-node/brave_screenshot_supabase.com.png" />
<img width="800" alt="Screenshot 2026-03-12 195001.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/dual-database-sync-via-n8n-compare-datasets-node/Screenshot%202026-03-12%20195001.png" />
