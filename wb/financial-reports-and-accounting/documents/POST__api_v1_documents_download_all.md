# `POST` /api/v1/documents/download/all

**Tag:** [Documents](index.md)

**Server:** `https://documents-api.wildberries.ru`

**Get Documents**

Описание метода

Returns more than one document.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 5 min | 1 request | 5 min | 5 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `params` | array |  |  |

[Request example](examples/POST__api_v1_documents_download_all_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |

[Response 200](../_shared/examples/POST__api_v1_documents_download_all_200.json)

- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
