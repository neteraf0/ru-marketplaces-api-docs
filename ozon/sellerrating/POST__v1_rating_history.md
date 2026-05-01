# `POST` /v1/rating/history

**Tag:** [SellerRating](index.md)

**operationId:** `RatingAPI_RatingHistoryV1`

**Получить информацию о рейтингах продавца за период**

Информация о рейтингах за заданный период и с фильтром по нужному рейтингу.
Соответствует разделу **Рейтинги → Рейтинги продавца** в личном кабинете.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Начало периода. |
| `date_to` | string | ✓ | Конец периода. |
| `ratings` |  | ✓ | Фильтр по рейтингу.  Рейтинги, по которым нужно получить значение за период:  - `rating_on_time` — процент заказов, выполненных вовремя за последние 30 дней. - `rating_review_avg_score_total` — средняя оценка всех товаров. - `rating_ssl` — оценка работы по FBO. Учитывает `rating_on_time_supply_delivery`, `rating_on_time_supply_cancellation` и `rating_order_accuracy`. - `rating_on_time_supply_delivery` — процент поставок, которые вы привезли на склад в выбранный временной интервал за последние 60 дней. - `rating_order_accuracy` — процент поставок без излишков, недостач, пересорта и брака за последние 60 дней. - `rating_on_time_supply_cancellation` — процент заявок на поставку, которые завершились или были отменены без опоздания за последние 60 дней. - `rating_reaction_time` — время в секундах, в течение которого покупатели в среднем ждали ответа на своё первое сообщение в чате за последние 30 дней. - `rating_average_response_time` — время в секундах, в течение которого покупатели в среднем ждали вашего ответа за последние 30 дней. - `rating_replied_dialogs_ratio` — доля диалогов хотя бы с одним вашим ответом в течение 24 часов за последние 30 дней. - `rating_general_indicator_fbs_rfbs` — индекс ошибок FBS и rFBS. - `rating_price_green` — выгодный индекс цен. - `rating_price_yellow` — умеренный индекс цен. - `rating_price_red` — невыгодный индекс цен. - `rating_price_super` — супер-выгодный индекс цен.  Если вы хотите получить информацию по начисленным штрафным баллам для рейтингов `rating_on_time` и `rating_review_avg_score_total`, передайте значения нужных рейтингов в этом параметре и `with_premium_scores=true`.  |
| `with_premium_scores` | boolean |  | Признак, что в ответе нужно вернуть информацию о штрафных баллах в Premium-программе. |
## Responses

### `200` Информация о рейтингах


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `premium_scores` |  |  | Информация о штрафных баллах в Premium-программе. |
| `ratings` |  |  | Информация о рейтингах продавца. |

[Response 200](../_shared/examples/POST__v1_rating_history_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
