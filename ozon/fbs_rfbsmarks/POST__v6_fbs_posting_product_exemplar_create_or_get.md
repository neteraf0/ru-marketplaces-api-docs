# `POST` /v6/fbs/posting/product/exemplar/create-or-get

**Tag:** [FBS&rFBSMarks](index.md)

**operationId:** `PostingAPI_FbsPostingProductExemplarCreateOrGetV6`

**Получить данные созданных экземпляров**

Метод для получения информации по экземплярам товаров из отправления, переданных в методе [/v6/fbs/posting/product/exemplar/set](#operation/PostingAPI_FbsPostingProductExemplarSetV6).

Используйте метод для получения `exemplar_id`.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Данные экземпляров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `multi_box_qty` | integer |  | Количество коробок, в которые упакован товар. |
| `posting_number` | string |  | Номер отправления. |
| `products` | array |  | Список товаров. |

[Response 200](../_shared/examples/POST__v6_fbs_posting_product_exemplar_create_or_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
