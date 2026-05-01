# `GET` /api/v1/analytics/antifraud-details

**Tag:** [Retention Reports](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Self-purchases**

Описание метода

Returns report with self-purchase deductions. The report is generated on Wednesdays at 7:00 UTC+4 and contains weekly data. Also you can get all data starting from August 2023.

Self-purchase deduction is 30% of product price. Minimum deduction is 100,000 ₽, if the total product cost delivered to the pick-up point is more than 100,000 ₽ per one week.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 min | 1 request | 10 min | 10 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `date` | query | string |  | Date from report period, `YYYY-MM-DD`, for example `2023-12-01`. To get all data from August 2023 do not use this parameter  *Example: `2023-12-01`* |

## Responses

- **200** OK
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400: IncorrectDate](../_shared/examples/GET__api_v1_analytics_antifraud_details_400_IncorrectDate.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
