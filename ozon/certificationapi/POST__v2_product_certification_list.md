# `POST` /v2/product/certification/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `ProductAPI_ProductCertificationList`

**Список сертифицируемых категорий**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `page` | integer | ✓ | Номер страницы. |
| `page_size` | integer | ✓ | Количество элементов на странице. |

[Request example](examples/POST__v2_product_certification_list_req.json)

## Responses

### `200` Список сертифицируемых категорий


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `certification` | array |  | Информация о сертифицируемых категориях. |
| `total` | integer |  | Всего категорий. |

[Response 200](../_shared/examples/POST__v2_product_certification_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
