# `POST` /api/advert/v1/bids/min

**Tag:** [Campaigns Creation](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Minimum Bids for Product Cards**

Описание метода

Method allows minimum bids for product cards in kopecks depending on the payment type and placements.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 20 requests | 3 s | 5 requests |
| Service | 1 min | 20 requests | 3 s | 5 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `advert_id` | integer | ✓ | Campaign ID |
| `nm_ids` | array | ✓ | WB articles list |
| `payment_type` | string (enum: cpm, cpc) | ✓ | Payment type:   - `cpm` — per mille   - `cpc` — per click  |
| `placement_types` | array | ✓ | Placements:   - `search` — search   - `recommendation` — recommendation   - `combined` — search and recommendation  |

[Request example](examples/POST__api_advert_v1_bids_min_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bids` | array | ✓ | List of product cards with bids |

[Response 200](../_shared/examples/POST__api_advert_v1_bids_min_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details *Example: `some nms are not belong to advert`* |
| `origin` | string | ✓ | WB internal service ID *Example: `camp-api-public-cache`* |
| `request_id` | string | ✓ | Unique request ID *Example: `123e4567-e89b-12d3-a456-426614174000`* |
| `status` | integer | ✓ | HTTP Status Code *Example: `400`* |
| `title` | string | ✓ | Error title *Example: `Invalid Params`* |

[Response 400](../_shared/examples/POST__api_advert_v1_bids_min_400.json)

- **401** Unauthorized
- **429** Too Many Requests
