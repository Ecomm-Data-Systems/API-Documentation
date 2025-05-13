# Catalog::Categories::Category Detail

There are multiple ways to retrieve a category object.


## Find By Path

GET:
```bash
/api/v1/product_categories/find/path?p={{full_path}}
```

Response example
```json
{
    "category": {
        "name": "Shirts",
        "full_path": "clothing-shoes-movies/shirts",
        "description": " ",
        "apikey": "f8G38ybLvEh6WOLy-qym4g"
    }
}
```

## Find by APIKey

Retrieve a single category object based on category_apikey.

GET:
```bash
/api/v1/product_categories/find/apikey/:category_apikey
```

Response example
```json
{
    "category": {
        "name": "Shirts",
        "full_path": "clothing-shoes-movies/shirts",
        "description": " ",
        "apikey": "f8G38ybLvEh6WOLy-qym4g"
    }
}

```

