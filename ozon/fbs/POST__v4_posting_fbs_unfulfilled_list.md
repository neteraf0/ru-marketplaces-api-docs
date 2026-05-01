# `POST` /v4/posting/fbs/unfulfilled/list

**Tag:** [FBS](index.md)

**operationId:** `PostingFbsUnfulfilledList`

**Получить список необработанных отправлений**

Возвращает список необработанных отправлений за указанный период времени — он должен быть не больше одного года.

Возможные статусы отправлений:
- `awaiting_registration` — ожидает регистрации;
- `acceptance_in_progress` — идёт приёмка;
- `awaiting_approve` — ожидает подтверждения;
- `awaiting_packaging` — ожидает упаковки;
- `awaiting_deliver` — ожидает отгрузки;
- `arbitration` — арбитраж;
- `client_arbitration` — клиентский арбитраж доставки;
- `delivering` — доставляется;
- `driver_pickup` — у водителя;
- `cancelled` — отменено;
- `not_accepted` — не принято на сортировочном центре.

Чтобы получать актуальную дату отгрузки, регулярно обновляйте информацию об отправлениях или подключите [пуш-уведомления](#tag/push_start).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `filter` | posting.v4.PostingFbsUnfulfilledListRequest.Filter |  | Фильтр запроса.  Используйте фильтр по времени сборки — `cutoff` или по дате передачи отправления в доставку — `delivering_date`. Если использовать их вместе, в ответе вернётся ошибка.  Чтобы использовать фильтр по времени сборки, заполните поля `cutoff_from` и `cutoff_to`.  Чтобы использовать фильтр по дате передачи отправления в доставку, заполните поля `delivering_date_from` и `delivering_date_to`.  |
| `limit` | integer |  | Количество значений в ответе. |
| `sort_dir` | posting.v4.PostingFbsUnfulfilledListRequest.SortDir.Enum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |
| `translit` | boolean |  | `true`, чтобы включить транслитерацию адреса из кириллицы в латиницу.  |
| `with` | posting.v4.PostingFbsUnfulfilledListRequest.With |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v4_posting_fbs_unfulfilled_list_req.json)

## Responses

### `200` Список необработанных отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `count` | integer |  | Количество отправлений в ответе. |
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все отправления.  |
| `postings` | array |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v4_posting_fbs_unfulfilled_list_200.json)

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
