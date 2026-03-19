# entra-p2-iam-lab

Enterprise Microsoft Entra ID lab demonstrating Privileged Identity Management (PIM), Conditional Access, Identity Protection, Governance, and monitoring capabilities using Microsoft Entra ID P2 features.
---
## Naming Convention Update

This lab originally used real NFL player names (e.g., Randy Moss, Larry Allen) for user accounts.

To better reflect enterprise IAM best practices, all identities were standardized to a role-based naming convention:

- QB1, WR1, OL1, etc.

This change improves:
- Scalability
- Consistency
- Role-based access modeling

---

## 🔐 Privileged Identity Management (PIM) – Just-In-Time (JIT) Implementation

Implemented a Just-In-Time (JIT) access model for the **User Administrator** role.

### Controls Implemented
- Removed permanent privileged assignment
- Converted role to Eligible assignment via PIM
- Enforced Azure MFA during activation
- Required justification for elevation
- Configured 1-hour maximum activation window
- Verified all actions via audit logs

📄 Full scenario documentation:
👉 [View JIT User Administrator Scenario](02-privileged-access-pim/jit-user-administrator-scenario.md)

---

## 🔎 Lab Structure

- **01-foundation** – Core Entra configuration
- **02-privileged-access-pim** – PIM role governance scenarios
- **03-conditional-access** – Access policy enforcement
- **04-identity-protection** – Risk-based controls
- **05-governance** – Access reviews & lifecycle management
- **06-monitoring-logs** – Audit & monitoring validation

---

## 🎯 Objective

Demonstrate real-world IAM governance controls aligned with:

- Least Privilege
- Just-In-Time Access
- Privileged Access Governance
- Audit & Monitoring
- Role-Based Access Control (RBAC)
