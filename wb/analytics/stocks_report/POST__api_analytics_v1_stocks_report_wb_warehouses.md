# `POST` /api/analytics/v1/stocks-report/wb-warehouses

**Tag:** [Stocks Report](index.md)

**operationId:** `postV1StocksReportWbWarehouses`

**Server:** `https://seller-analytics-api.wildberries.ru`

**WB Warehouses Inventory**

Описание метода

Method is available by token types: Personal, Service

The method returns current WB warehouses inventory.

The data is updated once every 30 minutes.

1 response row means data on 1 item size in 1 WB warehouse.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 3 requests | 20 s | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nmIds` | array |  | WB articles *Example: `[111222333, 47254354]`* |
| `chrtIds` | array |  | Size IDs. It is used only for the articles specified in the `nmIds` array *Example: `[111222333, 91663228]`* |
| `limit` | integer |  | Number of rows in the response *Example: `250000`* |
| `offset` | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element *Example: `500000`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | InventoryWbResponse | ✓ | Current WB warehouses inventory |

[Response 200](../_shared/examples/POST__api_analytics_v1_stocks_report_wb_warehouses_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title *Example: `Invalid request body`* |
| `detail` | string | ✓ | Error details *Example: `code=400, message=invalid: positionCluster (field required), limit (field required), offset (field required), internal=invalid: positionCluster (field required), limit (field required), offset (field required`* |
| `requestId` | string | ✓ | Unique request ID *Example: `fb25c9e9-cae8-52db-b68e-736c1466a3f5`* |
| `origin` | string | ✓ | Internal WB service ID *Example: `analytic-open-api`* |

[Response 400](../_shared/examples/POST__api_v2_search_report_report_400.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title *Example: `Authorization error`* |
| `detail` | string | ✓ | Error details *Example: `Authorization error`* |
| `requestId` | string | ✓ | Unique request ID *Example: `fb25c9e9-cae8-52db-b68e-736c1466a3f5`* |
| `origin` | string | ✓ | Internal WB service ID *Example: `analytic-open-api`* |

[Response 403](../_shared/examples/POST__api_v2_search_report_report_403.json)

- **429** Too Many Requests
