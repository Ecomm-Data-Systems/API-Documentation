# Products

> :bulb: IMPORTANT: The API delivers product with a ```published``` status. The admin tool allows an admin to create a product but to save it as a ```draft```. If you are not seeing a product you expect to see, double check the publish status in the admin.

- [List Products](#list-products)
- [Show Product](#show-product)
- [Variants](#variants)


## List Products

Retrieve a list of published products.

The list will be ordered in alphabetical order and paginated. Products can have many images and categories. And they can have only one brand.

Results are paginated. To show the next page of results, you will need to parse the pagination object to get the page(s) you need.
Optional parameters

- page: Returns page (n) of products
- c: Filters products for category
- b: Filters products for brand 

Resource (first page)
```bash
/api/v1/products
```

Resource (with pagination)
```bash
/api/v1/products?page=:n
```

Resource (category option)
```bash
/api/v1/products?c=:category_apikey
```

Resource (brand option)
```bash
/api/v1/products?b=:brand_apikey
```

Response example
```json
{
    "products": [
        {
            "apikey": "QcAeS71JwoEpDm_3MKO5OA",
            "product_type": "SIMPLE",
            "name": "Durable Concrete Gloves",
            "description": "Enim quia deleniti. Sint sunt quia. Et cupiditate voluptatibus.",
            "summary": "Accusamus id exercitationem. Voluptatem dolor dignissimos. Rem saepe accusantium.",
            "features": "Maiores et sit. Distinctio esse quaerat. Sapiente et quasi.",
            "specs": "Temporibus laborum ducimus. Vel consequatur placeat. Quia doloremque et.",
            "price": "40.3",
            "discount": "70.39",
            "stripe_product_id": null,
            "stripe_price_id": 123456789abcdefg,
            "stripe_taxcode_id": null,
            "status": "PUBLISHED",
            "categories": [
                {
                    "name": "Sports",
                    "apikey": "mmhlWDTIUpeTW06saTnoVg"
                }
            ],
            "brand": {
                "name": "Apple",
                "apikey": "HFH8dvpJuHpz6uxDKg6bag"
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

Retrieve a single product object based on product_apikey.

Resource
```bash
/api/v1/products/:product_apikey
```

Response example
```json
{
    "product": {
        "name": "Durable Concrete Gloves",
        "product_type": "SIMPLE",
        "description": "Enim quia deleniti. Sint sunt quia. Et cupiditate voluptatibus.",
        "summary": "Accusamus id exercitationem. Voluptatem dolor dignissimos. Rem saepe accusantium.",
        "features": "Maiores et sit. Distinctio esse quaerat. Sapiente et quasi.",
        "specs": "Temporibus laborum ducimus. Vel consequatur placeat. Quia doloremque et.",
        "inventory": 27,
        "slug": null,
        "keywords": "sales funnel",
        "sku": "474521489024",
        "price": "40.3",
        "discount": "70.39",
        "stripe_product_id": null,
        "stripe_price_id": 123456789abcdefg,
        "stripe_taxcode_id": null,
        "weight": null,
        "length": null,
        "height": null,
        "status": "PUBLISHED",
        "apikey": "QcAeS71JwoEpDm_3MKO5OA"
    },
    "categories": [
        {
            "name": "Sports",
            "apikey": "mmhlWDTIUpeTW06saTnoVg"
        }
    ],
    "brand": {
        "name": "Durable Concrete Gloves",
        "apikey": "QcAeS71JwoEpDm_3MKO5OA"
    }
}
```

<br><br>

## Variants

If a product has variants, it will have a product_type of ```ADVANCED``` and the product object will contain an array of variants of that product.

> :bulb: Tip: Your product detail page should detect if the product is advanced and has variants. And then present the user with the variant options.

Response example
```json

{
    "product": {
        "name": "Tshirt",
        "product_type": "ADVANCED",
        "description": "The comfiest tshirt ever.",
        "summary": "",
        "features": " ",
        "specs": "",
        "inventory": null,
        "slug": null,
        "keywords": null,
        "sku": null,
        "price": null,
        "discount": null,
        "weight": null,
        "length": null,
        "height": null,
        "status": "PUBLISHED",
        "apikey": "dI3q06LSWBw23J0yoJqjMw"
    },
    "images": [
        {
            "image": "https://..."
        }
    ],
    "categories": [
        {
            "name": "Kids & Clothing",
            "apikey": "hs0h836a26X-pv-0K_dsNQ"
        }
    ],
    "brand": {
        "name": "Tshirt",
        "apikey": "dI3q06LSWBw23J0yoJqjMw"
    },
    "variants": [
        {
            "name": "Large Blue T-Shirt",
            "price": null,
            "discount": null,
            "inventory": null,
            "sku": "",
            "weight": null,
            "length": "",
            "height": "",
            "apikey": "6pji7ht5GgxqL4db1k_DBg"
        },
        {
            "name": "Medium Blue T-Shirt",
            "price": null,
            "discount": null,
            "inventory": null,
            "sku": "",
            "weight": null,
            "length": "",
            "height": "",
            "apikey": "WxAoqm-BxV1P1s_YF6EvYQ"
        }
    ]
}

```
