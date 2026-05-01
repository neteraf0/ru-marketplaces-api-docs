# `POST` /api/v2/search-report/product/search-texts

**Tag:** [Search Queries for Your Items](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Search Texts by Product**

Описание метода

Forms the top search texts by product.

Search text selection parameters:
  - `limit` — number of queries, maximum 30. For the **Advanced** and **Premium** [Jam](https://seller.wildberries.ru/monetization/tariffs) tariffs, the maximum is 100.
  - `topOrderBy` — method for selecting the top queries

The parameters `includeSubstitutedSKUs` and `includeSearchTexts` cannot both be set to `false`.

The report data is updated once an hour.


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
| `currentPeriod` | Period | ✓ | Current period |
| `pastPeriod` | pastPeriod |  | Previous period for comparison. Number of days — less than or equal to `currentPeriod` |
| `nmIds` | array | ✓ | WB article numbers list *Example: `[162579635, 166699779]`* |
| `topOrderBy` | string (enum: openCard, addToCart, openToCart, orders, cartToOrder) | ✓ | Filtering by the search queries that brought the most:   - `openCard` — click-throughs   - `addToCart` — adds-to-Cart   - `openToCart` — conversion to cart   - `orders` — items ordered   - `cartToOrder` — conversion to order  *Example: `openToCart`* |
| `includeSubstitutedSKUs` | boolean |  | Show data for direct queries with [promo items](https://seller.wildberries.ru/help-center/article/A-524) *Example: `True`* |
| `includeSearchTexts` | boolean |  | Show data for search queries without promo items |
| `orderBy` | OrderByGrTe | ✓ | Sorting parameters |
| `limit` | TextLimit | ✓ |  |
## Responses

### `200` Success


[Response 200](../_shared/examples/POST__api_v2_search_report_product_search_texts_200.json)

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
