---
title: "/channels"
slug: "channels"
excerpt: "Get a list of channels"
hidden: false
createdAt: "2017-01-31T00:31:26.497Z"
updatedAt: "2017-05-25T22:04:35.789Z"
---
[block:api-header]
{
  "type": "basic",
  "title": "Channel properties"
}
[/block]

[block:parameters]
{
  "data": {
    "0-0": "uuid",
    "0-1": "Channel identifier.",
    "h-0": "Parameter",
    "h-1": "Description",
    "h-2": "Type",
    "0-2": "String",
    "1-0": "name",
    "1-1": "Merchant provided name of the channel",
    "1-2": "String",
    "2-0": "state",
    "2-1": "Connection status of the channel.\n<p></p>\n**\"active\"**: Channel is active\n**\"inactive\"**: Channel has been deactivated by the merchant\n**\"disconnected\"**: Channel has been disconnected as a result of an invalid token.",
    "2-2": "String",
    "3-0": "channel_type_display_name",
    "3-1": "Channel type display name (\"eBay\", \"Amazon\", \"Etsy\", etc.)",
    "3-2": "String",
    "4-0": "created_at",
    "4-1": "When channel was created in Sellbrite (ISO 8601).",
    "4-2": "String",
    "5-0": "site_id",
    "5-1": "Marketplace region id",
    "5-2": "String",
    "6-0": "channel_site_region",
    "6-1": "Name of the site region of the channel (\"Amazon.co.uk (United Kingdom)\", \"eBay UK\")\n** *For international channels **",
    "6-2": "String"
  },
  "cols": 3,
  "rows": 7
}
[/block]