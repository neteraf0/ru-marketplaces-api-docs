# `POST` /v2/warehouse/list

**Tag:** [WarehouseAPI](index.md)

**operationId:** `WarehouseListV2`

**Список складов**

Метод возвращает список складов FBS и rFBS. Чтобы получить список складов FBO, используйте метод [/v1/warehouse/fbo/list](#operation/SupplyDraftAPI_DraftGetWarehouseFboList).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `limit` | integer | ✓ | Количество значений в ответе. |
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `warehouse_ids` | array |  | Идентификаторы складов. |

[Request example](examples/POST__v2_warehouse_list_req.json)

## Responses

### `200` Список складов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `warehouses` | array |  | Список складов. |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все значения.  |

[Response 200](../_shared/examples/POST__v2_warehouse_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
