---
title: "/products/{sku}"
slug: "productssku"
hidden: false
createdAt: "2019-04-26T17:26:54.787Z"
updatedAt: "2019-04-29T18:06:43.785Z"
---
This endpoint retrieves properties about a given sku.  A sku in Sellbrite is unique and may be a single stand alone product, a child of a variation group, or a variation group parent (the type is not explicitly specified in the response but may be inferred from the presence (or absence) of conditional keys).  

All product response will have some common properties such as sku, name, description, price etc.  Depending on the type of the sku, they may also have conditional attributes that appear in the response.  For example a child of a variation group will have a parent_sku property and variation_fields property to specify what the child product varies on (e.g {"color": "red"}).  A parent sku on the other hand will have a variations key which contains an array of child products (each child would contain similar common properties).  A parent response would also contain a variation_keys key which is an array of property names for which its children vary on (e.g. ["color"]).  A single stand alone product will not have keys product_sku, variations, variation_keys or variation_fields.