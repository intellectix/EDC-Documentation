---
id: roles
title: Roles
sidebar_label: Roles [Pro]
---

Roles allow the EDC to provide real-time permissioning to the data that users can access. By default, no data is allowed to be accessed from the database until a permission has been added. In addition, the permissions can be broken down to the column level within tables. For example, assume there is a database with a User table which contains the following fields:

```c#
public class Users 
{
    string Name {get; set;}
    string Email {get; set;}
    string PhoneNumber {get; set;}
    int Age {get; set;}
    string SSN {get; set;}
}
```

Because SSN numbers are highly sensitive data, it is important that not all users of a system have access to this information. In this example, the developer can create a role called "HR Staff" which only has access to the Name and Email fields. When a user assigned to the HR Staff role makes a query, they can **only** see the Name and Email fields. As far as the system is aware when the query is generated, the other fields do not exist. Because these permissions are checked before the query is built, there is a 0% chance of data being leaked to users that should not have access.

## Adding a Role

To add a Role to the EDC, navigate to `Roles` on the left side of the EDC dashboard. Then click 'Add Role'.

Fill in the Name, Description, and Status and click 'Save'. The permissions tabs and Members tabs are now unlocked.

## Adding a Permission

Prerequisite: Make sure that a Connector has been added to the EDC before creating a Permission. The Connector information is needed.

On the Roles home page, click on the Name of the role to be directed to that Role's Edit page. Then, click on the Permissions tab and click 'Add Permission'.

Fill in the required information and click 'Save'. The Role now has permission to either Read,Write or Delete data within that connector.

## Deleting a Permission

On the Role's Edit page, click the 'Permissions' tab. Then click the 'X' in the table for the permission to delete. The permission will now be permanently deleted.

## Adding a Member

Members are the users that can interact with the system. By default, a user has no permissions to any data until it has been assigned to a role. 

Prerequisite: Make sure that a User has been added to the EDC before creating a Member.

In the Role's Edit page, click the 'Members' tab. Then, click 'Add Member'. Select the members to add and then click 'Save'. These Users can now interact with the database in accordance to the Permissions that have been applied to the Role.

## Deleting a Member

On the Role's Edit page, navigate to the Members tab and click the 'X' for the User to be deleted. This user will be permanently removed from the Role and all database access will be removed.



