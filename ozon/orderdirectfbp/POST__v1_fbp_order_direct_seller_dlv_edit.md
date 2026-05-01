# `POST` /v1/fbp/order/direct/seller-dlv/edit

**Tag:** [OrderDirectFBP](index.md)

**operationId:** `FbpAPI_FbpOrderDirectSellerDlvEdit`

**Обновить информацию о доставке силами продавца**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `driver_name` | string | ✓ | ФИО водителя. |
| `row_version` | integer | ✓ | Идентификатор актуальной версии черновика. |
| `supply_id` | string | ✓ | Идентификатор заявки на поставку. |
| `vehicle_number` | string | ✓ | Номер автомобиля. |
| `vehicle_type` | string | ✓ | Тип автомобиля. |
## Responses

### `200` Информация обновлена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | v1OrderValidationError |  | Информация об ошибке. |
| `is_error` | boolean |  | `true`, если есть ошибка.  |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |

[Response 200](../_shared/examples/POST__v1_fbp_order_direct_seller_dlv_edit_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
