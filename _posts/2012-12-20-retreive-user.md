---
category: User
rest_uri: '/api/users/:id'
title: 'Retrieve a user'
type: 'GET'

layout: null
---

This endpoint retrieves details of a previously created user.

_Note: You only have permission to retrieve details for users that you have created (i.e. via your API token)._

### Request

* The headers must include a **Valid Authorization Token** and an **Accept** header

Request headers:

```sh
Authorization: Token [API_TOKEN]
Accept: application/vnd.myfuturenow.v1+json
```

Example _curl_ command:

```sh
curl -X POST \
  -H "Authorization: Token $API_TOKEN" \
  -H "Accept: application/vnd.myfuturenow.v1+json" \
  "https://$API_HOST/api/users/12345"
```

### Response

Returns a summary of the user data, and a `callback_url` _(valid for 15 minutes)_

```
Status: 200 OK
```

``` json
{
  "callback_url": "https://[API_HOST]/log_in/[TOKEN]",
  "id": 1001,
  "email": "john@example.com",
  "inserted_at": "2016-12-16T12:35:42.965729"
  ...
}
```

For errors responses, see the [response status codes documentation](#/response-status-codes).
