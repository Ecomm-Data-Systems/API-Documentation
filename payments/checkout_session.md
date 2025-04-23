# Payments::Checkout Session

To show the Stripe payment widget on your site, you will need to obtain a valid checkout session.

> :boom: IMPORTANT: I think I have the PXP Development in test mode set incorrectly? I think it is currently collecting taxes for our clients. When we set up the actual EDS stripe account, we will need to make sure that we set the tax settings so that our clients are responsible to set their own origin address.

## Getting a checkout session

POST: ```/api/v1/checkout_session```

Body Example: 
```{
    "line_items": [
        {"stripe_price_id": "{{stripe_price_id}}", "quantity": 2, "flat_ship_rate": 500, "est_delivery_min": 3, "est_delivery_max": 8}
    ],
    "return_url": "{{address you need user to return to after payment}}"
}
```


Example Response:
```
{
    "clientSecret": "cs_test_a188yWtXQAZzDLh8eR4h30ytnotarealsecretGamh1aWBxbGprJz8nnothingtoseehereY2NjYyd4JSUl"

}
```
