# `POST` /v1/posting/fbs/traceable/split

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingFbsTraceableSplit`

**Разделить отправление с прослеживаемыми товарами**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Заказ разделён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `postings` | array |  | Информация об отправлениях. |

[Response 200](../_shared/examples/POST__v1_posting_fbs_traceable_split_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
