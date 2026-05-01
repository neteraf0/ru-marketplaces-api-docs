# `GET` /api/v1/claims

**Tag:** [Buyers Returns](index.md)

**Server:** `https://returns-api.wildberries.ru`

**Buyers Return Applications**

Описание метода

Returns buyers applications for product returns for the current 14 days.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 20 requests | 3 s | 10 requests |
| Service | 1 min | 20 requests | 3 s | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `is_archive` | query | boolean | ✓ | Application status:   * `false` — under review   * `true` — in archive  *Example: `True`* |
| `id` | query | string |  | Application ID *Example: `fe3e9337-e9f9-423c-8930-946a8ebef80`* |
| `limit` | query | integer |  | Number of applications in the response *Example: `50`* |
| `offset` | query | integer |  | From which element to start outputting data. `0` by default |
| `nm_id` | query | integer |  | WB article *Example: `196320101`* |

## Responses

- **200** OK
- **400** Bad Request
- **401** Unauthorized
- **429** Too Many Requests
