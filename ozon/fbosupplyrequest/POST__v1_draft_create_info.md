# `POST` /v1/draft/create/info

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftCreateInfo`

**Информация о черновике заявки на поставку**


Метод устаревает и будет отключён 16 марта 2026 года. Используйте /v2/draft/create/info.


Вы можете создавать черновики заявки на поставку 2 раза в минуту и 50 раз в час. Если превысите лимит, вернётся ошибка 429.

Возвращает информацию о созданном черновике заявки на поставку. В ответе вернутся склады размещения в каждом выбранном кластере, которые примут все товары.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Уникальный идентификатор генерации черновика заявки на поставку.  |

[Request example](examples/POST__v1_draft_create_info_req.json)

## Responses

### `200` Информация о черновике заявки на поставку


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `clusters` | array |  | Кластеры. |
| `draft_id` | integer |  | Идентификатор черновика заявки на поставку. |
| `errors` | array |  | Ошибки. |
| `status` | v1CalculationStatus |  | Статус создания черновика заявки на поставку: - `CALCULATION_STATUS_FAILED` — не удалось создать черновик, - `CALCULATION_STATUS_SUCCESS` — черновик создан, - `CALCULATION_STATUS_IN_PROGRESS` — черновик создаётся, - `CALCULATION_STATUS_EXPIRED` — истёк срок действия черновика.  |

[Response 200](../_shared/examples/POST__v1_draft_create_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
