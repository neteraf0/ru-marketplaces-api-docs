# `POST` /v5/fbs/posting/product/exemplar/status

**Tag:** [FBS&rFBSMarks](index.md)

**operationId:** `PostingAPI_FbsPostingProductExemplarStatusV5`

**Получить статус добавления экземпляров**

Метод для получения статусов добавления экземпляров, переданных в методе [/v6/fbs/posting/product/exemplar/set](#operation/PostingAPI_FbsPostingProductExemplarSetV6). Также возвращает данные по этим экземплярам.

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

### `200` Статусы проверки экземпляров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string |  | Номер отправления. |
| `products` | array |  | Список товаров. |
| `status` | string |  | Статус проверки всех экземпляров и доступности сборки:  - `ship_available` — сборка доступна;  - `ship_not_available` — сборка недоступна;  - `validation_in_process` — экземпляры на проверке;  - `update_available` — редактирование информации об экземплярах доступно;  - `update_not_available` — редактирование информации об экземплярах недоступно.  |

[Response 200](../_shared/examples/POST__v5_fbs_posting_product_exemplar_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
