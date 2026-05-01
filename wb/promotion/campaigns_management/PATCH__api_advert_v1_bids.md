# `PATCH` /api/advert/v1/bids

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Changing Campaigns Bids**

Описание метода

The method changes the bids of product cards by WB articles in campaigns:
  - with standard bid
  - with custom bid
  - with a `cpc` payment model — per click

For campaigns in statuses `4`, `9` and `11`.

Specify the placement in the request parameter `placement`:
  - `combined` —  in search and recommendations for campaigns with standard bid
  - `search `or `recommendations` — in search or recommendations for campaigns with custom bid


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 5 requests | 200 ms | 5 requests |
| Service | 1 s | 5 requests | 200 ms | 5 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bids` | array | ✓ | Bids in campaigns, kopecks |

[Request example](examples/PATCH__api_advert_v1_bids_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bids` | array | ✓ | The result of processing the request |

[Response 200](../_shared/examples/PATCH__api_advert_v1_bids_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID *Example: `camp-api-public-cache`* |
| `request_id` | string | ✓ | Unique request ID *Example: `6023d2950af564838f9b44a279d2140c`* |
| `status` | integer | ✓ | HTTP status code *Example: `400`* |
| `title` | string | ✓ | Error title *Example: `invalid payload`* |

[Response 400](../_shared/examples/PATCH__api_advert_v1_bids_400.json)

- **401** Unauthorized
- **429** Too Many Requests
