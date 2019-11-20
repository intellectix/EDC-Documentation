---
id: virtual-entities
title: Virtual Entities
sidebar_label: Virtual Entities
---

The EDC Virtual Entities endpoint allows for the EDC to retrieve data from Virtual Entities.

In order for the endpoint to work, make sure that a User's authorization token can be used in the header of the request.

## Retrieve data from a virtual entity

To retrieve data from a virtual entity, perform a `GET` request to the following endpoint:

`"server_url"/edc/api/{connectorName}/_vtable/{entityName}`

**Example** In a React application, this request might look like the following:

```js
var config = {
    headers: {
        'Access-Control-Allow-Headers': '*',
        'Authorization': "***Auth Token***
    }
}

fetch('"server_url"/edc/api/{connectorName}/_vtable/{entityName}', config)
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