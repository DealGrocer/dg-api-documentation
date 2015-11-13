# Settings

## Get

> #### Request

```shell
HTTP/1.1 GET /v1/settings
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "user": {
      "fullname": "John Doe",
      "email": "staging@dealgrocer.com"
    },
    "settings": {
      "notify-expiring-coupons": true
    }
  }
}
```

Get user settings.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Update

> #### Request

```shell
HTTP/1.1 PATCH /v1/settings
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "notify-expiring-coupons": notify-expiring-coupons
  }
}
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

Update user settings.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
notify-expiring-coupons | false | true
