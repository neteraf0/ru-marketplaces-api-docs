# `GET` /api/feedbacks/v1/pins/limits

**Tag:** [Pinned Feedback](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Pinned Feedback Limits**

Описание метода

The method returns the pinned feedback limits for a tariff and subscription.


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Responses

### `200` Success


[Response 200](../_shared/examples/GET__api_feedbacks_v1_pins_limits_200.json)

- **401** Unauthorized
- **429** Too Many Requests
