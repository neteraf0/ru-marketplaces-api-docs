# `PUT` /api/marketplace/v3/orders/{orderId}/meta/customs-declaration

**Tag:** [FBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Add Custom Declaration number to the Order**

Описание метода

The method updates the customs declaration number in the [metadata of the assembly order](/openapi/orders-fbs#tag/FBS-Metadata/paths/~1api~1marketplace~1v3~1orders~1meta/post).

An assembly order can have only one customs declaration number.

You can add the customs declaration number only for orders in the `confirm` or `complete` [status](./orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders~1status/post).


Request limit per one seller's account for all methods for adding FBS metadata:

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
| `customsDeclaration` | string |  | Customs declaration number *Example: `10704010/010624/0000302`* |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_orders_status_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **403** Forbidden
- **404** Not Found
### `409` Error updating custom declaration number


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToUpdateMeta](../_shared/examples/DELETE__api_v3_orders__orderId__meta_409_FailedToUpdateMeta.json)

- **429** Too Many Requests
