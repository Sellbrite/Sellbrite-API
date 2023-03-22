# /products/{sku}

```
POST https://api.sellbrite.com/v1/products/{sku}
```

Upsert a product

---

### Menu

[/channels (GET)](channels)

[/warehouses (GET)](warehouses)
  * [/warehouses (POST)](warehouses-post)
  * [/warehouses (PUT)](warehouses-put)

[/orders (GET)](orders)
  * [/orders/:sb_order_seq (GET)](orders-sb-order)
  * [/warehouses/fulfillments/:uuid (GET)](orders-fulfillments)

[/shipments (POST)](shipments)

[/products (GET)](products)
  * [/products/{sku} (GET)](products-sku-get)
  * [/products/{sku} (POST)](products-sku-post)
  * [/products/{sku} (DELETE)](products-sku-delete)
  * [/variation_groups (GET)](products-variation-groups)
  * [/variation_groups/{sku} (PUT)](products-variation-groups-put)
  * [/variation_groups/{sku} (DELETE)](products-variation-groups-delete)
  
[/inventory (GET)](inventory)
  * [/inventory (POST)](inventory-post)
  * [/inventory (PUT)](inventory-put)
  * [/inventory (PATCH)](inventory-patch)
  
---

This endpoint will upsert (create or update) a product.

Acceptable http methods are POST, PUT, PATCH.

Use this endpoint to create new individual products. After creating single products, you can group them together with the variation_groups APIs

Parameter 'name' only required when creating product.

### Path Params

**sku**: String <span style="color:red">required</span>

The sku must be unique in your product catalog

### Body Params

```
{
  name: String, (REQUIRED)
  asin: String,
  condition: String, (Allowed values: "new", "used", "reconditioned")
  brand: String,
  manufacturer: String,
  manufacturer_model_number: String,
  description: String,
  price: String,
  package_length: float,
  package_width: float,
  package_height: float,
  package_unit_of_length: String,
  package_weight: float,
  package_unit_of_weight: String,
  msrp: float,
  category_name: String,
  features: Array of Strings,
  warranty: String,
  condition_note: String,
  upc: String,
  ean: String,
  isbn: String,
  gtin: String,
  epid: String,
  image_list: Array of Strings,
  custom_attributes: Array of Strings,
  notes: String
}
```


### Responses

🟢 **200** 

🔴 **400** 

<br><br><br>

If you have any questions or doubts, visit our [discussion page](https://github.com/Sellbrite/Sellbrite-API/discussions).

