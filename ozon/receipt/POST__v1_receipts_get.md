# `POST` /v1/receipts/get

**Tag:** [Receipt](index.md)

**operationId:** `GetReceipt`

**Получить чек в формате PDF**


 Метод доступен продавцам, которые заключили договор с ТОО «ОЗОН Маркетплейс Казахстан».


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `receipt_id` | string | ✓ | Идентификатор чека. Получите значение параметра методом [/v1/receipts/seller/list](#operation/ReceiptsSellerList). |
## Responses

### `200` Чек


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `content` | string |  | PDF-файл с чеком в бинарном виде. |

[Response 200](../_shared/examples/POST__v1_receipts_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
