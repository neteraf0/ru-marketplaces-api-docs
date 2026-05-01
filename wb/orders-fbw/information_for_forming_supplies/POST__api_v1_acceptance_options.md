# `POST` /api/v1/acceptance/options

**Tag:** [Information for Forming Supplies](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Acceptance Options**

Описание метода

The method returns information about warehouses and package types available for supply. The warehouses list is determined by product's barcode and quantity


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 6 requests | 10 s | 6 requests |
| Service | 1 min | 6 requests | 10 s | 6 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseID` | query | integer |  | Warehouse ID.  If the parameter is not specified, data for all warehouses is returned.  **Maximum is one value** *Example: `507`* |

## Request Body

Content-Type: `application/json`

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `quantity` | integer |  | Total quantity of products planned for supply.  **Maximum 999999**  |
  | `barcode` | string |  | Barcode from the card of the product |

[Request: RequestOptions](examples/POST__api_v1_acceptance_options_req_RequestOptions.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  |  |
| `requestId` | string |  | Request ID if an error is present |

[Response 200: Response](../_shared/examples/POST__api_v1_acceptance_options_200_Response.json)

### `400` Incorrect request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 400: BadWarehouseIDsParam](../_shared/examples/POST__api_v1_acceptance_options_400_BadWarehouseIDsParam.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Access denied
- **404** Not found
- **429** Too Many Requests
