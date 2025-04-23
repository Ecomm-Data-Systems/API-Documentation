# Catalog::Brands

## List Brands

Retrieve a list of active brands from your account.

The list will be ordered in alphabetical order. Brands that are tagged as pending in the admin interface will not appear in this resource.

GET:
```bash
/api/v1/product_brands
```
Response example
```json

{
    "brands": [
        {
            "name": "GoPro",
            "apikey": "mmtWRw91vSW-I-ei_QOc_Q"
        },
        {
            "name": "LG",
            "apikey": "B_vADDWR08J44d5cyy9k-Q"
        },...
    ]
}
```

<br><br>

## Show Brand

Retrieve a single brand object based on brand_apikey.

GET:
```bash
/api/v1/product_brands/:brand_apikey
```

Response example
```json

{
    "brand": {
        "name": "LG",
        "apikey": "B_vADDWR08J44d5cyy9k-Q"
    }
}
```

