# `GET` /api/v1/analytics/banned-products/blocked

**Tag:** [Hidden Products](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Blocked Product Cards**

Описание метода

Returns the list of [blocked product cards](https://seller.wildberries.ru/analytics-reports/banned-products)


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 s | 1 request | 10 s | 6 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `sort` | query | string (enum: brand, nmId, title, vendorCode, reason) | ✓ | Sorting - `brand` — by brand - `nmId` — by WB article - `title` — by product title - `vendorCode` — by seller's article - `reason` — by reason for blocking  *Example: `nmId`* |
| `order` | query | string (enum: desc, asc) | ✓ | Data order - `desc` — from the largest numeric value to the smallest, from the last alphabetical value to the first - `asc` — from the smallest numeric value to the largest, from the first alphabetical value to the last  *Example: `asc`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `report` | array |  | Report |

[Response 200](../_shared/examples/GET__api_v1_analytics_banned_products_blocked_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title |
| `status` | number |  | HTTP status code |
| `detail` | string |  | Error details |
| `requestId` | string |  | Unique request ID |
| `origin` | string |  | WB internal service ID |

[Response 400](../_shared/examples/GET__api_v1_analytics_banned_products_blocked_400.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
