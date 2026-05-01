# `POST` /api/v2/search-report/table/details

**Tag:** [Search Queries for Your Items](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Pagination by Products Within a Group**

Описание метода

Pagination by products within a group. It is possible regardless of the presence of filters.

Filters for pagination by products within a group or without filters:
  - tuple `subjectId`, `brandName`, `tagId` — filter for the group
  - `nmIds` — filter by nomenclature

Additional parameters for selecting the list of products in the table:
  - `positionCluster` — average position in search

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
| `subjectId` | integer |  | Subject ID *Example: `123`* |
| `brandName` | string |  | Product name *Example: `Apple`* |
| `tagId` | integer |  | Label ID *Example: `45`* |
| `nmIds` | array |  | WB article numbers list *Example: `[162579635, 166699779]`* |
| `orderBy` | OrderByMainAndDetails | ✓ | Sorting parameters |
| `positionCluster` | string (enum: all, firstHundred, secondHundred, below) | ✓ | Which average search position of products to display in the report:   - `all` — all   - `firstHundred` — from 1 to 100   - `secondHundred` — from 101 to 200   - `below` — from 201 and below  |
| `includeSubstitutedSKUs` | boolean |  | Show data for direct queries with [promo items](https://seller.wildberries.ru/help-center/article/A-524) *Example: `True`* |
| `includeSearchTexts` | boolean |  | Show data for search queries without promo items |
| `limit` | integer | ✓ | Number of products in the response *Example: `150`* |
| `offset` | integer | ✓ | From which element to start outputting data *Example: `100`* |
## Responses

### `200` Success


[Response 200](../_shared/examples/POST__api_v2_search_report_table_details_200.json)

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
