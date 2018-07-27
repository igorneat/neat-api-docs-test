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
  "first_name": "John",
  "last_name": "Doe",
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
  "first_name": "John",
  "last_name": "Doe",
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
