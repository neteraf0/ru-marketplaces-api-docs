# `POST` /v1/supply-order/cancel/status

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyOrderAPI_SupplyOrderCancelStatus`

**Получить статус отмены заявки на поставку**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор операции на отмену заявки на поставку. |
## Responses

### `200` Статус отмены заявки на поставку


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error_reasons` | array |  | Причина, по которой не удалось отменить заявку на поставку:   - `INVALID_ORDER_STATE` — неверный статус заявки на поставку.   - `ORDER_IS_VIRTUAL` — заявка виртуальная.    - `ORDER_DOES_NOT_BELONG_TO_CONTRACTOR` —  заявка на поставку не принадлежит вашему юридическому лицу.   - `ORDER_DOES_NOT_BELONG_TO_COMPANY` — заявка на поставку не принадлежит продавцу.    - `OTHER_ASYNCHRONOUS_OPERATION_IN_PROGRESS` — заявка на поставку в процессе отмены.  |
| `result` | SupplyOrderCancelStatusResponseResult |  | Информация об отмене заявки на поставку. |
| `status` | v1SupplyOrderCancelStatusResponseStatus |  | Статус отмены заявки на поставку. Возможные значения: - `SUCCESS` — заявка отменена. - `IN_PROGRESS` — заявки в процессе отмены. - `ERROR` — ошибка.  |

[Response 200](../_shared/examples/POST__v1_supply_order_cancel_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
