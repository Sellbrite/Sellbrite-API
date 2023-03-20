# /shipments

```
POST https://api.sellbrite.com/v1/shipments
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

### Body Params

```
{
  shipment: {
    sb_order_seq: int32, (REQUIRED, Sellbrite generated sequence number)
    carrier_name: String, (REQUIRED, Name of the carrier used to ship the order. ("UPS", "USPS", "FedEx", etc.))
    tracking_number: String, (REQUIRED, Tracking number for this shipment)
    items: [ (REQUIRED)
      {
        sku: String, (REQUIRED, SKU of what is being shipped (This needs to match the order item sku. If it does not match, we attempt to match on the inventory_sku. If neither match, an error will be raised))
        quantity: int32 (REQUIRED, Quantity that is being shipped)
      }
    ],
    shipping_method: String, (Shipping method of the shipment ("Priority", "2 Day", "Express" etc.))
    warehouse_uuid: String (Warehouse uuid of the warehouse the shipment is shipping from),
    tracking_url: String (Tracking url of the shipment)
  }
}
```

### Responses

🟢 **200** 

🔴 **400** 

🔴 **404** 

🔴 **422** 

