# `PUT` /adv/v0/auction/placements

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Changing Placements in Campaigns with Custom Bid**

Описание метода

The method allows you to change placements in campaigns with custom bid and per mille payment model — `cpm`.

For campaigns in statuses `4`, `9` and `11`.


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
| `placements` | array | ✓ | Placements in campaigns |

[Request example](examples/PUT__adv_v0_auction_placements_req.json)

## Responses

- **204** Success
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID *Example: `camp-api-public-cache`* |
| `request_id` | string | ✓ | Unique request ID *Example: `6023d2950af564838f9b44a279d2140c`* |
| `status` | integer | ✓ | HTTP status code *Example: `400`* |
| `title` | string | ✓ | Error title *Example: `invalid payload`* |

[Response 400: BadRequest](../_shared/examples/PUT__adv_v0_auction_placements_400_BadRequest.json)


[Response 400: BadAdvertPaymentType](../_shared/examples/PUT__adv_v0_auction_placements_400_BadAdvertPaymentType.json)

- **401** Unauthorized
- **429** Too Many Requests
