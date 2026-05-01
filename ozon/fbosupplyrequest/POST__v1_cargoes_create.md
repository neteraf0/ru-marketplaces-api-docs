# `POST` /v1/cargoes/create

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesCreate`

**Установка грузомест**

Используйте метод, чтобы передать грузоместа и товарный состав в заявку на поставку.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cargoes` | array | ✓ | Информация о грузоместах. Вы можете передать не больше 40 палет или 30 коробок. |
| `delete_current_version` | boolean |  | `true`, если нужно удалить предыдущие грузоместа.  |
| `supply_id` | integer | ✓ | Идентификатор поставки. Можно получить с помощью метода [/v3/supply-order/get](#operation/SupplyOrderGet). Нужное значение — в параметре ответа `orders.supplies.supply_id`. |

[Request example](examples/POST__v1_cargoes_create_req.json)

## Responses

### `200` Грузоместа установлены


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор операции. |
| `errors` | v1CargoesCreateErrors |  | Ошибки. |

[Response 200](../_shared/examples/POST__v1_cargoes_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
