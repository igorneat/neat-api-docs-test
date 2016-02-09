---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
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





# Users

Users definition.

## Create a user

> ### DEFINITION
> POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users"
   -d email="test@email.com" \
   -d password="12345" \
   -d telephone_number="+85212341234" \
   -d first_name="John" \
   -d last_name="Doe" \
```

> ### Example Response

```json
{
  "id": "user_OCHy0G45SLmKcRZc",
  "created_at": 1452249298,
  "email": "2@test.com",
  "telephone_number": "+85212341234",
  "first_name": John,
  "last_name": Doe,
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
Users.

### HTTP Request

`POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------
email | **Y** | string | Email.
password | **Y** | string | Password.
telephone_number | **N** | string | Telephone number.
first_name | **N** | string | First name.
last_name | **N** | string | Last name.

### Returns
Returns a user object. Raises an error otherwise.





## Retrieve a user

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/user_OCHy0G45SLmKcRZc"
```

> ### Example Response

```json
{
  "id": "user_OCHy0G45SLmKcRZc",
  "created_at": 1452249298,
  "email": "2@test.com",
  "telephone_number": "+85212341234",
  "first_name": John,
  "last_name": Doe,
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
Retrieve specific user object.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a user object. Raises an error otherwise.





## Retrieve all users

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users"
```

> ### Example Response

```json
{
  "object": "list",
  "data": [
    {
      "id": "user_WN1ja3ZjRJ20QAHX",
      "created_at": 1451923608,
      "email": "test1@test.com",
      "first_name": "John",
      "last_name": "Doe",
      "admin": true
    },
    {
      "id": "user_dXiov7TSWCpOzNQw",
      "created_at": 1451928095,
      "email": "test2@test.com",
      "first_name": "John",
      "last_name": "Doe",
      "admin": true
    }
  ]
}

```
Users.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a list of user objects.






# Payments

Payments definition.

## Create a payment

> ### DEFINITION
> POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments"
   -d amount=400 \
   -d description="test_description" \
   -d account_id="acc_tmnmdPRWjyDSk8LI" \
   -d currency="usd"
```

> ### Example Response

```json
  {
    "id": "pay_5lTUlRwssPxFhM1K",
    "created_at": 1453981414,
    "livemode": true,
    "demo": null,
    "amount": "13.0",
    "currency": "hkd",
    "description": "test_1",
    "merchant_name": "123",
    "category": "shopping",
    "refunded": false,
    "account_balance": "2361.0",
    "request_longitude": "114.1667",
    "request_latitude": "22.25",
    "request_address": "Hong Kong",
    "network_type": "wifi",
    "network_ip": "127.1.0.0",
    "network_operator": "Smartone",
    "wireless_access_point": "MyWifi",
    "status": "succeeded"
  }

```
Payments.

### HTTP Request

`POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------
account_id | **Y** | string | Account ID for this payment.
amount | **Y** | string | Amount.
currency | **Y** | string | 3-letter [ISO code](https://support.tofupay.com/questions/which-currencies-does-tofupay-support) for currency.
description | **N** | string | Description of the payment.

### Returns
Returns a payment object. Raises an error otherwise.





## Retrieve a payment

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments/:payment_id
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments/pay_5lTUlRwssPxFhM1K"
```

> ### Example Response

```json
  {
    "id": "pay_5lTUlRwssPxFhM1K",
    "created_at": 1453981414,
    "livemode": true,
    "demo": null,
    "amount": "13.0",
    "currency": "hkd",
    "description": "test_1",
    "merchant_name": "123",
    "category": "shopping",
    "refunded": false,
    "account_balance": "2361.0",
    "request_longitude": "114.1667",
    "request_latitude": "22.25",
    "request_address": "Hong Kong",
    "network_type": "wifi",
    "network_ip": "127.1.0.0",
    "network_operator": "Smartone",
    "wireless_access_point": "MyWifi",
    "status": "succeeded"
  }

```
Retrieve specific payment object.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments/:payment_id`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a payment object. Raises an error otherwise.





## Retrieve all payments

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments"
```

> ### Example Response

```json
{
  "object": "list",
  "data": [
    {
      "id": "pay_jDkH4tWV5BA2uMHM",
      "created_at": 1453970215,
      "livemode": true,
      "demo": null,
      "amount": "200.0",
      "currency": "hkd",
      "description": "test_1",
      "merchant_name": "123",
      "category": "shopping",
      "refunded": false,
      "account_balance": "2361.0",
      "request_longitude": "114.1667",
      "request_latitude": "22.25",
      "request_address": "Hong Kong",
      "network_type": "wifi",
      "network_ip": "127.1.0.0",
      "network_operator": "Smartone",
      "wireless_access_point": "MyWifi",
      "status": "succeeded"
    },
    {
      "id": "pay_5lTUlRwssPxFhM1K",
      "created_at": 1453981414,
      "livemode": true,
      "demo": null,
      "amount": "13.0",
      "currency": "hkd",
      "description": "test_1",
      "merchant_name": "123",
      "category": "shopping",
      "refunded": false,
      "account_balance": "2361.0",
      "request_longitude": "114.1667",
      "request_latitude": "22.25",
      "request_address": "Hong Kong",
      "network_type": "wifi",
      "network_ip": "127.1.0.0",
      "network_operator": "Smartone",
      "wireless_access_point": "MyWifi",
      "status": "succeeded"
    }
  ]
}

```
Retrieve all payments for all accounts.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/payments`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a list of payment objects.



## Retrieve all payments for an account 

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/accounts/:account_id/payments
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/accounts/acc_tmnmdPRWjyDSk8LI/payments"
```

> ### Example Response

```json
{
  "object": "list",
  "data": [
    {
      "id": "pay_jDkH4tWV5BA2uMHM",
      "created_at": 1453970215,
      "livemode": true,
      "demo": null,
      "amount": "200.0",
      "currency": "hkd",
      "description": "test_1",
      "merchant_name": "123",
      "category": "shopping",
      "refunded": false,
      "account_balance": "2361.0",
      "request_longitude": "114.1667",
      "request_latitude": "22.25",
      "request_address": "Hong Kong",
      "network_type": "wifi",
      "network_ip": "127.1.0.0",
      "network_operator": "Smartone",
      "wireless_access_point": "MyWifi",
      "status": "succeeded"
    },
    {
      "id": "pay_5lTUlRwssPxFhM1K",
      "created_at": 1453981414,
      "livemode": true,
      "demo": null,
      "amount": "13.0",
      "currency": "hkd",
      "description": "test_1",
      "merchant_name": "123",
      "category": "shopping",
      "refunded": false,
      "account_balance": "2361.0",
      "request_longitude": "114.1667",
      "request_latitude": "22.25",
      "request_address": "Hong Kong",
      "network_type": "wifi",
      "network_ip": "127.1.0.0",
      "network_operator": "Smartone",
      "wireless_access_point": "MyWifi",
      "status": "succeeded"
    }
  ]
}

```
Accounts.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/accounts/:account_id/payments`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a list of account objects.







# Accounts

Accounts definition.

## Create a account

> ### DEFINITION
> POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id/accounts

> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/user_WN1ja3ZjRJ20QAHX/accounts
   -d name="test_account" \
   -d card_number="1234123412341234"
```

> ### Example Response

```json
{
  "id": "acc_KVWVWnoSu9MtI9",
  "created_at": 1455009001,
  "livemode": true,
  "name": "test",
  "balance": "0.0",
  "card_number": "1234123412341234",
  "status": "active"
}

```
Accounts.

### HTTP Request

`POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id/accounts`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------
name | **Y** | string | Name for this account.
card_number | **Y** | string | Card number.


### Returns
Returns an account object. Raises an error otherwise.




## Topup account

> ### DEFINITION
> POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/accounts/:account_id/topup

> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/accounts/acc_tmnmdPRWjyDSk8LI/topup
   -d amount="5000"
```

> ### Example Response

```json
{
  "id": "acc_tmnmdPRWjyDSk8LI",
  "created_at": 1452160703,
  "livemode": true,
  "name": "test_account",
  "balance": "5000.0",
  "card_number": "1234123412341234",
  "status": "active"
}

```
Accounts.

### HTTP Request

`POST http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/accounts/:account_id/accounts`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------
amount | **Y** | string | Amount to top up.


### Returns
Returns an account object. Raises an error otherwise.





## Retrieve an account

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id/accounts/:account_id
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/user_7KUEICiqlxUceEL/accounts/acc_KVWVWnoSu9MtI9"
```

> ### Example Response

```json
{
  "id": "acc_KVWVWnoSu9MtI9",
  "created_at": 1455009001,
  "livemode": true,
  "name": "test",
  "balance": "0.0",
  "card_number": "1234123412341234",
  "status": "active"
}

```
Retrieve specific account object.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id/accounts/:account_id`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a account object. Raises an error otherwise.




## Retrieve all user accounts 

> ### DEFINITION
> GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id/accounts
> ### Example Request


```shell
# With shell, you can just pass the correct header with each request
curl "http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/user_spOMe1PKI4dxU9lr/accounts"
```

> ### Example Response

```json
{
  "object": "list",
  "data": [
    {
      "id": "acc_tmnmdPRWjyDSk8LI",
      "created_at": 1452160703,
      "livemode": true,
      "name": "test_account",
      "balance": "0.0",
      "card_number": "1234123412341234",
      "status": "active"
    },
    {
      "id": "acc_tmnmdPRWjyDSk8LI",
      "created_at": 1452160703,
      "livemode": true,
      "name": "test_account",
      "balance": "0.0",
      "card_number": "1234123412341234",
      "status": "active"
    }
  ]
}

```
Accounts.

### HTTP Request

`GET http://neatmvpapidev.ap-southeast-1.elasticbeanstalk.com/v1/users/:user_id/accounts`

### Parameters

Parameter | Required | Type | Description
--------- | ------- | ----------- | -----------


### Returns
Returns a list of account objects for given user.


