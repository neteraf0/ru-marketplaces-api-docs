# `POST` /v2/review/info

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewInfoV2`

**Получить информацию по отзыву**

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
| `review_id` | string | ✓ | Идентификатор отзыва. |

[Request example](examples/POST__v2_review_info_req.json)

## Responses

### `200` Информация об отзыве


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `comments_amount` | integer |  | Количество комментариев к отзыву. |
| `dislikes_amount` | integer |  | Количество дизлайков на отзыве. |
| `id` | string |  | Идентификатор отзыва. |
| `is_rating_participant` | boolean |  | `true`, если отзыв участвует в подсчёте рейтинга.  |
| `likes_amount` | integer |  | Количество лайков на отзыве. |
| `order_status` | review.v2.ReviewInfoV2Response.OrderStatus.Enum |  | Статус заказа, на который покупатель оставил отзыв: - `DELIVERED` — доставлен; - `CANCELLED` — отменён.  |
| `photos` | array |  | Информация об изображениях. |
| `photos_amount` | integer |  | Количество изображений у отзыва. |
| `published_at` | string |  | Дата публикации отзыва. |
| `rating` | integer |  | Оценка отзыва. |
| `sku` | integer |  | Идентификатор товара в системе Ozon — SKU. |
| `status` | review.v2.ReviewInfoV2Response.Status.Enum |  | Статус отзыва: - `NEW` — новый; - `VIEWED` — просмотренный; - `PROCESSED` — обработанный.  |
| `text` | string |  | Текст отзыва. |
| `videos` | array |  | Информация о видео. |
| `videos_amount` | integer |  | Количество видео у отзыва. |

[Response 200](../_shared/examples/POST__v2_review_info_200.json)

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
