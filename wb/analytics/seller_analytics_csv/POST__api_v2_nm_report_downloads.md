# `POST` /api/v2/nm-report/downloads

**Tag:** [Seller Analytics CSV](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Create the Report**

Описание метода

The method creates a task for generating a report with advanced seller analytics.

You can create a CSV-version of [sales funnel](./analytics#tag/Sales-Funnel) or [search parameters](./analytics#tag/Search-Queries-for-Your-Items) report with grouping:

  * by WB articles
  * by categories, brands, and labels

In each of reports on sales funnel, you can group data by days, weeks, or months.

Also you can create a CSV-version of [search texts](./analytics#tag/Search-Queries-for-Your-Items/paths/~1api~1v2~1search-report~1product~1search-texts/post) or [inventory](./analytics#tag/Stocks-Report) report.


Each new report must have a unique ID.


  Do not use the same ID for different reports — this may cause errors during generation


The set of parameters in the `params` object depends on the report type. To get a description of the parameters, select the report type from the dropdown list in the description of the `reportType` parameter.

The parameters `includeSubstitutedSKUs` and `includeSearchTexts` cannot both be set to `false`

If it was not possible to [get report](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads~1file~1%7BdownloadId%7D/get), you can create a [repeat generation task](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads~1retry/post). You can also [get a list and check the statuses](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads/get) of reports.


  Inventory reports — the STOCK_HISTORY_REPORT_CSV and STOCK_HISTORY_DAILY_CSV types — can be created without Jam subscription


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 3 requests |
| Service | 1 min | 3 requests | 20 s | 3 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

Content-Type: `application/json`


[Request: SalesFunnelProductReq](examples/POST__api_v2_nm_report_downloads_req_SalesFunnelProductReq.json)


[Request: SalesFunnelGroupReq](examples/POST__api_v2_nm_report_downloads_req_SalesFunnelGroupReq.json)


[Request: SearchReportGroupReq](examples/POST__api_v2_nm_report_downloads_req_SearchReportGroupReq.json)


[Request: SearchReportProductReq](examples/POST__api_v2_nm_report_downloads_req_SearchReportProductReq.json)


[Request: SearchReportTextReq](examples/POST__api_v2_nm_report_downloads_req_SearchReportTextReq.json)


[Request: InventoryMetricsReportReq](examples/POST__api_v2_nm_report_downloads_req_InventoryMetricsReportReq.json)


[Request: InventoryHistoryReportReq](examples/POST__api_v2_nm_report_downloads_req_InventoryHistoryReportReq.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | string | ✓ | Notification that report generation has started. *Example: `Началось формирование файла/отчета`* |

[Response 200](../_shared/examples/POST__api_v2_nm_report_downloads_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title |
| `detail` | string | ✓ | Error details |
| `requestId` | string | ✓ | Unique request ID |
| `origin` | string | ✓ | WB internal service ID |

[Response 400: errorExample](../_shared/examples/POST__api_v2_nm_report_downloads_400_errorExample.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title |
| `detail` | string |  | Error details |
| `requestId` | string |  | Unique request ID |
| `origin` | string |  | WB internal service ID |

[Response 403: errorExample](../_shared/examples/POST__api_v2_nm_report_downloads_403_errorExample.json)

### `429` Too many requests


[Response 429](../_shared/examples/POST__api_v2_nm_report_downloads_429.json)
