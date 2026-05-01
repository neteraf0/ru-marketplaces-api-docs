# `POST` /v2/review/list

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewListV2`

**Получить список отзывов**

Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1985-Novye-beta-metody-dlia-raboty-s-otzyvami-v-Seller-API/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filters` | review.v2.ReviewListV2Request.Filters |  | Фильтры для поиска отзывов. |
| `last_id` | string |  | Идентификатор последнего отзыва в ответе. |
| `limit` | integer | ✓ | Количество отзывов в ответе. |
| `sort_dir` | review.v2.ReviewListV2Request.SortDir.Enum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |

[Request example](examples/POST__v2_review_list_req.json)

## Responses

### `200` Список отзывов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | `true`, если в ответе вернули не все отзывы.  |
| `last_id` | string |  | Идентификатор последнего отзыва на странице. |
| `reviews` | array |  | Список отзывов. |

[Response 200](../_shared/examples/POST__v2_review_list_200.json)

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
