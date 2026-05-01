# `POST` /v1/seller-actions/create/installment

**Tag:** [SellerActions](index.md)

**operationId:** `SellerActionsCreateInstallment`

**Создать акцию с механикой «Беспроцентная рассрочка»**

Период рассрочки — 6 месяцев.

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
| `date_start` | string | ✓ | Дата и время начала акции. |
| `title` | string | ✓ | Название акции. |
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
