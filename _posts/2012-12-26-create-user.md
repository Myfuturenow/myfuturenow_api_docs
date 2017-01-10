---
category: User
rest_uri: '/api/users'
title: 'Create a User'
type: 'POST'

layout: null
---

This method allows users to create a new user.

### Request

* The headers must include a **Valid Authorization Token** and an **Accept** header
* The mandatory user fields are `email`, `first_name` and `last_name`

Request headers:

```
Authorization: Token [API_TOKEN]
Accept: application/vnd.myfuturenow.v1+json
Content-Type: application/json
```

Request body:

```json
{
  "email": "john7@example.com",
  "password": "23423432",
  "first_name": "Jonny",
  "last_name": "Smith",
  "gender": "male",
  "maiden_name": "Jones",
  "date_of_birth": "1991-04-23",
  "phone_number": "0777 123 4566",
  "national_insurance_number": "AB 12 34 56 A",
  "current_address": {
    "street": "1 The Larch",
    "locality": "Larchington",
    "county": "Larchshire",
    "postcode": "LA1 1AA",
    "udprn": "12345678"
  },
  "pensions": [
    {
      "employer_name": "Royal Mail",
      "start_year": 1993
    }
  ]
}
```

Example _curl_ command:

```sh
curl -X POST \
  -H "Authorization: Token [$API_TOKEN]" \
  -H "Accept: application/vnd.myfuturenow.v1+json" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "john20@example.com",
    "password": "23423432",
    "first_name": "Jonny",
    "last_name": "Smith",
    "gender": "male",
    "maiden_name": "Jones",
    "date_of_birth": "1991-04-23",
    "phone_number": "0777 123 4566",
    "national_insurance_number": "AB 12 34 56 A",
    "current_address": {
      "street": "1 The Larch",
      "locality": "Larchington",
      "county": "Larchshire",
      "postcode": "LA1 1AA",
      "udprn": "12345678"
    },
    "pensions": [
      {
        "employer_name": "Royal Mail",
        "start_year": 1983
      }
    ]
  }' \
  "https://[$API_HOST]/api/users"
```

### Response

**If succeeds**, returns the created user.

```Status: 201 Created```

``` json
{
  "id": 1001,
  "email": "john@example.com",
  "inserted_at": "2016-12-16T12:35:42.965729"
  ...
}
```

For errors responses, see the [response status codes documentation](#response-status-codes).
