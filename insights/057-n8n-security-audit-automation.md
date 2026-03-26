# n8n Security Audit Automation

Security audit for n8n instances that identifies real infrastructure risks and delivers AI-filtered reports via Telegram.

## The Problem

Cybersecurity companies rely on n8n for critical automation:
- MDR firms: alert triage workflows
- GRC companies: compliance evidence collection
- Cloud Security: misconfiguration detection
- IAM/PAM: access provisioning automation

But **your automation infrastructure becomes attack surface**:
- Leftover credentials from testing (HIGH risk if compromised)
- Unprotected webhooks allowing unauthorized workflow triggers
- Risky nodes (Execute Command, HTTP Request) with broad permissions
- Filesystem access nodes creating data exfiltration paths

**Manual audits fail:** You check once during setup, then configuration drifts. Unused credentials accumulate. New risky nodes get added. By the time you notice, you're already exposed.

## The Solution

Automated weekly security audits with AI-powered false positive filtering:
- **Schedule trigger:** Runs every Sunday at 3 AM
- **n8n audit:** Scans database, credentials, filesystem, instance config, nodes
- **AI analysis:** Claude acts as security analyst, ignores count = 0 findings
- **Report delivery:** Telegram notification with only actionable items

**Key Features:**
- Catches unused credentials before they become liabilities
- Detects unprotected webhooks exposing workflows to internet
- Identifies risky nodes (Execute Command, SSH, FTP) for review
- Filters out noise (count = 0) to prevent alert fatigue
- Extracts clean text from AI response (handles structure changes)

## Use Cases

**For MDR/SOC Automation:**
Your n8n instance processes customer alerts. An unused credential with SIEM access = backdoor to all customer data. Weekly audits catch this before breach.

**For GRC Compliance Automation:**
You automate SOC 2 evidence collection. An unprotected webhook = anyone can trigger compliance checks and see your control status. Audit detects exposed endpoints.

**For Cloud Security Workflows:**
Your n8n runs CSPM checks across AWS/Azure. A risky Execute Command node with cloud credentials = lateral movement path. Report flags dangerous configurations.

**For Offensive Security Infrastructure:**
Red team uses n8n for attack simulation orchestration. Leftover credentials from old campaigns = OPSEC failure. Automated audit maintains clean operational security.

## Business Impact

**Time savings:** 2 hours/month manual security reviews → 5 min automated
**Risk reduction:** Unused credentials caught in days, not months
**Compliance:** Audit trail for internal automation security posture
**Scalability:** Works across dev/staging/prod n8n instances

## Report Categories

Audit covers five critical areas:
1. **Database:** Configuration security, connection risks
2. **Credentials:** Unused credentials (not in workflows, not in active workflows, not in recent workflows)
3. **Filesystem:** Nodes with file system access
4. **Instance:** Global security configuration
5. **Nodes:** Official risky nodes (Execute Command, HTTP Request, SSH, FTP), SQL injection vectors

Built by Kunsh Tanwar | ETXcyberops | Contact: kunsh@etxhuman.com

<img width="800" alt="brave_screenshot_etxn8n.etxhuman.com.png" src="https://dolpjhqzwsxbllsoqfnk.supabase.co/storage/v1/object/public/insight-attachments/insights/n8n-security-audit-automation/brave_screenshot_etxn8n.etxhuman.com.png" />
