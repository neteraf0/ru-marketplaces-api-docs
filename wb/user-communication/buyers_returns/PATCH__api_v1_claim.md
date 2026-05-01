# `PATCH` /api/v1/claim

**Tag:** [Buyers Returns](index.md)

**Server:** `https://returns-api.wildberries.ru`

**Answer Buyers Application**

Описание метода

Sends an answer to the buyers application for product return.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 20 requests | 3 s | 10 requests |
| Service | 1 min | 20 requests | 3 s | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

## Responses

- **200** Success
- **400** Bad Request
- **401** Unauthorized
- **429** Too Many Requests
