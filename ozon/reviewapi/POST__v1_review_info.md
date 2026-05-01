# `POST` /v1/review/info

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewAPI_ReviewInfo`

**Получить информацию об отзыве**


  Метод устаревает. Переключитесь на /v2/review/info.


Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1190-Metody-dlia-raboty-s-otzyvami) в сообществе разработчиков Ozon for dev.

> ⚠️ **Deprecated**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `review_id` | string | ✓ | Идентификатор отзыва. |
## Responses

### `200` Информация об отзыве


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `comments_amount` | integer |  | Количество комментариев к отзыву. |
| `dislikes_amount` | integer |  | Количество дизлайков на отзыве. |
| `id` | string |  | Идентификатор отзыва. |
| `is_rating_participant` | boolean |  | `true`, если отзыв участвует в подсчёте рейтинга.  |
| `likes_amount` | integer |  | Количество лайков на отзыве. |
| `order_status` | string |  | Статус заказа, на который покупатель оставил отзыв: - `DELIVERED` — доставлен, - `CANCELLED` — отменён.  |
| `photos` | array |  | Информация об изображении. |
| `photos_amount` | integer |  | Количество изображений у отзыва. |
| `published_at` | string |  | Дата публикации отзыва. |
| `rating` | integer |  | Оценка отзыва. |
| `sku` | integer |  | Идентификатор товара в системе Ozon — SKU. |
| `status` | string |  | Статус отзыва: - `UNPROCESSED` — не обработан, - `PROCESSED` — обработан.  |
| `text` | string |  | Текст отзыва. |
| `videos` | array |  | Информация о видео. |
| `videos_amount` | integer |  | Количество видео у отзыва. |

[Response 200](../_shared/examples/POST__v1_review_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
