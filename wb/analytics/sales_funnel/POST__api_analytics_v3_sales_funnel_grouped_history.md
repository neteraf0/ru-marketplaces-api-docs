# `POST` /api/analytics/v3/sales-funnel/grouped/history

**Tag:** [Sales Funnel](index.md)

**operationId:** `postSalesFunnelGroupedHistory`

**Server:** `https://seller-analytics-api.wildberries.ru`

**Grouped Product Cards Statistics per Days**

Описание метода

The method returns statistics for product cards by day or by week.
Product cards are grouped by subjects, brands and tags.
You can get data for a maximum of the last week.

The report data is updated once an hour.
Most of the data appears within an hour of the event:
  - orders
  - click-throughs
  - adds-to-Cart

A small part of this data may appear within a few days.

Purchases, cancellations, and returns are displayed in report for the day an item was ordered. For example, if an order was placed on January 1, and the customer returned the item on January 10, data about this return will appear in the report for January 1.
You can track the final sales results using [details for the realization reports](./financial-reports-and-accounting#tag/Financial-Reports/paths/~1api~1v5~1supplier~1reportDetailByPeriod/get).

The `brandNames`, `subjectIDs`, `tagIds`, and `nmIds` parameters can be empty `[]`, in which case the response will return all of the seller's product cards.

The product of the number of subjects, brands, and tags in the request cannot be more than 16. For example, 4 brands and 4 subjects or 2 subjects, 2 tags, and 4 brands.


  To get reports for a period of up to a year, use the Seller Analytics CSV methods — the GROUPED_HISTORY_REPORT type. Reports of this type are available only with Jam subscription


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
| `selectedPeriod` |  | ✓ |  |
| `brandNames` | array |  | List of brands for filtering *Example: `['nike', 'adidas']`* |
| `subjectIds` | array |  | List of subject IDs for filtering *Example: `[64, 334]`* |
| `tagIds` | array |  | List of label IDs for filtering *Example: `[32, 53]`* |
| `skipDeletedNm` | boolean |  | Skip deleted items |
| `aggregationLevel` | Level |  | Aggregation Type. If not specified, the default is aggregation by days.  Available aggregation levels: `day`, `week`  |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | GroupedHistoryResponse | ✓ | Statistics |

[Response 200](../_shared/examples/POST__api_analytics_v3_sales_funnel_grouped_history_200.json)

- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
