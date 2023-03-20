---
title: "/variation_groups/{sku}"
slug: "variation_groupssku"
hidden: false
createdAt: "2018-11-30T21:46:29.893Z"
updatedAt: "2019-04-08T21:58:21.960Z"
---
# Variation Groups
Variation groups are used to create a relationship between multiple products that vary on custom attributes. In Sellbrite, variation groups look and behave very much like regular products, and can be listed to channels.

Lets say you have a t-shirt that comes in two sizes: "regular" and "large". First, you would use the `/products` endpoint to create two products. The first product would have `custom_attributes = {Size: "regular"}`, and the second product would have `custom_attributes = {Size: "large"}`. Then you could create a variation group for these two products, where `variation_attributes = ["Size"]`.

**Note**: A product can only belong to one variation group at a time.

**Note 2**: By default, the variation group will inherit the properties of the child SKUs for things like "brand", "category", "weight", etc. If you would like to edit these values, you can retrieve and edit the variation group like a product, using the `/products` endpoint and the variation group SKU. 

**Note 3**: In the Sellbrite UI, variation groups are referred to as the "parent product". This language will most likely be updated in the future.

**Note 4**: In the Sellbrite UI, custom attribute values will be displayed with capitalized words and spaces e.g. "Waist Size." However, the variation attribute values you pass in would be in the snake cased form e.g. "waist_size." You can confirm this by making a GET request to the products endpoint and looking at the values listed under custom_attributes.