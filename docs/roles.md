---
id: roles
title: Roles
sidebar_label: Roles [Pro]
---

Roles allow the EDC to provide real-time permissioning to the data that users can access. By default, no data is allowed to be access from the database until a permission has been added. In addition, the permissions can be broken down to the column level within tables. For example, assume there is a database with a User table which contains the following fields:

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

To add a Role to the EDC, navigate to `Roles` on the left side of the EDC dashboard.