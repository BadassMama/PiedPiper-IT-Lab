# Ticket #007 — Employee Rehire & Account Reactivation

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management / Employee Lifecycle Management  
**Priority:** Medium  
**Status:** Resolved — Sign-in Log Verification Pending  
**Platform:** Microsoft Entra ID / Microsoft 365

## Issue Description

A previously offboarded employee, Richard Hendricks, was rehired by Pied Piper IT and assigned to the Engineering department.

During the earlier offboarding exercise, the employee's Microsoft Entra ID account had been disabled, authentication sessions revoked, and departmental security group membership removed.

The IT department was tasked with restoring the employee's account, resetting credentials, reviewing multi-factor authentication (MFA) methods, and reinstating appropriate departmental access.

The objective was to restore access without automatically reinstating obsolete permissions.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Entra Admin Center
- Microsoft Authenticator
- Microsoft Entra security groups
- Security Defaults enabled
- Unlicensed test employee account

## Initial Account Configuration

| Property | Initial State |
|---|---|
| Employee | Richard Hendricks |
| Account Status | Disabled |
| Department | Product Management |
| Departmental Group Membership | Removed during offboarding |
| Administrative Role | Standard user |
| Product License | Unassigned |

## Administrative Procedure

### Step 1 — Review Existing Employee Account

1. Signed in to the Microsoft Entra admin center using the IT administrator account.
2. Navigated to **Entra ID → Users → All users**.
3. Selected Richard Hendricks.
4. Confirmed that the employee's account remained in the directory.
5. Reviewed the account status, department information, administrative roles, and group memberships.

**Purpose:** Verify the account's existing configuration before restoring access.

### Step 2 — Reactivate Employee Account

1. Opened the employee's account properties.
2. Located the account status settings.
3. Changed **Account enabled** from No to Yes.
4. Saved the configuration.
5. Verified that the account was enabled.

**Purpose:** Restore the employee's ability to authenticate to the organization.

### Step 3 — Reset Employee Credentials

1. Selected the employee's account in Microsoft Entra ID.
2. Initiated an administrator password reset.
3. Generated a temporary password.
4. Required a password change at the next sign-in.
5. Used the temporary credentials during the employee authentication test.
6. Completed the password change successfully.

**Purpose:** Ensure the returning employee used newly issued credentials rather than relying on credentials from their previous employment.

### Step 4 — Review MFA Authentication Methods

1. Opened the employee's **Authentication methods** section.
2. Reviewed the registered Microsoft Authenticator configuration.
3. Confirmed that the existing authentication method remained available for the lab account.
4. Retained the existing MFA registration for continued testing.

**Purpose:** Verify the availability of the employee's authentication method before restoring regular account access.

In a production environment, the organization should verify that authentication methods remain under the returning employee's control and reset methods that are no longer trusted.

### Step 5 — Restore Departmental Access

1. Updated the employee's Department field from **Product Management** to **Engineering**.
2. Navigated to **Entra ID → Groups → All groups**.
3. Opened `SG-Engineering`.
4. Added Richard Hendricks as a member.
5. Verified that the employee belonged to the Engineering security group.
6. Did not restore the previous Product Management group membership.

**Purpose:** Restore only the departmental membership required for the employee's new position.

### Step 6 — Verify Authentication

1. Opened a separate browser session.
2. Navigated to the Microsoft account management portal.
3. Signed in using Richard's reactivated account.
4. Completed the required authentication process.
5. Confirmed successful access to the employee account.

**Result:** The employee successfully authenticated using the reactivated identity.

### Step 7 — Investigate Missing Sign-In Log Entry

After successful authentication, the administrator attempted to locate the new sign-in event in Microsoft Entra ID.

**Observed behavior:**

- Historical sign-in events for Richard Hendricks remained visible.
- The latest successful authentication did not appear in the sign-in log results examined.
- The employee was nevertheless able to authenticate successfully.

**Assessment
