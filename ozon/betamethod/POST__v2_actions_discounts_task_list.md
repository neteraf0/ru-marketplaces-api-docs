# `POST` /v2/actions/discounts-task/list

**Tag:** [BetaMethod](index.md)

**operationId:** `GetDiscountTaskListV2`

**Получить список заявок на скидку**

Возвращает список товаров, которые покупатели хотят купить со скидкой.

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1856-Novye-metody-dlia-raboty-s-polucheniem-Spiska-zaiavok-na-skidku/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `last_id` | integer |  | Идентификатор последнего значения на странице. При первом запросе оставьте это поле пустым. |
| `limit` | integer (enum: 5, 10, 15, 20, 30, 50) |  | Максимальное количество заявок на странице. |
| `status` | v2GetDiscountTaskListV2RequestDiscountTaskStatusEnum |  | Статус заявки на скидку:   - `ALL` — все статусы,   - `NEW` — новая,   - `APPROVED` — одобренная,   - `DECLINED` — отклонённая.  |
## Responses

### `200` Список заявок


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `tasks` | array |  | Список заявок. |

[Response 200](../_shared/examples/POST__v2_actions_discounts_task_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
