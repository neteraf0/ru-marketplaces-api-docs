# `POST` /v1/product/quant/list

**Tag:** [Quants](index.md)

**operationId:** `QuantProductList`

**Список эконом-товаров**

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
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `limit` | integer | ✓ | Максимальное количество элементов в ответе. |
| `visibility` | string (enum: ALL, VISIBLE, INVISIBLE, EMPTY_STOCK, NOT_MODERATED, MODERATED, DISABLED, STATE_FAILED, READY_TO_SUPPLY, VALIDATION_STATE_PENDING, VALIDATION_STATE_FAIL, VALIDATION_STATE_SUCCESS, TO_SUPPLY, IN_SALE, REMOVED_FROM_SALE, OVERPRICED, CRITICALLY_OVERPRICED, EMPTY_BARCODE, BARCODE_EXISTS, QUARANTINE, ARCHIVED, OVERPRICED_WITH_STOCK, PARTIAL_APPROVED) |  | Фильтр по видимости товара: - `ALL` — все товары, кроме архивных. - `VISIBLE` — товары, которые видны покупателям. - `INVISIBLE` — товары, которые не видны покупателям. - `EMPTY_STOCK` — товары, которых нет в наличии. - `NOT_MODERATED` — товары, которые не прошли модерацию. - `MODERATED` — товары, которые прошли модерацию. - `DISABLED` — товары, которые видны покупателям, но недоступны к покупке. - `STATE_FAILED` — товары, создание которых завершилось ошибкой. - `READY_TO_SUPPLY` — товары, готовые к поставке. - `VALIDATION_STATE_PENDING` — товары, которые проходят проверку валидатором на премодерации. - `VALIDATION_STATE_FAIL` — товары, которые не прошли проверку валидатором на премодерации. - `VALIDATION_STATE_SUCCESS` — товары, которые прошли проверку валидатором на премодерации. - `TO_SUPPLY` — товары, готовые к продаже. - `IN_SALE` — товары в продаже. - `REMOVED_FROM_SALE` — товары, скрытые от покупателей. - `OVERPRICED` — превышение цены. - `CRITICALLY_OVERPRICED` — критическое превышение цены. - `EMPTY_BARCODE` — пустой штрихкод. - `BARCODE_EXISTS` — штрихкод указан. - `QUARANTINE` — товар в карантине после изменения цены на 50% и больше. - `ARCHIVED` — товары в архиве. - `OVERPRICED_WITH_STOCK` — товары в продаже, цена которых выше, чем у конкурентов. - `PARTIAL_APPROVED` — товары в продаже, у которых пустое или неполное описание.  |

[Request example](examples/POST__v1_product_quant_list_req.json)

## Responses

### `200` Эконом-товары


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `products` |  |  | Эконом-товары. |
| `total_items` | integer |  | Остаток на всех складах, шт. |

[Response 200](../_shared/examples/POST__v1_product_quant_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
