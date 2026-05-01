# `GET` /api/v1/calendar/promotions/nomenclatures

**Tag:** [Promotions Calendar](index.md)

**Server:** `https://dp-calendar-api.wildberries.ru`

**List of Products for Participating in the Promotion**

Описание метода

Returns a list of products suitable for participation in the promotion.

Not applicable for auto promotions


Request limit per one seller's account for all methods in the Promotions Calendar category:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 6 s | 10 requests | 600 ms | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `promotionID` | query | integer | ✓ | Promotion ID *Example: `1`* |
| `inAction` | query | boolean | ✓ | Participates in the promotion:   - `true` — yes   - `false` — no  *Example: `True`* |
| `limit` | query | integer |  | Number of requested products *Example: `10`* |
| `offset` | query | integer |  | From which element to start outputting data |

## Responses

- **200** OK
- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **422** Unprocessable Entity
- **429** Too Many Requests
