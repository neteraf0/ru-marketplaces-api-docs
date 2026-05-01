# `POST` /v1/carriage/ettn/status

**Tag:** [DeliveryFBS](index.md)

**operationId:** `CarriageEttnStatus`

**Получить статус проверки электронной ТТН на прослеживаемой перевозке FBS**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `carriage_id` | integer | ✓ | Идентификатор перевозки. |
## Responses

### `200` Статус проверки электронной ТТН


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Ошибки проверки электронной ТТН на прослеживаемой отгрузке. |
| `status` | string (enum: NOT_UPLOADED, PROCESSING, SUCCESS, FAILED) |  | Статус проверки электронной ТТН на прослеживаемой отгрузке:  - `NOT_UPLOADED` — не загружена;  - `PROCESSING` — в процессе проверки;  - `SUCCESS` — проверена;  - `FAILED` — ошибка.  |

[Response 200](../_shared/examples/POST__v1_carriage_ettn_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
