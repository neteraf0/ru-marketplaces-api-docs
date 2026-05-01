# `POST` /v1/review/count

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewAPI_ReviewCount`

**Количество отзывов по статусам**


  Метод устаревает. Переключитесь на /v2/review/count.


Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1190-Metody-dlia-raboty-s-otzyvami) в сообществе разработчиков Ozon for dev.

> ⚠️ **Deprecated**

## Request Body

## Responses

### `200` Количество обработанных и необработанных отзывов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `processed` | integer |  | Количество обработанных отзывов. |
| `total` | integer |  | Количество всех отзывов. |
| `unprocessed` | integer |  | Количество необработанных отзывов. |

[Response 200](../_shared/examples/POST__v1_review_count_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
