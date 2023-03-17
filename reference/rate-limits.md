# Rate Limits

Information regarding rate limits for the Sellbrite API.

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

Clients who use the Sellbrite API are subjected to two rate limits:

* The maximum number of API calls per minute is 40 API requests.
* The maximum number of API calls per second is 2 API requests.

If your application hits the rate limit, an HTTP 403 Forbidden response will be returned with this body:

`Rate Limit Exceeded`
