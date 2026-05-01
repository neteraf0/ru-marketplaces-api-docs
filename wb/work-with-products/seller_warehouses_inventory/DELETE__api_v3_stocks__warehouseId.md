# `DELETE` /api/v3/stocks/{warehouseId}

**Tag:** [Seller Warehouses Inventory](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delete Inventory**

Описание метода

Deletes product inventory.


  This action is irreversible. Deleted stock will require re-uploading to continue sales


Request limit per one seller's account for all inventory methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 10 requests | 6 s | 2 requests |

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

- **204** Deleted
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
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 404](../_shared/examples/DELETE__api_v3_stocks__warehouseId_404.json)

### `409` Error deleting inventory


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 409: StoreIsProcessing](../_shared/examples/DELETE__api_v3_stocks__warehouseId_409_StoreIsProcessing.json)

- **429** Too Many Requests
