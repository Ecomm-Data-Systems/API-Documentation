# Orders::Order List

Filter your request by order status or, you can search for an order number or even a partial order number.

## Find Orders

GET:
```bash
/api/v1/orders
```

To add a status filter you can add this query string.

GET:
```bash
/api/v1/orders?status=OPEN
```

Or to seach for an order using the order number or even a partial order number.

GET:
```bash
/api/v1/orders?search=8675309
```
Example response:
```bash
{
    "orders": [
        {
            "apikey": "gUlSDKpoSyrwQuVD2PX0dA",
            "order_number": "ORD-20250423190015-LNYZ5B",
            "billing_name": "Alfonzo Lang",
            "billing_address1": "4326 Mike Trafficway",
            "billing_address2": null,
            "billing_city": "Wuckertview",
            "billing_state": "VA",
            "billing_postal": "26021-4207",
            "shipping_name": "Alfonzo Lang",
            "shipping_address1": "5296 Mckinley Stravenue",
            "shipping_address2": null,
            "shipping_city": "Westshire",
            "shipping_state": "RI",
            "shipping_postal": "94784",
            "payment_status": null,
            "fulfillment_status": "OPEN",
            "gift": true,
            "wrapping": true,
            "recipient_name": null,
            "gift_message": "Iste ratione dicta. Voluptatum nobis laboriosam. Ut enim laborum.",
            "status": "OPEN",
            "total_amount": "39.56",
            "customer": {
                "name": "alfonzo.lang4@gmail.com"
            }
        },...
    ]
}
```


