---
title: "/inventory"
slug: "inventory"
excerpt: "Get all your inventory"
hidden: false
createdAt: "2017-01-27T20:18:20.163Z"
updatedAt: "2018-06-25T17:03:12.696Z"
---
This endpoint will return all your inventory. The inventory can be filtered to return inventory scoped to a specific warehouse if you provide the ```warehouse_uuid``` in the query parameters.
[block:api-header]
{
  "type": "basic",
  "title": "Inventory properties"
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "h-2": "Type",
    "0-0": "sku",
    "1-0": "warehouse_uuid",
    "2-0": "on_hand",
    "3-0": "available",
    "4-0": "reserved",
    "5-0": "product_name",
    "5-1": "Product name",
    "4-1": "Quantity reserved by open orders.",
    "3-1": "Quantity available to ship. (on_hand - reserved)",
    "2-1": "Quantity physically available in the warehouse.",
    "1-1": "Warehouse identifier. See warehouses endpoint.",
    "0-1": "Stock keeping unit",
    "0-2": "String",
    "1-2": "String",
    "2-2": "String",
    "3-2": "String",
    "4-2": "String",
    "5-2": "String",
    "6-0": "package_length",
    "6-1": "Length of the package",
    "7-0": "package_width",
    "7-1": "Width of package",
    "8-0": "package_height",
    "8-1": "Height of package",
    "9-0": "package_weight",
    "9-1": "Weight of package",
    "6-2": "Number",
    "7-2": "Number",
    "8-2": "Number",
    "9-2": "Number",
    "10-0": "cost",
    "10-1": "Cost of inventory",
    "10-2": "Number",
    "11-0": "upc",
    "11-1": "UPC of inventory",
    "11-2": "String",
    "12-0": "ean",
    "12-1": "EAN of inventory",
    "12-2": "String",
    "13-0": "isbn",
    "13-1": "ISBN of inventory",
    "13-2": "String",
    "14-0": "gtin",
    "14-1": "GTIN of inventory",
    "14-2": "String",
    "15-0": "gcid",
    "15-1": "GCID of inventory",
    "15-2": "String",
    "16-0": "epid",
    "16-1": "ePID of inventory",
    "16-2": "String",
    "17-0": "asin",
    "17-1": "ASIN of inventory",
    "17-2": "String",
    "18-0": "fnsku",
    "18-1": "Fulfillment Network Stock Keeping Unit. The FNSKU is the way that Amazon identifies a product as unique to the seller that has sent it to the Amazon fulfillment center.",
    "18-2": "String",
    "19-0": "bin_location",
    "19-1": "Bin location of inventory",
    "19-2": "string"
  },
  "cols": 3,
  "rows": 20
}
[/block]