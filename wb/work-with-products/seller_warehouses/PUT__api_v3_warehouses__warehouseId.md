# `PUT` /api/v3/warehouses/{warehouseId}

**Tag:** [Seller Warehouses](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Update Warehouse**

Описание метода

Updates the seller's warehouse details. Changing the linked office is allowed once per day. You cannot link an office that is already in use.


Request limit per one seller's account for all seller warehouses methods:

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
| `name` | string | ✓ | Seller's warehouse name *Example: `Koledino`* |
| `officeId` | integer | ✓ | Office ID *Example: `15`* |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectRequestBody](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequestBody.json)


[Response 400: WarehouseNameInvalid](../_shared/examples/POST__api_v3_warehouses_400_WarehouseNameInvalid.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
### `409` Error updating a warehouse


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 409](../_shared/examples/POST__api_v3_warehouses_409.json)

- **429** Too Many Requests
