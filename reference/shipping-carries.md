# Shipping Carriers and Methods

---

### Menu

[Introduction](introduction)

[Credentials](credentials)

[Authentication](authentication)

[Rate Limits](rate-limits)

[DateTime Format](datetime-format)

[Carrier Names](carrier-names)

[Shipping Carries and Methods](shipping-carries)

---

Most channels do not require and do not accept carrier specific shipping methods. One exception is Sears, which requires a specific shipping method name that is compatible with the provided carrier name. Below is a list of accepted shipping methods that you can provide when creating a shipment for a specific carrier in Sellbrite. Sellbrite will use this in the api call to the channel if it is required.

**Examples**

shipping carrier: "USPS"

shipping method: "Priority Mail"



shipping carrier: "USPS"

shipping method: "Priority Mail International"



shipping carrier: "DHL eCommerce"

shipping method: "Domestic Express Doc"



USPS
```
Priority Mail
Priority Mail Express
First Class Mail
Parcel Select
Media Mail
Priority Mail International
Priority Mail Express International
First Class Mail International
```

FedEx
```
Ground
Home Delivery
SmartPost
2 Day
2 Day A.M.
Express Saver
Standard Overnight
Priority Overnight
First Overnight
International Economy
International Priority
International First
Europe First International Priority
```

UPS
```
Standard
Ground
Saver
Three-Day Select
Second Day Air
Second Day Air A.M.
Next Day Air
Next Day Air Saver
Next Day Air Early A.M.
Mail Innovations
SurePost
SurePost Lightweight
Express
Express Plus
Expedited
```

Australia Post
```
Express Post
Parcel Post
```

Canada Post
```
Regular Parcel
Expedited Parcel
Priority
Xpresspost
Xpresspost International
Xpresspost USA
Expedited Parcel USA
Packet USA
Small Packet USA Air
Tracked Packet International
Small Package International Air
```

Deutsche Post
```
Postkarte
Standardbrief
Kompaktbrief
Grossbrief
Maxibrief
Maxibrief Plus
```

DHL Express
```
Domestic Express Doc
Economy Select Doc
Express Worldwide Nondoc
Express Worldwide Doc
Worldwide
Express Worldwide EU Doc
Break Bulk Express Doc
Express 9:00 NonDoc
Economy Select NonDoc
Break Bulk Economy Doc
Express 9:00 Doc
Express 10:30 Doc
Express 10:30 NonDoc
Express 12:00 Doc
Europack NonDoc
Express Envelope Doc
Express 12:00 NonDoc
Express Worldwide (B2C) Doc
Express Worldwide (B2C) NonDoc
Medical Express
Express Easy NonDoc
```

DHL eCommerce
```
First Class Expedited
Priority Expedited
BPM Ground
BPM Expedited
Marketing Parcel Ground
Marketing Parcel Expedited
Parcel Plus Ground
Parcel Plus Expedited
Parcel Plus Expedited Max
Parcels Ground Expedited
Parcels Expedited
Parcels Expedited Max
Ground
Expedited (for Flats)
Light (for EZ Return)
Plus (for EZ Return)
```

Lasership
```
Routed Delivery
```

OnTrac
```
Ground
Sunrise Gold
Sunrise
```

Royal Mail
```
1st Class
Signed For 1st Class
2nd Class
Signed For 2nd Class
Special Delivery Guaranteed by 9am
Special Delivery Guaranteed by 1pm
```

