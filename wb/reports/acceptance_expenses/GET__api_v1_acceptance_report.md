# `GET` /api/v1/acceptance_report

**Tag:** [Acceptance Expenses](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Create the Report**

Описание метода

Creates a task for report generation.
Maximum of report period is 31 days.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Report period start, `YYYY-MM-DD` *Example: `2025-02-28`* |
| `dateTo` | query | string | ✓ | Report period end, `YYYY-MM-DD` *Example: `2025-03-21`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | CreateTaskResponseData |  |  |

[Response 200: CreateResponseData](../_shared/examples/GET__api_v1_warehouse_remains_200_CreateResponseData.json)

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
