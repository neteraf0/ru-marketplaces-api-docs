# `POST` /api/v2/stocks-report/products/products

**Tag:** [Stocks Report](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Product Data**

Описание метода

Forms a dataset for inventory by products.

You can get data for individual products as well as for the entire report if there are no filters in the query: `nmIDs`, `subjectID`, `brandName`, `tagID`.

The report data is updated once an hour.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 3 requests | 20 s | 3 requests |


## Request Body

Content-Type: `application/json`


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | TableProductResponse | ✓ |  |

[Response 200](../_shared/examples/POST__api_v2_stocks_report_products_products_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title *Example: `Invalid request body`* |
| `detail` | string | ✓ | Error details *Example: `code=400, message=invalid: positionCluster (field required), limit (field required), offset (field required), internal=invalid: positionCluster (field required), limit (field required), offset (field required`* |
| `requestId` | string | ✓ | Unique request ID *Example: `fb25c9e9-cae8-52db-b68e-736c1466a3f5`* |
| `origin` | string | ✓ | Internal WB service ID *Example: `analytic-open-api`* |

[Response 400](../_shared/examples/POST__api_v2_search_report_report_400.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title *Example: `Authorization error`* |
| `detail` | string | ✓ | Error details *Example: `Authorization error`* |
| `requestId` | string | ✓ | Unique request ID *Example: `fb25c9e9-cae8-52db-b68e-736c1466a3f5`* |
| `origin` | string | ✓ | Internal WB service ID *Example: `analytic-open-api`* |

[Response 403](../_shared/examples/POST__api_v2_search_report_report_403.json)

- **429** Too Many Requests
