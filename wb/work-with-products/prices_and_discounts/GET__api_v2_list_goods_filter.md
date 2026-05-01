# `GET` /api/v2/list/goods/filter

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Get Products with Prices**

Описание метода

Returns product data.

You can specify only one article in one request.

To get data for all products, do not set the article, set `limit=1000`, and use the `offset` field to set the data offset. The offset should be calculated using the formula: `offset` plus `limit` from the previous request. Repeat the request until you receive a response with an empty array.
Use separate methods to get data:
  - for [more than one product by article](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1list~1goods~1filter/post)
  - for [the size of the product](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1list~1goods~1size~1nm/get)


Request limit per one seller's account for all methods in the Prices and Discounts category:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 6 s | 10 requests | 600 ms | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `limit` | query | integer | ✓ | Number of elements per page (pagination) *Example: `10`* |
| `offset` | query | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element |
| `filterNmID` | query | integer |  | WB article for search *Example: `44589768676`* |

## Responses

- **200** OK
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 400: SortError](../_shared/examples/GET__api_v2_list_goods_filter_400_SortError.json)


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
