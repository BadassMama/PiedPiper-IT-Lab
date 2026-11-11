# Ticket #006 — Employee Offboarding & Access Revocation

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management / Employee Lifecycle Management  
**Priority:** High  
**Status:** Resolved  
**Platform:** Microsoft Entra ID / Microsoft 365

## Issue Description

Human Resources notified the IT department that a fictional employee, Richard Hendricks, was leaving Pied Piper IT.

The IT department was tasked with disabling the employee's organizational account, revoking existing authentication sessions, and removing departmental security group membership.

The account needed to remain in Microsoft Entra ID for administrative recordkeeping and future lab exercises.

The primary security objective was to prevent continued unauthorized access while preserving the employee's identity record.

This exercise represents the **Leaver** stage of the Joiner-Mover-Leaver (JML) identity lifecycle.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Entra Admin Center
- Microsoft Entra security groups
- Microsoft Entra sign-in controls
- Unlicensed fictional employee account

## Initial Account Configuration

| Property | Value |
|---|---|
| Employee | Richard Hendricks |
| Department | Product Management |
| Security Group | SG-ProductManagement |
| Account Status | Enabled |
| Administrative Role | Standard user |
| Product License | Unassigned |

## Administrative Procedure

### Step 1 — Disable Employee Sign-In

1. Signed in to the Microsoft Entra admin center at https://entra.microsoft.com using the administrator account.
2. Navigated to **Entra ID → Users → All users**.
3. Selected Richard Hendricks.
4. Located the employee's account status settings.
5. Changed **Account enabled** from Yes to No.
6. Saved the configuration.
7. Verified that the account was disabled.

**Purpose:** Prevent the employee from initiating new authenticated sessions after the account status change takes effect.

### Step 2 — Revoke Existing Authentication Sessions

1. Opened the employee's profile in Microsoft Entra ID.
2. Located the **Revoke sessions** administrative action.
3. Initiated session revocation.
4. Confirmed the operation.

**Purpose:** Invalidate applicable refresh tokens and browser authentication sessions to reduce the risk of continued access after employee separation.

**Important:** Session revocation does not necessarily invalidate every existing application access token immediately. Access may persist temporarily until token expiration or application-specific enforcement occurs.

### Step 3 — Remove Departmental Group Membership

1. Navigated to **Entra ID → Groups → All groups**.
2. Selected `SG-ProductManagement`.
3. Opened the group's **Members** section.
4. Located Richard Hendricks.
5. Removed the employee from the security group.
6. Verified that the employee was no longer listed as a member.

**Purpose:** Remove obsolete departmental group membership and prevent the account from retaining group-based access if it is reactivated later.

### Step 4 — Verify Account Deactivation

1. Returned to **Entra ID → Users → All users**.
2. Selected Richard Hendricks.
3. Confirmed that the account remained in the directory.
4. Verified that the account was disabled.
5. Attempted a new sign-in using the fictional employee account.
6. Confirmed that the sign-in was blocked.

## Final Account Configuration

| Property | Final State |
|---|---|
| Employee | Richard Hendricks |
| Account Status | Disabled |
| Authentication Sessions | Revocation initiated |
| SG-ProductManagement Membership | Removed |
| Account Deleted | No |
| New Sign-In Attempt | Blocked |
| Product License | Unassigned |

## Resolution

The employee account was successfully disabled in Microsoft Entra ID.

Existing
