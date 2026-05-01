# `POST` /v1/fbp/draft/direct/registrate

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpDraftDirectRegistrate`

**Перевести черновик в действующую поставку**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `row_version` | integer | ✓ | Идентификатор актуальной версии черновика. |
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | v1FbpDraftDirectRegistrateResponseRegistrationError |  | Ошибка. |
| `is_error` | boolean |  | `true`, если есть ошибка. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_registrate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
