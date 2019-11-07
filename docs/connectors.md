---
id: connectors
title: Connectors
sidebar_label: Connectors
---

Connectors are the critical piece to how the EDC provides all of its functionality. These connectors provide the EDC with access to a database as well as the ability to make requests on behalf of the system. 

## Adding A Connector

To add a connector to the EDC, navigate to the Connectors page by clicking `Connectors` on the left side of the EDC dashboard. The Connectors page shows a list of all connectors for the application.

1. Click "Add Connector" on the top right of the page.
2. Select the type of database that the EDC needs to connect to. Currently, the EDC supports SQL Server, MySQL and Oracle.
3. Fill in the requested information and hit "Save". 
    - The "Maximum Records Returned" field is required, because the EDC needs to know how many records it may return with each request. For example, if there was a database table with 20,000 records and the Maximum Records Returned was set to 10, then the EDC would only ever return 10 records at a time regardless of the endpoint that is being used to retrive the data.

## Adding A User Join

Once a connector has been created, user joins can be added to the connector. Click on the Edit icon on the Connectors home page, and navigate to the Joins tab. Click "Add Join". Fill in the requested information and then click "Save". 

## Editing a Connector

To edit a Connector, click on the "Edit" icon on the Connectors home page. All fields can then be updated. Click "Save" to update all changes.

## Delete a Connector

To delete a Connector, click on the "X" icon on the Connectors home page. Accept the prompt, and the Connector will be permanently deleted from the system.

