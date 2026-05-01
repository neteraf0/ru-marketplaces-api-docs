# `POST` /v1/review/list

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewAPI_ReviewList`

**Получить список отзывов**


  Метод устаревает. Переключитесь на /v2/review/list.


Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1190-Metody-dlia-raboty-s-otzyvami) в сообществе разработчиков Ozon for dev.

Метод не возвращает параметры «Достоинства» и «Недостатки», если они есть в отзывах на товар. Эти параметры устарели, в новых отзывах их нет.

> ⚠️ **Deprecated**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `last_id` | string |  | Идентификатор последнего отзыва на странице. |
| `limit` | integer | ✓ | Количество отзывов в ответе. Минимум — 20, максимум — 100. |
| `sort_dir` | string |  | Направление сортировки: - `ASC` — по возрастанию, - `DESC` — по убыванию.  |
| `status` | string |  | Статусы отзывов: - `ALL` — все, - `UNPROCESSED` — необработанные, - `PROCESSED` — обработанные.  |

[Request example](examples/POST__v1_review_list_req.json)

## Responses

### `200` Список отзывов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | `true`, если в ответе вернули не все отзывы.  |
| `last_id` | string |  | Идентификатор последнего отзыва на странице. |
| `reviews` | array |  | Информация об отзыве. |

[Response 200](../_shared/examples/POST__v1_review_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
