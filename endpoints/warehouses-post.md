# /warehouses

```
POST https://api.sellbrite.com/v1/warehouses
```

Create a warehouse resource

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
  name: String,
  sender_name: String,
  company_name: String,
  email: String,
  phone_number: String,
  address_1: String,
  address_2: String,
  postal_code: String,
  city: String,
  region: String,
  country_code: String,
  enable_shipstation: Boolean
}
```

### Responses

🟢 **200** 
```
{
  message: String,
  warehouse_uuid: String
}
```

🔴 **422** 

Response Body 
```
{
  error: {
    array: []
  }
}
```

