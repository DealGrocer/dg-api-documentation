# Collections

> #### Request

```shell
HTTP/1.1 GET /v1/collections
Authorization: Bearer SESSION
```

> #### Collections Found

```shell
HTTP/1.1 200 OK

{
  "data":[
    {
      "name":"Dining",
      "key":"dining"
    },
    {
      "name":"Getaways",
      "key":"getaways"
    },
    {
      "name":"Hotels",
      "key":"hotels"
    }
  ]
}
```

Get collection listing.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
