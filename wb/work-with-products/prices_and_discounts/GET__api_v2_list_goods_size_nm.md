# `GET` /api/v2/list/goods/size/nm

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Get Product Sizes with Prices**

Описание метода

Returns sizes data for the product. Only for products from categories where size price setting is available. For these products `"editableSizePrice":true`.


Request limit per one seller's account for all methods in the Prices and Discounts category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 6 s | 10 requests | 600 ms | 5 requests |
| Service | 6 s | 10 requests | 600 ms | 5 requests |
| Base | 1 h | 4 requests | 15 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `limit` | query | integer | ✓ | Number of elements per page (pagination) *Example: `10`* |
| `offset` | query | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element |
| `nmID` | query | integer | ✓ | WB article *Example: `1`* |

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
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 403: AccessDenied](../_shared/examples/POST__api_v2_upload_task_403_AccessDenied.json)

- **429** Too Many Requests
