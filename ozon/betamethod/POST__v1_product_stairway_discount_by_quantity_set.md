# `POST` /v1/product/stairway-discount/by-quantity/set

**Tag:** [BetaMethod](index.md)

**operationId:** `ProductAPI_SetProductStairwayDiscountByQuantity`

**Управлять скидкой от количества**

Устанавливает или удаляет скидку на товар в зависимости от его количества в заказе.

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1719-Novye-metody-dlia-raboty-so-skidkoi-ot-kolichestva/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stairways` | array | ✓ | Информация о скидке от количества по товарам. |
| `suppress_warnings` | boolean |  | Передайте `true`, чтобы игнорировать предупреждения и установить скидку.  |
## Responses

### `200` Настройки скидки изменены


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `accepted` | boolean |  | `true`, если запрос принят. Используйте метод [/v1/product/stairway-discount/by-quantity/get](#operation/ProductAPI_GetProductStairwayDiscountByQuantity), чтобы узнать результат изменения скидки.  |
| `errors` | array |  | Описание ошибок. |
| `warnings` | array |  | Описание предупреждения. |

[Response 200](../_shared/examples/POST__v1_product_stairway_discount_by_quantity_set_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
