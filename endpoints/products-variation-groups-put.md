# /variation_groups/{sku}

```
PUT https://api.sellbrite.com/v1/variation_groups/{sku}
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

### Variation Groups


Variation groups are used to create a relationship between multiple products that vary on custom attributes. In Sellbrite, variation groups look and behave very much like regular products, and can be listed to channels.

Lets say you have a t-shirt that comes in two sizes: "regular" and "large". First, you would use the `/products` endpoint to create two products. The first product would have `custom_attributes = {Size: "regular"}`, and the second product would have `custom_attributes = {Size: "large"}`. Then you could create a variation group for these two products, where `variation_attributes = ["Size"]`.

**Note**: A product can only belong to one variation group at a time.

**Note 2**: By default, the variation group will inherit the properties of the child SKUs for things like "brand", "category", "weight", etc. If you would like to edit these values, you can retrieve and edit the variation group like a product, using the `/products` endpoint and the variation group SKU.

**Note 3**: In the Sellbrite UI, variation groups are referred to as the "parent product". This language will most likely be updated in the future.

**Note 4**: In the Sellbrite UI, custom attribute values will be displayed with capitalized words and spaces e.g. "Waist Size." However, the variation attribute values you pass in would be in the snake cased form e.g. "waist_size." You can confirm this by making a GET request to the products endpoint and looking at the values listed under custom_attributes.

### Path Params

**sku**: String <span style="color:red">required</span>

### Body Params

```
{
  name: String, (REQUIRED, Group name)
  child_skus: Array of Strings, (REQUIRED, SKUs of the products you want to be in this group)
  variation_attributes: Array of Strings, (REQUIRED, The custom product attributes that the child SKUs vary on)
  description: String, (Group description)
  images: Array of Strings (Array of image URLs)
}
```

### Responses

🟢 **200** 

🔴 **400** 

