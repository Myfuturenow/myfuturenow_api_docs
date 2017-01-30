---
category: Introduction
title: Authentication
layout: null
---

You will have received an **API Token** from MyFutureNow technical team. Authenticate your account when using the API by including your API token as a HTTP header when making a request.

```
Authorization: Token [API_TOKEN]
```

Your API token carries many privileges, so be sure to keep it secret! Do not share your secret API token in publicly accessible areas such GitHub, client-side code, and so forth.

We recommend that all API requests be made over HTTPS (SSL). API requests without authentication will fail.
