# `GET` /api/v3/dbw/orders

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Information on Completed Orders**

Описание метода

Returns information on completed orders (either canceled or sold).

You can get data for a specified period, maximum of 30 calendar days per request.


Request limit per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `limit` | query | integer | ✓ | Pagination parameter. Sets the limit for the amount of data returned |
| `next` | query | integer | ✓ | Pagination parameter. Sets the value from which to retrieve the next batch. It should start at `0` to get the full list of data. For the subsequent requests, you must take the value from the `next` field in the response |
| `dateFrom` | query | integer | ✓ | Period start date in Unix timestamp format  |
| `dateTo` | query | integer | ✓ | Period end date in Unix timestamp format |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `next` | Next |  | Pagination parameter. Sets the value from which to retrieve the next batch |
| `orders` | array |  |  |

[Response 200](../_shared/examples/GET__api_v3_dbw_orders_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
