# Sessions

## Signup Validation

> #### Request

```shell
HTTP/1.1 POST /v1/signup/validation

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
```

> #### Signup Validation Failed

```shell
HTTP/1.1 400 Bad Request

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
HTTP/1.1 POST /v1/signup

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

{
  "data": {
    "session": "561b671b4f72695642000000"
  }
}
```

> #### Signup Failed

```shell
HTTP/1.1 400 Bad Request

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
HTTP/1.1 POST /v1/signup/confirmation
Authorization: Bearer SESSION

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
HTTP/1.1 POST /v1/authentication

{
  "data": {
    "email": email,
    "password": password,
  }
}
```

> #### Authentication successful.

```shell
HTTP/1.1 200 OK

{
  "data": {
    "session": "561b671b4f72695642000000"
  }
}
```

> #### Authentication failed.

```shell
HTTP/1.1 401 Unauthorized

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
