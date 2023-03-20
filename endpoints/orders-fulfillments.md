---
title: "/warehouses/fulfillments/:uuid"
slug: "warehousesuuidfulfillments"
excerpt: "List open orders assigned to specified warehouse"
hidden: false
createdAt: "2017-04-06T22:49:11.183Z"
updatedAt: "2020-09-03T17:18:57.657Z"
---
[block:callout]
{
  "type": "info",
  "title": "Notes on fulfillment_quantity field",
  "body": "The /warehouses/fulfillments/:uuid will return all of the same data fields found on the /orders endpoint, but will also include the fulfillment_quantity field."
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "h-2": "Type",
    "0-0": "fulfillment_quantity",
    "0-2": "Number",
    "0-1": "The predicted number of inventory that will be shipped out of the associated warehouse."
  },
  "cols": 3,
  "rows": 1
}
[/block]

[block:api-header]
{
  "title": "Use case"
}
[/block]
Pull only open orders that have order items assigned to be fulfilled from a specific warehouse location.
[block:api-header]
{
  "title": "Description of fulfillments"
}
[/block]
The /warehouses/fulfillments/:uuid endpoint returns current open orders that have order items assigned to the specified warehouse for fulfillment. A 'fulfillment' is the plan established in Sellbrite for how an open order is to be shipped given how the warehouses are prioritized by the merchant.  (For more information regarding configuring fulfillment options, please [click here.](https://support.sellbrite.com/en/articles/3367317-how-to-configure-fulfillment-options-in-sellbrite))

When an order comes into Sellbrite, all order items typically will ship from the same warehouse; however, there will be scenarios where a merchant will use multiple warehouses to fulfill their orders. If an order has multiple order items (or one item with a quantity >1) that are assigned to different warehouses (i.e. split shipment), only the order items assigned to the warehouse specified will be returned. In this case, the same order, with its other order items, will be returned in subsequent calls with other warehouses specified.

For example, a merchant has two warehouses: warehouse A and warehouse B. Both warehouses have a quantity of 1 for SKU 123. When Sellbrite receives an order for 2 pieces of SKU 123, there would be 2 fulfillments created (assuming the order's channel has an active warehouse list that includes both warehouses A and B).  Since warehouse A only has a quantity 1 of SKU 123, warehouse A would have one fulfillment created to ship 1 piece of SKU 123.  Due to insufficient quantity to ship the entire order, Sellbrite would also automatically create a fulfillment on warehouse B for the remaining 1 piece of SKU 123.

Fulfillment orders are transient.  They are a plan of which warehouse would be shipping what portion of open orders. Order items can be "unassigned" to a warehouse for various reasons (ex. item is out of stock on all warehouses, or Sellbrite cannot determine the relationship between the item ordered and an item in the merchant's inventory). If the order item is "unassigned", then no fulfillment will be created and those items will not be returned in this call. Therefore, use fulfillments as a reference for what to ship out of each warehouse. 

Notice that the returned fields are almost identical to the /orders endpoint, except that an additional "fulfillment_quantity" field is added to items resource. Fulfillment_quantity indicates the quantity of the item that is going to be shipped from the warehouse whose uuid was passed into this endpoint.

For more information regarding field definitions, please see [/orders endpoint.](https://developer.sellbrite.com/v1.0/reference#orders)