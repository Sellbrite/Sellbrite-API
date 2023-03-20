# /orders

```
GET https://api.sellbrite.com/v1/orders
```

Get a list of all orders (if fetching orders for fulfillment purposes, use /warehouses/fulfillments endpoint)

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

> 🚧 Note on order limit
>
> * Each request to the GET `/orders` endpoint will by default return 100 order records if a limit is not set.
> * The **limit** for each request is also 100 records. So even if you set the limit to 200, the response will only return 100 records.

### Use Case

Pull all order data to use for reporting, record keeping, or transferring to other systems.

To pull orders for fulfillment purposes, use the `/warehouses/fulfillments` endpoint.

### Response

This endpoint will return a list of orders. Returns an array of JSON objects with order information.

### Order properties

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| display_ref               | Order number as displayed in the channel | String |
| shipping_contact_name     | The full name of the person receiving the order | String |
| shipping_email            | The email of the person receiving the shipment	 | String |
| shipping_company_name     | The company of the person associated with the shipping address | String |
| shipping_address_1        | The street address of the shipping address  | String |
| shipping_address_2        | An optional additional field for the street address of the shipping address  | String |
| shipping_address_3        | Third optional additional field for the street address of the shipping address | String |
| shipping_state_region     | Either name of shipping state/region or the two-letter abbreviation of the state or province of the shipping address       | String |
| shipping_postal_code      | The zip or postal code of the shipping address | String |
| shipping_city             | The city of the shipping address      | String |
| shipping_country_code     | The ISO 2 letter country code	       | String |
| shipping_phone_number     | The phone number at the shipping address | String |
| subtotal                  | Order amount before shipping and taxes	  | Number |
| discount                  | Discount amount on the order	        | Number |
| shipping_cost             | Shipping cost of the order	        | Number |
| total                     | Total amount of the order	        | Number |
| tax 			     | Tax amount on the order	        | Number |
| sb_payment_status         | Payment status of the order according to the channel. One of the follow values: <br> **all**: All of the items have been paid. <br> **none**: None of the items have been paid <br> **partial**: Some of the items have been paid | String |
| shipment_status   | Shipment status of the order <br> **all**: All of the items have been shipped <br> **none**: None of the items have been shipped <br> **partial**: Some of the items have been shipped | String |
| ordered_at | The date and time in UTC when the sales order was placed.	 | String |
| sb_status | Sellbrite status of the order. <br> **open**: Order is still open and awaiting payment and/or fulfillment <br> **completed**: Order is paid and fullfiled <br> **cancelled**: Order is cancelled | String |
| cancelled_at | The date and time in UTC when the sales order was cancelled | String |
| shipped_at | The date and time in UTC when the sales order was shipped | String |
| billing_address_1 | The street address of the billing address | String |
| billing_address_2 | An optional additional field for the street address of the billing address | String |
| billing_address_3 | Third optional additional field for the street address of the billing address | String |
| billing_postal_code | The zip or postal code of the billing address | String |
| billing_state_region | Either name of billing state/region or the two-letter abbreviation of the state or province of the shipping address | String |
| billing_city | The city of the billing address | String |
| billing_country | The name of the country of the billing address | String |
| billing_country_code | The ISO two-letter code for the country of the billing address | String |
| billing_phone_number | The phone number at the billing address | String |
| billing_contact_name | The full name of the person associated with the payment method | String |
| billing_email | The email address of the billing address | String |
| billing_company | The company of the person associated with the billing address | String |
| sb_order_seq | Sellbrite generated sequence number | Number |
| channel_uuid | Channel identifier that is associated with the order. See channels endpoint | String |
| channel_type_display_name | Channel type of the channel associated with the order ("eBay", "Bigcommerce", "Amazon" etc.)	 | String |
| items | Collection of order items associated with the order. Please see order items properties | Array |
| requested_shipping_service | Shipping service requested by buyer as received from the channel. ("2nd Day", "Priority", "Express" etc.) | String |
| requested_shipping_provider | Shipping provider by buyer ("UPS", "USPS", "Amazon Prime" etc.) | String |
| requested_shipping_special | Special status of order ("ebay_guaranteed_delivery", "amazon_prime") | String |
| merchant_notes | Notes on the order made by the merchant (seller) | String |
| customer_notes | Notes on the order made by the customer (buyer)	 | String |
| channel_name | Merchant provided name of the channel where the order originates from | String |
| deliver_by_date | Date and time in UTC that order will be delivered by | String |
| ship_by_date | Date and time in UTC that order will be shipped by | String |
| paid_at | Date and time in UTC that the order was paid at | String |


### Order Item properties

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| order_item_ref            | Original item reference from the channel | String |
| quantity | Number of items ordered | Integer |
| title | Name of the item | String |
| sku | Stock keeping unit of item (this value comes from the channel) | String |
| unit_price | Per unit selling price of each individual item | Number |
| total | Unit price multiplied by quantity | Number |
| quantity_fulfilled | Number of items shipped | Integer |
| inventory_sku | Stock keeping unit of inventory associated with item. (This value comes from Sellbrite's linked inventory. <br> *This may differ from the sku that comes from the channel) | String |
| tax | Tax charged on this item | Number |
| cancelled_at | Time order was cancelled at | String |
| status | Status of the item found on the external channel | String |

### Query Params

```
{
  page: int32, (page number)
  limit: int32, (Number of results per page)
  min_ordered_at: date-time, (Filters orders ordered after date (ISO 8601))
  max_ordered_at: date-time, (Filters orders ordered before date (ISO 8601))
  sb_status: String, (Filters by order status. Accepts one of the following values: "completed", "canceled", "open")
  sb_payment_status: String, (Filters by payment status. Accepts one of the following values: "all", "partial", "none")
  shipment_status: String (Filters by the shipment status on the order. Accepts one of the following values: "all", "partial", or "none")
}
```

### Responses

🟢 **200** 

