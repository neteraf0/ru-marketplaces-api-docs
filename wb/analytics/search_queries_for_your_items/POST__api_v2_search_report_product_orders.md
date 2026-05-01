# `POST` /api/v2/search-report/product/orders

**Tag:** [Search Queries for Your Items](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Orders and Positions by Item Search Texts**

Описание метода

The method forms data for the table:
  - about orders for each search query for a specific item
  - about item positions in search results for each query

The data is provided within the period for the [requested item](./analytics#tag/Search-Queries-for-Your-Items/paths/~1api~1v2~1search-report~1product~1search-texts/post) and grouped by day. The maximum period is 7 days.

The report data is updated once per hour.


  You can get a report for a maximum of the last 365 days from the moment of the request


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 3 requests |
| Service | 1 min | 3 requests | 20 s | 3 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `period` | PeriodOrdersRequest | ✓ | Current period. Maximum of 7 days |
| `nmId` | integer | ✓ | WB article *Example: `211131895`* |
| `searchTexts` | array | ✓ | Search texts. For the **Advanced** and **Premium** [Jam](https://seller.wildberries.ru/monetization/tariffs) tariffs, the maximum is 100  *Example: `['костюм', 'пиджак']`* |
## Responses

### `200` Success


[Response 200](../_shared/examples/POST__api_v2_search_report_product_orders_200.json)

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
