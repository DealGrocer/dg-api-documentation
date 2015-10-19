# Locations

## Current Location

> Request

```shell
HTTP/1.1 GET /v1/location?latitude=LATITUDE&longitude=LONGITUDE&accuracy=ACCURACY
Authorization: Bearer SESSION
```

> Location Found

```shell
HTTP/1.1 200 OK

{
  "data": {
    "location": {
      "name": "Makati"
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
accuracy | true | 30



## Locations

> Request

```shell
HTTP/1.1 GET /v1/locations?location-name=Makati
Authorization: Bearer SESSION
```

> Locations Found

```shell
HTTP/1.1 200 OK

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
location-name | true | Makati
