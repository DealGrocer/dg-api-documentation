# Locations

## Current Location

> #### Request

```shell
HTTP/1.1 GET /v2/location?latitude=:latitude&longitude=:longitude&accuracy=:accuracy
Content-Type: application/json
Authorization: Bearer :session
```

> #### Location Found

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "location": {
      "name": "Makati",
      "key": "makati"
    }
  }
}
```

Get current location information given the latitude and longitude.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
latitude | true | 14.5525991
longitude | true | 121.0502954
accuracy | false | 30



## Locations

> #### Request

```shell
HTTP/1.1 GET /v2/locations?location=:location
Content-Type: application/json
Authorization: Bearer :session
```

> #### Locations Found

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "Metro Manila":[
      {
        "current":true,
        "name":"Makati",
        "key":"makati",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      },
      {
        "name":"Quezon City",
        "key":"quezon-city",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      },
      {
        "name":"Taguig",
        "key":"taguig",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      },
      {
        "name":"Muntinlupa",
        "key":"muntinlup",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      }
    ],
    "Outside Metro Manila":[
      {
        "name":"Palawan",
        "key":"palawan",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      },
      {
        "name":"Tagaytay",
        "key":"tagaytay",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      },
      {
        "name":"Boracay",
        "key":"boracay",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      },
      {
        "name":"Baguio",
        "key":"baguio",
        "merchant-names":[
          "Crosswinds Resort Suites",
          "Utopia Resort & Spa",
          "Mandala Spa & Villas",
          "The Manor at Camp John Hay"
        ]
      }
    ]
  }
}
```

Get location listing.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
location | true | Makati
