# `POST` /adv/v0/normquery/list

**Tag:** [Search Clusters](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Active and Inactive Search Cluster Lists**

Описание метода

Returns lists of active and inactive search clusters with at least 100 views.

Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 5 requests | 200 ms | 10 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ |  |

[Request example](examples/POST__adv_v0_normquery_list_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ |  |

[Response 200](../_shared/examples/POST__adv_v0_normquery_list_200.json)

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
