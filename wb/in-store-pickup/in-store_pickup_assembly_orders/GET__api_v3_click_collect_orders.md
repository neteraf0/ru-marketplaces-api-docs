# `GET` /api/v3/click-collect/orders

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Retrieve Information on Completed Assembly Orders**

Описание метода

The method provides information on completed assembly orders after the sale or cancellation of an order.

You can get data for a specified period, maximum of 30 calendar days per request.


Request limit per one seller's account for In-Store Pickup assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `limit` | query | integer | ✓ | Pagination parameter. Sets the maximum number of returned data.  |
| `next` | query | integer | ✓ | Pagination parameter. Sets the value from which the next batch of data should be retrieved. To obtain the complete list of data, it should be set to 0 in the first request. For subsequent requests, the values should be taken from the field with the same name in the response.  |
| `dateFrom` | query | integer | ✓ | Period start date in the Unix timestamp format |
| `dateTo` | query | integer | ✓ | Period end date in the Unix timestamp format |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `next` | integer |  | Pagination parameter. Contains the value which should be specified in the request to retrieve the next batch of data  *Example: `12345566`* |
| `orders` | array |  | Assembly orders list |

[Response 200](../_shared/examples/GET__api_v3_click_collect_orders_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectParameter](../_shared/examples/PATCH__api_v3_click_collect_orders__orderId__confirm_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
