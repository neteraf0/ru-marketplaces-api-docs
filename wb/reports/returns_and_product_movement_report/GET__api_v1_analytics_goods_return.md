# `GET` /api/v1/analytics/goods-return

**Tag:** [Returns and Product Movement Report](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get Report**

Описание метода

Returns a list of [goods returns to the seller](https://seller.wildberries.ru/analytics-reports/goods-return). With one request, you can obtain a report for a maximum of 31 days.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 10 requests |
| Service | 1 min | 1 request | 1 min | 10 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Beginning date of the reporting period *Example: `2024-08-13`* |
| `dateTo` | query | string | ✓ | End date of the reporting period *Example: `2024-08-27`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `report` | array |  | Report |

[Response 200](../_shared/examples/GET__api_v1_analytics_goods_return_200.json)

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
