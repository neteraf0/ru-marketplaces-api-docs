# `GET` /api/v3/passes/offices

**Tag:** [FBS Passes](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Offices for Pass**

Описание метода

Returns a list of offices that require a pass.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `name` | string |  | Name *Example: `Koledino`* |
  | `address` | string |  | Address *Example: `Kosmonavtov 10А`* |
  | `id` | integer |  | ID *Example: `1`* |

[Response 200](../_shared/examples/GET__api_v3_passes_offices_200.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
