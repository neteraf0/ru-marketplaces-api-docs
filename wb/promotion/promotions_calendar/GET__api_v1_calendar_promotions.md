# `GET` /api/v1/calendar/promotions

**Tag:** [Promotions Calendar](index.md)

**Server:** `https://dp-calendar-api.wildberries.ru`

**Promotions List**

Описание метода

Returns a promotions list with dates and times of occurrence


Request limit per one seller's account for all methods in the Promotions Calendar category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 6 s | 10 requests | 600 ms | 5 requests |
| Service | 6 s | 10 requests | 600 ms | 5 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `startDateTime` | query | string | ✓ | Period start, format `YYYY-MM-DDTHH:MM:SSZ` *Example: `2023-09-01T00:00:00Z`* |
| `endDateTime` | query | string | ✓ | Period end, format `YYYY-MM-DDTHH:MM:SSZ` *Example: `2024-08-01T23:59:59Z`* |
| `allPromo` | query | boolean | ✓ | Show promotions:   - `false` — available for participating   - `true` — all promotion  |
| `limit` | query | integer |  | Number of requested promotions *Example: `10`* |
| `offset` | query | integer |  | From which element to start outputting data |

## Responses

- **200** OK
- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
