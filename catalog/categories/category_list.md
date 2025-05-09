# Catalog::Categories::Category List

Retrieve a list of product categories.

GET:
```bash
/api/v1/product_categories
```

Response example
```json

{
    "categories": [
        {
          "name": "Tools",
          "full_path": "Automotive+%26+Movies/Tools",
          "apikey": "z2SMPIWPJpAjqwXCG35ZVg",
          "children": [
              {
                  "name": "Drills",
                  "full_path": "Automotive+%26+Movies/Tools/Drills",
                  "apikey": "hSR6xvekRnmsNszhqD10qA"
              },
              {
                  "name": "Screwdrivers",
                  "full_path": "Automotive+%26+Movies/Tools/Screwdrivers",
                  "apikey": "-JIt3zPfBAep17o5wIgGSA"
              }...
            ]
        },...
    ]
}

```

