# Just-In-Time (JIT) Role Implementation – User Administrator

## Objective
Transition the **User Administrator** role from permanent assignment to Just-In-Time (JIT) access using Microsoft Entra Privileged Identity Management (PIM).

---

## 1. Initial State – Permanent Role Assignment

User had a permanent assignment to the User Administrator role.

![Permanent Role Assignment](../../assets/screenshots/pim_01_before_permanent_role.png)

---

## 2. Remove Permanent Assignment

Permanent role assignment was removed to eliminate standing privilege.

![Permanent Role Removed](../../assets/screenshots/pim_02_permanent_removed.png)

---

## 3. Assign Role as Eligible via PIM

User was assigned as **Eligible** for the User Administrator role.

![Eligible Assignment](../../assets/screenshots/pim_03_eligible_assignment.png)

---

## 4. Configure PIM Activation Settings

Activation requirements configured:
- Azure MFA required
- Justification required
- Maximum activation duration: 1 hour
- No approval required (lab environment)

![Activation Settings](../../assets/screenshots/pim_04_activation_settings.png)

---

## 5. User Requests Activation (JIT)

User initiated role activation with justification.

![Activation Request](../../assets/screenshots/pim_05_user_activation_request.png)

---

## 6. Role Activated (Temporary Access)

Role successfully activated for limited duration.

![Role Active](../../assets/screenshots/pim_05b_role_active.png)

---

## 7. Audit Log Verification

Audit logs confirm:
- Role activation request
- Activation completion
- Removal of permanent assignment
- All actions recorded successfully

![Audit Log Event](../../assets/screenshots/pim_06_audit_log_event.png)

---

## Security Outcome

- Eliminated standing privileged access
- Enforced MFA during elevation
- Required justification for accountability
- Enabled audit trail visibility
- Reduced risk exposure window

---

## Key IAM Concepts Demonstrated

- Least Privilege
- Just-In-Time (JIT) Access
- Privileged Identity Management (PIM)
- Audit Logging & Monitoring
- Privileged Role Governance
