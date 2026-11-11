# Ticket #002 — Password Reset & MFA Enrollment

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management  
**Priority:** Medium  
**Status:** Resolved  
**Platform:** Microsoft 365 Admin Center / Microsoft Entra ID

## Issue Description

A simulated employee, Richard Hendricks, reported being unable to access his organizational account because he had forgotten his password.

The help desk was tasked with resetting the employee's credentials, enforcing a password change, and assisting with multi-factor authentication (MFA) enrollment.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Authenticator
- Unlicensed test employee account
- Microsoft Entra Security Defaults enabled

## Troubleshooting and Resolution Steps

1. Simulated employee identity verification before initiating account recovery.
2. Signed in to the Microsoft 365 Admin Center using the administrator account.
3. Navigated to **Users → Active users**.
4. Selected Richard Hendricks and initiated a password reset.
5. Used an administrator-generated temporary password.
6. Required the employee to change the temporary password during the next sign-in.
7. Opened a separate browser session to test the employee's credentials.
8. Successfully authenticated using the temporary password and created a new password.
9. Registered the employee account with Microsoft Authenticator.
10. Completed the MFA setup and confirmed successful account access.

## Resolution

The employee's password was reset successfully, and the account was accessible using the newly configured credentials.

Microsoft Authenticator registration was completed successfully.

**Ticket Status:** Resolved

## Skills Demonstrated

- Microsoft 365 password administration
- Microsoft Entra ID user management
- Password recovery procedures
- Multi-factor authentication enrollment
- Authentication troubleshooting
- Identity verification practices
- Account security management

## Lessons Learned

Password resets and MFA enrollment are common help desk responsibilities.

Requiring users to change administrator-issued temporary passwords helps prevent continued reliance on temporary credentials.

Configuring Microsoft Authenticator establishes an authentication method, but successful registration does not necessarily mean MFA will be challenged during every subsequent sign-in.

MFA behavior depends on tenant security policies, authentication sessions, and token claims.

## Security Considerations

- Follow approved identity verification procedures before resetting passwords.
- Never disclose passwords or authentication codes through insecure channels.
- Protect administrator accounts with MFA.
- Ensure temporary credentials are replaced.
- Investigate unusual authentication behavior through Microsoft Entra sign-in
