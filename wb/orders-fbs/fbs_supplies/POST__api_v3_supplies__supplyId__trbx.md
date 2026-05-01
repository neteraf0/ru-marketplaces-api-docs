# `POST` /api/v3/supplies/{supplyId}/trbx

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Add Shipping Units to the Supply**

Описание метода

Adds the required number of shipping units to the supply.


You should add shipping units only to supplies shipped to the pickup points.
You can add shipping units to an open supply only. You can add as many shipping units as there are items in the supply, plus one more shipping unit.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `supplyId` | path | string | ✓ | Supply ID *Example: `WB-GI-1234567`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `amount` | integer | ✓ | Shipping units amount to add to the supply *Example: `4`* |
## Responses

### `201` Created


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `trbxIds` | array |  | List of IDs of created shipping units |

[Response 201](../_shared/examples/POST__api_v3_supplies__supplyId__trbx_201.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
