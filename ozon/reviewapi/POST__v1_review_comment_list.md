# `POST` /v1/review/comment/list

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewAPI_CommentList`

**Получить список комментариев на отзыв**

Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1190-Metody-dlia-raboty-s-otzyvami) в сообществе разработчиков Ozon for dev.

Метод возвращает информацию по комментариям на отзывы, которые прошли модерацию.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | review.v1.CommentListRequest.Filter |  | Фильтры для поиска отзывов. |
| `limit` | integer | ✓ | Ограничение значений в ответе. Минимум — 20. Максимум — 100.  |
| `offset` | integer |  | Количество элементов, которое будет пропущено с начала списка в ответе. Например, если `offset = 10`, то ответ начнётся с 11-го найденного элемента. |
| `review_id` | string |  | Идентификатор отзыва. |
| `sort_dir` | v1CommentSort |  | Направление сортировки:   - `ASC` — по возрастанию,   - `DESC` — по убыванию.  |

[Request example](examples/POST__v1_review_comment_list_req.json)

## Responses

### `200` Информация о комментариях на отзыв


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `comments` | array |  | Информация о комментарии. |
| `offset` | integer |  | Количество элементов в выдаче. |

[Response 200](../_shared/examples/POST__v1_review_comment_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
