# `GET` /api/v3/supplies

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get a Supplies List**

Описание метода

Returns the supply list.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `limit` | query | integer | ✓ | Pagination parameter. Sets the limit for the amount of data returned. |
| `next` | query | integer | ✓ | Pagination parameter. Sets the value from which to retrieve the next batch. It should start at 0 to get the full list of data. For the subsequent requests, you must take the value from the `next` field in the response. |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `next` | Next |  | Pagination parameter. Sets the value from which to get the next batch |
| `supplies` | array |  | Supplies list |

[Response 200](../_shared/examples/GET__api_v3_supplies_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
