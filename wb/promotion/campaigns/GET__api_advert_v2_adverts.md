# `GET` /api/advert/v2/adverts

**Tag:** [Campaigns](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Campaigns Information**

Описание метода

The method returns information about campaigns with standard or custom bid via statuses, payment types and IDs.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 5 requests | 200 ms | 5 requests |
| Service | 1 s | 5 requests | 200 ms | 5 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `ids` | query | string |  | Campaign IDs, maximum 50 *Example: `12345,23456,34567,45678,56789`* |
| `statuses` | query | string |  | Campaign statuses: - `-1` — deleted, the deletion process will be completed within 10 minutes - `4` — ready to be launched - `7` — completed - `8` — declined - `9` — active - `11` — paused  *Example: `-1,4,8`* |
| `payment_type` | query | string (enum: cpm, cpc) |  | Payment type: - `cpm` — cost per mille - `cpc` — cost per click  |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `adverts` | array | ✓ | Campaigns |

[Response 200](../_shared/examples/GET__api_advert_v2_adverts_200.json)

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
- **429** Too Many Requests
