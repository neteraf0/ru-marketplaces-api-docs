# `POST` /v4/posting/fbs/ship

**Tag:** [FBS&rFBSMarks](index.md)

**operationId:** `PostingAPI_ShipFbsPostingV4`

**Собрать заказ (версия 4)**


Ответ с кодом 200 не гарантирует успешную сборку заказа. Используйте метод /v3/posting/fbs/get, чтобы проверить, что заказ собран. Если в ответе указан result.substatus = ship_failed, повторите сборку заказа.


Делит заказ на отправления и переводит его в статус `awaiting_deliver`.

Каждый элемент в `packages` может содержать несколько элементов `products` или отправлений.
Каждый элемент в `products` — это товар, включённый в данное отправление.

Разделить заказ нужно, если:
  - товары не помещаются в одну упаковку,
  - товары нельзя сложить в одну упаковку.

Чтобы разделить заказ, передайте в массиве `packages` несколько объектов.

Пример запроса, когда заказ разделять не нужно: 2 товара будут в одном отправлении.
```
{
  "packages": [
    {
      "products": [
        {
          "product_id": 185479045,
          "quantity": 2
        }
      ]
    }
  ],
  "posting_number": "89491381-0072-1"
}
```

Пример запроса, когда заказ нужно разделить: каждый товар будет в отдельном отправлении.

```
{
  "packages": [
    {
      "products": [
        {
          "product_id": 185479045,
          "quantity": 1
        }
      ]
    },
    {
      "products": [
        {
          "product_id": 185479045,
          "quantity": 1
        }
      ]
    }
  ],
  "posting_number": "89491381-0072-1"
}
```

Чтобы внести информацию по экземплярам, используйте метод [/v6/fbs/posting/product/exemplar/set](#operation/PostingAPI_FbsPostingProductExemplarSetV6).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `packages` |  | ✓ | Список упаковок. Каждая упаковка содержит список отправлений, на которые делится заказ. |
| `posting_number` | string | ✓ | Номер отправления. |
| `with` | FbsPostingShipV4RequestWith |  | Дополнительная информация. |

[Request example](examples/POST__v4_posting_fbs_ship_req.json)

## Responses

### `200` Результат сборки заказа


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `additional_data` |  |  | Дополнительная информация об отправлениях. |
| `result` |  |  | Результат сборки отправлений. |

[Response 200](../_shared/examples/POST__v4_posting_fbs_ship_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
