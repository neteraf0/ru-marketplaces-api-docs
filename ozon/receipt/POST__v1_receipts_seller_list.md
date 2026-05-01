# `POST` /v1/receipts/seller/list

**Tag:** [Receipt](index.md)

**operationId:** `ReceiptsSellerList`

**Получить список чеков продавца**


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
| `page` | integer |  | Количество страниц, которое нужно пропустить. |
| `page_size` | integer |  | Количество элементов на странице. |
| `posting_numbers` | array |  | Фильтр по номерам отправлений. |
## Responses

### `200` Список чеков продавца


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | Признак, что в ответе вернулись не все записи:  - `true` — сделайте повторный запрос с новым параметром `page`, чтобы получить остальные значения;  - `false` — ответ содержит все записи с чеками.  |
| `receipts` | array |  | Информация о чеках. |

[Response 200](../_shared/examples/POST__v1_receipts_seller_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
