# `GET` /v1/actions

**Tag:** [Promos](index.md)

**operationId:** `Promos`

**Список акций**

Метод для получения списка акций Ozon, в которых можно участвовать.

[Подробнее об акциях Ozon](https://seller-edu.ozon.ru/ceny-i-akcii/akcii-skidki-i-kupony/promo)

## Responses

### `200` Список акций


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Результаты запроса. |

[Response 200](../_shared/examples/GET__v1_actions_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
