# `POST` /v1/actions/discounts-task/list

**Tag:** [Promos](index.md)

**operationId:** `promos_task_list`

**Список заявок на скидку**


 Метод устаревает и будет отключён в будущем. Переключитесь на /v2/actions/discounts-task/list.


 Метод для получения списка товаров, которые покупатели хотят купить со скидкой.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | v1DiscountTaskStatus | ✓ | Статус заявки на скидку: - `NEW` — новая, - `SEEN` — просмотренная, - `APPROVED` — одобренная, - `PARTLY_APPROVED` — одобренная частично, - `DECLINED` — отклонённая, - `AUTO_DECLINED` — отклонена автоматически, - `DECLINED_BY_USER` — отклонена покупателем, - `COUPON` — скидка по купону, - `PURCHASED` — купленная.  |
| `page` | integer | ✓ | Страница, с которой нужно выгрузить список заявок на скидку. |
| `limit` | integer | ✓ | Максимальное количество заявок на странице. |

[Request example](examples/POST__v1_actions_discounts_task_list_req.json)

## Responses

### `200` Список заявок


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Список заявок. |

[Response 200](../_shared/examples/POST__v1_actions_discounts_task_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
