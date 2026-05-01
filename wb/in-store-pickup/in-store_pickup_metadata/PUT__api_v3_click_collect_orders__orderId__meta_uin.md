# `PUT` /api/v3/click-collect/orders/{orderId}/meta/uin

**Tag:** [In-Store Pickup Metadata](index.md)

**Add UIN (Unique Identification Number) to the Assembly Order**

Описание метода

This method is deprecated. It will be removed on [May 19](https://dev.wildberries.ru/en/release-notes?id=474)


Request limit per one seller's account for all methods for adding In-Store Pickup metadata:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1000 requests | 60 ms | 20 requests |
| Service | 1 min | 1000 requests | 60 ms | 20 requests |
| Base | 1 h | 10 requests | 6 min | 1 request |

One request with a response code of 409 is counted as 10 requests


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `uin` | string |  | UIN |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_click_collect_orders_client_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/PUT__api_v3_click_collect_orders__orderId__meta_sgtin_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/PATCH__api_v3_click_collect_orders__orderId__confirm_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
### `409` Error adding label


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  |  |
| `data` | object |  |  |
| `message` | string |  |  |

[Response 409: FailedToUpdateMeta](../_shared/examples/PUT__api_v3_click_collect_orders__orderId__meta_sgtin_409_FailedToUpdateMeta.json)

- **429** Too Many Requests
