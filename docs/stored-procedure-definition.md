---
id: stored-procedure-definition
title: Stored Procedure Definitions
sidebar_label: Stored Procedure Definitions
---

The EDC Stored Procedure Definition endpoint allows for the EDC to return all the parameters used in a stored procedure in JSON format.

In order for the endpoint to work, make sure that a User's authorization token can be used in the header of the request.

## All Parameters in a Stored Procedure

To get all of the parameters used in a Stored Procedure, make the following `GET` request to the EDC Web Api:

`"server_url"/edc/api/{connectorName}/_definition/_sproc/{sprocName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_definition/_sproc/{sprocName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

The EDC will return the Stored Procedure Definition in the following format:

```JSON
{
  "Name": "string",
  "Parameters": [
    {
      "Name": "string",
      "Type": "string",
      "IsOutput": true,
      "IsNullable": true
    },
    {
      "Name": "string",
      "Type": "string",
      "IsOutput": true,
      "IsNullable": true
    }
  ]
}
```

## Single Parameter

To get the information of a single parameter within a stored procedure, make the following `GET` request to the EDC Web Api:

`"server_url"/edc/api/{connectorName}/_definition/_sproc/{sprocName}/{paramName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_definition/_sproc/{sprocName}/{paramName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

The EDC will return the definition of a single parameter in the following format:

```json
{
  "Name": "string",
  "Type": "string",
  "IsOutput": true,
  "IsNullable": true
}
```