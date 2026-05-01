# `DELETE` /api/v3/orders/{orderId}/meta

**Tag:** [FBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delete Assembly Order Metadata**

Описание метода

Removes all assembly order metadata values for the passed key.

Possible metadata are:
  - `imei` — [IMEI](/openapi/orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1imei/put)
  - `uin` — [UIN](/openapi/orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1uin/put)
  - `gtin` — [GTIN](/openapi/orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1gtin/put)
  - `sgtin` — [labeling code Chestny ZNAK](/openapi/orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1sgtin/put)
  - `customsDeclaration` — [customs declaration number](./orders-fbs#tag/FBS-Metadata/paths/~1api~1marketplace~1v3~1orders~1%7BorderId%7D~1meta~1customs-declaration/put)


Request limit per one seller's account for all methods for getting and deleting FBS metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID *Example: `5632423`* |
| `key` | query | string |  | Name of the metadata to remove (`imei`, `uin`, `gtin`, `sgtin`, `customsDeclaration`) |

## Responses

- **204** Deleted
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_orders_status_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
### `409` Error deleting metadata


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToUpdateMeta](../_shared/examples/DELETE__api_v3_orders__orderId__meta_409_FailedToUpdateMeta.json)

- **429** Too Many Requests
