# Catalog::Categories

## List Categories

GET:
```bash
/api/v1/product_categories
```

Response example
```json

{
    "categories": [
        {
            "name": "Computers & Games",
            "apikey": "j0gcEpRddG859StfDWD1yQ"
        },
        {
            "name": "Garden & Shoes",
            "apikey": "y42ZUktRiq_u36Dv1W8Xjg"
        },...
    ]
}

```

<br><br>

## Show Category

Retrieve a single category object based on category_apikey.

GET:
```bash
/api/v1/product_categories/:category_apikey
```

Response example
```json

{
    "category": {
        "name": "Garden & Shoes",
        "description": "Est qui porro. Dolores quidem impedit. Eveniet earum maxime.",
        "apikey": "y42ZUktRiq_u36Dv1W8Xjg"
    }
}

```

