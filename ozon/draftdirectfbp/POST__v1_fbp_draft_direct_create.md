# `POST` /v1/fbp/draft/direct/create

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpDraftDirectCreate`

**Создать черновик заявки на поставку без указания способа доставки**

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
| `bundle_id` | string | ✓ | Идентификатор провалидированного списка товаров. Чтобы получить, используйте метод [/v1/fbp/draft/direct/product/validate](#operation/FbpDraftDirectProductValidate). |
| `delivery_details` | v1FbpDraftDirectCreateRequestDirectDetails | ✓ | Детали доставки. |
| `package_units_count` | integer | ✓ | Количество единиц упаковки. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Черновик создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer |  | Идентификатор черновика. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |
| `supply_id` | string |  | Идентификатор поставки. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_seller_dlv_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
