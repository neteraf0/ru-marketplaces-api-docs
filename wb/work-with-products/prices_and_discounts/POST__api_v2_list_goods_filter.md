# `POST` /api/v2/list/goods/filter

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Get Products with Prices by Articles**

Описание метода

Returns product data by its article.

You can specify more than one article in one request.

Use separate methods to get data:
  - for [all products without specifying articles](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1list~1goods~1filter/get)
  - for [the size of the product](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1list~1goods~1size~1nm/get).


Request limit per one seller's account for all methods in the Prices and Discounts category:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 6 s | 10 requests | 600 ms | 5 requests |


## Request Body

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
