# `GET` /api/v1/paid_storage

**Tag:** [Paid Storage](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Generate the Report**

Описание метода

Create a task to generate a report. Maximum of report period — 8 days


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Start of the report period, RFC3339 format. Date or date and time, for example:    * `2019-06-20`   * `2019-06-20T23:59:59`   * `2019-06-20T00:00:00.12345`   * `2017-03-25T00:00:00`  *Example: `2022-01-01`* |
| `dateTo` | query | string | ✓ | End of the report period, RFC3339 format. Date or date and time, for example:    * `2019-06-20`   * `2019-06-20T23:59:59`   * `2019-06-20T00:00:00.12345`   * `2017-03-25T00:00:00`  *Example: `2022-01-09`* |

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


[Response 400: DateRangeExceeded](../_shared/examples/GET__api_v1_paid_storage_400_DateRangeExceeded.json)


[Response 400: DateRanges](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_DateRanges.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
