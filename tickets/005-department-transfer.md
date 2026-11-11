# Ticket #005 — Employee Department Transfer

**Organization:** Pied Piper IT  
**Category:** Identity & Access Management / User Lifecycle Management  
**Priority:** Medium  
**Status:** Resolved  
**Platform:** Microsoft Entra ID

## Issue Description

A fictional employee, Richard Hendricks, was transferred from the Engineering department to Product Management.

The IT department was tasked with updating the employee's organizational information and modifying security group memberships to reflect the new position.

The primary security objective was to ensure that the employee received appropriate departmental group membership while removing obsolete access associated with the previous department.

This exercise simulates the **Mover** stage of the Joiner-Mover-Leaver (JML) identity lifecycle.

## Environment

- Microsoft 365 Business Premium with Copilot trial
- Microsoft Entra ID
- Microsoft Entra Admin Center
- Cloud-managed employee identities
- Assigned security group memberships

## Initial Configuration

Before the department transfer, the employee's account had the following configuration:

| Property | Initial Value |
|---|---|
| Employee | Richard Hendricks |
| Department | Engineering |
| Security Group | SG-Engineering |
| Administrative Role | Standard user |
| Product License | Unassigned |

## Administrative Procedure

### Step 1 — Create the New Department Security Group

1. Signed in to the Microsoft Entra admin center at https://entra.microsoft.com.
2. Navigated to **Entra ID → Groups → All groups**.
3. Selected **New group**.
4. Created the following security group:

   | Setting | Configuration |
   |---|---|
   | Group type | Security |
   | Group name | SG-ProductManagement |
   | Description | Product Management department access |
   | Membership type | Assigned |
   | Group owner | IT administrator |
   | Microsoft Entra role assignment | Disabled |

5. Added Richard Hendricks as a member.
6. Verified that the employee appeared in the new group's membership list.

### Step 2 — Update Employee Department Information

1. Navigated to **Entra ID → Users → All users**.
2. Selected Richard Hendricks.
3. Opened the employee's profile properties.
4. Updated the Department field from **Engineering** to **Product Management**.
5. Saved the changes.

### Step 3 — Remove Obsolete Group Membership

1. Navigated to **Entra ID → Groups → All groups**.
2. Opened `SG-Engineering`.
3. Selected **Members**.
4. Located Richard Hendricks.
5. Removed the employee from the group.
6. Verified that Richard no longer appeared in the Engineering security group's membership list.

### Step 4 — Verify Final Configuration

Reviewed the employee profile and group memberships to confirm that the department transfer was reflected correctly.

## Final Configuration

| Property | Final Value |
|---|---|
| Employee | Richard Hendricks |
| Department | Product Management |
| Security Group | SG-ProductManagement |
| Previous Group | Removed from SG-Engineering |
| Administrative Role | Standard user |
| Product License | Unassigned |

## Resolution

The employee's department information was updated successfully.

The employee was added to the Product Management security group and removed from the previous Engineering security group.

The final identity configuration was verified in Microsoft Entra ID.

**Ticket Status:** Resolved

## Skills Demonstrated

- Microsoft Entra ID administration
- Employee identity lifecycle management
- Security group creation
- Group membership modification
- Department attribute management
- Access change verification
- Principle of least privilege
- Joiner-Mover-Leaver workflows

## Lessons Learned

### Employee Transfers Require Access Reviews

When employees change departments, their access requirements may change.

Simply updating an employee's department information does not automatically update assigned security group memberships.

Administrators must review and modify access based on the employee's new responsibilities.

### Understanding Privilege Creep

**Privilege creep** occurs when users accumulate permissions they no longer require.

For example, an employee transferring from Engineering to Product Management might retain unnecessary access to Engineering resources if obsolete permissions are not removed.

Regular access reviews and appropriate group membership management help reduce this risk.

### Assigned vs. Dynamic Groups

This exercise used assigned security group memberships.

Assigned groups require administrators to manually update membership.

Dynamic membership groups, where supported and appropriately licensed, can automatically update membership based on defined user attributes.

### Department Changes and Resource Permissions

Changing group membership does not automatically guarantee access to new resources or revoke every existing permission.

Actual access depends on how applications and resources are configured.

Administrators should verify resource-level permissions as part of a complete employee transfer workflow.

## Security Considerations

- Verify that department transfers are authorized before changing access.
- Grant only the permissions required for the employee's new role.
- Remove obsolete group memberships promptly.
- Review direct permissions and application-specific access where applicable.
- Confirm the employee retains access to required business
