# `PUT` /api/v3/dbw/orders/{orderId}/meta/imei

**Tag:** [DBW Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Add IMEI to the Order**

Описание метода

Sets the IMEI for the order. The order can have only one IMEI. You can add the code only for orders in the `confirmed` status.


Request limit per one seller's account for all methods for adding DBW metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1000 requests | 60 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID *Example: `5632423`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `imei` | string | ✓ | IMEI *Example: `123456789012345`* |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
### `409` Metadata update error


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToUpdateMeta](../_shared/examples/DELETE__api_v3_dbw_orders__orderId__meta_409_FailedToUpdateMeta.json)

- **429** Too Many Requests
