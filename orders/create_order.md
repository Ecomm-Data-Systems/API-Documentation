# Orders::Create Order

After you have recieved a successful response from Stripe, you may now submit the order to the API for processing. The success key you get from Stripe will need to be added to your post body to create the order.

POST:
```bash
/api/v1/orders
```

Body Example:
```bash
{
    "order": {"success_key": "goooooaaaaallll",
              "total_amount": "456.78",
              "total_tax": "23.45",
              "total_shipping": "56.78",
              "item_subtotal_amount": "123.45",
              "gift": false,
              "wrapping": true,
              "recipient_name": "Barbara",
              "gift_message": "Thank you for the dam water",
              "shipping_name": "required name",
              "shipping_address1": "123 somewhere", 
              "shipping_city": "Thayne", 
              "shipping_state": "WY", 
              "shipping_postal": "12345", 
              "billing_name": "optional name",
              "billing_address1": "321 anywhere", 
              "billing_city": "Afton", 
              "billing_state": "WY", 
              "billing_postal": "54321"},
    "order_items": [
        {"order_item": {"product_apikey": "mSWbktAMXZGXUP8OsKPQFQ", 
                        "quantity": "1", 
                        "item_amount": "123.45", 
                        "total_amount": "123.45"}}
    ],
    "customer": {"first_name": "Murray", 
                 "last_name": "Moose", 
                 "mobile": "", 
                 "email": "murray@stoneflyranch.com"} 
}
```

Example response:
```bash
```
