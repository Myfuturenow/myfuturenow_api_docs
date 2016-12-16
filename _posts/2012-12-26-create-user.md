---
category: User
rest_uri: '/api/v1/users'
title: 'Create a User (v1)'
type: 'POST'

layout: null
---

This method allows users to create a new user.

### Request

* The headers must include a **valid authentication token**.
* **The body can't be empty** and must include at least the email attribute, a `string` that will be used as the email-address of the user.

```Authentication: Token TOKEN```

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
  "current_address_udprn": "12345678"
}
```

### Response

**If succeeds**, returns the created user.

```Status: 201 Created```

``` json
{
  "id": 1001,
  "email": "john@example.com"
  ...
}
```

For errors responses, see the [response status codes documentation](#response-status-codes).
