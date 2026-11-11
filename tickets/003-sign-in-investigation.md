# Ticket #003 — Authentication Log Investigation

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management / Security Monitoring  
**Priority:** Medium  
**Status:** Resolved  
**Platform:** Microsoft Entra ID

## Issue Description

Following a password reset and Microsoft Authenticator enrollment, the IT department needed to verify that a simulated employee, Richard Hendricks, could successfully authenticate to the organization's Microsoft 365 environment.

During the investigation, a successful sign-in event was found with an authentication requirement of "Single-factor authentication."

The objective was to determine whether the sign-in was successful, examine the recorded MFA behavior, and review the tenant's security configuration.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Entra sign-in logs
- Microsoft Authenticator
- Microsoft Entra Security Defaults enabled

## Investigation and Troubleshooting Steps

1. Signed in to the Microsoft Entra admin center at https://entra.microsoft.com.
2. Navigated to **Entra ID → Monitoring & health → Sign-in logs**.
3. Filtered the sign-in logs to locate recent authentication activity for Richard Hendricks.
4. Selected a successful interactive sign-in event.
5. Reviewed the sign-in status and authentication requirement.
6. Confirmed that the event's status was **Success**.
7. Observed that the authentication requirement was recorded as **Single-factor authentication**.
8. Opened the **Authentication Details** tab to investigate the recorded authentication behavior.
9. Identified the message **"MFA requirement satisfied by claim in the token."**
10. Navigated to the tenant's Security Defaults configuration.
11. Verified that **Security Defaults were enabled**.

## Investigation Findings

| Log Field | Observed Result |
|---|---|
| Employee | Richard Hendricks |
| Sign-in status | Success |
| Authentication requirement | Single-factor authentication |
| Authentication details | MFA requirement satisfied by claim in the token |
| Security Defaults | Enabled |

### MFA Token Claim Analysis

Microsoft Entra ID can recognize MFA authentication evidence contained in an existing authentication token.

When a valid MFA claim satisfies an authentication requirement, Microsoft may not need to prompt the user for another MFA challenge.

This is commonly associated with previously satisfied authentication requirements and session-based authentication behavior.

The "Single-factor authentication" label describes the authentication requirement recorded for the selected sign-in event. It should not be interpreted on its own as proof that MFA is disabled throughout the tenant.

The authentication details indicated that an MFA requirement was satisfied through a token claim rather than through a new interactive MFA challenge during the examined event.

## Resolution

The employee's sign-in was successful.

The investigation confirmed that Microsoft Entra Security Defaults were enabled and that the selected sign-in event contained an MFA satisfaction message associated with an existing token claim.

The available evidence was consistent with expected Microsoft Entra authentication behavior.

No immediate configuration change was required based on this investigation.

**Ticket Status:** Resolved

## Skills Demonstrated

- Microsoft Entra ID administration
- Authentication log investigation
- Sign-in event analysis
- MFA troubleshooting
- Token-based authentication concepts
- Microsoft Entra Security Defaults verification
- Security event documentation

## Lessons Learned

A successful sign-in event does not necessarily mean that an MFA challenge was performed during that particular sign-in.

Microsoft Entra can reuse valid authentication evidence through token claims.

The authentication requirement field and authentication details provide different information and should be interpreted together.

Security Defaults help protect organizational accounts, but their enabled status alone does not prove that every sign-in receives an MFA challenge.

Sign-in investigations require examining multiple fields before determining whether authentication behavior is expected or suspicious.

## Security Considerations

- Maintain appropriate MFA protections for organizational accounts.
- Review authentication details rather than relying exclusively on sign-in status.
- Investigate unexpected authentication patterns.
- Monitor failed and interrupted sign-in attempts.
- Avoid disabling tenant security protections merely to simplify troubleshooting.
- Protect sensitive sign-in information, including IP addresses, account identifiers, session details, and authentication records.

## Documentation Notes

This investigation was conducted using a fictional employee account in a controlled Microsoft 365 home lab.

No authentication tokens, passwords, MFA secrets, or identifying tenant information are included in this documentation.

## Microsoft Documentation

- [Microsoft Entra MFA reporting](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-mfa-reporting)
- [Microsoft Entra sign-in logs](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/concept-sign-ins)
