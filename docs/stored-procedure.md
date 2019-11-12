---
id: stored-procedure
title: Stored Procedure
sidebar_label: Stored Procedure
---

The EDC Stored Procedure endpoint allows for the EDC to call a stored procedure inside of the connector on behalf of a user.

In order for the endpoint to work, make sure that a User's authorization token can be used in the header of the request.

## Request With No Parameters

To make the request with no parameters, make the following `GET` request to the EDC Web Api:

`"server_url"/edc/api/{connectorName}/_sproc/{sprocName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_sproc/{sprocName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

If successful, the EDC returns `{}` with a status of `200`.

## Request With Parameters

To make a request with parameters, make the following `POST` request to the EDC Web Api:

`"server_url"/edc/api/{connectorName}/_sproc/{sprocName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
    body: {bodyVariable}
}

fetch('"server_url"/edc/api/{connectorName}/_sproc/{sprocName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

If successful, the EDC returns `{}` with a status of `200`.