# Coupons

## Summary

> #### Request

```shell
HTTP/1.1 GET /v1/coupons
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "sections": [
    {
      "name": "ENDING SOON",
      "deals": [
        {
          "id": "5603d92269702d4042800100",
          "name": "P500 Worth of Award-Winning Fare by Chef JP Anglo",
          "merchant-name": "SARSA Kitchen+Bar",
          "end-of-redemption": "2015-12-28",
          "redeemability": "7 DAYS LEFT",
          "coupons": "1 COUPONS"
        }
      ]
    },
    {
      "name": "REDEEMABLE NOW",
      "deals": [
        {
          "id": "561c6d7f69702d2ee26b0000",
          "name": "Weekend Japanese Buffet with Unlimited Iced Tea",
          "merchant-name": "Midas Hotel and Casino",
          "end-of-redemption": "2016-02-21",
          "redeemability": "62 DAYS LEFT",
          "coupons": "1 COUPONS"
        }
      ]
    },
    {
      "name": "UPCOMING",
      "deals": [
        {
          "id": "55b7156769702d20c3a70000",
          "name": "Early Bird's Lovely Weekday Breakfast Special for 2 ",
          "merchant-name": "Early Bird Breakfast Club",
          "end-of-redemption": "2016-03-21",
          "redeemability": "91 DAYS LEFT",
          "coupons": "3 COUPONS"
        }
      ]
    }
  ]
}
```

Get coupon summary.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000



## List by Deal

> #### Request

```shell
HTTP/1.1 GET /v1/coupons/:deal
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "deal": {
      "name": "P500 Worth of Award-Winning Fare by Chef JP Anglo",
      "merchant-name": "SARSA Kitchen+Bar",
      "terms": "- One (1) coupon is valid for Php500 Worth of Food (NOT valid for drinks and for retail items).\r\n- Redeemable Mondays to Fridays only from October 14, 2015 to November 16, 2015 excluding declared holidays.\r\n- Valid at SARSA Kitchen+Bar The Fort, Makati or SM Mall of Asia branch. Branch chosen during purchase is FINAL and CANNOT be changed afterwards.\r\n- Valid for dine-in only. Not valid for takeout and delivery. Maximum of 2 coupons per table, per visit (regardless if under 1 name or different names). No splitting of bills allowed.\r\n- Reservations are required 24 hours in advance. Subject to seat availability. Reserve early: SARSA Kitchen+Bar will strictly honor 20 coupons per day to ensure high quality of service. To aid in redemption, please let them know that you have a Deal Grocer coupon.\r\n- Coupon printout & a valid government-issued ID must be presented before ordering. No name changes will be accommodated. If coupon will be transferred, a valid ID of the coupon owner must be presented together with the printout of the coupon.\r\n- Coupon value must be used in 1 visit. Buy as many as you want. Not valid for cash back. Not valid with other promos and discounts, such as Senior Citizen, PWD or Diplomat.\r\n- Coupon can be used to pay for taxes and charges. Any purchases in excess of the coupon value must be settled directly with the merchant, subject to applicable taxes and charges.",
      "terms-html": "<ul>\n<li>One (1) coupon is valid for Php500 Worth of Food (NOT valid for drinks and for retail items).</li>\n<li>Redeemable Mondays to Fridays only from October 14, 2015 to November 16, 2015 excluding declared holidays.</li>\n<li>Valid at SARSA Kitchen+Bar The Fort, Makati or SM Mall of Asia branch. Branch chosen during purchase is FINAL and CANNOT be changed afterwards.</li>\n<li>Valid for dine-in only. Not valid for takeout and delivery. Maximum of 2 coupons per table, per visit (regardless if under 1 name or different names). No splitting of bills allowed.</li>\n<li>Reservations are required 24 hours in advance. Subject to seat availability. Reserve early: SARSA Kitchen+Bar will strictly honor 20 coupons per day to ensure high quality of service. To aid in redemption, please let them know that you have a Deal Grocer coupon.</li>\n<li>Coupon printout &amp; a valid government-issued ID must be presented before ordering. No name changes will be accommodated. If coupon will be transferred, a valid ID of the coupon owner must be presented together with the printout of the coupon.</li>\n<li>Coupon value must be used in 1 visit. Buy as many as you want. Not valid for cash back. Not valid with other promos and discounts, such as Senior Citizen, PWD or Diplomat.</li>\n<li>Coupon can be used to pay for taxes and charges. Any purchases in excess of the coupon value must be settled directly with the merchant, subject to applicable taxes and charges.</li>\n</ul>\n",
      "redemption": "October 14, 2015 - December 28, 2015"
    },
    "coupons": [
      {
        "code": "C6WM-3D7T-ZRVXJ-1C8F0H",
        "recipient-name": "Erol Fornoles",
        "recipient-birthdate": "August 31, 1979"
      }
    ]
  }
}
```

Get coupon listing by deal.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
deal | true | 5603d92269702d4042800100



## Count

> #### Request

```shell
HTTP/1.1 GET /v2/coupons/count
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "count": 104
  }
}
```

Get coupon count.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
