# `POST` /adv/v0/normquery/bids

**Tag:** [Search Clusters](index.md)

**Set Bids for Search Clusters**

Описание метода

The method sets the bids for search clusters.
You can use this method only for campaigns with:
  - custom bid
  - a `cpm` payment model — per displays


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 2 requests | 500 ms | 4 requests |
| Service | 1 s | 2 requests | 500 ms | 4 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bids` | array | ✓ |  |

[Request example](examples/POST__adv_v0_normquery_bids_req.json)

## Responses

- **200** Success
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
