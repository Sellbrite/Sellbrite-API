---
title: "/orders"
slug: "orderssb_order_seq"
excerpt: "Get a list of all orders\n(if fetching orders for fulfillment purposes, use /warehouses/fulfillments endpoint)"
hidden: false
createdAt: "2017-01-27T19:31:07.011Z"
updatedAt: "2020-09-03T16:48:30.688Z"
---
[block:callout]
{
  "type": "warning",
  "title": "Note on order limit",
  "body": "- Each request to the GET /orders endpoint will by default return 100 order records if a limit is not set.\n- The **limit** for each request is also 100 records. So even if you set the limit to 200, the response will only return 100 records."
}
[/block]

[block:api-header]
{
  "title": "Use Case"
}
[/block]
Pull all order data to use for reporting, record keeping, or transferring to other systems.

***To pull orders for fulfillment purposes, use the [/warehouses/fulfillments endpoint](https://developer.sellbrite.com/reference#warehousesuuidfulfillments).***
[block:api-header]
{
  "type": "basic",
  "title": "Response"
}
[/block]
This endpoint will return a list of orders. Returns an array of JSON objects with order information. 
[block:api-header]
{
  "type": "basic",
  "title": "Order properties"
}
[/block]

[block:parameters]
{
  "data": {
    "0-0": "display_ref",
    "1-0": "shipping_contact_name",
    "2-0": "shipping_email",
    "3-0": "shipping_company_name",
    "h-0": "Parameter",
    "h-1": "Description",
    "h-2": "Type",
    "4-0": "shipping_address_1",
    "5-0": "shipping_address_2",
    "6-0": "shipping_address_3",
    "8-0": "shipping_postal_code",
    "9-0": "shipping_city",
    "10-0": "shipping_country_code",
    "11-0": "shipping_phone_number",
    "12-0": "subtotal",
    "13-0": "discount",
    "14-0": "shipping_cost",
    "15-0": "total",
    "16-0": "tax",
    "17-0": "sb_payment_status",
    "18-0": "shipment_status",
    "19-0": "ordered_at",
    "20-0": "sb_status",
    "21-0": "cancelled_at",
    "22-0": "shipped_at",
    "23-0": "billing_address_1",
    "24-0": "billing_address_2",
    "25-0": "billing_address_3",
    "26-0": "billing_postal_code",
    "27-0": "billing_state_region",
    "28-0": "billing_city",
    "29-0": "billing_country",
    "30-0": "billing_country_code",
    "31-0": "billing_phone_number",
    "32-0": "billing_contact_name",
    "33-0": "billing_email",
    "34-0": "billing_company",
    "35-0": "sb_order_seq",
    "36-0": "channel_uuid",
    "37-0": "channel_type_display_name",
    "38-0": "items",
    "0-1": "Order number as displayed in the channel",
    "1-1": "The full name of the person receiving the order",
    "2-1": "The email of the person receiving the shipment",
    "3-1": "The company of the person associated with the shipping address.",
    "4-1": "The street address of the shipping address.",
    "5-1": "An optional additional field for the street address of the shipping address.",
    "6-1": "Third optional additional field for the street address of the shipping address.",
    "8-1": "The zip or postal code of the shipping address.",
    "9-1": "The city of the shipping address.",
    "10-1": "The ISO 2 letter country code.",
    "11-1": "The phone number at the shipping address.",
    "12-1": "Order amount before shipping and taxes",
    "13-1": "Discount amount on the order",
    "14-1": "Shipping cost of the order",
    "15-1": "Total amount of the order",
    "16-1": "Tax amount on the order",
    "17-1": "Payment status of the order according to the channel. One of the follow values:\n<p></p>\n  **\"all\"**: All of the items have been paid.\n  **\"none\"**: None of the items have been paid\n  **\"partial\"**: Some of the items have been paid",
    "18-1": "Shipment status of the order.\n<p></p>\n  **\"all\"**: All of the items have been shipped.\n  **\"none\"**: None of the items have been shipped\n  **\"partial\"**: Some of the items have been shipped",
    "19-1": "The date and time in UTC when the sales order was placed.",
    "20-1": "Sellbrite status of the order.\n<p></p>\n **\"open\"**: Order is still open and awaiting payment and/or fulfillment\n  **\"completed\"**: Order is paid and fullfiled\n  **\"cancelled\"**: Order is cancelled",
    "21-1": "The date and time in UTC when the sales order was cancelled.",
    "22-1": "The date and time in UTC when the sales order was shipped.",
    "23-1": "The street address of the billing address.",
    "24-1": "An optional additional field for the street address of the billing address.",
    "25-1": "Third optional additional field for the street address of the billing address.",
    "26-1": "The zip or postal code of the billing address.",
    "27-1": "Either name of billing state/region or the two-letter abbreviation of the state or province of the shipping address.",
    "28-1": "The city of the billing address.",
    "29-1": "The name of the country of the billing address.",
    "30-1": "The ISO two-letter code for the country of the billing address.",
    "32-1": "The full name of the person associated with the payment method.",
    "31-1": "The phone number at the billing address.",
    "33-1": "The email address of the billing address.",
    "34-1": "The company of the person associated with the billing address.",
    "35-1": "Sellbrite generated sequence number.",
    "36-1": "Channel identifier that is associated with the order. See channels endpoint.",
    "37-1": "Channel type of the channel associated with the order (\"eBay\", \"Bigcommerce\", \"Amazon\" etc.)",
    "38-1": "Collection of order items associated with the order. Please see order items properties.",
    "38-2": "Array",
    "37-2": "String",
    "36-2": "String",
    "35-2": "Number",
    "34-2": "String",
    "33-2": "String",
    "32-2": "String",
    "31-2": "String",
    "30-2": "String",
    "29-2": "String",
    "28-2": "String",
    "27-2": "String",
    "26-2": "String",
    "25-2": "String",
    "24-2": "String",
    "23-2": "String",
    "21-2": "String",
    "22-2": "String",
    "20-2": "String",
    "19-2": "String",
    "18-2": "String",
    "17-2": "String",
    "16-2": "Number",
    "15-2": "Number",
    "14-2": "Number",
    "13-2": "Number",
    "12-2": "Number",
    "11-2": "String",
    "10-2": "String",
    "9-2": "String",
    "8-2": "String",
    "6-2": "String",
    "5-2": "String",
    "4-2": "String",
    "3-2": "String",
    "2-2": "String",
    "1-2": "String",
    "0-2": "String",
    "39-0": "requested_shipping_service",
    "39-1": "Shipping service requested by buyer as received from the channel. (\"2nd Day\", \"Priority\", \"Express\" etc.)",
    "39-2": "String",
    "40-0": "requested_shipping_provider",
    "40-1": "Shipping provider by buyer (\"UPS\", \"USPS\", \"Amazon Prime\" etc.)",
    "40-2": "String",
    "42-0": "merchant_notes",
    "43-0": "customer_notes",
    "42-2": "String",
    "43-2": "String",
    "42-1": "Notes on the order made by the merchant (seller)",
    "43-1": "Notes on the order made by the customer (buyer)",
    "7-0": "shipping_state_region",
    "7-1": "Either name of shipping state/region or the two-letter abbreviation of the state or province of the shipping address.",
    "7-2": "String",
    "44-0": "channel_name",
    "44-1": "Merchant provided name of the channel where the order originates from",
    "44-2": "String",
    "46-0": "ship_by_date",
    "45-0": "deliver_by_date",
    "45-2": "String",
    "46-2": "String",
    "45-1": "Date and time in UTC that order will be delivered by",
    "46-1": "Date and time in UTC that order will be shipped by",
    "41-0": "requested_shipping_special",
    "41-1": "Special status of order (\"ebay_guaranteed_delivery\", \"amazon_prime\")",
    "41-2": "String",
    "47-0": "paid_at",
    "47-1": "Date and time in UTC that the order was paid at",
    "47-2": "String"
  },
  "cols": 3,
  "rows": 48
}
[/block]

[block:api-header]
{
  "type": "basic",
  "title": "Order Item properties"
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "h-2": "Type",
    "0-0": "order_item_ref",
    "0-1": "Original item reference from the channel",
    "0-2": "String",
    "1-0": "quantity",
    "1-1": "Number of items ordered",
    "1-2": "Integer",
    "2-0": "title",
    "2-1": "Name of the item",
    "2-2": "String",
    "3-0": "sku",
    "3-1": "Stock keeping unit of item (this value comes from the channel).",
    "3-2": "String",
    "4-0": "unit_price",
    "4-1": "Per unit selling price of each individual item",
    "4-2": "Number",
    "5-0": "total",
    "5-1": "Unit price multiplied by quantity",
    "5-2": "Number",
    "6-0": "quantity_fulfilled",
    "6-1": "Number of items shipped",
    "6-2": "Integer",
    "7-0": "inventory_sku",
    "7-1": "Stock keeping unit of inventory associated with item. (This value comes from Sellbrite's linked inventory. *This may differ from the sku that comes from the channel).",
    "7-2": "String",
    "8-0": "tax",
    "8-1": "Tax charged on this item",
    "8-2": "Number",
    "9-0": "cancelled_at",
    "9-2": "String",
    "9-1": "Time order was cancelled at",
    "10-0": "status",
    "10-1": "Status of the item found on the external channel",
    "10-2": "String"
  },
  "cols": 3,
  "rows": 11
}
[/block]