# `PUT` /api/v3/orders/{orderId}/meta/expiration

**Tag:** [FBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Add Expiration Date to the Assembly Order**

Описание метода

Sets the expiration date for the assembly order.

The expiration date can only be added for assembly orders that are delivered by WB and are in the `confirm` status.


You can get the uploaded data in the [metadata of the assembly order](./orders-fbs#tag/FBS-Metadata/paths/~1api~1marketplace~1v3~1orders~1meta/post).

To change the expiration date, send a request with the new date.
It is impossible to remove the expiration date from the metadata of the assembly order.


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
| `expiration` | string |  | The date until which the product is valid. No less than 30 days from the current date. *Example: `12.09.2030`* |
## Responses

- **204** Sent
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: LowExpirationDate](../_shared/examples/PUT__api_v3_orders__orderId__meta_expiration_400_LowExpirationDate.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_orders_status_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
### `409` Error updating metadata


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToUpdateMeta](../_shared/examples/DELETE__api_v3_orders__orderId__meta_409_FailedToUpdateMeta.json)

- **429** Too Many Requests
