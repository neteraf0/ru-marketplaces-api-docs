# `GET` /api/v1/calendar/promotions/details

**Tag:** [Promotions Calendar](index.md)

**Server:** `https://dp-calendar-api.wildberries.ru`

**Promotions Details**

Описание метода

Returns detailed information about the selected promotions


Request limit per one seller's account for all methods in the Promotions Calendar category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 6 s | 10 requests | 600 ms | 5 requests |
| Service | 6 s | 10 requests | 600 ms | 5 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `promotionIDs` | query | array | ✓ | IDs of the promotions for which information should be returned *Example: `[1, 3, 64]`* |

## Responses

- **200** OK
- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
