# `POST` /v1/seller-actions/list

**Tag:** [SellerActions](index.md)

**operationId:** `SellerActionsList`

**Получить список акций**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1872-Novye-metody-dlia-raboty-s-aktsiiami-sellera) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `action_ids` | array |  | Идентификаторы акций. |
| `action_type` | array |  | Механика акции:   - `DISCOUNT` — скидка;   - `VOUCHER_DISCOUNT` — скидка по промокоду;   - `DISCOUNT_WITH_CONDITION` — скидка от суммы заказа;   - `INSTALLMENT` — беспроцентная рассрочка;   - `INDIVIDUAL_DISCOUNT_BY_PRODUCTS` — бонусы продавца;   - `OZON_ACCOUNT_DISCOUNT` — повышенная скидка с картой Ozon Банка;   - `MULTI_LEVEL_DISCOUNT_ON_AMOUNT` — многоуровневая скидка от суммы.  |
| `limit` | integer | ✓ | Количество значений на странице. |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе. Например, если `offset = 10`, то ответ начнётся с 11-го найденного элемента. |
| `search` | string |  | Поиск по названию акции. |
| `status` | array |  | Статус акции:  - `ACTIVE` — активна;  - `ENDED` — завершена;  - `PLANNED` — запланирована;  - `PAUSED` — приостановлена.  |
## Responses

### `200` Список акций


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `actions` | array |  | Список акций. |
| `total` | integer |  | Общее количество акций. |

[Response 200](../_shared/examples/POST__v1_seller_actions_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
