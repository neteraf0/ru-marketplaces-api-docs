# `GET` /adv/v1/promotion/count

**Tag:** [Campaigns](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Campaigns Lists**

Описание метода

Method allows to get campaigns lists grouped by type and status with information about last campaign change date.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 5 requests | 200 ms | 5 requests |
| Service | 1 s | 5 requests | 200 ms | 5 requests |
| Base | 1 h | 4 requests | 15 min | 1 request |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `adverts` | array |  | Campaign data |
| `all` | integer |  | Total number of campaigns with all statuses and types |

[Response 200](../_shared/examples/GET__adv_v1_promotion_count_200.json)

- **401** Unauthorized
- **429** Too Many Requests
