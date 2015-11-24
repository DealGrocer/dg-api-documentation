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
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "entries": {
          "for-myself": {
            "id": "565420c6ea2c4c0ba4000008",
            "variant": {
              "id": "55f7b01169702d47c11b0000",
              "properties": {
                "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
              },
              "quantity": 1
            }
          },
          "for-someone": [
            {
              "id": "565420d3ea2c4c0ba700000f",
              "variant": {
                "id": "55f7b01169702d47c11b0000",
                "properties": {
                  "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
                },
                "quantity": 1,
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
  },
  "deal": {
    "id": "55f7b01169702d47c1190000",
    "available": 0,
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "address": "Makati",
        "latitude": 14.554729,
        "longitude": 121.0244452,
        "phone-numbers": [],
        "variants": [
          {
            "id": "55f7b01169702d47c11b0000",
            "available": 1,
            "properties": {
              "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
            }
          },
          {
            "id": "55f7b01169702d47c11c0000",
            "available": 7,
            "properties": {
              "Schedule": "November 24-December 1 (Tuesday & Thursday), 6-9PM"
            }
          }
        ]
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
    "id": "56542125ea2c4c0b9f000007"
  },
  "order": {
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "entries": {
          "for-myself": {
            "id": "56542125ea2c4c0b9f000007",
            "variant": {
              "id": "55f7b01169702d47c11b0000",
              "properties": {
                "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
              },
              "quantity": 1
            }
          }
        }
      }
    ]
  },
  "deal": {
    "id": "55f7b01169702d47c1190000",
    "available": 1,
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "address": "Makati",
        "latitude": 14.554729,
        "longitude": 121.0244452,
        "phone-numbers": [],
        "variants": [
          {
            "id": "55f7b01169702d47c11b0000",
            "available": 2,
            "properties": {
              "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
            }
          },
          {
            "id": "55f7b01169702d47c11c0000",
            "available": 7,
            "properties": {
              "Schedule": "November 24-December 1 (Tuesday & Thursday), 6-9PM"
            }
          }
        ]
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
variant-id | true | 55f7b01169702d47c11b0000
quantity | true | 1



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
    "id": "56542184ea2c4c0baa000007"
  },
  "order": {
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "entries": {
          "for-someone": [
            {
              "id": "56542184ea2c4c0baa000007",
              "variant": {
                "id": "55f7b01169702d47c11b0000",
                "properties": {
                  "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
                },
                "quantity": 1,
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
  },
  "deal": {
    "id": "55f7b01169702d47c1190000",
    "available": 1,
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "address": "Makati",
        "latitude": 14.554729,
        "longitude": 121.0244452,
        "phone-numbers": [],
        "variants": [
          {
            "id": "55f7b01169702d47c11b0000",
            "available": 2,
            "properties": {
              "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
            }
          },
          {
            "id": "55f7b01169702d47c11c0000",
            "available": 7,
            "properties": {
              "Schedule": "November 24-December 1 (Tuesday & Thursday), 6-9PM"
            }
          }
        ]
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
variant-id | true | 55f7b01169702d47c11b0000
quantity | true | 1
firstname | true | Juan
lastname | true | Dela Cruz



## Update Entry

> #### Request

```shell
HTTP/1.1 PATCH /platform/v1/order/entries/:entry
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

> #### Entry Successfully Updated

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "entry": {
    "id": "56542184ea2c4c0baa000007"
  },
  "order": {
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "entries": {
          "for-someone": [
            {
              "id": "56542184ea2c4c0baa000007",
              "variant": {
                "id": "55f7b01169702d47c11b0000",
                "properties": {
                  "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
                },
                "quantity": 2,
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
  },
  "deal": {
    "id": "55f7b01169702d47c1190000",
    "available": 1,
    "branches": [
      {
        "id": "543f96b669702d45fa990000",
        "name": "Makati",
        "address": "Makati",
        "latitude": 14.554729,
        "longitude": 121.0244452,
        "phone-numbers": [],
        "variants": [
          {
            "id": "55f7b01169702d47c11b0000",
            "available": 2,
            "properties": {
              "Schedule": "November 10-17 (Tuesday-Thursday), 6-9PM"
            }
          },
          {
            "id": "55f7b01169702d47c11c0000",
            "available": 7,
            "properties": {
              "Schedule": "November 24-December 1 (Tuesday & Thursday), 6-9PM"
            }
          }
        ]
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
entry | true | 565290adea2c4c5a80000003
variant-id | true | 56276e9269702d3c6d980000
quantity | true | 2




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
    "id": "565290adea2c4c5a80000003"
  },
  "order": {
    "branches": []
  },
  "deal": {
    "id": "56276e9269702d3c6d970000",
    "available": 6,
    "branches": [
      {
        "id": "56273ab169702d425ca20000",
        "name": "Banawe",
        "address": "TCC Building, 190 D. Tuazon Street, Santa Mesa Heights, Quezon City",
        "latitude": 14.633504,
        "longitude": 120.998042,
        "phone-numbers": [
          "(02) 219 1023",
          "(0917) 832 1262"
        ],
        "variants": [
          {
            "id": "56276e9269702d3c6d980000",
            "available": 890,
            "properties": {}
          }
        ]
      },
      {
        "id": "562738f969702d3c70700000",
        "name": "Kapitolyo",
        "address": "D-Strip Building, 20 United Street, West Capitol, Kapitolyo, Pasig",
        "latitude": 14.569208,
        "longitude": 121.0601574,
        "phone-numbers": [
          "(02) 218 4859"
        ],
        "variants": [
          {
            "id": "56298ce869702d35c3250000",
            "available": 952,
            "properties": {}
          }
        ]
      },
      {
        "id": "5627384b69702d3c6d730000",
        "name": "Little Baguio",
        "address": "285 P. Guevarra Street, Little Baguio, San Juan",
        "latitude": 14.60225,
        "longitude": 121.034294,
        "phone-numbers": [
          "(02) 624 5974",
          "(0917) 629 2818"
        ],
        "variants": [
          {
            "id": "56298ce969702d35c3260000",
            "available": 921,
            "properties": {}
          }
        ]
      }
    ]
  }
}
```

Delete an order entry for the customer.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
entry | true | 565253043edf8c434b000014
