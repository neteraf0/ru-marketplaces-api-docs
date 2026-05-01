# `POST` /v4/product/info/stocks

**Tag:** [Prices&StocksAPI](index.md)

**operationId:** `ProductAPI_GetProductInfoStocks`

**Информация о количестве товаров**

Возвращает информацию о ĸоличестве товаров по схемам FBS, rFBS и FBP:
  - сĸольĸо единиц есть в наличии,
  - сĸольĸо зарезервировано поĸупателями.

Чтобы получить информацию об остатках по схеме FBO, используйте метод [/v1/analytics/stocks](#operation/AnalyticsAPI_AnalyticsStocks).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `filter` | v4GetProductInfoStocksRequestFilter | ✓ | Фильтр по товарам. |
| `limit` | integer | ✓ | Количество значений на странице. Минимум — 1, максимум — 1000. |

[Request example](examples/POST__v4_product_info_stocks_req.json)

## Responses

### `200` Количество товара


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `items` | array |  | Информация о товарах. |
| `total` | integer |  | Количество уникальных товаров, для которых выводится информация об остатках. |

[Response 200](../_shared/examples/POST__v4_product_info_stocks_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
