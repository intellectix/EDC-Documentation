---
id: basic-auth
title: Basic Authentication
sidebar_label: Basic Authentication
---

The EDC authentication endpoint allows developers to make a web request to get a users authorization token. This token must be implemented in the header of each request so that the EDC can verify that the user is allowed to query the data.

To make the request, the EDC needs an object in the following format:

```json
{
    "Username": "string",
    "Password": "string",
    "ApplicationId": "string"
}
```

Note: The application ID can be obtained in the App Key section of the EDC dashboard.

Make a POST request to the following endpoint with the new object in the body of the request:

`"server_url"/BasicAuth/GetToken`

**Example**: In a React application, the request may look like the following:

```js

var userData = {
    "Username": "test",
    "Password": "test",
    "ApplicationId": "test"
}

fetch('"server_url"/BasicAuth/GetToken', {
    method: 'post',
    headers: {'content-type':'application/json'},
    body: userData
})
.then(res => res.json()
.then(data => console.log(data)))
```

If the request is successful, the EDC returns a fully encypted token:

```json
{
    eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjM0ZDk3YjVjLWE4MDUtNDcwYi1iZDU1LWI2ODVjM2UwYTBkMSIsImh0dHA6Ly9zY2hlbWFzLnhtbHNvYXAub3JnL3dzLzIwMDUvMDUvaWRlbnRpdHkvY2xhaW1zL25hbWUiOiJodW1waDJtdyIsIkFzcE5ldC5JZGVudGl0eS5TZWN1cml0eVN0YW1wIjoiTzVGT1RKMzJZM1I0Q1M2R1hGN1lMTEoyQTdER1VHRlQiLCJ1c2VyX3JvbGVzIjoiMSwyIiwiYXBwbGljYXRpb25faWQiOiJiNTY3N2Y1Yi0yMmQ1LTQyNTUtYjQ2ZC0zMTM4YmFmY2RiZTgiLCJuYmYiOjE1NzM1ODk0MDgsImV4cCI6MTU3MzU5MTIwOCwiaXNzIjoiaHR0cDovL2xvY2FsaG9zdDo2MzU2MSIsImF1ZCI6Imh0dHA6Ly9sb2NhbGhvc3Q6NjM1NjEifQ.dg_YOR40M2dFu0WVpSOqipKd6WdmeTrykV3Q-NQLKGQ
}
```

