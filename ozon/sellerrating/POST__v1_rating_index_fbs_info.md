# `POST` /v1/rating/index/fbs/info

**Tag:** [SellerRating](index.md)

**operationId:** `RatingAPI_GetFBSRatingIndexInfoV1`

**Получить индекс ошибок FBS и rFBS**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Индекс ошибок


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `currency_code` | string |  | Код валюты стоимости обработки ошибок. |
| `defects` | array |  | Индекс ошибок по дням. |
| `index` | number |  | Значение индекса ошибок за период. |
| `period_from` | string |  | Дата начала расчётного периода в формате `YYYY-MM-DD`. |
| `period_to` | string |  | Дата окончания расчётного периода в формате `YYYY-MM-DD`. |
| `processing_costs_sum` | number |  | Расходы на обработку ошибок за период. |

[Response 200](../_shared/examples/POST__v1_rating_index_fbs_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
