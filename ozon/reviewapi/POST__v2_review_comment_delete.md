# `POST` /v2/review/comment/delete

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewCommentDeleteV2`

**Удалить комментарий на отзыв**

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
| `comment_id` | string | ✓ | Идентификатор комментария. |
| `sku` | integer | ✓ | Идентификатор товара в системе Ozon — SKU. |
## Responses

- **200** Комментарий удалён
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
