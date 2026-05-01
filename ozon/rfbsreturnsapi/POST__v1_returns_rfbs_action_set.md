# `POST` /v1/returns/rfbs/action/set

**Tag:** [RFBSReturnsAPI](index.md)

**operationId:** `ReturnsAPI_ReturnsRfbsActionSet`

**Передать доступные действия для rFBS возвратов**

Метод для передачи действий для возврата rFBS.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `comment` | string |  | Комментарий продавца.  Обязателен для `id: -1` и `id: -10`.  |
| `compensation_amount` | number |  | Сумма компенсации.  Обязательна для `id: 1020`.  |
| `id` | integer |  | Идентификатор действия.   Получите доступные действия `returns.available_actions` методом [/v2/returns/rfbs/get](#operation/RFBSReturnsAPI_ReturnsRfbsGetV2).  |
| `rejection_reason_id` | integer |  | Идентификатор причины отмены.  Обязателен для `id: -1` и `id: -10`.  Получите возможные причины отмены `returns.rejection_reason` методом [/v2/returns/rfbs/get](#operation/RFBSReturnsAPI_ReturnsRfbsGetV2).  |
| `return_for_back_way` | number |  | Сумма, возмещаемая покупателю за пересылку товара.  Отрицательные значения приравниваются к `0`.  |
| `return_id` | integer | ✓ | Идентификатор заявки на возврат. |
## Responses

- **200** Действие передано
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
