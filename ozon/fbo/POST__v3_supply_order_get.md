# `POST` /v3/supply-order/get

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderGet`

**Информация о заявке на поставку**

Учитываются заявки с поставкой на конкретный склад и через [виртуальный распределительный центр (вРЦ)](https://seller-edu.ozon.ru/fbo/scheme-of-work/about#чем-отличаются-процессы-при-заявках-через-врц-и-напрямую-на-склад).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_ids` | array | ✓ | Идентификаторы заявок на поставку. |

[Request example](examples/POST__v3_supply_order_get_req.json)

## Responses

### `200` Информация о заявке


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Список заявок на поставку. |

[Response 200](../_shared/examples/POST__v3_supply_order_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
