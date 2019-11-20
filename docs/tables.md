---
id: tables
title: Tables
sidebar_label: Tables
---

The EDC Table endpoint allows for the EDC to interact with tables in the following ways:
- Retrieve data from a given table
- Insert a record into a given table
- Remove record from a given table
- Retrieve single row by primary key
- Update record in a given table

In order for the endpoint to work, make sure that a User's authorization token can be used in the header of the request.

## Retrieve data from a table

To retrieve data from a table through the EDC, perform the following `GET` request:

`"server_url"/edc/api/{connectorName}/_table/{tableName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_table/{tableName}', config)
.then(res => res.json())
.then(data => console.log(data))
```

The EDC will return the list of columns in the following format:

```json
[
  {
    "Id": "00000000-0000-0000-0000-000000000000",
    "Column1": "string",
    "Column2": 0
  }
]
```

## Retrieve a single row from a table

To retrieve a single row from a table, perform the following `GET` request:

`"server_url"/edc/api/{connectorName}/_table/{tableName}/{id}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_table/{tableName}/{id}', config)
.then(res => res.json())
.then(data => console.log(data))
```

The EDC will return the record in the following format:

```json
{
  "Id": "00000000-0000-0000-0000-000000000000",
  "Column1": "string",
  "Column2": 0
}
```

## Insert a record into a table

To insert a record into a table, perform the following `POST` request:

`"server_url"/edc/api/{connectorName}/_table/{tableName}`

**Example** In a React application, this request might look like the following: 

```js
//Must create an object containing the required fields to POST to the database.
var data = {
  "Id": "00000000-0000-0000-0000-000000000000",
  "Column1": "string",
  "Column2": 0
}

fetch('"server_url"/edc/api/{connectorName}/_table/{tableName}', {
    method: 'post',
    headers: {'content-type':'application/json'},
    body: data
})
.then(res => res.json()
.then(data => console.log(data)))
```

If successful, the EDC will return a `200` status as well as the exact object that was inserted into the database.

## Delete a record in a table

To delete a record, perform the following `DELETE` request:

`"server_url"/edc/api/{connectorName}/_table/{tableName}/{id}`

**Example** In a React application, this request might look like the following: 

```js

fetch('"server_url"/edc/api/{connectorName}/_table/{tableName}/{id}', {
    method: 'post',
    headers: {'content-type':'application/json'}
})
.then(res => res.json()
.then(data => console.log(data)))
```

If successful, the EDC will return a `200` status as well as the exact object that was inserted into the database.

## Update a record in a table

To update a record, perform the following `PUT` request:

`"server_url"/edc/api/{connectorName}/_table/{tableName}/{id}`

**Example** In a React application, this request might look like the following: 

```js
var data = {
  "Id": "00000000-0000-0000-0000-000000000000",
  "Column1": "string",
  "Column2": 0
}

fetch('"server_url"/edc/api/{connectorName}/_table/{tableName}/{id}', {
    method: 'put',
    headers: {'content-type':'application/json'},
    body: data
})
.then(res => res.json()
.then(data => console.log(data)))
```

If successful, the EDC will return a `200` status as well as the object that was updated into the database.