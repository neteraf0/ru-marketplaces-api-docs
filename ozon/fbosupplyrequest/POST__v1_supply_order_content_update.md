# `POST` /v1/supply-order/content/update

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyOrderAPI_SupplyOrderContentUpdate`

**Редактирование товарного состава**

Метод для редактирования товарного состава в заявке на поставку.

Чтобы проверить статус редактирования, используйте метод [/v1/supply-order/content/update/status](#operation/SupplyOrderAPI_SupplyOrderContentUpdateStatus).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ | Новый товарный состав заявки на поставку.  Максимум 5000 товаров.  |
| `order_id` | integer | ✓ | Идентификатор заказа. |
| `supply_id` | integer | ✓ | Идентификатор поставки. |
## Responses

### `200` Товарный состав обновлён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Ошибки при редактировании товарного состава: - `INVALID_DRAFT_BUNDLE_ID`, `SOME_SERVICE_ERROR`, `ORDER_IS_NOT_FOUND`, `SUPPLY_IS_NOT_FOUND`, `SUPPLY_DOES_NOT_BELONGS_TO_ORDER` — ошибка при редактировании поставки. - `HAS_UTD`, `UTD_IS_UPLOADED` — документы в системе ЭДО не удалены. Аннулируйте документы в системе ЭДО. Когда отредактируете состав, сформируйте и подпишите новые документы. - `ORDER_SKU_LIMIT` — количество товаров в поставке должно быть меньше или равно 5000. - `SAME_SKU` — товарный состав поставки остался прежним. - `SUPPLY_LOCKED` — обновление товарного состава в процессе, попробуйте позже. - `INBOUND_NO_CAPACITY` — на складе недостаточно места для поставки. - `INBOUND_LOCK`, `ORDER_LOCKED`, `STORAGE_WAREHOUSE_IS_NOT_WMS` — нельзя редактировать товарный состав. - `SUPPLY_CONTENT_NOT_VALID` — в составе поставки есть товары, которые склад не может принять. - `SUPPLY_BELONG_TO_ANOTHER_CONTRACTOR`, `COMPANY_DOES_NOT_BELONGS_TO_CONTRACTOR`, `ORDER_DOES_NOT_BELONG_TO_CONTRACTOR` — заявка на поставку не принадлежит вашему юридическому лицу. - `SUPPLY_BELONG_TO_ANOTHER_COMPANY`, `ORDER_DOES_NOT_BELONGS_TO_COMPANY` — заявка на поставку не принадлежит вашему кабинету. - `INCORRECT_SUPPLY_STATE` — нельзя изменить поставку в этом статусе. - `INCORRECT_SUPPLY_SOURCE` — нельзя изменить поставку с этим источником данных. - `INCORRECT_STORAGE_WAREHOUSE` — нельзя изменить поставку с этим складом хранения. - `NO_SUPPLY_PRODUCT_BUNDLE_ID` — отсутствует идентификатор товарного состава поставки. - `INVALID_VOLUME` — некорректный объём поставки. - `SUPPLY_IS_VIRTUAL` — нельзя редактировать виртуальную поставку. - `DEADLINE` — нельзя изменить поставку за час до таймслота. - `INACTIVE_CONTRACT` — нельзя редактировать состав поставки с истекшим договором. - `QUANTITY_OUT_OF_RANGE_BOTTOM` — количество экземпляров каждого товара должно быть больше 0. - `QUANTITY_OUT_OF_RANGE_UPPER` — количество экземпляров каждого товара должно быть меньше или равно 1 000 000. - `EMPTY_CONTENT` — не сможем принять пустую поставку, добавьте товары. - `CONTRACT_IS_NOT_FOUND`, `CONTRACT_IS_NOT_VALID_FOR_HANDLING_ORDERS` — в этом личном кабинете нельзя изменить поставку.  |
| `operation_id` | string |  | Идентификатор операции. |

[Response 200](../_shared/examples/POST__v1_supply_order_content_update_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
