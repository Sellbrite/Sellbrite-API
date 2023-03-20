# /channels

GET https://api.sellbrite.com/v1/channels

Get a list of channels

---

### Menu

[/channels (GET)](channels)

[/warehouses (GET)](channels)
  * [/warehouses (POST)](channels)
  * [/warehouses (PUT)](channels)

[/orders (GET)](channels)
  * [/orders/:sb_order_seq (GET)](channels)
  * [/warehouses/fulfillments/:uuid (GET)](channels)

[/shipments (POST)](channels)

[/products (GET)](channels)
  * [/products/{sku} (GET)](channels)
  * [/products/{sku} (POST)](channels)
  * [/products/{sku} (DELETE)](channels)
  * [/variation_groups (GET)](channels)
  * [/variation_groups/{sku} (PUT)](channels)
  * [/variation_groups/{sku} (DELETE)](channels)
  
[/inventory (GET)](channels)
  * [/inventory (POST)](channels)
  * [/inventory (PUT)](channels)
  * [/inventory (PATCH)](channels)
  
---

### Channel properties

| Parameter                 | Description                           | Type   |
| ------------------------- | ------------------------------------- | ----   |
| uuid                      | Channel identifier                    | String |
| name                      | Merchant provided name of the channel | String |
| state                     | Connection status of the channel \n "*active*": Channel is active \n "*inactive*": Channel has been deactivated by the merchant \n "*disconnected*": Channel has been disconnected as a result of an invalid token.  | String |
| channel_type_display_name | Channel type display name ("eBay", "Amazon", "Etsy", etc.) | String |
| created_at                | When channel was created in Sellbrite (ISO 8601) | String |
| site_id                   | Marketplace region id                 | String |
| channel_site_region       | Name of the site region of the channel ("Amazon.co.uk (United Kingdom)", "eBay UK") \n *For international channels*  | String |

### Responses

🟢 *200* \n
Response Body \n
[
  {
    *uuid*: String,
    *name*: String,
    *state*: String,
    *channel_type_display_name*: string,
    *created_at*: string,
    *site_id*: string,
    *channel_site_region*: string
  }
]

🔴 *400* \n
Response Body \n
{
}

