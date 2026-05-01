# `GET` /api/v1/analytics/region-sale

**Tag:** [Sales by Regions](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get Report**

Описание метода

Returns sales data grouped by regions of the countries. You can obtain a report for a maximum of 31 days.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 s | 1 request | 10 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Report period start, `YYYY-MM-DD` *Example: `2025-02-28`* |
| `dateTo` | query | string | ✓ | Report period end, `YYYY-MM-DD` *Example: `2025-03-21`* |

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
