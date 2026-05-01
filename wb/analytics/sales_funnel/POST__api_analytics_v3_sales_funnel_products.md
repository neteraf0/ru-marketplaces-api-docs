# `POST` /api/analytics/v3/sales-funnel/products

**Tag:** [Sales Funnel](index.md)

**operationId:** `postSalesFunnelProducts`

**Server:** `https://seller-analytics-api.wildberries.ru`

**Product Cards Statistics per Period**

Описание метода

The method generates a report on products by comparing key metrics for the current period with a similar past one.

The report data is updated once an hour.

Most of the data appears within an hour of the event:
  - orders
  - click-throughs
  - adds-to-Cart

A small part of this data may appear within a few days.

Purchases, cancellations, and returns are displayed in report for the day an item was ordered. For example, if an order was placed on January 1, and the customer returned the item on January 10, data about this return will appear in the report for January 1.
You can track the final sales results using [details for the realization reports](./financial-reports-and-accounting#tag/Financial-Reports/paths/~1api~1v5~1supplier~1reportDetailByPeriod/get).

The `brandNames`, `subjectIds`, `tagIds`, and `nmIds` parameters can be empty `[]`, in which case the response will return all of the seller's product cards.

If you specify multiple parameters, the response will include cards that match all of these parameters simultaneously. If no cards match the request parameters, an empty response `[]` will be returned.

You can get a report for a maximum of the last 365 days.

In the previous period's data:
* The data in `pastPeriod` covers the same duration as in `selectedPeriod`
* If the `pastPeriod` start date is more than a year before the current date, it will be adjusted to: `pastPeriod.start = current date - 365 days`

Pagination can be used.


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
| `pastPeriod` |  |  |  |
| `nmIds` | array |  | WB articles to include in the report. Leave empty to get a report for all products  *Example: `[1234567]`* |
| `brandNames` | array |  | List of brands for filtering *Example: `['nike', 'adidas']`* |
| `subjectIds` | array |  | List of subject IDs for filtering *Example: `[64, 334]`* |
| `tagIds` | array |  | List of label IDs for filtering *Example: `[32, 53]`* |
| `skipDeletedNm` | boolean |  | Skip deleted items |
| `orderBy` | OrderBy |  | Sorting parameters |
| `limit` | integer |  | Number of product cards in the response *Example: `231`* |
| `offset` | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element *Example: `10`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` |  | ✓ |  |

[Response 200](../_shared/examples/POST__api_analytics_v3_sales_funnel_products_200.json)

- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
