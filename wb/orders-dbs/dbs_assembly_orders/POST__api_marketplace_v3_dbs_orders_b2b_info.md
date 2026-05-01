# `POST` /api/marketplace/v3/dbs/orders/b2b/info

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**B2B Buyer Information**

Описание метода

The method returns B2B buyers data by assembly orders ID:
  - Taxpayer Identification Number (TIN or INN in Russian)
  - Code of Reason for Registration (CRR or KPP in Russian)
  - Company name


Request limit per one seller's account for DBS assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `ordersIds` | array |  | List of assembly order IDs *Example: `[123456, 234567]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `requestId` | string | ✓ | Unique request ID |
| `results` | array |  |  |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbs_orders_b2b_info_200.json)

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
