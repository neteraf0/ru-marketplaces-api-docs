# `POST` /v1/actions/discounts-task/decline

**Tag:** [Promos](index.md)

**operationId:** `promos_task_decline`

**Отклонить заявку на скидку**

Вы можете отклонить заявки в статусах: `NEW` — новые, `SEEN` — просмотренные.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `tasks` | array | ✓ | Список заявок. |

[Request example](examples/POST__v1_actions_discounts_task_decline_req.json)

## Responses

### `200` Заявки отклонены


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1ApproveDeclineDiscountTasksResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_actions_discounts_task_approve_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
