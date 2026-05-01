# `POST` /v1/seller-actions/voucher/get

**Tag:** [SellerActions](index.md)

**operationId:** `SellerActionsVoucherGet`

**Получить файл с промокодами в формате CSV**

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
| `action_id` | integer | ✓ | Идентификатор акции. Получите значение параметра методом [/v1/seller-actions/list](#operation/SellerActionsList). |
## Responses

### `200` Файл с промокодами


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `file` | string |  | Ссылка на CSV-файл с промокодами. |

[Response 200](../_shared/examples/POST__v1_seller_actions_voucher_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
