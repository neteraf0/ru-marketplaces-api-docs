# `GET` /api/v1/documents/categories

**Tag:** [Documents](index.md)

**Server:** `https://documents-api.wildberries.ru`

**Documents Categories**

Описание метода

Returns documents categories


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 s | 1 request | 10 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | `title` field language:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  *Example: `ru`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |

[Response 200](../_shared/examples/GET__api_v1_documents_categories_200.json)

- **401** Unauthorized
- **429** Too Many Requests
