# `POST` /v2/posting/digital/list

**Tag:** [BetaMethod](index.md)

**operationId:** `PostingDigitalList`

**Получить список отправлений**

Возвращает список отправлений, по которым нужно загрузить коды цифровых товаров. Метод доступен только продавцам, которые работают с цифровыми товарами.

Чтобы получить список отправлений в любом статусе, используйте метод [/v3/posting/fbo/list](#operation/PostingFboList).

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/2050-Novyi-beta-metod-dlia-postingov-s-zagruzkoi-kodov-tsifrovykh-tovarov-v-Seller-API/) в сообществе разработчиков Ozon for dev.

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
| `filter` | posting.v2.PostingDigitalListRequest.Filter |  | Фильтр для поиска отправлений. |
| `limit` | integer |  | Количество значений в ответе. |
| `sort_dir` | posting.v2.PostingDigitalListRequest.SortDir.Enum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |
| `with` | posting.v2.PostingDigitalListRequest.With |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v2_posting_digital_list_req.json)

## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все отправления.  |
| `postings` | array |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v2_posting_digital_list_200.json)

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
