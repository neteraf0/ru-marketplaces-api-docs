# `GET` /api/v3/passes

**Tag:** [FBS Passes](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Passes**

Описание метода

Returns a list of all seller's passes.


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
  | `firstName` | string |  | First name *Example: `Alex`* |
  | `dateEnd` | string |  | Pass expiration date *Example: `2022-07-31 17:53:13+00:00`* |
  | `lastName` | string |  | Last name *Example: `Petrov`* |
  | `carModel` | string |  | Car model *Example: `Lamborghini`* |
  | `carNumber` | string |  | Car number *Example: `A456BC123`* |
  | `officeName` | string |  | Office name *Example: `Koledino`* |
  | `officeAddress` | string |  | Office address *Example: `Kosmonavtov 10А`* |
  | `officeId` | integer |  | Office ID *Example: `15`* |
  | `id` | integer |  | Pass ID *Example: `1`* |

[Response 200](../_shared/examples/GET__api_v3_passes_200.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
