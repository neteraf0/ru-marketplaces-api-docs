# `POST` /v1/review/comment/create

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewAPI_CommentCreate`

**Оставить комментарий на отзыв**

Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1190-Metody-dlia-raboty-s-otzyvami) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `mark_review_as_processed` | boolean |  | Обновление статуса у отзыва: - `true` — статус изменится на `Processed`. - `false` — статус не изменится.  |
| `parent_comment_id` | string |  | Идентификатор родительского комментария, на который вы отвечаете. |
| `review_id` | string | ✓ | Идентификатор отзыва. |
| `text` | string | ✓ | Текст комментария. |
## Responses

### `200` Комментарий создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `comment_id` | string |  | Идентификатор комментария. |

[Response 200](../_shared/examples/POST__v1_review_comment_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
