# `POST` /v1/returns/list

**Tag:** [ReturnsAPI](index.md)

**operationId:** `returnsList`

**Информация о возвратах FBO и FBS**

Метод для получения информации о возвратах FBO и FBS.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | GetReturnsListRequestFilter |  | Фильтры. Используйте только один фильтр в запросе: `logistic_return_date`, `storage_tariffication_start_date` или `visual_status_change_moment`, иначе вернётся ошибка.  |
| `limit` | integer | ✓ | Количество подгружаемых возвратов. Максимальное значение — 500. |
| `last_id` | integer |  | Идентификатор последнего подгруженного возврата. |

[Request example](examples/POST__v1_returns_list_req.json)

## Responses

### `200` Информация по возвратам


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `returns` | array |  | Информация о возвратах. |
| `has_next` | boolean |  | `true`, если у продавца есть другие возвраты.  |

[Response 200](../_shared/examples/POST__v1_returns_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
