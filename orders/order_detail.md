# Orders::Order Detail

Retrieve a single order from your account with the ```order_apikey```.

GET:
```bash
/api/v1/orders/:order_apikey
```


Response example
```bash
{
    "order": {
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
            "apikey": "SJgiJeAgWLec4RL6R2Hk_w",
            "name": "Alfonzo Lang",
            "email": "alfonzo.lang4@gmail.com"
        }
    },
    "order_items": [
        {
            "product": {
                "name": "Sleek Iron Plate",
                "quantity": 2,
                "item_amount": "19.78",
                "total_amount": "39.56",
                "status": "OPEN",
                "apikey": "F5tZUYQ-rX2YJH_fFtmqMw"
            }
        }
    ]
}
```
