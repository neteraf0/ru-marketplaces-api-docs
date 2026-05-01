# `POST` /v1/posting/fbo/cancel-reason/list

**Tag:** [FBO](index.md)

**operationId:** `PostingAPI_GetPostingFboCancelReasonList`

**Причины отмены отправлений по схеме FBO**

Возвращает список причин отмены для всех FBO-отправлений.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Причины отмены отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `reasons` | array |  | Информация о причинах отмены. |

[Response 200](../_shared/examples/POST__v1_posting_fbo_cancel_reason_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
