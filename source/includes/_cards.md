# Cards

## List

> #### Request

```shell
HTTP/1.1 GET /v1/cards
Content-Type: application/json
Authorization: Bearer :session
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "cards": [
      {
        "token": "3kbnhw",
        "type": "Visa",
        "expiry-month": "12",
        "expiry-year": "2020",
        "card-number-last-4": "7777"
      }
    ]
  }
}
```

Get credit card listing.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000

Credit card details are returned as an array of objects, with the following keys and values:

Key | Description
--- | ---
token | Secure token of the credit card. This is the token which needs to be passed to complete a checkout using a credit card.
type | The credit card type. Can be Visa or Mastercard.
expiry-month | The month of expiry.
expiry-year | The year of expiry.
card-number-last-4 | The last 4 digits of the credit card.



## Add

> #### Request

```shell
HTTP/1.1 POST /v1/cards/new
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "nonce": nonce
  }
}
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "token": "8hmr52"
  }
}
```

Add credit card.

Parameter | Required | Sample
--- | --- | --- | ---
session | true | 561b671b4f72695642000000
nonce | true |

Call this to add a new credit card. A NONCE needs to be acquired from Braintree using the supplied credit card details given by the user. Documentation for acquiring a NONCE can be found below:

  - [Braintree: Set Up Your Client] (https://developers.braintreepayments.com/start/hello-client/ios/v3)
  - [Braintree: Credit Cards / Client-Side Implementation](https://developers.braintreepayments.com/guides/credit-cards/client-side/ios/v3)



## Remove

> #### Request

```shell
HTTP/1.1 DELETE /v1/cards/delete
Content-Type: application/json
Authorization: Bearer :session

{
  "data": {
    "token": "8hmr52"
  }
}
```

> #### Response

```shell
HTTP/1.1 200 OK
Content-Type: application/json
```

Remove credit card.

Parameter | Required | Sample
--- | --- | ---
session | true | 561b671b4f72695642000000
token | true | 8hmr52

Remove the current user's credit card identified with the supplied TOKEN. Tokens can be retrieved from the listing of credit cards.
