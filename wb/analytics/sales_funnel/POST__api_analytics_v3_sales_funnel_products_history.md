# `POST` /api/analytics/v3/sales-funnel/products/history

**Tag:** [Sales Funnel](index.md)

**operationId:** `postSalesFunnelProductsHistory`

**Server:** `https://seller-analytics-api.wildberries.ru`

**Product Cards Statistics per Days**

Описание метода

The method returns statistics for product cards by day or by week.
You can get data for a maximum of the last week.

The report data is updated once an hour.

Most of the data appears within an hour of the event:
  - orders
  - click-throughs
  - adds-to-Cart

A small part of this data may appear within a few days.

Purchases, cancellations, and returns are displayed in report for the day an item was ordered. For example, if an order was placed on January 1, and the customer returned the item on January 10, data about this return will appear in the report for January 1.
You can track the final sales results using [details for the realization reports](./financial-reports-and-accounting#tag/Financial-Reports/paths/~1api~1v5~1supplier~1reportDetailByPeriod/get).


  To get reports for a period of up to a year, use the Seller Analytics CSV methods — the DETAIL_HISTORY_REPORT type. Reports of this type are available only with Jam subscription


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
| `nmIds` | array | ✓ | WB articles to include in the report |
| `skipDeletedNm` | boolean |  | Skip deleted items |
| `aggregationLevel` | Level |  | Aggregation Type. If not specified, the default is aggregation by days.  Available aggregation levels: `day`, `week`  |
## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `product` |  | ✓ |  |
  | `history` | array | ✓ | Statistics per period |
  | `currency` | Currency | ✓ | Report currency |

[Response 200](../_shared/examples/POST__api_analytics_v3_sales_funnel_products_history_200.json)

- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
