# Authentication

---

### Menu

[Getting Started with Sellbrite API](/Sellbrite-API)

[Test/Developer accounts](dev-accounts)

[Finding your API credentials](credentials)

[Authentication](authentication)

---

The Sellbrite API uses Basic HTTP authentication. Please use your `account token` as the "username" and the `secret key` as the "password." The `account token` and `secret key` can be found under the "API" section of the settings page of your Sellbrite account. The Authorization field is constructed as follows:


* Username ( `account token` ) and password ( `secret key` ) are combined into a string "username:password"
* The resulting string is encoded using the RFC2045-MIME variant of Base64
* The authorization method and a space i.e. "Basic " is then put before the encoded string.

For example, given the `account token` "Aladdin" and the `secret key` as "OpenSesame",
the authorization field should end up as Authorization: "Basic QWxhZGRpbjpPcGVuU2VzYW1l"

```cURL
curl --user aladdin:opensesame "https://app.sellbrite.com/api/v1/orders/7777"
```

