# `GET` /api/v2/buffer/tasks

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Unprocessed Upload State**

Описание метода

Returns the processing upload data.


Request limit per one seller's account for all methods in the Prices and Discounts category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 6 s | 10 requests | 600 ms | 5 requests |
| Service | 6 s | 10 requests | 600 ms | 5 requests |
| Base | 1 h | 4 requests | 15 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `uploadID` | query | integer | ✓ | Download ID *Example: `146567`* |

## Responses

- **200** OK
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 400: InvalidRequestParameters](../_shared/examples/GET__api_v2_history_tasks_400_InvalidRequestParameters.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 403: AccessDenied](../_shared/examples/POST__api_v2_upload_task_403_AccessDenied.json)

- **429** Too Many Requests
