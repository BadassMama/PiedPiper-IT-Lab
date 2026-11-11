# Ticket #004 — Security Group Creation

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management  
**Priority:** Low  
**Status:** Resolved  
**Platform:** Microsoft Entra ID

## Issue Description

The Engineering department at Pied Piper IT required a security group to organize employee identities and support future department-specific access control.

The IT department was tasked with creating a Microsoft Entra security group, assigning the appropriate employee membership, and verifying the configuration.

The group needed to follow the principle of least privilege and avoid unnecessary administrative permissions.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Entra Admin Center
- Cloud-managed user identities
- Assigned security group membership

## Troubleshooting and Resolution Steps

1. Signed in to the Microsoft Entra admin center at https://entra.microsoft.com.
2. Navigated to **Entra ID → Groups → All groups**.
3. Selected **New group**.
4. Configured the group with the following settings:

   | Setting | Configuration |
   |---|---|
   | Group type | Security |
   | Group name | SG-Engineering |
   | Description | Security group for Pied Piper IT Engineering employees |
   | Membership type | Assigned |
   | Group owner | IT administrator account |
   | Microsoft Entra role assignment | Disabled |

5. Added the fictional employee Richard Hendricks as a group member.
6. Created the security group.
7. Opened the newly created group and navigated to **Members**.
8. Verified that Richard Hendricks was listed as a member.
9. Confirmed the group was configured for departmental membership management rather than administrative role assignment.

## Resolution

Successfully created the `SG-Engineering` security group in Microsoft Entra ID.

Assigned the appropriate employee membership and verified that the group was configured without unnecessary administrative permissions.

The group was available for future department-specific resource access assignments.

**Ticket Status:** Resolved

## Skills Demonstrated

- Microsoft Entra ID administration
- Security group creation and configuration
- Group membership management
- Identity and access management
- Principle of least privilege
- Access control planning
- Administrative configuration verification

## Lessons Learned

### Security Groups Simplify Access Management

Security groups allow administrators to manage collections of users instead of assigning permissions individually.

For example, a department containing 20 employees could use a single security group to manage access to authorized resources.

### Group Membership Does Not Automatically Grant Access

Creating a security group and adding employees does not automatically provide access to applications, files, or other resources.

Administrators must separately configure supported resources to use the security group for authorization.

### Assigned vs. Dynamic Membership

Microsoft Entra supports different group membership models.

**Assigned membership:** Administrators manually add and remove members.

**Dynamic membership:** Users can be added or removed automatically according to configured membership rules, subject to applicable licensing and feature requirements.

This exercise used assigned membership.

### Security Groups vs. Administrative Roles

A security group organizes identities for access management.

Microsoft Entra administrative roles grant specific administrative permissions.

These are different concepts, and ordinary departmental security groups should not receive privileged roles without an approved business requirement.

## Security Considerations

- Follow the principle of least privilege.
- Assign group ownership only to authorized administrators or designated owners.
- Review group membership regularly.
- Remove obsolete memberships when employees change departments or leave the organization.
- Avoid assigning privileged administrative roles to standard departmental groups.
- Document group purpose and ownership.
- Verify access changes before closing administrative tickets.

## Documentation Notes

This exercise was completed in a controlled Microsoft 365 home lab using fictional employee information.

The security group was created for training purposes and was not connected to a production system.

No credentials, sensitive tenant identifiers, or authentication information are included in this documentation.

## Microsoft Documentation

- [Microsoft Entra group management](https://learn.microsoft.com/en-us/entra/fundamentals/how-to-manage-groups)
- [Microsoft Entra group-based access management](https://learn.microsoft.com/en-us/entra/identity/users/groups-concept)
