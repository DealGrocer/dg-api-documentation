# Installments

## List

> #### Request

```shell
HTTP/1.1 GET /v2/installments
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "installments": [
      {
        "items": [
          {
            "item-caption": "Sunday Brunch for 4 at Café Ilang-Ilang",
            "merchant-name": "The Manila Hotel",
            "cover-photo-url": "https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/55541c0369702d6efe010000/cover-2015-05-14.jpg"
          }
        ],
        "cycles": [
          {
            "state": "PAID",
            "date": "August 2015",
            "amount": "₱2,958.15"
          },
          {
            "state": "PAID",
            "date": "September 2015",
            "amount": "₱2,958.16"
          },
          {
            "state": "PAID",
            "date": "October 2015",
            "amount": "₱2,958.16"
          }
        ],
        "balance-php": "₱0.00",
        "total-php": "₱8,874.47"
      },
      {
        "items": [
          {
            "item-caption": "Overnight Stay in 1-Bedroom Suite for Up to 4 Guests",
            "merchant-name": "Crosswinds Resort Suites",
            "cover-photo-url": "https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/56133c3669702d31b0370000/cover-2015-10-06.jpg"
          },
          {
            "item-caption": "3D2N in a Studio Room for 2",
            "merchant-name": "Crosswinds Resort Suites",
            "cover-photo-url": "https://dxjamgtjhgl48.cloudfront.net/uploads/5524bd3c69702d11291b0000/tb_merchant_tile_photos/553481ff69702d45f8080000/merchant-2015-04-27.jpg"
          }
        ],
        "cycles": [
          {
            "state": "PAID",
            "date": "January 2016",
            "amount": "₱4,050.00"
          },
          {
            "state": "SCHEDULED",
            "date": "February 2016",
            "amount": "₱4,050.00"
          },
          {
            "state": "SCHEDULED",
            "date": "March 2016",
            "amount": "₱4,050.00"
          }
        ],
        "balance-php": "₱8,100.00",
        "total-php": "₱12,150.00"
      }
    ]
  }
}
```

Get installments.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000

Installment details are returned as an array of objects, with the following keys and values:

Key | Description
--- | ---
items | An array specifying the items the given installment covers.
cycles | An array specifying the monthly installment cycles.
balance-php | The remaining balance for the given installment.
total-php | The total amount for the given installment.

