---
category: User
rest_uri: '/api/users'
title: 'Create a User (Customer)'
type: 'POST'

layout: null
---

This method creates a new user (customer registration)

### Attributes

| Attribute name              | Description                          | Mandatory? |
|:----------------------------|:-------------------------------------|-----------:|
| email                       | Customer email address               | Y          |
| _password_                  | _For testing purposes_               | N          |
| first_name                  | Forename(s)                          | Y          |
| last_name                   | Last name(s) _(aka Surname)_         | Y          |
| gender                      | `male`, `female`, `trans` or `other` | N          |
| maiden_name                 | Previous name(s)                     | N          |
| date_of_birth               | e.g. `1991-04-23`                    | Y          |
| phone_number                | Customer _mobile_ phone number       | Y          |
| national_insurance_number   | Full National Insurance number       | Y          |
| year_of_retirement          | Retirement year (e.g. `2044`)        | Y          |
| _current_address:_ street   | Building number & street             | Y          |
| _current_address:_ locality | Town or city                         | Y          |
| _current_address:_ county   | County or region                     | N          |
| _current_address:_ postcode | Full postal code                     | Y          |
| _current_address:_ udprn    | [Unique Delivery Point Reference Number](https://ideal-postcodes.co.uk/documentation/udprn) | N |
| _pension:_ employer_name    | Workplace pension employer name      | Y          |
| _pension:_ start_year       | Pension start year (e.g. `1983`)     | Y          |
| _pension:_ current_value    | Pension current value (£)            | Y          |
| _pension:_ annual_fees_percent | Pension annual fees (%)           | Y          |
| _pension:_ policy_number    | Scheme, Plan or Policy number        | Y          |


### Request

* The headers must include a **Valid Authorization Token** and an **Accept** header
* The mandatory user fields are `email`, `first_name` and `last_name`

Request headers:

```sh
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
  "year_of_retirement": 2044,
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
      "start_year": 1993,
      "current_value": 20000,
      "annual_fees_percent": 0.75,
      "policy_number": "ABC/12345"
    }
  ]
}
```

Example _curl_ command:

```sh
curl -X POST \
  -H "Authorization: Token $API_TOKEN" \
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
    "year_of_retirement": 2044,
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
        "start_year": 1983,
        "current_value": 20000,
        "annual_fees_percent": 0.75,
        "policy_number": "ABC/12345"
      }
    ]
  }' \
  "https://$API_HOST/api/users"
```

### Response

**If succeeds**, returns a summary of the created user data, and a `callback_url`

```
Status: 201 Created
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
