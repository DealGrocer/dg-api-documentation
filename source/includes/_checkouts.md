# Checkouts

## Summary

> #### Request

```shell
HTTP/1.1 GET /v1/checkout
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "checkout": {
      "can-complete": false,
      "total-php": "₱23,960.00",
      "balance-php": "₱23,960.00"
    },
    "credits": {
      "total-usd": "$50.00",
      "in-use": false,
      "in-use-usd": "$0.00",
      "balance-usd": "$50.00"
    },
    "cards": [
      {
        "token": "8hmr52",
        "type": "American Express",
        "expiry-month": "12",
        "expiry-year": "2020",
        "card-number-last-4": "0005"
      },
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

Get checkout summary.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Turn On Usage of Prepaid Credits

> #### Request

```shell
HTTP/1.1 POST /v1/checkout/prepayment/use
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "checkout": {
      "can-complete": false,
      "total-php": "₱23,960.00",
      "balance-php": "₱21,521.54"
    },
    "credits": {
      "total-usd": "$50.00",
      "in-use": true,
      "in-use-usd": "$50.00",
      "balance-usd": "$0.00"
    },
    "cards": [
      {
        "token": "8hmr52",
        "type": "American Express",
        "expiry-month": "12",
        "expiry-year": "2020",
        "card-number-last-4": "0005"
      },
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

Turn on usage of prepaid credits.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Turn Off Usage of Prepaid Credits

> #### Request

```shell
HTTP/1.1 POST /v1/checkout/prepayment/unuse
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "checkout": {
      "can-complete": false,
      "total-php": "₱23,960.00",
      "balance-php": "₱23,960.00"
    },
    "credits": {
      "total-usd": "$50.00",
      "in-use": false,
      "in-use-usd": "$0.00",
      "balance-usd": "$50.00"
    },
    "cards": [
      {
        "token": "8hmr52",
        "type": "American Express",
        "expiry-month": "12",
        "expiry-year": "2020",
        "card-number-last-4": "0005"
      },
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

Turn off usage of prepaid credits.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Checkout Using Prepaid Credits

> #### Request

```shell
HTTP/1.1 POST /v1/checkout/prepaid
Content-Type: application/json
Authorization: Bearer :session
```

> #### Success

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "deals": [
    {
      "name": "1 Pint of Merry Moo Ice Cream (For Pick-Up) ",
      "merchant-name": "Merry Moo",
      "end-of-redemption": "2016-11-30",
      "redeemability": "352 DAYS LEFT",
      "coupons": "2 COUPONS"
    }
  ],
  "checkout": {
    "total-amount-php": "₱440.00"
  }
}
```

> #### Failure

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "errors": {
    "message": "There was a problem processing your payment. Please try again."
  }
}
```

Checkout using prepaid credits.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Checkout Using Credit Cards

> #### Request

```shell
HTTP/1.1 POST /v1/checkout/card
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "token": token,
    "installment": false
  }
}
```

> #### Success

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "deals": [
    {
      "name": "1 Pint of Merry Moo Ice Cream (For Pick-Up) ",
      "merchant-name": "Merry Moo",
      "end-of-redemption": "2016-11-30",
      "redeemability": "352 DAYS LEFT",
      "coupons": "2 COUPONS"
    }
  ],
  "checkout": {
    "total-amount-php": "₱440.00"
  }
}
```

> #### Failure

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "errors": {
    "message": "Your bank did not authorize this transaction. Please contact your bank for further details."
  }
}
```

Checkout using credit cards. Set the `installment` parameter to `true` to make an installment payment.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
token | true | 3kbnhw
installment | false | false
