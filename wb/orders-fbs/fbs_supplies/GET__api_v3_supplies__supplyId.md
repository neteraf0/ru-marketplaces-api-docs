# `GET` /api/v3/supplies/{supplyId}

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Supply Details**

Описание метода

Returns supply details.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `supplyId` | path | string | ✓ | Supply ID *Example: `WB-GI-1234567`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | string |  | Supply ID *Example: `WB-GI-1234567`* |
| `isB2b` | boolean |  | Indicator of a B2B sale:   - `true` — B2B sale   - `false` — not B2B sale   - `null` — no value, no assembly orders added to the supply  |
| `done` | boolean |  | An indication that the supply is closed   - `true` — closed   - `false` — open  |
| `createdAt` | string |  | Supply creation date (RFC3339) *Example: `2022-05-04T07:56:29Z`* |
| `closedAt` | string |  | Supply close date (RFC3339) *Example: `2022-05-04T07:56:29Z`* |
| `scanDt` | string |  | Supply scan date (RFC3339) *Example: `2022-05-04T07:56:29Z`* |
| `name` | string |  | Supply name *Example: `My test supply`* |
| `cargoType` | integer (enum: 0, 1, 2, 3) |  | Type of cargo:   - `1` — small-sized goods   - `2` — over dimensional cargo (ODC)   - `3` — dimensional cargo+ (CD+)  |
| `crossBorderType` | integer (enum: 0, 1) |  | Supply type:   - `0` — Non-Cross-Border   - `1` — Cross-Border   - `null` — no value  *Example: `1`* |
| `destinationOfficeId` | integer |  | ID of the destination office for the supply. If `null`, destination office ID is not specified *Example: `123`* |
| `recommendedWhId` | integer |  | ID of the recommended warehouse for acceptance of the supply for Moscow and Moscow region.  The warehouse closest to the customers chain is defined automatically when the supply is transferred to delivery, taking into account the parameters of all assembly orders in the supply. If `0`, the recommended warehouse is not determined  *Example: `123569`* |

[Response 200](../_shared/examples/GET__api_v3_supplies__supplyId_200.json)

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
