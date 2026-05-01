# `POST` /api/v2/stocks-report/products/sizes

**Tag:** [Stocks Report](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Size Data**

Описание метода

Forms a dataset for inventory by the size of the product.

Possible cases:
1. The product has dimensions and `"includeOffice":true`, then the response body will contain data on the inventory for each of the sizes with nested details by warehouse.
2. The product has dimensions and `"includeOffice":false`, then the response body will contain data on the inventory for each of the sizes without nested details by warehouse.
3. The product has no size and `"include Office":true`, then the response body will contain details by warehouse without data on the inventory for each of the sizes.
4. The product has no size and `"include Office":false`, then the response body will be empty.
`The product has no size` means the size of the product is the same and has `"techSize":"0"`. In responses of the method for getting data on [products](./analytics#tag/Stocks-Report/paths/~1api~1v2~1stocks-report~1products~1products/post), such products have `hasSizes':false`.

The data on the seller's warehouses are in an aggregated form — for all of them together without detailing specific warehouses —  and responses contain `"regionName":"Маркетплейс"` and `"officeName":""` in such cases.

The report data is updated once an hour.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 3 requests |
| Service | 1 min | 3 requests | 20 s | 3 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nmID` | integer | ✓ | WB article *Example: `123456789`* |
| `currentPeriod` | PeriodInv | ✓ | Period |
| `stockType` | StockType | ✓ | Type of products storage warehouse:   - `""` — all   - `wb` — WB warehouses   - `mp` — seller's warehouses  |
| `orderBy` | TableOrderBy | ✓ | Sorting parameters |
| `includeOffice` | boolean | ✓ | Include warehouse details *Example: `True`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | TableSizeResponse | ✓ |  |

[Response 200](../_shared/examples/POST__api_v2_stocks_report_products_sizes_200.json)

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
