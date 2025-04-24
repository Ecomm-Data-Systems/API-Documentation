# Catalog::Products::Product Detail

Retrieve a single product with the ```product_apikey```.

GET:
```bash
/api/v1/products/:product_apikey
```

Your website will need to accomodate 2 different types of products from the API. ```SIMPLE``` and ```ADVANCED``` products have slightly different data structures. Your Product Detail Page (PDP) should check for what type of product it is and show the correct information.

<br>

### Simple Products

If a product has a ```product_type``` of ```SIMPLE```. It will contain all of the pricing, inventory, sku and dimension data in the product object. If the product is ```ADVANCED``` you will want to [look at advanced products](#advanced-products).

Response example
```json
{
    "product": {
        "name": "Durable Concrete Gloves",
        "product_type": "SIMPLE",
        "description": "<p>Enim quia deleniti. Sint sunt quia. Et cupiditate voluptatibus.</p>",
        "summary": "Accusamus id exercitationem. Voluptatem dolor dignissimos. Rem saepe accusantium.",
        "features": "Maiores et sit. Distinctio esse quaerat. Sapiente et quasi.",
        "specs": "Temporibus laborum ducimus. Vel consequatur placeat. Quia doloremque et.",
        "inventory": 27,
        "keywords": "sales funnel",
        "sku": "474521489024",
        "price": "39.3",
        "discount": "27.83",
        "stripe_price_id": "123456789abcdefg",
        "stripe_taxcode_id": "txcd_99999999",
        "weight": null,
        "length": null,
        "height": null,
        "flat_ship_rate": 500,
        "ship_rate_type": null,
        "est_delivery_min": 5,
        "est_delivery_max": 7,
        "status": "PUBLISHED",
        "apikey": "123imnotarealapikey789"
    },
    "categories": [
        {
            "name": "Sports",
            "apikey": "123imnotarealapikey789"
        }
    ],
    "brand": {
        "name": "Durable Concrete Gloves",
        "apikey": "123imnotarealapikey789"
    }
}
```

<br><br>

### Advanced products

If a product has variants, it will have a product_type of ```ADVANCED``` and the product object will contain an array of variants of that product.

> :bulb: Tip: Your product detail page should detect if the product is advanced and has variants. And then present the user with the variant options.

Note that ```ADVANCED``` products do not have pricing, inventory, sku or dimensions. Those attributes are with the variant.

Response example
```json

{
    "product": {
        "name": "Tshirt",
        "product_type": "ADVANCED",
        "description": "<p>The comfiest tshirt ever.</p>",
        "summary": "",
        "features": " ",
        "specs": "123IMASKU789",
        "keywords": null,
        "stripe_taxcode_id": "txcd_99999999",
        "status": "PUBLISHED",
        "apikey": "R5QdOnotarealkeyOpkQ"
    },
    "images": [
        {
            "image": "https://..."
        }
    ],
    "categories": [
        {
            "name": "Kids & Clothing",
            "apikey": "R5QdOnotarealkeyOpkQ"
        }
    ],
    "brand": {
        "name": "Tshirt",
        "apikey": "R5QdOnotarealkeyOpkQ"
    },
    "variants": [
        {
            "name": "Large Blue T-Shirt",
            "stripe_price_id": "price_123notarealid789",
            "price": "14.67",
            "discount": null,
            "inventory": 3,
            "sku": "123IMASKU789",
            "weight": null,
            "length": "",
            "height": "",
            "flat_ship_rate": 500,
            "ship_rate_type": null,
            "est_delivery_min": 5,
            "est_delivery_max": 7,
            "apikey": "R5QdOnotarealkeyOpkQ"
        },
        {
            "name": "Medium Blue T-Shirt",
            "stripe_price_id": "price_123notarealid789",
            "price": "14.67",
            "discount": null,
            "inventory": 13,
            "sku": "123IMASKU789",
            "weight": null,
            "length": "",
            "height": "",
            "flat_ship_rate": 500,
            "ship_rate_type": null,
            "est_delivery_min": 5,
            "est_delivery_max": 7,
            "apikey": "R5QdOnotarealkeyOpkQ"
        }
    ]
}

```
