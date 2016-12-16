---
title: 'Response status codes'

layout: null
---

### Success

Successes differ from errors in that their body may not be a simple response object with a code and a message. The headers however are consistent across all calls:

* `GET`, `PUT`, `PATCH`, `DELETE` return `200 OK` on success
* `POST` returns 201 on success

### Error

Error responses are simply returning [standard HTTP error codes](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html) along with some additional information:

* The error code is sent back as a status header
* The body includes a message object (for debugging and/or display purposes)

For a call with an invalid authentication token, for example:

```Status: 401 Access denied```

``` json
{
  "message": "Access denied: Invalid authentication token"
}
```
