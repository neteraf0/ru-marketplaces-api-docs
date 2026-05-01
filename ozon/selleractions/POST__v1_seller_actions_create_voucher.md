# `POST` /v1/seller-actions/create/voucher

**Tag:** [SellerActions](index.md)

**operationId:** `SellerActionsCreateVoucher`

**Создать акцию с механикой «Скидка по промокоду»**

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
| `budget` | integer | ✓ | Бюджет акции. Если бюджет закончится, акция остановится. |
| `date_end` | string | ✓ | Дата и время окончания акции. |
| `date_start` | string | ✓ | Дата и время начала акции. |
| `discount_type` | v1SellerActionsCreateVoucherRequestDiscountTypeEnum | ✓ | Тип скидки:  - `PERCENT` — скидка в процентах;  - `CURRENCY` — скидка в валюте.  |
| `discount_value` | number | ✓ | Размер скидки. |
| `title` | string | ✓ | Название акции. |
| `user_ids` | array |  | Идентификаторы пользователей, которым доступен промокод. |
| `voucher_parameters` | v1SellerActionsCreateVoucherRequestVoucherParameter | ✓ | Параметры промокодов. |
## Responses

### `200` Акция создана


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `action_id` | integer |  | Идентификатор акции. |

[Response 200](../_shared/examples/POST__v1_seller_actions_create_discount_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
