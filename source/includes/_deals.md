# Deals

## Mobile Dashboard

> #### Request

```shell
HTTP/1.1 GET /v1/dashboard/mobile?location-name=LOCATION-NAME
Authorization: Bearer SESSION
```

> #### Dashboard Found

```shell
HTTP/1.1 200 OK

{
  "data":{
    "location":{
      "name":"Makati",
      "merchant-names":[
        "Crosswinds Resort Suites",
        "Utopia Resort & Spa",
        "Mandala Spa & Villas",
        "The Manor at Camp John Hay"
      ]
    },
    "deals":[
      {
        "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswind Resort Suites",
        "discount-price":"₱3,600",
        "original-price":"₱4,500",
        "available":5,
        "location-names":[
          "Makati",
          "Tagaytay"
        ],
        "rating":5,
        "badge":"Redeem Now",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      },
      {
        "name":"Sampaguita Duplex Suite for 2 with Breakfast and Massage",
        "merchant-name":"Utopia Resort & Spa",
        "discount-price":"₱7,500",
        "original-price":"₱8,990",
        "available":5,
        "location-names":[
          "Makati"
        ],
        "rating":4,
        "badge":"₱2,500 / 3-Months",
        "cover-photo-url":"https://cloudfront.net/fdsjkghdskj/hfkdjhfsdjkg.jpg"
      }
    ],
    "expiring-coupons":[
      {
        "notice":"2 Days Left",
        "deal-name":"Overnight Stay in 1-Bedroom Suite for Up to 4 Guests",
        "merchant-name":"Crosswinds Resort Suites"
      },
      {
        "notice":"1 Day Left",
        "deal-name":"Arstisanal Whole Cakes For Pick-Up, Valid Daily Including Holidays",
        "merchant-name":"Holiday Inn & Suites Makati"
      }
    ]
  }
}
```

Get information necessary for rendering the mobile dashboard.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
location-name | true | Makati


## Deals By Collection

> #### Request

```shell
HTTP/1.1 GET /v1/collections/:collection/deals
Authorization: Bearer SESSION
```

> Summary & Deals Found

```shell
HTTP/1.1 200 OK

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
Authorization: Bearer SESSION
```

> Summary & Deals Found

```shell
HTTP/1.1 200 OK

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
location | true | dining



## Deal

> #### Request

```shell
HTTP/1.1 GET /v1/deals/:deal
Authorization: Bearer SESSION
```

> #### Deal Found

```shell
HTTP/1.1 200 OK

{
  "data":{
    "name":"Stay in 1-Bedroom Suite for Up to 4 Guests",
    "merchant-name":"Crosswind Resort Suites",
    "discount-price":"P3600",
    "original-price":"P4500",
    "installment-price":"P18678",
    "available":5,
    "locations":[
      {
        "name":"Makati",
        "key":"makati",
        "address":"Ground Level, Somerset Olympia, Makati Ave. cor. Sto. Tomas St., Makati City",
        "latitude":"3248235789",
        "longitude":"432563278",
        "phone-numbers":[
          "+63 2 432 8579",
          "+63 2 573 8456"
        ]
      }
    ],
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
	    	"name":"Makati",
	    	"key":"makati",
	    	"options":[
	    		{
	    			"name":"Schedule",
	    			"key":"Schedule",
	    			"values":[
	    				{
	    					"name":"Morning"
	    					"key":"Morning"
	    					"available":3
	    				},
	    				{
	    					"name":"Evening"
	    					"key":"Evening"
	    					"available":2
	    				}
	    			]
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
