# /inventory

```
GET https://api.sellbrite.com/v1/inventory
```

Get all your inventory

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

This endpoint will return all your inventory. The inventory can be filtered to return inventory scoped to a specific warehouse if you provide the `warehouse_uuid` in the query parameters.

### Inventory properties

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| sku                       | Stock keeping unit                    | String |
| warehouse_uuid            | Warehouse identifier. See warehouses endpoint. | String | 
| on_hand                   | Quantity physically available in the warehouse. | String |
| available                 | Quantity available to ship. (on_hand - reserved) | String |
| reserved                  | Quantity reserved by open orders.     | String | 
| product_name              | Product name                          | String | 
| package_length            | Length of the package                 | Number | 
| package_width             | Width of package                      | Number | 
| package_height            | Height of package                     | Number | 
| package_weight            | Weight of package                     | Number | 
| cost                      | Cost of inventory                     | Number | 
| upc                       | UPC of inventory                      | String | 
| ean                       | EAN of inventory                      | String | 
| isbn                      | ISBN of inventory                     | String | 
| gtin                      | GTIN of inventory                     | String | 
| gcid                      | GCID of inventory                     | String | 
| epid                      | ePID of inventory                     | String | 
| asin                      | ASIN of inventory                     | String | 
| fnsku | Fulfillment Network Stock Keeping Unit. The FNSKU is the way that Amazon identifies a product as unique to the seller that has sent it to the Amazon fulfillment center. | String | 
| bin_location              | Bin location of inventory             | String | 

### Query Params

```
{
  limit: String,
  page: String,
  warehouse_uuid: String,
  sku: String,
  created_at_min: date,
  created_at_max: date,
  updated_at_min: date,
  updated_at_max: date
}
```

### Responses

🟢 **200** 

🔴 **400** 

