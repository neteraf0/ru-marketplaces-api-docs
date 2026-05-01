# `POST` /api/marketplace/v3/dbs/orders/meta/info

**Tag:** [DBS Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Assembly Orders Metadata**

Описание метода

This method is deprecated. It will be removed on [July 27](https://dev.wildberries.ru/en/release-notes?id=508)


Request limit per one seller's account for all methods for getting and deleting DBS metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 150 requests | 400 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


> ⚠️ **Deprecated**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `ordersIds` | array |  | List of assembly order IDs *Example: `[123456, 234567]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `meta` | array |  | Assembly orders metadata |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbs_orders_meta_info_200.json)

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

- **429** Too Many Requests
