# Cards

## List

> #### Request

```shell
HTTP/1.1 GET /v1/cards
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "cards": [
      {
        "token": "3kbnhw",
        "type": "Visa",
        "expiry-month": "12",
        "expiry-year": "2020",
        "card-number-last-4": "7777"
      }
    ]
  }
}
```

Get credit card listing.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Add

> #### Request

```shell
HTTP/1.1 POST /v1/cards
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "nonce": nonce
  }
}
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "token": "8hmr52"
  }
}
```

Add credit card.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
nonce | true |



## Remove

> #### Request

```shell
HTTP/1.1 POST /v1/cards
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "token": token
  }
}
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

Add credit card.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
token | true | 8hmr52

