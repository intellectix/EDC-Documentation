---
id: developer-console
title: Developer Console
sidebar_label: Developer Console [Pro]
---

The Developer Console provides a simple to use GUI for quickly making data requests on behalf of the EDC. The Developer Console leverages OData to filter responses. Learn more about OData [here](https://www.odata.org/).

Here is a list of the requests that can be performed in the developer console:

1. Basic Auth
    * `POST` /BasicAuth/GetToken

2. Schema
    * `GET` /edc/api/{connectorName}/_schema

3. Stored Procedure
    * `GET` /edc/api/{connectorName}/_sproc/{sprocName}
    * `POST` /edc/api/{connectorName}/_sproc/{sprocName}

4. Stored Procedure Definition
    * `GET` /edc/api/{connectorName}/_definition/_sproc/{sprocName}
    * `GET` /edc/api/{connectorName}/_definition/_sproc/{sprocName}/{paramName}

5. Table Definition
    * `GET` /edc/api/{connectorName}/_definition/_table/{tableName}
    * `GET` /edc/api/{connectorName}/_definition/_table/{tableName}/{columnName}

6. Tables
    * `GET` /edc/api/{connectorName}/_table/{tableName}
    * `POST` /edc/api/{connectorName}/_table/{tableName}
    * `DELETE` /edc/api/{connectorName}/_table/{tableName}/{id}
    * `GET` /edc/api/{connectorName}/_table/{tableName}/{id}
    * `PUT` /edc/api/{connectorName}/_table/{tableName}/{id}

7. Views
    * `GET` /edc/api/{connectorName}/_view/{viewName}

8. Virtual Entities
    * `GET` /edc/api/{connectorName}/_vtable/{entityName}