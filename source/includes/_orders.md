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



## Get

> #### Request

```shell
HTTP/1.1 GET /platform/v1/order
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "order": {
    "branches": [
      {
        "id": "540e745169702d79643d0000",
        "name": "SM Aura",
        "entries": {
          "for-myself": {
            "id": "565253023edf8c434b000013",
            "variant": {
              "id": "55ffed3869702d1df8920100",
              "properties": {},
              "quantity": 10
            }
          },
          "for-someone": [
            {
              "id": "565253043edf8c434b000014",
              "variant": {
                "id": "55ffed3869702d1df8920100",
                "properties": {},
                "quantity": 10,
                "recipient": {
                  "firstname": "Juan",
                  "lastname": "Dela Cruz"
                }
              }
            }
          ]
        }
      }
    ]
  }
}
```

Get a customer's order information.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## Buy for Myself

> #### Request

```shell
HTTP/1.1 POST /platform/v1/order/entries
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "variant-id": variant-id,
    "quantity": quantity
  }
}
```

> #### Entry Successfully Added

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "entry": {
    "id": "565252073edf8c434b000012"
  },
  "order": {
    "branches": [
      {
        "id": "540e745169702d79643d0000",
        "name": "SM Aura",
        "entries": {
          "for-myself": {
            "id": "565252073edf8c434b000012",
            "variant": {
              "id": "55ffed3869702d1df8920100",
              "properties": {
                "Branch": "SM Aura"
              },
              "quantity": 10
            }
          }
        }
      }
    ]
  }
}
```

> #### Insufficient Stock Available

```shell
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, someone beat you to it. Please select a lower quantity."
  },
  "data": {
    "available": 5
  }
}
```

> #### Deal No Longer Available

```shell
HTTP/1.1 404 Not Found
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, this deal is no longer available."
  }
}
```

Create an order entry for the customer.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
variant-id | true | 56276e9269702d3c6d980000
quantity | true | 5



## Buy for Someone

> #### Request

```shell
HTTP/1.1 POST /platform/v1/order/entries
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "variant-id": variant-id,
    "quantity": quantity,
    "recipient": {
      "firstname": firstname,
      "lastname": lastname
    }
  }
}
```

> #### Entry Successfully Added

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "entry": {
    "id": "565251e43edf8c434b000010"
  },
  "order": {
    "branches": [
      {
        "id": "540e745169702d79643d0000",
        "name": "SM Aura",
        "entries": {
          "for-someone": [
            {
              "id": "565251e43edf8c434b000010",
              "variant": {
                "id": "55ffed3869702d1df8920100",
                "properties": {},
                "quantity": 10,
                "recipient": {
                  "firstname": "Juan",
                  "lastname": "Dela Cruz"
                }
              }
            }
          ]
        }
      }
    ]
  }
}
```

> #### Insufficient Stock Available

```shell
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, someone beat you to it. Please select a lower quantity."
  },
  "data": {
    "available": 5
  }
}
```

> #### Deal No Longer Available

```shell
HTTP/1.1 404 Not Found
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, this deal is no longer available."
  }
}
```

Create an order entry for the customer.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
variant-id | true | 56276e9269702d3c6d980000
quantity | true | 5
firstname | true | Juan
lastname | true | Dela Cruz



## Delete Entry

> #### Request

```shell
HTTP/1.1 DELETE /platform/v1/order/entries/:entry
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "entry": {
    "id": "565253043edf8c434b000014"
  },
  "order": {
    "branches": []
  }
}
```

Delete an order entry for the customer.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
entry | true | 565253043edf8c434b000014
