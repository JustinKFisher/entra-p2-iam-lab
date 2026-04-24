# 🏈 SC-300 Lab: Entitlement Management & Access Packages
## Microsoft Entra ID — Identity Governance

---

## Overview

This lab demonstrates **Entitlement Management** in Microsoft Entra ID using Access Packages — a core Identity Governance feature tested on the SC-300 exam.

The lab uses an NFL-themed simulation to model a real-world Zero Trust governance scenario:

> A **Defense group user (LB1)** requests temporary access to **Offense group resources** during game prep week. The request requires business justification, goes through an approval workflow, expires automatically after 7 days, and is subject to weekly access reviews.

This mirrors real enterprise IAM scenarios where cross-team or cross-department access must be governed, time-limited, and auditable.

---

## Zero Trust Principles Demonstrated

| Principle | Implementation |
|---|---|
| **Least Privilege** | Defense users only get Offense access when explicitly requested and approved |
| **Time-bound access** | Assignment expires automatically after 7 days |
| **Verify explicitly** | Requestor must provide business justification |
| **Assume breach** | Access reviews ensure continued access is validated weekly |
| **Audit trail** | Every request, approval, and assignment is logged |

---

## Lab Architecture

JFLabs Entra Tenant
│
├── Catalog: "Lab Test Catalog"
│     └── Resource: Offense Group (Security Group)
│
├── Access Package: "Lab Test Package"
│     ├── Resource Role: Offense Group → Member
│     ├── Requestor scope: Defense group users only
│     ├── Policy: Approval required (Justin Fisher — approver)
│     ├── Requestor justification: Required
│     ├── Expiration: 7 days
│     └── Access reviews: Weekly (Justin Fisher — reviewer)
│
└── Users
├── Approver/Reviewer: Justin Fisher (Admin)
└── Requestor: LB1 (Defense group user)




---

## Lab Steps

### Step 1 — Create a Catalog
Created "Lab Test Catalog" as the container for lab resources and access packages.

📸 `em_01-Catalogs.Empty.png` — Empty catalogs blade before creation
📸 `em_02-CreatedCatalog.png` — New catalog form filled out
📸 `em_03-CatalogCreatedSuccessfully.png` — Catalog confirmed in list

---

### Step 2 — Add Resource to Catalog
Added the **Offense** security group as a resource inside the catalog.

📸 `em_04-CatalogResourcesEmpty.png` — Empty resources tab
📸 `em_05-AddingGrouptoCatalog.png` — Offense group selected
📸 `em_06-resource-confirmed.png` — Offense group confirmed as catalog resource

---

### Step 3 — Create Access Package
Created "Lab Test Package" linked to Lab Test Catalog with Offense group assigned as Member role.

📸 `em_07-NewAccesPackage.png` — Access package basics configured
📸 `em_08-AccessPackageResource.png` — Offense group added as Member role

---

### Step 4 — Configure Request Policy
- Requestor scope: **Defense group users only**
- Who can request: **Self + Admin**
- Require approval: **Yes**
- Approver: **Justin Fisher**
- Decision deadline: **14 days**
- Require requestor justification: **Yes**
- Require approver justification: **Yes**

📸 `em_09-PolicyRequester-scope.png` — Defense group scoped as requestors
📸 `em_10-policy-approval-settings.png` — Approval settings configured

---

### Step 5 — Configure Requestor Information
Added a required business justification question:
> *"Why do you need access to the Offense group? Please provide business justification."*

📸 `em_11-Requester-question.png` — Required justification question configured

---

### Step 6 — Configure Lifecycle & Access Reviews
- Expiration: **7 days** — models game prep week access window
- Access reviews: **Weekly**
- Reviewer: **Justin Fisher**
- Require reviewer justification: **Yes**

📸 `em_12-Lifecycle-expiration.png` — 7-day expiration + weekly access reviews

---

### Step 7 — Review & Create
Reviewed full configuration summary before creating the package.

📸 `em_13-review-create-page1.png` — Summary page 1
📸 `em_14-review-create-page2.png` — Summary page 2

---

### Step 8 — Package Created
Access package confirmed live with 1 enabled policy and Offense group resource.

📸 `em_16-package-created-overview.png` — Package overview confirmed

---

### Step 9 — End User Experience (LB1 — Defense user)
Logged in as LB1 via the My Access portal. Located "Lab Test Package" and submitted a request with full business justification.

**LB1's provided justification:**
> *"Preparing defensive scheme for this week's game — need to review Offense formations and play calls."*

**Business justification:**
> *"Game prep week — defensive group requires access to Offense playbook to prepare defensive assignments."*

📸 `em_15-myaccess-portal-defense-user.png` — LB1 viewing available access packages
📸 `em_17-request-panel-justification.png` — Justification submitted by LB1

---

### Step 10 — Admin Approval Workflow
Reviewed LB1's pending request in the admin center and My Access portal. Approved with justification.

**Approver reason:**
> *"Approved for game prep week — temporary access granted."*

📸 `em_18-pending-request-admin.png` — LB1 request pending in admin center
📸 `em_19-request-details-admin.png` — Full audit trail
📸 `em_20-admin-pending-approval.png` — Admin My Access overview showing 1 pending action
📸 `em_21-approvals-queue.png` — Approvals queue showing LB1 request
📸 `em_22-approval-action.png` — Approval decision with reason submitted
📸 `em_23-request-approved.png` — Request confirmed as Approved

---

### Step 11 — Verify Group Membership
Confirmed LB1 now appears as a member of the Offense group.

📸 `em_24-lb1-offense-group-confirmed.png` — LB1 confirmed in Offense group members list

---

## Key Concepts Demonstrated

| Concept | What Was Shown |
|---|---|
| **Catalog** | Logical container scoping resources and access packages |
| **Access Package** | Bundled resource role with governed request/approval workflow |
| **Requestor scoping** | Only Defense group users can request this package |
| **Approval workflow** | Single-stage approval with specific approver and justification |
| **Time-bound access** | 7-day expiration enforcing least-privilege lifecycle |
| **Access reviews** | Weekly review by admin to validate continued access need |
| **Audit trail** | Full request, justification, approval, and assignment history logged |
| **My Access portal** | Self-service end-user interface at myaccess.microsoft.com |

---

## SC-300 Exam Relevance

Covers **Plan and Automate Identity Governance (25-30%)** section:
- Plan and implement entitlement management
- Create and manage catalogs
- Create and manage access packages
- Configure approval, expiration, and access review policies
- Implement self-service access request workflows

> **Key exam distinction:** Entitlement management access packages are for existing users needing self-service access to resources. User Flows in Microsoft Entra External ID handle new external identity creation. If a user already exists and needs governed self-service access — the answer is always **entitlement management**.

---

## References
- [Entitlement Management Overview — Microsoft Learn](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-overview)
- [Create an access package — Microsoft Learn](https://learn.microsoft.com/en-us/entra/id-governance/entitlement-management-access-package-create)
- [My Access portal — Microsoft Learn](https://learn.microsoft.com/en-us/entra/id-governance/my-access-portal-overview)

