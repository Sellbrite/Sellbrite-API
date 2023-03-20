# /channels

```
GET https://api.sellbrite.com/v1/channels
```

Get a list of channels

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

### Channel properties

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| uuid                      | Channel identifier                    | String |
| name                      | Merchant provided name of the channel | String |
| state                     | Connection status of the channel <br> **active**: Channel is active <br> **inactive**: Channel has been deactivated by the merchant <br> **disconnected**: Channel has been disconnected as a result of an invalid token.  | String |
| channel_type_display_name | Channel type display name ("eBay", "Amazon", "Etsy", etc.) | String |
| created_at                | When channel was created in Sellbrite (ISO 8601) | String |
| site_id                   | Marketplace region id                 | String |
| channel_site_region       | Name of the site region of the channel ("Amazon.co.uk (United Kingdom)", "eBay UK") <br> **For international channels**  | String |

### Responses

🟢 **200** 

Response Body
```
[
  {
    uuid: String,
    name: String,
    state: String,
    channel_type_display_name: String,
    created_at: String,
    site_id: String,
    channel_site_region: String
  }
]
```


🔴 **400** 

Response Body
```
{}
```

