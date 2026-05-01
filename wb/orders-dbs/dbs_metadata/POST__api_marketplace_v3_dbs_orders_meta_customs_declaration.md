# `POST` /api/marketplace/v3/dbs/orders/meta/customs-declaration

**Tag:** [DBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Add Custom Declaration to the Orders**

Описание метода

Sets the cargo customs declaration number in the metadata of the assembly orders.

One assembly order can have only one cargo customs declaration number.

The customs declaration number can only be added to assembly orders that are in `deliver` status.


Request limit per one seller's account for all methods for adding DBS metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 500 requests | 120 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbs_groups_info_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbs_orders_client_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbs_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **403** Forbidden
- **404** Not Found
### `409` Metadata update error


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToUpdateMeta](../_shared/examples/POST__api_marketplace_v3_dbs_orders_meta_customs_declaration_409_FailedToUpdateM.json)

- **429** Too Many Requests
