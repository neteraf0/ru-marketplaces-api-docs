# `POST` /v1/rating/summary

**Tag:** [SellerRating](index.md)

**operationId:** `RatingAPI_RatingSummaryV1`

**Получить информацию о текущих рейтингах продавца**

Рейтинг продавца по следующим показателям: индекс цен, доставки вовремя, процент отмен, жалобы и другие.
Соответствует разделу **Рейтинги → Рейтинги продавца** в личном кабинете.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
## Responses

### `200` Информация о рейтингах


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `groups` |  |  | Список с группами рейтингов. |
| `localization_index` |  |  | Данные по индексу локализации. Если за последние 14 дней у вас не было продаж, поля параметра будут пустыми. |
| `penalty_score_exceeded` | boolean |  | Признак, что баланс штрафных баллов превышен. |
| `premium` | boolean |  | Признак наличия подписки [Premium](https://seller-edu.ozon.ru/seller-rating/about-rating/premium-program). |
| `premium_plus` | boolean |  | Признак наличия подписки [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus). |

[Response 200](../_shared/examples/POST__v1_rating_summary_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
