# /warehouses/fulfillments/:uuid

```
GET https://api.sellbrite.com/v1/warehouses/fulfillments/{uuid}
```

List open orders assigned to specified warehouse

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

> 📘 Notes on fulfillment_quantity field
>
> The /warehouses/fulfillments/:uuid will return all of the same data fields found on the /orders endpoint, but will also include the fulfillment_quantity field.

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| fulfillment_quantity      | The predicted number of inventory that will be shipped out of the associated warehouse | Number |


### Use Case

Pull only open orders that have order items assigned to be fulfilled from a specific warehouse location.

### Description of fulfillments

The /warehouses/fulfillments/:uuid endpoint returns current open orders that have order items assigned to the specified warehouse for fulfillment. A 'fulfillment' is the plan established in Sellbrite for how an open order is to be shipped given how the warehouses are prioritized by the merchant. (For more information regarding configuring fulfillment options, please [click here](https://support.sellbrite.com/en/articles/3367317-how-to-configure-fulfillment-options-in-sellbrite).)

When an order comes into Sellbrite, all order items typically will ship from the same warehouse; however, there will be scenarios where a merchant will use multiple warehouses to fulfill their orders. If an order has multiple order items (or one item with a quantity >1) that are assigned to different warehouses (i.e. split shipment), only the order items assigned to the warehouse specified will be returned. In this case, the same order, with its other order items, will be returned in subsequent calls with other warehouses specified.

For example, a merchant has two warehouses: warehouse A and warehouse B. Both warehouses have a quantity of 1 for SKU 123. When Sellbrite receives an order for 2 pieces of SKU 123, there would be 2 fulfillments created (assuming the order's channel has an active warehouse list that includes both warehouses A and B). Since warehouse A only has a quantity 1 of SKU 123, warehouse A would have one fulfillment created to ship 1 piece of SKU 123. Due to insufficient quantity to ship the entire order, Sellbrite would also automatically create a fulfillment on warehouse B for the remaining 1 piece of SKU 123.

Fulfillment orders are transient. They are a plan of which warehouse would be shipping what portion of open orders. Order items can be "unassigned" to a warehouse for various reasons (ex. item is out of stock on all warehouses, or Sellbrite cannot determine the relationship between the item ordered and an item in the merchant's inventory). If the order item is "unassigned", then no fulfillment will be created and those items will not be returned in this call. Therefore, use fulfillments as a reference for what to ship out of each warehouse.

Notice that the returned fields are almost identical to the /orders endpoint, except that an additional "fulfillment_quantity" field is added to items resource. Fulfillment_quantity indicates the quantity of the item that is going to be shipped from the warehouse whose uuid was passed into this endpoint.

For more information regarding field definitions, please see [/orders endpoint](../reference/introduction).

### Path Params

**uuid**: String <span style="color:red">required</span>

Universal unique identifier of the warehouse

### Query Params

```
{
  page: String, (page number)
  limit: String, (Number of results per page)
  min_ordered_at: date-time, (Filters orders ordered after date (ISO 8601))
  max_ordered_at: date-time, (Filters orders ordered before date (ISO 8601))
  sb_status: String, (Filters by order status. Accepts one of the following values: "completed", "canceled", "open")
  sb_payment_status: String, (Filters by payment status. Accepts one of the following values: "all", "partial", "none")
  shipment_status: String (Filters by the shipment status on the order. Accepts one of the following values: "all", "partial", or "none")
}
```

### Responses

🟢 **200** 

🔴 **400** 


