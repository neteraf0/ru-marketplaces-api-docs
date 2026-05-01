# `POST` /v2/conditional-cancellation/reject

**Tag:** [CancellationAPI](index.md)

**operationId:** `CancellationAPI_ConditionalCancellationRejectV2`

**Отклонить заявку на отмену rFBS**

Метод позволяет отклонить заявку на отмену в статусе `ON_APPROVAL`. В параметре `comment` опишите причину. Заказ останется в том же статусе, и его нужно будет доставить покупателю.

## Request Body

## Responses

- **200** Заявка отклонена
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
