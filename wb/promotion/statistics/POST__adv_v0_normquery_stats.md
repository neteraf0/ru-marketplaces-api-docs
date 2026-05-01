# `POST` /adv/v0/normquery/stats

**Tag:** [Statistics](index.md)

**Search Clusters Statistics**

Описание метода

The method returns statistics for search clusters over a specified period.
You can use this method only for campaigns with a `cpm` payment model — for displays.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 10 requests | 6 s | 20 requests |
| Service | 1 min | 10 requests | 6 s | 20 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `from` | string | ✓ | Period start date  *Example: `2025-10-07`* |
| `to` | string | ✓ | Period end date *Example: `2025-10-08`* |
| `items` | array | ✓ |  |

[Request example](examples/POST__adv_v0_normquery_stats_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stats` | array | ✓ |  |

[Response 200](../_shared/examples/POST__adv_v0_normquery_stats_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID *Example: `camp-api-public-cache`* |
| `request_id` | string | ✓ | Unique request ID *Example: `6023d2950af564838f9b44a279d2140c`* |
| `status` | integer | ✓ | HTTP status code *Example: `400`* |
| `title` | string | ✓ | Error title *Example: `invalid payload`* |

[Response 400](../_shared/examples/GET__api_advert_v2_adverts_400.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
