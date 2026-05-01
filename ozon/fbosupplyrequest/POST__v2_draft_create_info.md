# `POST` /v2/draft/create/info

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `DraftCreateInfo`

**Получить информацию о черновике заявки на поставку**

Вы можете создавать черновики заявки на поставку 2 раза в минуту и 50 раз в час.

Если превысите лимит, вернётся ошибка 429.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer | ✓ | Идентификатор черновика из методов [/v1/draft/crossdock/create](#operation/DraftCrossdockCreate), [/v1/draft/direct/create](#operation/DraftDirectCreate) или [/v1/draft/multi-cluster/create](#operation/DraftMultiClusterCreate). |
## Responses

### `200` Информация о черновике


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `clusters` | array |  | Кластеры. |
| `errors` | array |  | Ошибки. |
| `status` | v2DraftCreateInfoResponseStatusEnum |  | Статус создания черновика заявки на поставку:   - `UNSPECIFIED` — не определён,   - `SUCCESS` — создан,   - `IN_PROGRESS` — создаётся,   - `FAILED` — не удалось создать.  |

[Response 200](../_shared/examples/POST__v2_draft_create_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
