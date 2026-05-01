# `POST` /v1/product/quant/info

**Tag:** [Quants](index.md)

**operationId:** `QuantGetInfo`

**Информация об эконом-товаре**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1084-Metody-po-tarifu-Ekonom) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `quant_code` |  | ✓ | Список квантов с товарами.  |
## Responses

### `200` Информация об эконом-товаре


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Эконом-товары. |

[Response 200](../_shared/examples/POST__v1_product_quant_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
