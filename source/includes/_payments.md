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