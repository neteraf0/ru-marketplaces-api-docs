# `POST` /adv/v0/normquery/get-bids

**Tag:** [Search Clusters](index.md)

**List of Search Clusters Bids**

Описание метода

The method returns a list of search clusters with bids by:
  - campaign IDs
  - WB articles


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 5 requests | 200 ms | 10 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ |  |

[Request example](examples/POST__adv_v0_normquery_get_bids_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bids` | array | ✓ |  |

[Response 200](../_shared/examples/POST__adv_v0_normquery_get_bids_200.json)

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
