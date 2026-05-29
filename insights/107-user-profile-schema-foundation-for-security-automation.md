# User Profile Schema Foundation for Security Automation

A PostgreSQL-backed profiles table designed as the identity data layer for SOC analyst management, access control enforcement, and audit trail generation in security automation platforms.

## The Problem

Most cybersecurity automation tools fail at the data layer before a single workflow runs. Profiles tables get designed like generic SaaS apps: name, email, created_at. No role hierarchy. No clearance level. No MFA status. No alert quota.

The result is access control logic hardcoded into application code, RBAC that drifts every time a new analyst joins, and zero audit trail when a privilege escalation happens in production. 74% of breaches involve credential or identity abuse. The schema is where that defense starts or collapses.

## The Solution

A structured profiles table built with security operations in mind from day one. Role, clearance level, MFA enforcement flag, and client assignment quota live at the schema level, not scattered across app configs.

Accessed and inspected through Adminer for rapid visual validation of structure and data integrity before any automation layer is built on top.

**Key Features:**
- Role field enforces operator classification at the data layer (SOC Analyst, MDR Lead, GRC Manager, Pentest Lead)
- Clearance level column supports tiered access models (L1, L2, L3) without custom join tables
- MFA enforcement flag stored per profile so authentication policy is auditable in the database, not inferred from app state
- Alert quota and assigned clients as integers enable workload-aware routing logic in automation workflows
- UUID default on id prevents enumeration attacks common in sequential integer PKs

## Use Cases

**IAM/PAM > Zero Trust Identity:**
Identity architects use the role and clearance_level columns as the source of truth for policy engine rules. When zero trust posture checks run, they query this table, not app session state.

**MDR/SOC > SOC-as-a-Service:**
MSSP operators seed this table per deployment to enforce per-analyst alert quotas and client assignments. Automation workflows route incoming alerts based on assigned_clients, preventing cross-client data leakage in multi-tenant SOC environments.

**GRC > SOC 2 Compliance:**
The is_admin and mfa_enabled columns feed directly into SOC 2 CC6.1 (logical access) evidence collection. Automated evidence runs query this table to prove MFA enforcement and privilege separation to auditors.

## Impact

- Eliminates RBAC drift caused by access logic scattered across application code
- Provides a single queryable source for SOC 2 CC6.x access control evidence
- Prevents cross-client data exposure in multi-tenant MDR deployments via schema-enforced workload separation
- UUID primary keys block analyst profile enumeration in externally accessible API surfaces

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
