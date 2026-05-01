# `POST` /v2/posting/fbs/act/create

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingAPI_PostingFBSActCreate`

**Подтвердить отгрузку и создать документы**

Подтверждает отгрузку и запускает формирование транспортной накладной и штрихкода для отгрузки.
Для продавцов из России также запускается формирование листа отгрузки, а для продавцов из СНГ — акта приёма-передачи.

Чтобы сформировать и получить документы, переведите отправление в статус `awaiting_deliver`.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `containers_count` | integer |  | Количество грузовых мест.   Используйте параметр, если вы подключены к доверительной приёмке и отгружаете заказы грузовыми местами. Если вы не подключены к доверительной приёмке, пропустите его.  [Подробнее в Базе знаний продавца](https://docs.ozon.ru/partners/prodayoa-so-svoego-sklada-fbs/doveritel-naya-priemka-gruzovogo-mesta)  |
| `delivery_method_id` | integer | ✓ | Идентификатор метода доставки. Для realFBS-складов получите его с помощью метода [/v2/delivery-method/list](#operation/WarehouseAPI_DeliveryMethodListV2). Для FBS-складов используйте значение параметра `warehouse_id`. Его можно получить с помощью метода [/v2/warehouse/list](#operation/WarehouseListV2). |
| `departure_date` | string |  | Дата отгрузки. |

[Request example](examples/POST__v2_posting_fbs_act_create_req.json)

## Responses

### `200` Отгрузка подтверждена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | PostingFBSActCreateResponseAct |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_act_create_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
