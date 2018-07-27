---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - users
  - accounts
  - payments
  - errors

search: true
---

# Introduction

Welcome to Neat API.

# Authentication

> ### DEFINITION
> POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/auth
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/auth"
   -d email=test@text.com \
   -d password=12345
```

> ### Example Response

```json
{
  "id": "user_OCHy0G45SLmKcRZc",
  "created_at": 1452249298,
  "email": "2@test.com",
  "first_name": null,
  "last_name": null,
  "admin": true,
  "account": {
    "id": "acc_WcuWD6gDzNsop4lE",
    "created_at": "2016-01-08 10:34:58 +0000",
    "livemode": true,
    "name": "1",
    "balance": "150000.0",
    "card_number": "1111222233334444",
    "status": "active"
  }
}

```
Authentication.

### HTTP Request

`POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/auth`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------
email | **Y** | string | Email.
password | **Y** | string | Password.

### Returns
Returns a user object if the authentication succeeded. 






















