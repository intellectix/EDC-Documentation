---
id: table-definition
title: Table Definitions
sidebar_label: Table Definitions
---

The EDC Table Definition endpoint allows for the EDC to return all the columns in a table in JSON format.

In order for the endpoint to work, make sure that a User's authorization token can be used in the header of the request.

## List all Columns

To list all columns in a table, make a `GET` request to the following endpoint:

`"server_url"/edc/api/{connectorName}/_definition/_table/{tableName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_definition/_table/{tableName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

The EDC will return the list of columns in the following format:

```json
[
  {
    "Name": "string",
    "Type": "string",
    "Length": "string",
    "IsNullable": true
  },
  {
    "Name": "string",
    "Type": "string",
    "Length": "string",
    "IsNullable": true
  }
]
```

## Get Column Attributes

To get the attributes to a column in a table, make a `GET` request to the following endpoint:

`"server_url"/edc/api/{connectorName}/_definition/_table/{tableName}/{columnName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_definition/_table/{tableName}/{columnName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

The EDC will return the attributes of the column in the following format:

```json
{
  "IsPK": true,
  "IsFK": true,
  "Name": "string",
  "Type": "string",
  "Length": "string",
  "IsNullable": true
}
```