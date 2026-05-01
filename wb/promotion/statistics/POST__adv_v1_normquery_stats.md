# `POST` /adv/v1/normquery/stats

**Tag:** [Statistics](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Daily Search Clusters Statistics**

Описание метода

Returns statistics (views, clicks, add-to-cart, orders, CTR, CPC, CPM, etc.) by search clusters for the specified period detailed by day.


 You can use this method for campaigns with `cpm` — for displays, and `cpc` — for clicks payment models.

Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 10 requests | 6 s | 20 requests |
| Service | 1 min | 10 requests | 6 s | 20 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `from` | string | ✓ | Period start date *Example: `2025-01-01`* |
| `to` | string | ✓ | Period end date *Example: `2025-01-31`* |
| `items` | array | ✓ |  |

[Request example](examples/POST__adv_v1_normquery_stats_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ |  |

[Response 200](../_shared/examples/POST__adv_v1_normquery_stats_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID *Example: `camp-api-public-cache`* |
| `request_id` | string | ✓ | Unique request ID *Example: `6023d2950af564838f9b44a279d2140c`* |
| `status` | integer | ✓ | HTTP status code *Example: `400`* |
| `title` | string | ✓ | Error title *Example: `invalid payload`* |

[Response 400](../_shared/examples/POST__adv_v1_normquery_stats_400.json)

- **401** Unauthorized
- **429** Too Many Requests
