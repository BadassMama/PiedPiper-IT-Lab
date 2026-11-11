# Ticket #001 — New Employee Onboarding

**Organization:** Pied Piper IT  
**Category:** User Account Management  
**Priority:** Medium  
**Status:** Resolved  
**Platform:** Microsoft 365 Admin Center / Microsoft Entra ID

## Issue Description

A new employee, Richard Hendricks, requires an organizational account to access company resources.

The account must follow standard identity management practices and should not receive unnecessary administrative permissions.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Cloud-managed user accounts
- Limited license availability

## Troubleshooting and Resolution Steps

1. Signed in to the Microsoft 365 Admin Center using an administrator account.
2. Navigated to **Users → Active users → Add a user**.
3. Created a new employee identity using the fictional employee's information.
4. Configured an initial password and required a password change at first sign-in.
5. Created the user without a Microsoft 365 product license due to limited trial license availability.
6. Retained standard user permissions without assigning administrative roles.
7. Verified that the new employee appeared in the active users directory.

## Resolution

The employee account was successfully provisioned in Microsoft Entra ID without a product license.

The account was available for subsequent authentication and identity management exercises.

**Ticket Status:** Resolved

## Skills Demonstrated

- Microsoft 365 user provisioning
- Microsoft Entra ID administration
- Identity lifecycle management
- Account configuration
- Least-privilege access
- License management awareness

## Lessons Learned

Microsoft Entra ID user accounts can be created without Microsoft 365 product licenses.

User account provisioning, product licensing, and administrative role assignment are separate administrative activities.

Creating accounts with only the permissions required for their responsibilities helps reduce unnecessary security exposure.

## Security Considerations

- Do not assign administrative roles without a business requirement.
- Protect temporary passwords and account recovery information.
- Require secure authentication for organizational accounts.
- Avoid publishing real tenant identifiers or credentials in public project documentation.
