# /products/{sku}

```
GET https://api.sellbrite.com/v1/products/{sku}
```

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

This endpoint retrieves properties about a given sku. A sku in Sellbrite is unique and may be a single stand alone product, a child of a variation group, or a variation group parent (the type is not explicitly specified in the response but may be inferred from the presence (or absence) of conditional keys).

All product response will have some common properties such as sku, name, description, price etc. Depending on the type of the sku, they may also have conditional attributes that appear in the response. For example a child of a variation group will have a parent_sku property and variation_fields property to specify what the child product varies on (e.g {"color": "red"}). A parent sku on the other hand will have a variations key which contains an array of child products (each child would contain similar common properties). A parent response would also contain a variation_keys key which is an array of property names for which its children vary on (e.g. ["color"]). A single stand alone product will not have keys product_sku, variations, variation_keys or variation_fields.

### Path Params

**sku**: String <span style="color:red">required</span>

### Responses

🟢 **200** 

🔴 **400** 

<br><br><br>

If you have any questions or doubts, visit our [discussion page](https://github.com/Sellbrite/Sellbrite-API/discussions).

