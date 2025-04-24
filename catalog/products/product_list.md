# Catalog::Products::Product List


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
            "price": "39.3",
            "discount": "27.83",
            "stripe_price_id": "123456789abcdefg",
            "stripe_taxcode_id": "txcd_99999999",
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
