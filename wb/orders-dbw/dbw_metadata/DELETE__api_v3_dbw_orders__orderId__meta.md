# `DELETE` /api/v3/dbw/orders/{orderId}/meta

**Tag:** [DBW Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delete Order Metadata**

Описание метода

Removes all order metadata values for the passed key. Possible metadata is `imei`, `uin`, `gtin`, `sgtin`.


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID *Example: `5632423`* |
| `key` | query | string |  | Name of metadata to delete (`imei`, `uin`, `gtin`, `sgtin`). Only one value is passed |

## Responses

- **204** Удалено
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
### `409` Ошибка удаления метаданных


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToUpdateMeta](../_shared/examples/DELETE__api_v3_dbw_orders__orderId__meta_409_FailedToUpdateMeta.json)

- **429** Too Many Requests
