# `GET` /api/marketplace/v3/fbs/orders/archive

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get the List of Archived Assembly Orders**

Описание метода

The method returns assembly orders created more than 3 months ago.
Some assembly orders are archived later than 3 months after creation, as the supply is archived only after all orders in it are completed.
For example, this happens if the seller did not deliver one of the orders in the supply and the order was canceled automatically after a few days.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `year` | query | integer | ✓ | Year the order was created *Example: `2023`* |
| `month` | query | integer | ✓ | Month the order was created *Example: `2`* |
| `next` | query | integer | ✓ | Pagination parameter. Sets the value from which to retrieve the next batch. It should start at 0 to get the full list of data. For the subsequent requests, you must take the value from the `next` field in the response. |
| `limit` | query | integer | ✓ | Number of assembly orders in the response *Example: `150`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `next` | integer | ✓ | Pagination parameter. Sets the value from which to get the next batch |
| `orders` | array | ✓ | Archived assembly orders |

[Response 200](../_shared/examples/GET__api_marketplace_v3_fbs_orders_archive_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `detail` | string | ✓ | Error details |
| `errors` | array |  |  |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `status` | integer |  | HTTP status code |
| `title` | string | ✓ | Error title |

[Response 400: BadRequest](../_shared/examples/GET__api_marketplace_v3_fbs_orders_archive_400_BadRequest.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `detail` | string | ✓ | Error details |
| `errors` | array |  |  |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `status` | integer |  | HTTP status code |
| `title` | string | ✓ | Error title |

[Response 403: AccessDenied](../_shared/examples/GET__api_marketplace_v3_fbs_orders_archive_403_AccessDenied.json)

- **429** Too Many Requests
