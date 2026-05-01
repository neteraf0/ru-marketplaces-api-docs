# `POST` /v1/draft/direct/create

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `DraftDirectCreate`

**Создать черновик заявки на прямую поставку**

Черновик заявки на поставку доступен 30 минут.

Вы можете создавать черновики заявки на поставку:
- 2 раза в минуту;
- 50 раз в час;
- 500 раз в день.

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
| `cluster_info` | v1DraftDirectCreateRequestClusterInfo | ✓ | Информация о кластере. |
| `deletion_sku_mode` | v1DraftDirectCreateRequestDeleteSkuModeEnum |  | Режим удаления SKU, которые не попали в поставку.  Возможные значения:  - `PARTIAL` — система удалит только те единицы SKU, которые не прошли проверку;  - `FULL` — система удалит все единицы SKU, если хотя бы 1 единица этого SKU не прошла проверку.  |
## Responses

### `200` Черновик создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer |  | Идентификатор черновика. Используйте в методе [/v2/draft/create/info](#operation/DraftCreateInfo). |
| `errors` | array |  | Ошибки. |

[Response 200](../_shared/examples/POST__v1_draft_crossdock_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
