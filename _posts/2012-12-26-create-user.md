---
category: User
rest_uri: '/api/v1/users'
title: 'Create a User'
type: 'POST'

layout: null
---

This method allows users to create a new user.

### Request

* The headers must include a **Valid Authentication Token** and an **Accept** header
* The mandatory user fields are `email`, `first_name` and `last_name`

Request headers:

```
Authentication: Token TOKEN
Accept: application/vnd.myfuturenow.v1+json
Content-Type: application/json
```

Request body:

``` json
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
  "current_address_street": "1 The Larch",
  "current_address_locality": "Larchington",
  "current_address_county": "Larchshire",
  "current_address_postcode": "LA1 1AA",
  "current_address_udprn": "12345678",
  "pension_employer_name": "Royal Mail",
  "pension_start_year": 1993
}
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
