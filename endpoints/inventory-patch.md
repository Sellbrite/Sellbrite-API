# /inventory

```
PATCH https://api.sellbrite.com/v1/inventory
```

Adjusts the inventory for the given sku and warehouse_uuid (up to 50 individual inventories may be adjusted in one API call). Adjustments are queued and processed asynchronously in the background. If the inventory record has not yet been created this endpoint will skip it (use PUT endpoint to automatically create the inventory record).

Exactly one of "on_hand" or "available" field must exist for each individual inventory payload. A pre-validation error will occur for the entire api call if ANY inventory payload includes both fields or if any payload is found to be missing both fields.

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

> 🚧 Note on update limits
> Only 50 inventory records can be updated per API call to the PATCH /inventory endpoint

> 📘 A word on when to use "on_hand" vs "available"
> Sellbrite uses 3 internal values to track inventory: "on_hand", "reserved" and "available". "on_hand" is the value Sellbrite believes to be physically present in a warehouse, while "reserved" is the assignment of open orders against that inventory. "available" is always "on_hand minus reserved" and it is what Sellbrite uses to sync remaining available inventory to the listings. Using the api you may update either "on_hand" or "available" and Sellbrite will adjust the other internal values.
> 
> Send us "available" instead of "on_hand" to avoid the double deduction problem as described here: Suppose you have an "on_hand" of 3, "reserved" of 0 and "available" of 3. When Sellbrite receives an order for 1 pc, Sellbrite will then have "on_hand" of 3, "reserved" of 1 and "available" of 2. If you are also fetching new orders through Sellbrite's orders api, you may also be deducting your own internal inventory from 3 to 2. If you also periodically update Sellbrite with your new inventory you could be "double deducting" the inventory in Sellbrite if you send us "on_hand" of 2, because Sellbrite would then have: "on_hand" of 2, "reserved" of 1 and "available" of 1, when really we should still have available of 2. If instead you send "available" of 2, Sellbrite would still have: "on_hand" of 3, "reserved" of 1, and "available" of 2 (no adjustment needed), and would be in agreement with your system.

### Body Params

```
{
  inventory: {
    sku: String, (REQUIRED, Stock keeping unit)
    description: String, (Adjustment reason)
    warehouse_uuid: String, (REQUIRED, Warehouse identifier. See warehouses endpoint)
    on_hand: int32, (REQUIRED, Physical quantity in the warehouse (exactly one of on_hand or available field must exist in payload))
    available: int32, (REQUIRED, Available quantity to ship from this warehouse (exactly one of on_hand or available field must exist in payload))
    bin_location: String, (Bin location where inventory is located)
    cost: int32 (Cost of inventory)
  }
}
```

### Responses

🟢 **200** 

🔴 **404** 

🔴 **422** 
