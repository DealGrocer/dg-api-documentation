# Sessions

## Signup Validation

> #### Request

```shell
HTTP/1.1 POST /v2/signup/validation
Content-Type: application/json

{
  "data": {
    "mobile": mobile,
    "email": email,
    "password": password
  }
}
```

> #### Signup Validation Passed

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

> #### Signup Validation Failed

```shell
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  "errors": {
    "email": "Email is already taken.",
    "password": "Password is too short."
  }
}
```

Check if given signup fields are valid. No actual signup is performed.

Parameter | Required | Sample
--- | --- | ---
mobile | true | +63 012 345 6789
email | true | me@email.com
password | true | hUE4PT7NkuFCuG



## Signup

> #### Request

```shell
HTTP/1.1 POST /v2/signup
Content-Type: application/json

{
  "data": {
    "mobile": mobile,
    "email": email,
    "password": password,
    "firstname": firstname,
    "lastname": lastname,
    "birthdate": birthdate,
    "gender": gender
  }
}
```

> #### Signup Successful

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "session": "561b671b4f72695642000000"
  }
}
```

> #### Signup Failed

```shell
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  "errors": {
    "mobile": "Mobile number is invalid."
  }
}
```

Signup a new user using the given fields

Parameter | Required | Sample
--- | --- | ---
mobile | true | +63 012 345 6789
email | true | me@email.com
password | true | hUE4PT7NkuFCuG
firstname | true | Juan
lastname | true | Dela Cruz
birthdate | true | 1990-01-01
gender | true | Male



## Signup Confirmation

> #### Request

```shell
HTTP/1.1 POST /v2/signup/confirmation
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "code": code
  }
}
```

> #### Signup Confirmation Successful

```shell
HTTP/1.1 200 OK
```

> Signup confirmation failed.

```shell
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  "errors": {
    "code": "Confirmation code is invalid."
  }
}
```

Confirm a user signup.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
code | true | ABCD



## Authentication

> #### Request

```shell
HTTP/1.1 POST /v2/authentication
Content-Type: application/json

{
  "data": {
    "email": email,
    "password": password
  }
}
```

> #### Authentication successful.

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "session": "561b671b4f72695642000000"
  }
}
```

> #### Authentication failed.

```shell
HTTP/1.1 401 Unauthorized
Content-Type: application/json

{
  "errors": {
    "credentials": "No matching email and password found."
  }
}
```

Authenticate an existing user

Parameter | Required | Sample
--- | --- | ---
email | true | me@email.com
password | true | hUE4PT7NkuFCuG

## Reset Password

```shell
HTTP/1.1 POST /v2/password/reset
Content-Type: application/json

{
  "data": {
    "email": email
  }
}
```

> #### Reset Password Successful

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

> #### Reset Password Failed

```shell
HTTP/1.1 404 Not Found
Content-Type: application/json

{
  "errors": {
    "email": "No matching email not found."
  }
}
```

Parameter | Required | Sample
--- | --- | ---
email | true | me@email.com
