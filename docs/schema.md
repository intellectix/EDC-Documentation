---
id: schema
title: Schema
sidebar_label: Schema
---

The EDC Schema endpoint allows for the schema of connectors to be retrieved in a json format.

In order for the endpoint to work, make sure that a User's authorization token can be used in the header of the request.

To make the request, make the following `GET` request to the EDC Web Api:

`"server_url"/edc/api/{connectorName}/_schema`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_schema', config)
.then(res => res.json())
.then(data => console.log(data))
```

If successful, the EDC will return a JSON object in the following format:

```json
{
  "ConnectorId": 0,
  "ConnectorName": "string",
  "Name": "string",
  "DbName": "string",
  "Tables": [
    "string",
    "string",
    "string"
  ],
  "Views": [
    "string",
    "string"
  ],
  "StoredProcedures": [
    "string",
    "string"
  ],
  "VirtualEntities": [
    "string"
  ]
}
```