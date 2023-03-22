# /inventory

```
POST https://api.sellbrite.com/v1/inventory
```

This POST endpoint creates an inventory record only if it does not exist. If the inventory does exist it will error with an HTTP CONFLICT error. If you would like to ignore errors and upsert inventories see the PUT /inventories endpoint.


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

### Body Params

```
{
  inventory: {
    sku: String, (REQUIRED, The inventory SKU)
    warehouse_uuid: String, (REQUIRED, The unique identifier for the warehouse (see /warehouses endpoint))
    on_hand: String (REQUIRED, The physical quantity in the warehouse)
  }
}
```

### Responses

🟢 **201** 

<br><br><br>

If you have any questions or doubts, visit our [discussion page](https://github.com/Sellbrite/Sellbrite-API/discussions).

