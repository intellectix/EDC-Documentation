---
id: schema-operations
title: Schema Operations
sidebar_label: Schema Operations
---

In order to use the EDC to interact with the database Schema, the following prerequisits must be met:

1. A [connector]() to the database must have been created through the EDC dashboard.
2. A [role]() with permissions to the data inside of the connector must be created through the EDC dashboard.
3. A [user]() must be created and added to the role.
4. `using EDC;` has been added to the controller.

The final parameter in each request determines if a user has to be signed in to make the request. Setting loggingService = true allows the EDC to store a log of each request that has been made. 

## Free

### Connector Definition

Get the definition of a specific connector.

```c#
public ActionResult GetDefinition(string connectorName)
{
    EDC.Api.SchemaOperations.Definition(connectorName, LoggingService loggingService = null)
}
```

If successful, the EDC returns an object in the following format containing the requested Schema definition.

```json
{
  "ConnectorId": 0,
  "ConnectorName": "string",
  "Name": "string",
  "DbName": "string",
  "Tables": [
    "string"
  ],
  "Views": [
    "string"
  ],
  "StoredProcedures": [
    "string"
  ],
  "VirtualEntities": [
    "string"
  ]
}
```

### Database Table List 

Get a list of all the tables in a database.

```c#
public ActionResult GetDBList(string connectorName)
{
    EDC.Api.SchemaOperations.DbTableList(connectorName, LoggingService loggingService = null)
}
```

If successful, the EDC will return a JSON object containing the names of all the Tables inside the connector.

## Pro

### Connector Definition

```c#
public ActionResult GetDefinition(string connectorName, IPrincipal user)
{
    var definition = EDC.Api.Pro.SchemaOperations.Definition(connectorName, user, LoggingService loggingService = null);

    return definition;
}
```

The EDC logs which user made the request, and returns the formatted definition of the requested connector.

### Database Table List

```c#
public ActionResult GetDBList(string connectorName, IPrincipal user)
{
    var list = EDC.Api.SchemaOperations.DbTableList(connectorName, user LoggingService loggingService = null);

    return list;
}
```

The EDC logs which user made the request, and returns the list of tables from the requested connector.