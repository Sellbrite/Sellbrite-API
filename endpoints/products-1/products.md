---
title: "/products/{sku}"
slug: "products"
excerpt: "Upsert a product"
hidden: false
createdAt: "2018-11-28T00:39:24.583Z"
updatedAt: "2020-05-06T20:53:52.241Z"
---
This endpoint will upsert (create or update) a product.

Acceptable http methods are POST, PUT, PATCH.

Use this endpoint to create new individual products. After creating single products, you can group them together with the [variation_groups](#variation_groupssku) APIs

Parameter 'name' only required when creating product.