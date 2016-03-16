# Orders

## Prepare

> #### New Order For A Given Deal And Branch Without Pickers

> ##### Request

```shell
HTTP/1.1 GET /platform/v2/order/deals/:deal/branches/:branch
Content-Type: application/json
Authorization: Bearer :session
```

> ##### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "variants": [
      {
        "id": "56276e9269702d3c6d980000",
        "available": 4
      }
    ]
  }
}
```

> #### New Order For A Given Deal And Branch With Pickers

> ##### Request

```shell
HTTP/1.1 GET /platform/v2/order/deals/:deal/branches/:branch
Content-Type: application/json
Authorization: Bearer :session
```

> ##### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "variants": [
      {
        "id": "56276e9269702d3c6d900000",
        "available": 4,
        "property-name": "Schedule",
        "property-value": "Monday"
      },
      {
        "id": "56276e9269702d3c6d910000",
        "available": 5,
        "property-name": "Schedule",
        "property-value": "Tuesday"
      },
      {
        "id": "56276e9269702d3c6d920000",
        "available": 3,
        "property-name": "Schedule",
        "property-value": "Wednesday"
      },
      {
        "id": "56276e9269702d3c6d930000",
        "available": 1,
        "property-name": "Schedule",
        "property-value": "Thursday"
      },
      {
        "id": "56276e9269702d3c6d940000",
        "available": 2,
        "property-name": "Schedule",
        "property-value": "Friday"
      }
    ]
  }
}
```

Prepare an order for a given deal and branch. Returns information necessary for rendering the buying screen.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
deal | true | 56276e9269702d3c6d970000
branch | true | 56273ab169702d425ca20000



## Post

> #### New Order For Myself Of A Given Deal And Branch Without Pickers

> ##### Request

```shell
HTTP/1.1 POST /platform/v2/order/deals/:deal/branches/:branch
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "order": {
      "variant-id": :variant,
      "quantity": :quantity,
    }
  }
}
```

> ##### Response: Success

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

> ##### Response: Deal Or Branch No Longer Available

```shell
HTTP/1.1 404 OK
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, this deal is no longer available."
  }
}
```

> ##### Response: Insufficient Stocks Available

```shell
HTTP/1.1 400 OK
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, someone beat you to it. Please select a lower quantity."
  },
  "data": {
    "variants": [
      {
        "id": "56276e9269702d3c6d980000",
        "available": 4
      }
    ]
  }
}
```

> #### New Order For Someone Else Of A Given Deal And Branch Without Pickers

> ##### Request

```shell
HTTP/1.1 POST /platform/v2/order/deals/:deal/branches/:branch
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "order": {
      "variant-id": :variant,
      "quantity": :quantity,
      "recipient": {
        "firstname": :recipient-firstname,
        "lastname": :recipient-lastname
      }
    }
  }
}
```

> ##### Response: Success

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

> ##### Response: Deal Or Branch No Longer Available

```shell
HTTP/1.1 404 OK
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, this deal is no longer available."
  }
}
```

> ##### Response: Insufficient Stocks Available

```shell
HTTP/1.1 400 OK
Content-Type: application/json

{
  "errors": {
    "message": "Uh oh, someone beat you to it. Please select a lower quantity."
  },
  "data": {
    "variants": [
      {
        "id": "56276e9269702d3c6d980000",
        "available": 4
      }
    ]
  }
}
```

Post an order for the given deal and branch.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
deal | true | 56276e9269702d3c6d970000
branch | true | 56273ab169702d425ca20000
variant | true | 56276e9269702d3c6d980000
quantity | true | 1
recipient-firstname | false | John
recipeint-lastname | false | Doe
