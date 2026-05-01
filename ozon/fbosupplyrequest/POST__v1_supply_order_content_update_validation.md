# `POST` /v1/supply-order/content/update/validation

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyOrderContentUpdateValidation`

**Проверить новый товарный состав**

Используйте этот метод, если в [/v1/supply-order/content/update/status](#operation/SupplyOrderAPI_SupplyOrderContentUpdateStatus) вы получили ошибку `SUPPLY_CONTENT_NOT_VALID`.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `new_bundle_id` | string | ✓ | Идентификатор нового товарного состава поставки. |
| `supply_id` | integer | ✓ | Идентификатор поставки. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `editing_errors` | array |  | Ошибки:  - `UNSPECIFIED` — не определено.  - `UNKNOWN` — неизвестный тип.  - `INCORRECT_SUPPLY_STATE` — нельзя изменить поставку в этом статусе.  - `DEADLINE` — нельзя изменить поставку за час до таймслота.  - `UTD_IS_UPLOADED` — документы в системе ЭДО не удалены. Аннулируйте документы в системе ЭДО. Когда отредактируете состав, сформируйте и подпишите новые документы.  - `STORAGE_WAREHOUSE_IS_NOT_WMS` — нельзя редактировать товарный состав.  - `CONTRACT_IS_NOT_VALID_FOR_HANDLING_ORDERS` — в этом личном кабинете нельзя изменить поставку.  - `SUPPLY_IS_VIRTUAL` — нельзя редактировать виртуальную поставку.  - `SUPPLY_DOES_NOT_BELONG_TO_COMPANY` — заявка на поставку не принадлежит вашему кабинету.  - `ASSORTMENT_REJECTION_REASON_CORRUPTED_ASSORTMENT` — не получилось добавить товар в заявку. Попробуйте ещё раз.  - `ASSORTMENT_REJECTION_REASON_STORAGE_BELARUS_SKU_HAS_NO_ANY_FEACN`, `ASSORTMENT_REJECTION_REASON_STORAGE_BELARUS_SKU_HAS_NO_SELLER_FEACN` — у товара нет кода ТН ВЭД ЕАЭС.   - `ASSORTMENT_REJECTION_REASON_TRACEABLE_SKU_HAS_NO_GTIN_BARCODE` — у товара нет штрихкода GTIN.  - `ASSORTMENT_REJECTION_REASON_TRACEABLE_SKU_HAS_NO_MEASUREMENT_UNIT_QUANTITY` — не указано количество товара в унифицированных единицах измерения.  |
| `validated_assortment` | SupplyOrderContentUpdateValidationResponseValidatedAssortment |  | Информация о товарном составе. |

[Response 200](../_shared/examples/POST__v1_supply_order_content_update_validation_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
