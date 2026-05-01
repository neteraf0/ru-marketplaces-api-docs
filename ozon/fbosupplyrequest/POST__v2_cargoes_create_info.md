# `POST` /v2/cargoes/create/info

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesCreateInfoV2`

**Получить информацию по установке грузомест**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1721-Novyi-metod-dlia-peredachi-offer-id-pri-ustanovke-GM) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор операции. |
## Responses

### `200` Результат запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | v2CargoesCreateErrors |  | Ошибки. |
| `result` | CargoesCreateInfoV2ResponseResult |  | Результат запроса. |
| `status` | CargoesCreateInfoV2ResponseStatusEnum |  | Статус формирования грузоместа:   - `SUCCESS` — успешно;   - `IN_PROGRESS` — формируются;   - `FAILED` — при формировании грузомест произошла ошибка.  |

[Response 200](../_shared/examples/POST__v2_cargoes_create_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
