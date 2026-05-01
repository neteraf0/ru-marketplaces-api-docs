# `POST` /api/v3/stocks/{warehouseId}

**Tag:** [Seller Warehouses Inventory](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Inventory**

Описание метода

Returns product inventory.


Request limit per one seller's account for all inventory methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseId` | path | integer | ✓ | The seller's warehouse ID *Example: `2`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `chrtIds` | array | ✓ | Size IDs array |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stocks` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_stocks__warehouseId_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectRequestBody](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
