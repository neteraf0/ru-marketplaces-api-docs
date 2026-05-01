# `GET` /api/v1/analytics/brand-share/brands

**Tag:** [Share of Brand in Sales](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Seller Brands**

Описание метода

Returns the list of the seller brands.

You can only get brands that:
- were sold in the last 90 days
- are in WB


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 10 requests |


## Responses

- **200** OK
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
