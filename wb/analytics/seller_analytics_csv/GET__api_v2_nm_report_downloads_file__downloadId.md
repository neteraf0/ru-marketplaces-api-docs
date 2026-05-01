# `GET` /api/v2/nm-report/downloads/file/{downloadId}

**Tag:** [Seller Analytics CSV](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get the Report**

Описание метода

The method provides a report with advanced seller analytics by [generation task](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads/post) ID.

You can get a report that was generated within the last 48 hours.The report will be downloaded inside a ZIP archive in CSV format.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 3 requests |
| Service | 1 min | 3 requests | 20 s | 3 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `downloadId` | path | string | ✓ | Report ID |

## Responses

### `200` Success

`string` — Fields description in the CSV file:


**Sales funnel reports**

| Name | Type | Format | Description |
|-----------------| --- | --- | --- |
| nmID (only `DETAIL_HISTORY_REPORT`) | integer | int32 | WB article |
| dt | string | date | Date |
| openCardCount | integer | int32 | Click-throughs |
| addToCartCount | integer | int32 | Adds-to-Cart |
| ordersCount | integer | int32 | Items ordered |
| ordersSumRub | integer | int32 | Total order value |
| buyoutsCount | integer | int32 | Items purchased |
| buyoutsSumRub | integer | int32 | Total purchase value |
| cancelCount | integer | int32 | Items canceled and returned |
| cancelSumRub | integer | int32 | Canceled and returned item value |
| addToCartConversion | number | int32 | Conversion to Cart, % (Percentage of visitors who added the product to the cart after opening the product page) |
| cartToOrderConversion | integer | int32 | Conversion to order, % (Percentage of visitors who made an order after adding the product to the cart) |
| buyoutPercent | integer | int32 | Purchase rate, % (Percentage of visitors who ordered the product and purchased it. Excluding products still being delivered to the buyer) |
| addToWishlist | integer | int32 | Adds-to-Favorites |
| currency | string | string | Report currency |


**Search parameters report. By categories, brands, and labels**

| Name | Type | Format | Description |
|-----------------| --- | --- | --- |
| SubjectName |	string | string | Subject name |
| SubjectID | integer | int32 | Subject ID |
| BrandName | string | string | Brand |
| TagID | integer | int64 | Label ID |
| AveragePosition | integer | uint64 | Average product position in search results in the current period |
| OpenCard | integer | uint64 | Click-throughs from search in the current period |
| AddToCart | integer | uint64 | Adds-to-Cart from search in the current period |
| OpenToCart | integer | uint64	| Conversion to cart from search in the current period |
| Orders | integer | uint64 | Items ordered from search in the current period |
| CartToOrder | integer | uint64 | Conversion to order from search in the current period |
| Visibility  |integer | uint64 | Visibility in search results in the current period. Probability percentage that a user will see the product card. Depends on the average position |
| AveragePositionPast | integer | uint64 | Average product position in search results in the past period (filled in if the previous period is specified) |
| OpenCardPast | integer | uint64 | Click-throughs from search in the past period (filled in if the previous period is specified) |
| AddToCartPast | integer | uint64 | Adds-to-Cart from search in the past period (filled in if the previous period is specified) |
| OpenToCartPast | integer | uint64 | Conversion to cart from search in the past period filled in if the previous period is specified) |
| OrdersPast | integer | uint64 | Items ordered from search in the past period (filled in if the previous period is specified) |
| CartToOrderPast | integer | uint64 | Conversion to order from search in the past period (filled in if the previous period is specified) |
| VisibilityPast | integer | uint64 | Visibility in search results in the past period. Probability percentage that a user will see the product card. Depends on the average position (filled in if the previous period is specified) |


**Search parameters report. By WB articles**

| Name | Type | Format | Description |
|-----------------| --- | --- | --- |
| NmID | integer | int64 | WB article |
| VendorCode | string | string | Seller's article |
| Name | string	| string | Product name |
| SubjectName | string	| string | Subject name |
| BrandName | string | string  | Brand |
| IsAdvertised | boolean | bool	| Is the product being promoted in search results |
| IsRated | boolean | bool | Is there an opportunity to rate the product card quality |
| Rating | float | float64 | Product card rating |
| FeedbackRating | float | float64 | Feedbacks rating |
| MinPrice | integer | uint64 | Minimal seller's price with seller's discount (excluding WB Club discount) |
| MaxPrice | integer | uint64 | Maximal seller's price with seller's discount (excluding WB Club discount) |
| AveragePosition | integer | uint64 | Average product position in search results in the current period |
| OpenCard | integer | uint64 | Click-throughs from search in the current period |
| AddToCart | integer | uint64 | Adds-to-Cart from search in the current period |
| OpenToCart | integer | uint64	| Conversion to cart from search in the current period |
| Orders | integer | uint64 | Items ordered from search in the current period |
| CartToOrder | integer | uint64 | Conversion to order from search in the current period |
| Visibility  |integer | uint64 | Visibility in search results in the current period. Probability percentage that a user will see the product card. Depends on the average position |
| AveragePositionPast | integer | uint64 | Average product position in search results in the past period (filled in if the previous period is specified) |
| OpenCardPast | integer | uint64 | Click-throughs from search in the past period (filled in if the previous period is specified) |
| AddToCartPast | integer | uint64 | Adds-to-Cart from search in the past period (filled in if the previous period is specified) |
| OpenToCartPast | integer | uint64 | Conversion to cart from search in the past period (filled in if the previous period is specified) |
| OrdersPast | integer | uint64 | Items ordered from search in the past period (filled in if the previous period is specified) |
| CartToOrderPast | integer | uint64 | Conversion to order from search in the past period (filled in if the previous period is specified) |
| VisibilityPast | integer | uint64 | Visibility in search results in the past period. Probability percentage that a user will see the product card. Depends on the average position (filled in if the previous period is specified) |
| IsSubstitutedSKU | boolean | bool | If the product was searched by the promo item. This will be in the response if the request contains `includeSubstitutedSKUs` and/or `includeSearchTexts` |
| Currency | string | string | Report currency |


**Search texts report**

| Name | Type | Format | Description |
|-----------------| --- | --- | --- |
| Text | string	| string | Search text |
| NmID | integer | int64 | WB article |
| SubjectName | string	| string | Subject name |
| BrandName | string | string  | Brand |
| VendorCode | string | string | Seller's article |
| Name | string	| string | Product name |
| Rating | float | float64 | Product card rating. If there is no rating, the value will be `no rating` |
| FeedbackRating | float | float64 | Feedbacks rating |
| MinPrice | integer | uint64 | Minimal seller's price with seller's discount (excluding WB Club discount) |
| MaxPrice | integer | uint64 | Maximal seller's price with seller's discount (excluding WB Club discount) |
| Frequency | integer | uint64 | Number of the search text requests in the current period |
| MedianPosition | float | float64 | Median position of the product in search in the current period. Only positions from which users added the product to the cart or visited its page are considered. It is the middle value of the position in search results, which excludes significant deviations from the average |
| AveragePosition | integer | uint64 | Average product position in search results in the current period. Only positions from which users added the product to the cart or visited its page are considered |
| OpenCard | integer | uint64 | Click-throughs from search in the current period |
| OpenCardPercentile | float | float64 | The percentage by which click-throughs is higher than that of competitors' pages for the search text |
| AddToCart | integer | uint64 | Adds-to-Cart in search results in the current period |
| AddToCartPercentile | float | float64 | The percentage by which adds-to-Cart is higher than that of competitors' pages for the search text |
| OpenToCart | integer | uint64	| Conversion to cart from search in the current period, % |
| OpenToCartPercentile	| float	| float64	| The percentage by which conversion to cart is higher than that of competitors' pages for the search text |
| Orders | integer | uint64 | Items ordered from search in the current period |
| OrdersPercentile | float | float64 | The percentage by which items ordered is higher than that of competitors' pages for the search text |
| CartToOrder | integer | uint64 | Conversion to order from search in the current period, % |
| CartToOrderPercentile | float | float64 | The percentage by which conversion to order is higher than that of competitors' pages for the search text |
| Visibility  |integer | uint64 | Visibility in search results in the current period. Probability percentage that a user will see the product card. Depends on the average position |
| FrequencyPast | integer | uint64 | Number of the search text requests in the past period (filled in if the previous period is specified) |
| MedianPositionPast | float | float64 | Median position of the product in search in the past period (filled in if the previous period is specified) |
| AveragePositionPast | integer | uint64 | Average product position in search results in the past period (filled in if the previous period is specified) |
| OpenCardPast | integer | uint64 | Click-throughs from search in the past period (filled in if the previous period is specified) |
| AddToCartPast | integer | uint64 | Adds-to-Cart from search in the past period (filled in if the previous period is specified) |
| OpenToCartPast | integer | uint64 | Conversion to cart from search in the past period (filled in if the previous period is specified) |
| OrdersPast | integer | uint64 | Items ordered from search in the past period (filled in if the previous period is specified) |
| CartToOrderPast | integer | uint64 | Conversion to order from search in the past period (filled in if the previous period is specified), % |
| VisibilityPast | integer | uint64 | Visibility in search results in the past period. Probability percentage that a user will see the product card. Depends on the average position (filled in if the previous period is specified) |
| Currency | string | string | Report currency |


**Inventory metrics report**

| Name | Type | Format | Description |
|-----------------| --- | --- | --- |
| VendorCode | string | string | Seller's article |
| Name | string	| string | Product name |
| NmID | integer | int64 | WB article |
| SubjectName | string	| string | Subject name |
| BrandName | string | string  | Brand |
| SizeName | string	| string | Size name |
| ChrtID | integer | int64 | Size ID |
| RegionName | string	| string | Region name. For seller's warehouses, the value in the lines will be `Маркетплейс`, since the data on the seller's warehouses is displayed in an aggregated form — for all of them together without details for a specific warehouses |
| OfficeName | string	| string | Warehouse name. . For seller's warehouses, the value in the lines will be `Маркетплейс`, since the data on the seller's warehouses is displayed in an aggregated form — for all of them together without details for a specific warehouses |
| Availability | string	| enum | Item availability status |
| OrdersCount | integer	| uint64 | Items ordered |
| OrdersSum | integer	| uint64 | Total order value |
| BuyoutCount | integer	| uint64 | Items purchased |
| BuyoutSum | integer	| uint64 | Total purchase value |
| BuyoutPercent | integer	| uint32 | Purchase rate |
| AvgOrders | number	| float64 | Average daily orders |
| StockCount | integer	| uint64 | Current inventory |
| StockSum | integer	| uint64 | Current inventory value |
| SaleRate | integer	| int32 |  Current DSI in hours |
| AvgStockTurnover | integer	| int32 | Average DSI in hours |
| ToClientCount | integer	| uint64 | On the way to user |
| FromClientCount | integer	| uint64 | On the way from user |
| Price | integer	| uint64 | Current seller's price with seller's discount (excluding WB Club discount) |
| OfficeMissingTime | integer	| int32 | Out-of-stock time in hours |
| LostOrdersCount | number	| float64 | Lost orders |
| LostOrdersSum | number	| float64 | Lost order value |
| LostBuyoutsCount | number	| float64 | Lost sales |
| LostBuyoutsSum | number	| float64 | Lost sale value |
| AvgOrdersByMonth_MM.YYYY | number	| float64 | The average number of orders by month. The columns are formed dynamically depending on the current period transmitted in the request. Each month of the current period has one column. If the product did not exist at the time of a particular month, the value will be skipped |
| Currency | string | string | Report currency |


**Inventory history report**

| Name | Type | Format | Description |
|-----------------| --- | --- | --- |
| VendorCode | string | string | Seller's article |
| Name | string	| string | Product name |
| NmID | integer | int64 | WB article |
| SubjectName | string	| string | Subject name |
| BrandName | string | string  | Brand |
| SizeName | string	| string | Size name |
| ChrtID | integer | int64 | Size ID |
| OfficeName | string	| string | Warehouse name. For seller's warehouses, the value in the lines will be `Маркетплейс`, since the data on the seller's warehouses is displayed in an aggregated form — for all of them together without details for a specific warehouses |
| DD.MM.YYYY | integer | uint64 | Inventory as of 23:59 p.m. in the header. The columns are formed dynamically depending on the period transmitted in the request. Each day of the period has one column. If the product was not available on a particular day, the value will be skipped |


[Response 200: SalesFunnelProductRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_SalesFunnelProductRes.json)


[Response 200: SalesFunnelGroupRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_SalesFunnelGroupRes.json)


[Response 200: SearchReportGroupRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_SearchReportGroupRes.json)


[Response 200: SearchReportProductRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_SearchReportProductRes.json)


[Response 200: SearchReportTextRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_SearchReportTextRes.json)


[Response 200: InventoryMetricsReportRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_InventoryMetricsReportRes.json)


[Response 200: InventoryHistoryReportRes](../_shared/examples/GET__api_v2_nm_report_downloads_file__downloadId_200_InventoryHistoryReportRes.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title |
| `detail` | string | ✓ | Error details |
| `requestId` | string | ✓ | Unique request ID |
| `origin` | string | ✓ | WB internal service ID |

[Response 400: errorExample](../_shared/examples/GET__api_v2_nm_report_downloads_400_errorExample.json)

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

- **429** Too Many Requests
