# `POST` /api/marketplace/v3/orders/meta

**Tag:** [FBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Assembly Orders Metadata**

Описание метода

The method returns metadata for [assembly orders](./orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders/get) by the list of their IDs.

You can get the list of metadata available for an assembly order in the `requiredMeta` and `optionalMeta` fields in the response of the [Get New Assembly Orders](./orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders~1new/get) method.

Possible metadata:
  - `imei` — [IMEI](./orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1imei/put)
  - `uin` — [UIN](./orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1uin/put)
  - `gtin` — [GTIN](./orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1gtin/put)
  - `sgtin` — [labeling code Chestny ZNAK](./orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1sgtin/put)
  - `expiration` — [Expiration date](./orders-fbs#tag/FBS-Metadata/paths/~1api~1v3~1orders~1%7BorderId%7D~1meta~1expiration/put)
  - `customsDeclaration` — [customs declaration number](./orders-fbs#tag/FBS-Metadata/paths/~1api~1marketplace~1v3~1orders~1%7BorderId%7D~1meta~1customs-declaration/put)

  If any of the metadata objects are not returned in the response, it means that the assembly order cannot have such metadata, and they cannot be added


Request limit per one seller's account for all methods for getting and deleting FBS metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ |  *Example: `[123456, 234567, 345678]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |

[Response 200](../_shared/examples/POST__api_marketplace_v3_orders_meta_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400](../_shared/examples/POST__api_marketplace_v3_orders_meta_400.json)

- **401** Unauthorized
### `403` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 403](../_shared/examples/POST__api_marketplace_v3_orders_meta_403.json)

### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 404](../_shared/examples/POST__api_marketplace_v3_orders_meta_404.json)

- **429** Too Many Requests
