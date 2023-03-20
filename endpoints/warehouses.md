# /warehouses

```
GET https://api.sellbrite.com/v1/warehouses
```

Get a list of warehouses

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

### Warehouse properties

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| uuid                      | Warehouse identifier                  | String |
| name                      | Name of the warehouse                 | String |
| inventory_master          | Type of warehouse <br> **Sellbrite**: Any warehouse that is non-FBA <br> **Amazon**: Fulfilled By Amazon warehouse  | String |
| address_1                 | Address of warehouse  | String |
| address_2                 | Additional address information of warehouse  | String |
| city                      | City location of warehouse | String |
| state_region              | State or region of warehouse         | String |
| postal_code               | Postal code of warehouse  | String |
| country_code              | Two-letter abbreviated code of country of warehouse  | String |
| archived                  | Determines whether warehouse is archived  | Boolean |


### Responses

🟢 **200** 

Response Body
```
[
  {
    uuid: String,
    name: String,
    inventory_master: String,
    address_1: String,
    address_2: String,
    city: String,
    state_region: String,
    postal_code: String,
    country_code: String,
    archived: Boolean
  }
]
```

🔴 **400** 

Response Body
```
{}
```

