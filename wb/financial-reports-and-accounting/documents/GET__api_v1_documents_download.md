# `GET` /api/v1/documents/download

**Tag:** [Documents](index.md)

**Server:** `https://documents-api.wildberries.ru`

**Get Document**

Описание метода

Returns one document


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 s | 1 request | 10 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `serviceName` | query | string | ✓ | Unique document ID *Example: `redeem-notification-44841941`* |
| `extension` | query | string | ✓ | Document format *Example: `zip`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |

[Response 200](../_shared/examples/GET__api_v1_documents_download_200.json)

- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
