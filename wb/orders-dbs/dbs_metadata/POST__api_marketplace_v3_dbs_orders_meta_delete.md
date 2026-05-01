# `POST` /api/marketplace/v3/dbs/orders/meta/delete

**Tag:** [DBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delete Assembly Orders Metadata**

Описание метода

Removes all [assembly order metadata](./orders-dbs#tag/DBS-Metadata/paths/~1api~1marketplace~1v3~1dbs~1orders~1meta~1info/post) values.

You can only delete one type of metadata in one request.
Specify the metadata type in the request:
- `imei` — [IMEI](./orders-dbs#tag/DBS-Metadata/paths/~1api~1marketplace~1v3~1dbs~1orders~1meta~1imei/post)
- `uin` — [UIN](./orders-dbs#tag/DBS-Metadata/paths/~1api~1marketplace~1v3~1dbs~1orders~1meta~1uin/post)
- `gtin` — [GTIN](./orders-dbs#tag/DBS-Metadata/paths/~1api~1marketplace~1v3~1dbs~1orders~1meta~1gtin/post)
- `sgtin` — [labeling code Chestny ZNAK](./orders-dbs#tag/DBS-Metadata/paths/~1api~1marketplace~1v3~1dbs~1orders~1meta~1sgtin/post)
- `customsDeclaration` — [customs declaration number](./orders-dbs#tag/DBS-Metadata/paths/~1api~1marketplace~1v3~1dbs~1meta~1customs-declaration/post)


Request limit per one seller's account for all methods for getting and deleting DBS metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 150 requests | 400 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `key` | string | ✓ | Name of metadata to delete (**imei**, **uin**, **gtin**, **sgtin**). Only one value is passed *Example: `imei`* |
| `orderIds` | array | ✓ | Assembly orders IDs list *Example: `[123456, 234567]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `results` | array |  |  |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbs_orders_status_cancel_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 400](../_shared/examples/POST__api_marketplace_v3_dbs_orders_b2b_info_400.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 403](../_shared/examples/POST__api_marketplace_v3_dbs_orders_b2b_info_403.json)

### `409` Metadata deletion error


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `FailedToUpdateMeta`* |

[Response 409](../_shared/examples/POST__api_marketplace_v3_dbs_orders_meta_delete_409.json)

- **429** Too Many Requests
