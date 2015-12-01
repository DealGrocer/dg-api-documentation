# Orders

## Delete

> #### Request 

```shell
HTTP/1.1 DELETE /platform/v1/order
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

Clear a customer's order. Must be called everytime the customer navigates to the deal information page.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Get Order Summary per Branch

> #### Request

```shell
HTTP/1.1 GET /platform/v1/order/branches?product-id=:product
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "branches": [
      {
        "id": "56273ab169702d425ca20000",
        "name": "Banawe",
        "recipients": [
          {
            "firstname": "You",
            "quantity": 1
          },
          {
            "firstname": "John",
            "quantity": 1
          }
        ]
      },
      {
        "id": "562738f969702d3c70700000",
        "name": "Kapitolyo",
        "recipients": []
      },
      {
        "id": "5627384b69702d3c6d730000",
        "name": "Little Baguio",
        "recipients": []
      }
    ],
    "order": {
      "total-php": "₱2,200.00"
    }
  }
}
```

Get summary of order entries grouped by deal branches.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
product | true | 56276e9269702d3c6d970000


## Get Order Entries by Branch

> #### Request

```shell
HTTP/1.1 GET /platform/v1/order/branches/:branch?product-id=:product
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "branch": {
      "id": "56273ab169702d425ca20000",
      "name": "Banawe"
    },
    "product": {
      "id": "56276e9269702d3c6d970000",
      "name": "Greeka Kouzina Feast: Choose Your Own 3-Course Meal for 2"
    },
    "variants": [
      {
        "id": "56276e9269702d3c6d980000",
        "remaining": 4,
        "properties": {}
      }
    ],
    "for-myself": {
      "id": "565d642cea2c4c6725000001",
      "variant": {
        "id": "56276e9269702d3c6d980000",
        "properties": {}
      },
      "quantity": 1
    },
    "for-someone": [
      {
        "id": "565d642cea2c4c6725000002",
        "variant": {
          "id": "56276e9269702d3c6d980000",
          "properties": {}
        },
        "quantity": 1,
        "recipient": {
          "firstname": "John",
          "lastname": "Doe"
        }
      }
    ]
  }
}
```

Get order entries by branch.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
branch | true | 56273ab169702d425ca20000
product | true | 56276e9269702d3c6d970000



## Save Order Entries by Branch

> #### Request

```shell
HTTP/1.1 PATCH /platform/v1/order/branches/:branch?product-id=:product
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "for-myself": {
      "variant-id": variant,
      "quantity": quantity
    },
    "for-someone": [
      {
        "variant-id": variant,
        "quantity": quantity,
        "recipient": {
          "firstname": recipient-firstname,
          "lastname": recipient-lastname
        }
      }
    ]
  }
}
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "branch": {
      "id": "56273ab169702d425ca20000",
      "name": "Banawe"
    },
    "product": {
      "id": "56276e9269702d3c6d970000",
      "name": "Greeka Kouzina Feast: Choose Your Own 3-Course Meal for 2"
    },
    "variants": [
      {
        "id": "56276e9269702d3c6d980000",
        "remaining": 4,
        "properties": {}
      }
    ],
    "for-myself": {
      "id": "565d642cea2c4c6725000001",
      "variant": {
        "id": "56276e9269702d3c6d980000",
        "properties": {}
      },
      "quantity": 1
    },
    "for-someone": [
      {
        "id": "565d642cea2c4c6725000002",
        "variant": {
          "id": "56276e9269702d3c6d980000",
          "properties": {}
        },
        "quantity": 1,
        "recipient": {
          "firstname": "John",
          "lastname": "Doe"
        }
      }
    ]
  }
}
```

Save order entries by branch.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
branch | true | 56273ab169702d425ca20000
product | true | 56276e9269702d3c6d970000
variant | true | 56276e9269702d3c6d980000
quantity | true | 1
recipient-firstname | true | John
recipient-lastname | true | Doe
