# `GET` /adv/v1/count

**Tag:** [Media](index.md)

**Server:** `https://advert-media-api.wildberries.ru`

**Media Campaigns Number**

Описание метода

Method allows you to get the number of the seller's media campaigns.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 10 requests | 100 ms | 10 requests |
| Service | 1 s | 10 requests | 100 ms | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `all` | integer |  | Total number of media campaigns with all statuses and types |
| `adverts` | object |  |  |

[Response 200](../_shared/examples/GET__adv_v1_count_200.json)

- **401** Unauthorized
- **429** Too Many Requests
