# `POST` /api/v1/calendar/promotions/upload

**Tag:** [Promotions Calendar](index.md)

**Server:** `https://dp-calendar-api.wildberries.ru`

**Add Product to the Promotion**

Описание метода

Creates a product upload for the promotion.The upload status can be checked using [separate methods](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1history~1tasks/get).

Not applicable for auto promotions


Request limit per one seller's account for all methods in the Promotions Calendar category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 6 s | 10 requests | 600 ms | 5 requests |
| Service | 6 s | 10 requests | 600 ms | 5 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

## Responses

- **200** OK
- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **422** Unprocessable Entity
- **429** Too Many Requests
