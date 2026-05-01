# `GET` /api/v1/analytics/goods-labeling

**Tag:** [Retention Reports](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Product Labeling**

Описание метода

Returns a report on deductions for the absence of mandatory product labeling.
The report contains photos of products where the labeling is absent or cannot be read.
Data can be obtained for up to 31 days, starting from March 2024


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 10 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Report period start, `YYYY-MM-DD`  *Example: `2024-04-01`* |
| `dateTo` | query | string | ✓ | Report period end, `YYYY-MM-DD`  *Example: `2024-04-30`* |

## Responses

- **200** OK
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400: MissingDateTimeFrom](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_MissingDateTimeFrom.json)


[Response 400: MissingDateTimeTo](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_MissingDateTimeTo.json)


[Response 400: IncorrectDateTimeFrom](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_IncorrectDateTimeFrom.json)


[Response 400: IncorrectDateTimeTo](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_IncorrectDateTimeTo.json)


[Response 400: DateRangeExceeded](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_DateRangeExceeded.json)


[Response 400: DateRanges](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_DateRanges.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
