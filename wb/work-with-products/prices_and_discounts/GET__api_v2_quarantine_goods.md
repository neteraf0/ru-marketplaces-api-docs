# `GET` /api/v2/quarantine/goods

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Get Products in Quarantine**

Описание метода

Returns information about products in quarantine.

If the product new price with discount will be minimum 3 times less than the old price, the product will be placed in [quarantine](https://seller.wildberries.ru/discount-and-prices/quarantine) and will be sold at the old price. An error about this will be in the [upload states](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1history~1tasks/get) method response.

You can change price or discount via API or release product from quarantine in [personal account](https://seller.wildberries.ru/discount-and-prices/quarantine).

For products with [size-based pricing](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1upload~1task~1size/post), quarantine does not apply.


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

### `422` Unexpected result


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 422: UnexpectedResult](../_shared/examples/POST__api_v2_upload_task_422_UnexpectedResult.json)

- **429** Too Many Requests
