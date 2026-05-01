# `POST` /v2/posting/fbo/list

**Tag:** [FBO](index.md)

**operationId:** `PostingAPI_GetFboPostingList`

**Список отправлений**


С 1 июня 2026 года метод будет отключён. Переключитесь на /v3/posting/fbo/list.


Возвращает список отправлений за указанный период времени.
Если период больше года, вернётся ошибка `PERIOD_IS_TOO_LONG`.

Дополнительно можно отфильтровать отправления по их статусу.

> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `dir` | string |  | Направление сортировки:   - `ASC` — по возрастанию,   - `DESC` — по убыванию.  |
| `filter` | postingGetFboPostingListRequestFilter | ✓ | Фильтр для поиска отправлений. |
| `limit` | integer | ✓ | Количество значений в ответе:   - максимум — 1000,   - минимум — 1.  |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе. Например, если `offset = 10`, то ответ начнётся с 11-го найденного элемента. Максимальное значение — 20000. |
| `translit` | boolean |  | Если включена транслитерация адреса из кириллицы в латиницу — `true`. |
| `with` | postingFboPostingWithParams |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v2_posting_fbo_list_req.json)

## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Массив отправлений. |

[Response 200](../_shared/examples/POST__v2_posting_fbo_list_200.json)

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
