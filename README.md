# Pied Piper IT — Microsoft 365 Administration & Help Desk Lab

![Project Status](https://img.shields.io/badge/Status-In%20Progress-blue)
![Microsoft 365](https://img.shields.io/badge/Microsoft-365-0078D4)
![Microsoft Entra ID](https://img.shields.io/badge/Microsoft-Entra%20ID-5C2D91)
![Help Desk](https://img.shields.io/badge/Help%20Desk-6%20Tickets%20Completed-brightgreen)

## Project Overview

Pied Piper IT is a simulated small-business IT environment created to develop practical skills in Microsoft 365 administration, technical support, identity and access management (IAM), and security troubleshooting.

Using a Microsoft 365 Business Premium with Copilot trial tenant, this project simulates common responsibilities performed by IT help desk technicians and Microsoft 365 administrators.

The lab focuses on completing realistic support tickets, documenting troubleshooting procedures, applying security best practices, and gaining hands-on experience with enterprise administration tools.

**Project Type:** IT Administration / Home Lab  
**Environment:** Microsoft 365 Business Tenant  
**Status:** Active — Ongoing Development

## Technologies & Tools

| Technology | Purpose |
|---|---|
| Microsoft 365 Admin Center | User administration and account management |
| Microsoft Entra ID | Identity and access management |
| Microsoft Authenticator | Multi-factor authentication |
| Microsoft Entra Sign-in Logs | Authentication monitoring and troubleshooting |
| Microsoft Entra Security Groups | Group membership and access management |
| GitHub | Documentation and project tracking |

## Lab Environment

**Organization:** Pied Piper IT (fictional)

**Subscription:** Microsoft 365 Business Premium with Copilot (Trial)

**Architecture:** Cloud-based Microsoft 365 tenant

**Administrative Configuration:**
- Dedicated administrator account
- Simulated employee identities
- Microsoft Entra security groups
- Security Defaults enabled
- MFA registration through Microsoft Authenticator
- Unlicensed test employee accounts for identity administration exercises

This lab uses fictional employee identities and does not contain production business data.

## Completed Help Desk Tickets

### Ticket #001 — New Employee Onboarding

**Scenario:** A new employee requires access to the company environment.

**Tasks Completed:**
- Created an employee account through the Microsoft 365 Admin Center
- Configured account information and initial credentials
- Created the account without an assigned product license
- Maintained standard user permissions

**Skills Demonstrated:** User provisioning, account administration, least privilege, Microsoft 365 administration.

### Ticket #002 — Password Reset & MFA Enrollment

**Scenario:** An employee cannot access their account and requires a password reset.

**Tasks Completed:**
- Performed an administrator-initiated password reset
- Required a password change during the next sign-in
- Registered Microsoft Authenticator
- Successfully verified employee authentication

**Skills Demonstrated:** Account recovery, MFA enrollment, identity verification procedures, authentication troubleshooting.

### Ticket #003 — Authentication Log Investigation

**Scenario:** The IT security team requests verification of an employee's authentication activity.

**Tasks Completed:**
- Accessed Microsoft Entra ID sign-in logs
- Located and examined successful authentication events
- Reviewed authentication requirements and details
- Identified an MFA requirement satisfied by an existing token claim
- Verified that tenant Security Defaults were enabled

**Finding:** An existing MFA claim satisfied the applicable authentication requirement without an additional MFA prompt during the examined sign-in.

**Skills Demonstrated:** Sign-in log analysis, Microsoft Entra monitoring, MFA troubleshooting, identity security.

### Ticket #004 — Security Group Creation

**Scenario:** Engineering requires a departmental security group for future access assignments.

**Tasks Completed:**
- Created the `SG-Engineering` security group
- Configured assigned group membership
- Added the employee to the security group
- Verified membership through Microsoft Entra ID

**Skills Demonstrated:** Security group administration, access management, least privilege.

### Ticket #005 — Employee Department Transfer

**Scenario:** An employee transfers from Engineering to Product Management.

**Tasks Completed:**
- Created `SG-ProductManagement`
- Updated the employee's department information
- Added the employee to the new departmental security group
- Removed obsolete Engineering group membership
- Verified the updated identity and group configuration

**Skills Demonstrated:** Joiner-Mover-Leaver (JML) workflows, access reviews, identity lifecycle management, prevention of privilege creep.

### Ticket #006 — Employee Offboarding

**Scenario:** An employee leaves the organization and their access must be revoked while retaining the account.

**Tasks Completed:**
- Disabled the employee's account
- Revoked active sign-in sessions
- Removed departmental security group membership
- Retained the employee identity for administrative purposes
- Verified that new sign-in attempts were blocked

**Skills Demonstrated:** User offboarding, session revocation, access termination, account lifecycle management.

## Identity Lifecycle Management

The lab has completed exercises covering all three stages of the Joiner-Mover-Leaver lifecycle:

| Lifecycle Stage | Administrative Activities | Status |
|---|---|---|
| Joiner | Account creation, initial credentials, MFA registration | Completed |
| Mover | Department updates, group membership changes | Completed |
| Leaver | Account deactivation, session revocation, access removal | Completed |

## Security Concepts Practiced

- Principle of least privilege
- Multi-factor authentication
- Identity and access management
- Role and group membership administration
- Authentication monitoring
- Microsoft Entra Security Defaults
- Session and token revocation
- Access lifecycle management
- Help desk ticket documentation

## Planned Lab Exercises

Future exercises will expand into:

- Microsoft 365 license administration
- Exchange Online and shared mailbox management
- Microsoft Teams administration
- SharePoint permissions and collaboration
- Microsoft Intune device management
- Microsoft Entra administrative roles
- PowerShell administration and automation
- Additional help desk troubleshooting scenarios

These sections will be updated as exercises are completed.

## Project Goals

1. Develop practical Microsoft 365 administration skills applicable to entry-level IT and help desk roles.
2. Build experience troubleshooting common enterprise authentication and access issues.
3. Apply cybersecurity principles to everyday IT operations.
4. Practice documenting incidents and administrative changes using professional help desk procedures.
5. Demonstrate hands-on technical experience through a continuously maintained GitHub portfolio.

## Documentation & Security

All employees, departments, and support scenarios in this repository are fictional.

Screenshots and documentation will exclude or redact sensitive information, including account credentials, MFA secrets, authentication tokens, tenant identifiers, and personal information.

No production systems are used in this lab.

---

**Project Status:** In Progress

This repository is an ongoing documentation of practical Microsoft 365 administration and IT support exercises performed in a controlled home lab environment.
