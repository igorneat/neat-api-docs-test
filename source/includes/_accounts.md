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