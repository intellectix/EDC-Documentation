---
id: table-operations
title: Table Operations
sidebar_label: Table Operations
---

In order to use the EDC to interact with data, the following prerequisits must be met:

1. A [connector]() to the database must have been created through the EDC dashboard.
2. A [role]() with permissions to the data inside of the connector must be created through the EDC dashboard.
3. A [user]() must be created and added to the role.
4. `using EDC;` has been added to the controller.

The final parameter in each request determines if a user has to be signed in to make the request. Setting loggingService = true allows the EDC to store a log of each request that has been made. 

## Get Requests

The EDC GET requests allow for simplified data retrieval directly from controller methods without the use of pre-exisiting models. Once the prerequisits have been met, the EDC allows for the following methods to be called:

### Get All

Get All returns all records from the requested table.

If the Get is successful, the EDC returns a list of all the objects from the table.

```c#
public ActionResult Get(string connectorName, string tableName) 
{
    EDC.Api.TableOperations.GetAll(connectorName, tableName, HttpRequestMessage request, LoggingService loggingService = null)
}
```

### Get By Id

Get By Id returns a single record from the requested table.

If the Get is successful, the EDC returns a single object.

```c#
public ActionResult Get(string connectorName, string tableName, string id) 
{
    EDC.Api.TableOperations.GetById(connectorName, tableName, id, LoggingService loggingService = null)
}
```

## Create New Row

The EDC allows for new data to quickly be inserted into a database without the need for pre-existing models.

```c#
public ActionResult AddData(formData)
{

}
```

## Update Row

To update records with the EDC, call the Update Row method and pass in the connector name, table name, id, and the object you are updating.

If the update is successful, the EDC returns the object that was updated.

```c#
public ActionResult Update(string connectorName, string tableName, string id, object item)
{
    EDC.Api.TableOperations.UpdateRow connectorName, tableName, id, item, LoggingService loggingService = null)
}
```

## Delete Row
To delete records with the EDC, call the Delete Row method and pass in the connector name, table name and id.

If the delete is successful, the EDC returns the object that was deleted.

```c#
public ActionResult Delete(string connectorName, string tableName, string id)
{
    EDC.Api.TableOperations.DeleteRow(connectorName, tableName, id, LoggingService loggingService = null)
}
```


