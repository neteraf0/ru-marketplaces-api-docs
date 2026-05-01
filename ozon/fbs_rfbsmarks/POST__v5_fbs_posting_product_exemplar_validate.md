# `POST` /v5/fbs/posting/product/exemplar/validate

**Tag:** [FBS&rFBSMarks](index.md)

**operationId:** `PostingAPI_FbsPostingProductExemplarValidateV5`

**Валидация кодов маркировки**

Метод для проверки кодов на соответствие требованиям системы «Честный ЗНАК» по количеству и составу символов, а также других маркировок.

Если у вас нет номера грузовой таможенной декларации (ГТД), вы можете его не указывать.

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
| `products` | array | ✓ | Список товаров. |
## Responses

### `200` Результат валидации


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `products` | array |  | Список товаров. |

[Response 200](../_shared/examples/POST__v5_fbs_posting_product_exemplar_validate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
