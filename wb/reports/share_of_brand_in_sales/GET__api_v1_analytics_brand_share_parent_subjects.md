# `GET` /api/v1/analytics/brand-share/parent-subjects

**Tag:** [Share of Brand in Sales](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Parent Categories of the Brand**

Описание метода

Returns parent categories of the brand.

Data can be obtained starting from 1 November 2022, for up to 365 days.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 5 s | 1 request | 5 s | 20 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | Language of the response field `parentName`:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  *Example: `ru`* |
| `brand` | query | string | ✓ | Brand *Example: `H%26M`* |
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

[Response 400: IncorrectDateFrom](../_shared/examples/GET__api_v1_analytics_brand_share_parent_subjects_400_IncorrectDateFrom.json)


[Response 400: MissingDateTimeFrom](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_MissingDateTimeFrom.json)


[Response 400: MissingDateTimeTo](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_MissingDateTimeTo.json)


[Response 400: IncorrectDateTimeFrom](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_IncorrectDateTimeFrom.json)


[Response 400: IncorrectDateTimeTo](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_IncorrectDateTimeTo.json)


[Response 400: DateRangeExceeded](../_shared/examples/GET__api_v1_analytics_brand_share_parent_subjects_400_DateRangeExceeded.json)


[Response 400: DateRanges](../_shared/examples/GET__api_v1_analytics_goods_labeling_400_DateRanges.json)


[Response 400: LocaleError](../_shared/examples/GET__api_v1_analytics_brand_share_parent_subjects_400_LocaleError.json)


[Response 400: MissingBrand](../_shared/examples/GET__api_v1_analytics_brand_share_parent_subjects_400_MissingBrand.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
