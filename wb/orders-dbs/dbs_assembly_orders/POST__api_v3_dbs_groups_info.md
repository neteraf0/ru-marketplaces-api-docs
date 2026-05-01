# `POST` /api/v3/dbs/groups/info

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Information on Paid Delivery**

Описание метода

The method provides information on paid delivery for assembly orders that have been received at a single warehouse (warehouseId) as part of a single buyer transaction (orderUid).


Request limit per one seller's account for DBS assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `groups` | array |  | List of `groupId` values. Can be obtained from [new](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1v3~1dbs~1orders~1new/get) and [completed](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1v3~1dbs~1orders/get) assembly orders. |
## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `groupID` | string |  | Assembly order group ID *Example: `0596a30a-d11c-4210-a231-ee1c39d61fe4`* |
  | `deliveryCost` | integer |  | The cost of paid delivery in the sale currency, multiplied by 100 *Example: `1108`* |
  | `convertedDeliveryCost` | integer |  | The cost of paid delivery in the seller's country currency, multiplied by 100. Provided for informational purposes *Example: `29803`* |
  | `currencyCode` | integer |  | Sale currency code *Example: `933`* |
  | `convertedCurrencyCode` | integer |  | Seller's country currency code *Example: `643`* |

[Response 200](../_shared/examples/POST__api_v3_dbs_groups_info_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbs_groups_info_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
