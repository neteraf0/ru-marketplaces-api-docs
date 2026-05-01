# `POST` /api/v1/analytics/excise-report

**Tag:** [Report on Products with Mandatory Labeling](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Report on Products with Mandatory Labeling**

Описание метода

Returns operations with labeled products


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 5 h | 10 requests | 30 min | 10 requests |
| Service | 5 h | 10 requests | 30 min | 10 requests |
| Base | 24 h | 2 requests | 12 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Report period start, `YYYY-MM-DD` *Example: `2025-02-28`* |
| `dateTo` | query | string | ✓ | Report period end, `YYYY-MM-DD` *Example: `2025-03-21`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `countries` | array |  | Country code in according with ISO 3166-2. Set the empty parameter to get data without filters by country |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `response` | models.ExciseReportResponse |  |  |

[Response 200](../_shared/examples/POST__api_v1_analytics_excise_report_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/POST__api_v1_analytics_excise_report_400.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
