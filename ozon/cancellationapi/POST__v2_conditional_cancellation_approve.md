# `POST` /v2/conditional-cancellation/approve

**Tag:** [CancellationAPI](index.md)

**operationId:** `CancellationAPI_ConditionalCancellationApproveV2`

**Подтвердить заявку на отмену rFBS**

Метод позволяет согласовать заявку на отмену в статусе `ON_APPROVAL`. Заказ будет отменён, а деньги вернутся покупателю.

## Request Body

## Responses

- **200** Заявка подтверждена
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
