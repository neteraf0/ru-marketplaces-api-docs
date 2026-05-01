# `POST` /v1/review/change-status

**Tag:** [ReviewAPI](index.md)

**operationId:** `ReviewAPI_ReviewChangeStatus`

**Изменить статус отзывов**


  Метод устаревает. Переключитесь на /v2/review/change-status.


Доступно для продавцов с подпиской [Управление отзывами](https://seller-edu.ozon.ru/libra/seller-rating/podpiska-upravlenie-otzyvami) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1190-Metody-dlia-raboty-s-otzyvami) в сообществе разработчиков Ozon for dev.

> ⚠️ **Deprecated**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `review_ids` | array | ✓ | Массив с идентификаторами отзывов от 1 до 100. |
| `status` | string | ✓ | Статус отзыва: - `PROCESSED` — обработанный, - `UNPROCESSED` — необработанный.  |
## Responses

### `200` Статус изменён


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_pricing_strategy_update_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
