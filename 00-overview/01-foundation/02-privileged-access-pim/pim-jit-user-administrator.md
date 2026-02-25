# Scenario: Converting Standing Privilege to Just-in-Time (JIT) Access

## Objective

Eliminate permanent privileged access and implement Just-In-Time (JIT) elevation using Microsoft Entra Privileged Identity Management (PIM).

---

## Initial State (Risk Identified)

The **User Administrator** role was permanently assigned to a user, creating standing administrative privilege.

Risk:
- Increased attack surface
- Persistent elevated access
- No time-bound enforcement
- Higher lateral movement potential if account compromised

---

## Implementation Steps

### 1. Removed Permanent Role Assignment
- Navigated to Roles and Administrators
- Removed direct permanent assignment

### 2. Assigned Role as Eligible via PIM
- Added user as **Eligible**
- Scope: Directory
- Permanent eligibility (not permanent active)

### 3. Configured Activation Controls
- Activation maximum duration: 1 hour
- MFA required
- Justification required
- No approval required (lab scenario)

### 4. Tested Activation
- Logged in as user
- Activated role
- Provided justification
- Verified expiration timestamp

### 5. Verified Audit Logging
- Confirmed activation events in Audit Logs
- Verified RoleManagement category entries
- Confirmed successful PIM activation lifecycle

---

## Security Improvements Achieved

- Eliminated standing privilege
- Enforced Just-In-Time elevation
- Required MFA during activation
- Required justification logging
- Implemented time-bound access
- Ensured full audit traceability

---

## Screenshots

See `/assets/screenshots/` for evidence of:
- Permanent role removal
- Eligible assignment
- Activation configuration
- Activation request
- Active role with expiration
- Audit log validation
