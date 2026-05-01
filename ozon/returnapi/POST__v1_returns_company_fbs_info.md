# `POST` /v1/returns/company/fbs/info

**Tag:** [ReturnAPI](index.md)

**operationId:** `returnsCompanyFBSInfo`

**Количество возвратов FBS**

Метод для получения информации о возвратах FBS и их количестве.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | v1ReturnsCompanyFbsInfoRequestFilter |  | Фильтры. |
| `pagination` | ReturnsCompanyFbsInfoRequestPagination | ✓ | Разделение ответа метода. |

[Request example](examples/POST__v1_returns_company_fbs_info_req.json)

## Responses

### `200` Количество возвратов FBS


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `drop_off_points` | array |  | Информация о drop-off пунктах. |
| `has_next` | boolean |  | Признак, есть ли ещё пункты, где продавца ожидают возвраты. |

[Response 200](../_shared/examples/POST__v1_returns_company_fbs_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
