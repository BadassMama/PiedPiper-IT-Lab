# Ticket #008 — Helpdesk Administrator Role-Based Access Control

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management / Privileged Access  
**Priority:** Medium  
**Status:** Resolved  
**Platform:** Microsoft Entra ID / Microsoft 365

## Issue Description

Pied Piper IT required a dedicated help desk technician account with sufficient permissions to support standard users without granting unrestricted administrative access.

The objective was to implement and verify delegated administration using Microsoft Entra ID role-based access control (RBAC).

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Entra built-in administrator roles
- Unlicensed test employee accounts
- Security Defaults enabled

## Administrative Procedure

### Step 1 — Create Help Desk Account

1. Signed in to the Microsoft 365 Admin Center.
2. Created the fictional employee Jared Dunn.
3. Configured the department as IT and job title as IT Support Technician.
4. Created the account without assigning a Microsoft 365 product license.
5. Initially configured the account as a standard user.

### Step 2 — Delegate Administrative Permissions

1. Opened the Microsoft Entra admin center.
2. Navigated to **Entra ID → Roles & admins**.
3. Located the built-in **Helpdesk Administrator** role.
4. Assigned the role to Jared Dunn.
5. Verified the assignment through the user's assigned roles.

### Step 3 — Test Help Desk Permissions

Signed in as Jared Dunn and tested administrative capabilities.

| Test | Observed Result | Outcome |
|---|---|---|
| Verify Helpdesk Administrator role | Role assignment confirmed | Passed |
| Access Richard Hendricks' password reset control | Reset password action available | Passed |
| Assign Global Administrator privileges | Action blocked or unavailable | Passed |

**Testing scope:** The password reset control was inspected but an actual password reset was not performed. Administrative role restrictions were verified through the available interface controls.

## Resolution

Successfully assigned the Helpdesk Administrator role to a dedicated support account.

Permission testing confirmed that Jared could access the expected password reset function for a standard employee while Global Administrator role assignment remained restricted.

The configuration demonstrated delegated administration consistent with the principle of least privilege.

**Ticket Status:** Resolved

## Skills Demonstrated

- Microsoft Entra ID administration
- Role-based access control (RBAC)
- Delegated administrative permissions
- Built-in administrator role assignment
- Least-privilege security principles
- Permission verification and testing
- Privileged access management awareness
- IT help desk account provisioning

## Lessons Learned

### Least Privilege Reduces Administrative Risk

Help desk employees should receive permissions appropriate to their responsibilities rather than unrestricted tenant administration.

### Administrative Roles Have Different Capabilities

The Helpdesk Administrator role permits certain password resets, session management operations, and support functions.

It does not grant the same permissions as the Global Administrator role.

### Role Assignment Must Be Verified

Creating an account and assigning an administrative role are separate operations.

Testing access through the delegated account helps verify that the intended permissions are available and inappropriate privileges are restricted.

### Interface Checks Have Limitations

An available password reset button demonstrates that the administrative action is exposed to the user, but does not prove successful execution.

Likewise, an unavailable administrative control is evidence of restricted interface access rather than a comprehensive security penetration test.

## Security Considerations

- Use dedicated accounts for privileged administrative work.
- Protect administrator accounts with MFA.
- Avoid unnecessary Global Administrator assignments.
- Review privileged role assignments periodically.
- Remove administrative privileges when no longer required.
- Monitor sensitive administrative actions through audit logs.
- Follow approved identity verification procedures before password resets.

## Documentation Notes

This exercise was completed in a controlled Microsoft 365 home lab using fictional identities.

No production accounts or systems were affected.

Passwords, MFA secrets, authentication tokens, and sensitive tenant identifiers are excluded from this documentation.

## Microsoft Documentation

- [Microsoft Entra built-in roles](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference)
- [Microsoft Entra privileged roles and permissions](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/privileged-roles-permissions)
