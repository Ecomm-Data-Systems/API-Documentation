# Catalog::Categories::Category Detail

There are multiple ways to retrieve a category object. 



## Find By Path

Retrieves detailed information about a single category based on the slug(s), including its ID, name, slug, and full hierarchical path. If the category has nested subcategories (children), they will be included recursively in the response.

The ```full_path``` field represents the complete path from the root category to the current category (e.g., "men/clothing/t-shirts").

If the category has no children, the children field will either be an empty array or omitted entirely.

The nesting continues as deep as the category structure requires.

GET:
```bash
/api/v1/product_categories/find/path?p=:full_path
```

Response example
```json
{
    "category": {
        "name": "Clothing, Shoes & Movies",
        "full_path": "clothing-shoes-movies",
        "description": "Molestiae sint sunt. Voluptatibus incidunt sed. Sit quasi sunt.",
        "apikey": "ydiNotAreEaLLkeyuc6kOg"
    },
    "children": [
        {
            "name": "Shirts",
            "full_path": "clothing-shoes-movies/shirts",
            "apikey": "f8Gnot-Anactu9alKeyu-m4g"
        }
    ]
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
        "apikey": "f8Gnot-Anactu9alKeyu-m4g"
    }
}

```

