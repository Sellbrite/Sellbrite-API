---
title: "/inventory"
slug: "inventory-2"
excerpt: "Adjusts the inventory for the given sku and warehouse_uuid (up to 50 individual inventories may be adjusted in one API call).  Adjustments are queued and processed asynchronously in the background.  If the inventory record has not yet been created this endpoint will automatically create the missing inventory records before applying the adjustment.\n\nExactly one of \"on_hand\" or \"available\" field must exist for each individual inventory payload.  A pre-validation error will occur for the entire api call if ANY inventory payload includes both fields or if any payload is found to be missing both fields."
hidden: false
createdAt: "2018-01-23T19:13:05.058Z"
updatedAt: "2018-12-21T22:13:37.164Z"
---
[block:callout]
{
  "type": "warning",
  "body": "Only 50 inventory records can be updated per API call to the PUT /inventory endpoint",
  "title": "Note on update limits"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Sellbrite uses 3 internal values to track inventory: \"on_hand\", \"reserved\" and \"available\".  \"on_hand\" is the value Sellbrite believes to be physically present in a warehouse, while \"reserved\" is the assignment of open orders against that inventory.  \"available\" is always \"on_hand minus reserved\" and it is what Sellbrite uses to sync remaining available inventory to the listings.  Using the api you may update either \"on_hand\" or \"available\" and Sellbrite will adjust the other internal values.  \n\nSend us \"available\" instead of \"on_hand\" to avoid the double deduction problem as described here:\n\nSuppose you have an \"on_hand\" of 3, \"reserved\" of 0 and \"available\" of 3.  When Sellbrite receives an order for 1 pc, Sellbrite will then have \"on_hand\" of 3, \"reserved\" of 1 and \"available\" of 2.  If you are also fetching new orders through Sellbrite's orders api, you may also be deducting your own internal inventory from 3 to 2.  If you also periodically update Sellbrite with your new inventory you could be \"double deducting\" the inventory in Sellbrite if you send us \"on_hand\" of 2, because Sellbrite would then have: \"on_hand\" of 2, \"reserved\" of 1 and \"available\" of 1, when really we should still have available of 2.  If instead you send \"available\" of 2, Sellbrite would still have: \"on_hand\" of 3, \"reserved\" of 1, and \"available\" of 2 (no adjustment needed), and would be in agreement with your system.",
  "title": "A word on when to use \"on_hand\" vs \"available\""
}
[/block]