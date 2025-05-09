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
          "full_path": "/Tools",
          "apikey": "z2SMNOtaRealAPIKeyPIVg",
          "children": [
              {
                  "name": "Drills",
                  "full_path": "/Tools/Drills",
                  "apikey": "hSNotArealAPiKeyqA"
              },
              {
                  "name": "Screwdrivers",
                  "full_path": "/Tools/Screwdrivers",
                  "apikey": "-JItNoTAreaLAPIKeYGSA"
              }...
            ]
        },...
    ]
}

```

