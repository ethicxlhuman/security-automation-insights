# Frontend Auth Identity Layer for SOC Tooling

A sign-up and login system connecting a hacker-terminal frontend directly to PostgreSQL, with bcrypt-hashed credentials stored in the profiles table. Day 2 of building the identity data layer for security automation platforms.

## The Problem

Security automation tools get built on top of broken identity layers. Credentials stored in plaintext. No role enforced at registration. No schema-level separation between an L1 analyst and an admin. When a breach happens inside the tooling itself, there is nothing to audit and nothing to contain.

74% of breaches involve identity abuse. Most internal security tools ironically have weaker auth than the systems they protect.

## The Solution

A Node.js/Express backend exposes two endpoints: register and login. Passwords are bcrypt-hashed with salt rounds of 12 before touching the database. Role is captured at registration and stored directly in the profiles table from Day 1. The frontend enforces field validation before any request fires.

**Key Features:**
- bcrypt hashing at salt factor 12 means brute force on the database yields nothing usable
- Role selection at registration wires directly into the existing clearance and assignment schema
- Duplicate email check on register prevents silent overwrites of existing analyst profiles
- Login response surfaces role, clearance level, MFA status, and admin flag so downstream workflows have full identity context immediately

## Use Cases

**IAM/PAM > Zero Trust Identity:**
Identity architects use this as the registration gateway for internal SOC tooling. Every analyst account created carries role and clearance from day one, feeding directly into access policy engines without a secondary provisioning step.

**MDR/SOC > SOC-as-a-Service:**
MSSP operators register analysts per client deployment with pre-assigned roles. The profiles table already holds assigned_clients and alert_quota, so the auth layer and workload routing layer share the same record.

**GRC > SOC 2 Compliance:**
The registration flow creates an auditable identity record with timestamps. Every account has a created_at, a role, and a hashed credential. That is your CC6.1 access provisioning evidence, automated.

## Impact

- Eliminates plaintext credential storage risk in internal security tools
- Connects identity creation directly to role and workload schema from first login
- Creates an auditable registration trail that satisfies SOC 2 CC6.1 logical access controls without additional tooling

---

Built by Kunsh Tanwar | ETXcyberops | kunsh@etxhuman.com

<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
<img width="800" alt="image.png" src="https://etx-megasupabase.etxhuman.com/storage/v1/object/public/insight-attachments/insights/draft/image.png" />
