---
id: view-operations
title: View Operations
sidebar_label: View Operations
---

In order to use the EDC to interact with views, the following prerequisits must be met:

1. A [connector]() to the database must have been created through the EDC dashboard.
2. A [role]() with permissions to the data inside of the connector must be created through the EDC dashboard.
3. A [user]() must be created and added to the role.
4. `using EDC;` has been added to the controller.

The final parameter in each request determines if a user has to be signed in to make the request. Setting loggingService = true allows the EDC to store a log of each request that has been made. 

### Get All and Record Limit

Get all views in the database with their corresponding record limit.

If the request is successful, the EDC returns a list of all the views in the database.

```c#
public ActionResult GetAllViews(string connectorName, string viewName) 
{
    EDC.Api.ViewOperations.GetAllAndRecordLimit(connectorName, viewName, LoggingService loggingService = null)
}
```

### Get All

Get All returns a list of all the rows in the requested view.

If the request is successful, the EDC returns a list of all the rows in the view.

```c#
public ActionResult GetAll(string connectorName, string viewName)
{
    EDC.Api.ViewOperations.GetAll(connectorName, viewName, LoggingService loggingService = null)
}
```