# Catalog::Products

This document covers how you can pull a list of products with filters and a single product that is simple, or advanced with variants.

> :bulb: IMPORTANT: The API delivers product with a ```published``` status. The admin tool allows an admin to create a product but to save it as a ```draft```. If you are not seeing a product you expect to see, double check the publish status in the admin.

- [List Products](#list-products)
- [Show Product](#show-product)
    - [Simple](#simple-products)
    - [Advanced](#advanced-products)


## List Products

Retrieve a list of published products.

The list will be ordered in alphabetical order and paginated. Products can have many images and categories. And they can have only one brand.

Results are paginated. To show the next page of results, you will need to parse the pagination object to get the page(s) you need.
Optional parameters

- page: Returns page (n) of products
- c: Filters products for category
- b: Filters products for brand 

GET: (first page)
```bash
/api/v1/products
```

GET: (with pagination)
```bash
/api/v1/products?page=:n
```

GET: (category option)
```bash
/api/v1/products?c=:category_apikey
```

GET: (brand option)
```bash
/api/v1/products?b=:brand_apikey
```

Response example
```json
{
    "products": [
        {
            "apikey": "123imnotarealapikey789",
            "product_type": "SIMPLE",
            "name": "Durable Concrete Gloves",
            "description": "<p>Enim quia deleniti. Sint sunt quia. Et cupiditate voluptatibus.</p>",
            "summary": "Accusamus id exercitationem. Voluptatem dolor dignissimos. Rem saepe accusantium.",
            "features": "Maiores et sit. Distinctio esse quaerat. Sapiente et quasi.",
            "specs": "Temporibus laborum ducimus. Vel consequatur placeat. Quia doloremque et.",
            "price": "40.3",
            "discount": "70.39",
            "stripe_product_id": null,
            "stripe_price_id": "123456789abcdefg",
            "stripe_taxcode_id": null,
            "status": "PUBLISHED",
            "categories": [
                {
                    "name": "Sports",
                    "apikey": "123imnotarealapikey789"
                }
            ],
            "brand": {
                "name": "Apple",
                "apikey": "123imnotarealapikey789"
            }
        },...
    ],
    "pagination": {
        "prev_url": "/api/v1/products?page=",
        "next_url": "/api/v1/products?page=2",
        "count": 5,
        "page": 1,
        "next": null
    }
}

```

<br><br>

## Show Product

Retrieve a single product with the ```product_apikey```.

Resource
```bash
/api/v1/products/:product_apikey
```

<br>

### Simple Products

If a product has a ```product_type``` of ```SIMPLE```. It will contain all of the pricing, inventory, sku and dimension data in the product object. If the product is ```ADVANCED``` you will want to [look at advanced products](#advanced_products).

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
        "price": "40.3",
        "discount": "70.39",
        "stripe_product_id": null,
        "stripe_price_id": "123456789abcdefg",
        "stripe_taxcode_id": null,
        "weight": null,
        "length": null,
        "height": null,
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
        "sku": null,
        "stripe_taxcode_id": "",
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
            "apikey": "R5QdOnotarealkeyOpkQ"
        }
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
            "apikey": "R5QdOnotarealkeyOpkQ"
        }
    ]
}

```
