---
id: table-operations
title: Table Operations
sidebar_label: Table Operations
---

The EDC revolutionizes the way developers build .Net applications. Rather than building out the entire MVC structure, the EDC allows for fully permissioned data requests to be made directly in controller methods with a single line of code without the need of pre-existing models or repositories. These requests can also be filtered with Linq to ensure that queries are only returning the information that is needed.

In order to use the EDC to interact with data, the following prerequisits must be met:

1. A [connector]() to the database must have been created through the EDC dashboard.
2. A [role]() with permissions to the data inside of the connector must be created through the EDC dashboard.
3. A [user]() must be created through the EDC dashboard and added to the role.
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

## Filtering Requests

The EDC allows requests to be filtered before they are sent to a database by utilizing [Linq](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/). In order to filter a request with the EDC, make sure that you have a `ViewModel` implemented that represents the object you would like to return. 

For example, assume there is a `Customer` class and the expected output should only return a few fields from this class.

1. Create View Model
```c#
public class CustomerViewModel
{
    string FirstName {get;set;}
    string LastName {get;set;}
    string Email {get;set;}
}
```

2. Call the requested EDC method with the new View Model attached.

```c#
public ActionResult Get(string connectorName, string tableName)
{
    var customers = EDC.Api.TableOperations.GetAll<CustomerViewModel>(connectorName, tableName, LoggingService loggingService = null).where(FirstName == "John");

    return customers;
}
```

The EDC will returns the View Model of Customers containing only the FirstName, LastName and Email where FirstName equals "John". This View Model can then be used in a View to display the data on the page.

To add more customer data in the future, update the View Model and the new data will be available on the corresponding Views.

