# Catalog::Categories

Categories in this API are organized as a hierarchical tree. A store can define categories that are either flat (one level deep) or deeply nested, depending on its product organization needs. For example, a simple store might use top-level categories like "Clothing" and "Accessories", while a more complex catalog might include multiple layers, such as "Men > Clothing > T-Shirts". 

Each category includes a ```full_path``` field, which represents its complete path in the hierarchy, making it easy to construct navigation menus or filter products accordingly.

:bulb: For easy navigation, your website should follow the same hierarchy structure from the API. But, because this is a headless solution you are are free to build your navigation structure as you like it. 

- [Category List](./category_list.md)
- [Category Detail](./category_detail.md)
