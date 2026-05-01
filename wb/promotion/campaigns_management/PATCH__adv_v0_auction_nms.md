# `PATCH` /adv/v0/auction/nms

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Changing the List of Product Cards in Campaigns**

Описание метода

The method allows you to add and remove product cards in campaigns.

For campaigns in statuses `4`, `9` and `11`.

The current minimum bid is set for the added products.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 1 request | 1 s | 1 request |
| Service | 1 s | 1 request | 1 s | 1 request |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nms` | array | ✓ | Product cards in campaigns |

[Request example](examples/PATCH__adv_v0_auction_nms_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nms` | array | ✓ | The result of processing the request |

[Response 200](../_shared/examples/PATCH__adv_v0_auction_nms_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID *Example: `camp-api-public-cache`* |
| `request_id` | string | ✓ | Unique request ID *Example: `6023d2950af564838f9b44a279d2140c`* |
| `status` | integer | ✓ | HTTP status code *Example: `400`* |
| `title` | string | ✓ | Error title *Example: `invalid payload`* |

[Response 400](../_shared/examples/PATCH__adv_v0_auction_nms_400.json)

- **401** Unauthorized
- **429** Too Many Requests
