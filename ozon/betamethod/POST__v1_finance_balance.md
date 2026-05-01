# `POST` /v1/finance/balance

**Tag:** [BetaMethod](index.md)

**operationId:** `GetFinanceBalanceV1`

**Получить отчёт о балансе**

Соответствует разделу **Финансы → Баланс** в личном кабинете.

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1732-Novyi-metod-polucheniia-dannykh-po-balansu/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата начала отчётного периода в формате `YYYY-MM-DD`. |
| `date_to` | string | ✓ | Дата окончания отчётного периода в формате `YYYY-MM-DD`. Максимальный период между `date_from` и `date_to` — 30 дней. |
## Responses

### `200` Отчёт о балансе


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cashflows` | GetFinanceBalanceV1ResponseCashflows |  | Информация о доходах и расходах. |
| `total` | GetFinanceBalanceV1ResponseTotal |  | Общие данные по балансу за период. |

[Response 200](../_shared/examples/POST__v1_finance_balance_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
