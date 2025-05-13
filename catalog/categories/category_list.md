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
          "full_path": "/tools",
          "apikey": "z2SMNOtaRealAPIKeyPIVg",
          "children": [
              {
                  "name": "Drills",
                  "full_path": "/tools/drills",
                  "apikey": "hSNotArealAPiKeyqA"
              },
              {
                  "name": "Screwdrivers",
                  "full_path": "/tools/screwdrivers",
                  "apikey": "-JItNoTAreaLAPIKeYGSA"
              }...
            ]
        },...
    ]
}

```

