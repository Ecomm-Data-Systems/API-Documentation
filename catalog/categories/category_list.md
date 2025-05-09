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
          "apikey": "z2SMNOtaRealAPIKeyPIVg",
          "children": [
              {
                  "name": "Drills",
                  "full_path": "Automotive+%26+Movies/Tools/Drills",
                  "apikey": "hSNotArealAPiKeyqA"
              },
              {
                  "name": "Screwdrivers",
                  "full_path": "Automotive+%26+Movies/Tools/Screwdrivers",
                  "apikey": "-JItNoTAreaLAPIKeYGSA"
              }...
            ]
        },...
    ]
}

```

