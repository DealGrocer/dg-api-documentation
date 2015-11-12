# Deals

## Mobile Dashboard

> #### Request

```shell
HTTP/1.1 GET /v1/dashboard/mobile?location=:location&page=:page
Content-Type: application/json
Authorization: Bearer :session
```

> #### Dashboard Found

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "location":{
      "name":"Makati",
      "key":"makati",
      "merchant-names":[
        "Dillingers 1903 Steak-Brew",
        "Kafe Batwan by Sarsa",
        "Sugarleaf Makati"
      ]
    },
    "collections":[
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
      },
      {
        "name":"Beauty & Fitness",
        "key":"beauty"
      },
      {
        "name":"Experiences",
        "key":"experiences"
      },
      {
        "name":"Our Fresh Picks",
        "key":"new"
      }
    ],
    "deals":[
      {
        "id":"56276e9269702d3c6d970000",
        "name":"Greeka Kouzina Feast: Choose Your Own 3-Course Meal for 2",
        "merchant-name":"Greeka Kouzina",
        "discount-price":"₱1,100.00",
        "original-price":"₱1,650.00",
        "available":10,
        "location-names":[
          "Pasig",
          "Quezon City",
          "San Juan"
        ],
        "rating":null,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/5629cd9d69702d5de1190000/cover-2015-10-23.jpg"
      },
      {
        "id":"561c5de469702d7789830000",
        "name":"Taiwanese All-You-Can-Eat Hot Pot (Valid Daily)",
        "merchant-name":"Huat Pot",
        "discount-price":"₱599.00",
        "original-price":"₱750.00",
        "available":53,
        "location-names":[
          "San Juan"
        ],
        "rating":3.909090909090909,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/561df87b69702d2ee2d40000/cover-2015-10-14.jpg"
      },
      {
        "id":"56120af469702d4d380e0000",
        "name":"P500 Worth of American Comfort Food & Drinks at Dillingers ",
        "merchant-name":"Dillingers 1903 Steak-Brew",
        "discount-price":"₱295.00",
        "original-price":"₱500.00",
        "available":16,
        "location-names":[
          "Makati"
        ],
        "rating":4.333333333333333,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/561769e869702d2ee21f0000/cover-2015-10-09.jpg"
      },
      {
        "id":"5630927a69702d4a97700000",
        "name":"P500 Worth of Filipino Delicacies & Drinks ",
        "merchant-name":"Kafe Batwan by Sarsa",
        "discount-price":"₱350.00",
        "original-price":"₱500.00",
        "available":31,
        "location-names":[
          "Makati"
        ],
        "rating":null,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/5630927a69702d4a97730000/cover-2015-10-28.jpg"
      },
      {
        "id":"563092e669702d4a9a860000",
        "name":"P500 Worth of Deliciously Nutritious Food & Drinks at Sugarleaf ",
        "merchant-name":"Sugarleaf Makati",
        "discount-price":"₱295.00",
        "original-price":"₱500.00",
        "available":11,
        "location-names":[
          "Makati"
        ],
        "rating":null,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/563092e769702d4a9a8a0000/cover-2015-10-28.jpg"
      },
      {
        "id":"5629b06869702d5de4100000",
        "name":"P1000 Worth of Your Favorite Comfort Food & More",
        "merchant-name":"Relik Restaurant and Bar ",
        "discount-price":"₱500.00",
        "original-price":"₱1,000.00",
        "available":6,
        "location-names":[
          "Bgc",
          "Taguig"
        ],
        "rating":null,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/562a0b3469702d5de43c0000/cover-2015-10-23.jpg"
      },
      {
        "id":"5627187169702d3c70600000",
        "name":"Chakra Café's 1-Day 100% Organic Elixir Juice Cleanse ",
        "merchant-name":"Chakra Café",
        "discount-price":"₱1,110.00",
        "original-price":"₱1,575.00",
        "available":21,
        "location-names":[
          "Bgc",
          "Taguig"
        ],
        "rating":4,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/5628b52469702d4259420100/cover-2015-10-22.jpg"
      },
      {
        "id":"5627195869702d4259b90000",
        "name":"Chakra Café's 3-Day 100% Organic Elixir Juice Cleanse",
        "merchant-name":"Chakra Café",
        "discount-price":"₱3,050.00",
        "original-price":"₱4,350.00",
        "available":12,
        "location-names":[
          "Bgc",
          "Taguig"
        ],
        "rating":4,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/5628b4d369702d425c290100/cover-2015-10-22.jpg"
      },
      {
        "id":"5627763669702d4259ca0000",
        "name":"Chic and Elegant Private Party Package for 10 ",
        "merchant-name":"Back of the House",
        "discount-price":"₱18,000.00",
        "original-price":"₱25,000.00",
        "available":1,
        "location-names":[
          "Quezon City"
        ],
        "rating":null,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/56292a2b69702d1417240000/cover-2015-10-23.jpg"
      },
      {
        "id":"55ed23e369702d66fe290000",
        "name":"Weekday Treat: P500 Worth of Famous Shibuya Toast & More ",
        "merchant-name":"Café Shibuya",
        "discount-price":"₱300.00",
        "original-price":"₱500.00",
        "available":41,
        "location-names":[
          "Quezon City"
        ],
        "rating":null,
        "badge":"Redeem Now",
        "cover-photo-url":"https://dxjamgtjhgl48.cloudfront.net/uploads/cover_photo/image/55f8f2a769702d3446a80000/cover-2015-09-16.jpg"
      }
    ],
    "expiring-coupons":[
      {
        "notice":"4 Days Left",
        "deal-name":"P300 Worth of Food and Drinks at Serenitea ",
        "merchant-name":"Serenitea"
      },
      {
        "notice":"4 Days Left",
        "deal-name":"P500 Worth of Award-Winning Fare by Chef JP Anglo",
        "merchant-name":"SARSA Kitchen+Bar"
      },
      {
        "notice":"4 Days Left",
        "deal-name":"P500 Worth of Award-Winning Fare by Chef JP Anglo",
        "merchant-name":"SARSA Kitchen+Bar"
      },
      {
        "notice":"7 Days Left",
        "deal-name":"Early Bird's Lovely Weekday Breakfast Special for 2 ",
        "merchant-name":"Early Bird Breakfast Club"
      }
    ],
    "credits":{
      "balance":"$50.00"
    },
    "coupons":{
      "count":86
    }
  }
}
```

Get information necessary for rendering the mobile dashboard.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
location | true | makati
page | false | 1


## Deals By Collection

> #### Request

```shell
HTTP/1.1 GET /v1/collections/:collection/deals
Content-Type: application/json
Authorization: Bearer :session
```

> Summary & Deals Found

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "type":"Collection"
    "name":"Dining",
    "key":"dining",
    "heading":"Satiate your appetite at the most exciting and vibrant dining establishments across the country. Take comfort in the classic restaurants, discover secret spots, and embrace hits-in-the-making – it's a melting pot just waiting to be revealed.",
    "deals":[
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"P3600",
        "original-price":"P4500",
        "available":5,
        "location-names":[
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      },
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"P3600",
        "original-price":"P4500",
        "available":5,
        "location-names":[
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      }
    ]
  }
}
```

Get the summary and deal listing for a specified collection.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
collection | true | dining



## Deals By Location

> #### Request

```shell
HTTP/1.1 GET /v1/locations/:location/deals
Content-Type: application/json
Authorization: Bearer :session
```

> Summary & Deals Found

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "type":"Location"
    "name":"Makati",
    "key":"makati",
    "heading":"Find cool new spots to hang out in Makati, fitness and pampering bargains, unbelievably-priced staycations and incredible dining offers that take you from brunch to late night gimmicks. If you’re looking for value-packed deals in the busiest city in the metro, you’re in the right place.",
    "deals":[
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"P3600",
        "original-price":"P4500",
        "available":5,
        "location-names":[
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      },
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"P3600",
        "original-price":"P4500",
        "available":5,
        "location-names":[
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      }
    ]
  }
}
```

Get the summary and deal listing for a specified location.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
location | true | makati



## All Deals

> #### Request

```shell
HTTP/1.1 GET /v1/deals?page=:page
Content-Type: application/json
Authorization: Bearer :session
```

> Deals Found

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "name":"All Deals",
    "deals":[
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"P3600",
        "original-price":"P4500",
        "available":5,
        "location-names":[
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      }
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"P3600",
        "original-price":"P4500",
        "available":5,
        "location-names":[
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      }
    ]
  }
}
```

Get the listing of all deals.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
page | true | 1



## Deal

> #### Request

```shell
HTTP/1.1 GET /v1/deals/:deal
Content-Type: application/json
Authorization: Bearer :session
```

> #### Single Branch Deal Without Pickers

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
    "merchant-name":"Crosswind Resort Suites",
    "discount-price":"P3600",
    "original-price":"P4500",
    "installment-price":"P18678",
    "available":5,
    "rating":5,
    "badge":"Redeem Now",
    "gist":"San Juan is Manila's smallest city in terms of distance. Despite of this, it is slowly becoming recognized as a mecca for foodies. What started out as a myriad of Chinese restaurants eventually evolved to a melting pot of different cuisines, catering to nearly every craving in existence.",
    "terms":"Valid for Friday, Saturday, or Sunday check-ins from August 22, 2015 to December 27, 2015. Subject to availability.",
    "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
    "carousel-photo-urls":[
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
    ],
    "branches":[
      {
        "id":"540e745169702d79643d0000",
        "name":"Makati",
        "address":"Ground Level, Somerset Olympia, Makati Ave. cor. Sto. Tomas St., Makati City",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ],
        "variants":[
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {},
            "available": 15
          }
        ]
      }
    ]
  }
}
```

> #### Single Branch Deal With Pickers

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
    "merchant-name":"Crosswind Resort Suites",
    "discount-price":"P3600",
    "original-price":"P4500",
    "installment-price":"P18678",
    "available":5,
    "rating":5,
    "badge":"Redeem Now",
    "gist":"San Juan is Manila's smallest city in terms of distance. Despite of this, it is slowly becoming recognized as a mecca for foodies. What started out as a myriad of Chinese restaurants eventually evolved to a melting pot of different cuisines, catering to nearly every craving in existence.",
    "terms":"Valid for Friday, Saturday, or Sunday check-ins from August 22, 2015 to December 27, 2015. Subject to availability.",
    "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
    "carousel-photo-urls":[
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
    ],
    "branches":[
      {
        "id":"540e745169702d79643d0000",
        "name":"SM Aura",
        "address":"Level 4, Food on Four area, BGC, Taguig",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ],
        "variants":[
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {
              "Schedule": "Morning"
            },
            "available": 15
          },
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {
              "Schedule": "Afternoon"
            },
            "available": 18
          }
        ]
      }
    ]
  }
}
```

> #### Multiple Branch Deal Without Pickers

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
    "merchant-name":"Crosswind Resort Suites",
    "discount-price":"P3600",
    "original-price":"P4500",
    "installment-price":"P18678",
    "available":5,
    "rating":5,
    "badge":"Redeem Now",
    "gist":"San Juan is Manila's smallest city in terms of distance. Despite of this, it is slowly becoming recognized as a mecca for foodies. What started out as a myriad of Chinese restaurants eventually evolved to a melting pot of different cuisines, catering to nearly every craving in existence.",
    "terms":"Valid for Friday, Saturday, or Sunday check-ins from August 22, 2015 to December 27, 2015. Subject to availability.",
    "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
    "carousel-photo-urls":[
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
    ],
    "branches":[
      {
        "id":"540e745169702d79643d0000",
        "name":"Makati",
        "address":"Ground Level, Somerset Olympia, Makati Ave. cor. Sto. Tomas St., Makati City",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ],
        "variants":[
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {},
            "available": 15
          }
        ]
      },
      {
        "id":"540e745169702d79643d0000",
        "name":"SM Megamall",
        "address":"2nd Floor (near Cotton On & Toby's Sports Shop), Bldg. A, Mandaluyong",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ],
        "variants":[
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {}
            "available": 18
          }
        ]
      }
    ]
  }
}
```

> #### Multiple Branch Deal With Pickers

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data":{
    "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
    "merchant-name":"Crosswind Resort Suites",
    "discount-price":"P3600",
    "original-price":"P4500",
    "installment-price":"P18678",
    "available":5,
    "rating":5,
    "badge":"Redeem Now",
    "gist":"San Juan is Manila's smallest city in terms of distance. Despite of this, it is slowly becoming recognized as a mecca for foodies. What started out as a myriad of Chinese restaurants eventually evolved to a melting pot of different cuisines, catering to nearly every craving in existence.",
    "terms":"Valid for Friday, Saturday, or Sunday check-ins from August 22, 2015 to December 27, 2015. Subject to availability.",
    "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
    "carousel-photo-urls":[
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg",
      "https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
    ],
    "branches":[
      {
        "id":"540e745169702d79643d0000",
        "name":"SM Aura",
        "address":"Level 4, Food on Four area, BGC, Taguig",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ],
        "variants":[
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {
              "Schedule": "Morning"
            },
            "available": 15
          },
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {
              "Schedule": "Afternoon"
            },
            "available": 18
          }
        ]
      },
      {
        "id":"540e745169702d79643d0000",
        "name":"SM Megamall",
        "address":"2nd Floor (near Cotton On & Toby's Sports Shop), Bldg. A, Mandaluyong",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ],
        "variants":[
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {
              "Schedule": "Morning"
            },
            "available": 15
          },
          {
            "id": "55ffed3869702d1df8920100"
            "properties": {
              "Schedule": "Afternoon"
            },
            "available": 18
          }
        ]
      }
    ]
  }
}
```

Get deal information.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
deal | true | 561c7b0e69702d7789de0000
