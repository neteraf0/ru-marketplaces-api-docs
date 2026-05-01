# `POST` /v4/product/info/limit

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_GetUploadQuota`

**Лимиты на ассортимент, создание и обновление товаров**

Метод для получения информации о лимитах:
- На ассортимент — сколько всего товаров можно создать в вашем личном кабинете.
- На создание товаров — сколько товаров можно создать в сутки.
- На обновление товаров — сколько товаров можно отредактировать в сутки.

Если у вас есть лимит на ассортимент и вы израсходуете его, вы не сможете создавать новые товары.

[Подробнее о лимитах в Базе знаний продавца](https://seller-edu.ozon.ru/work-with-goods/zagruzka-tovarov/creating-goods/limit/)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Лимиты на ассортмент, создание и обновление товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `daily_create` | GetUploadQuotaResponseDailyCreate |  | Суточный лимит на создание товаров. |
| `daily_update` | GetUploadQuotaResponseDailyUpdate |  | Суточный лимит на обновление товаров. |
| `total` | GetUploadQuotaResponseTotal |  | Лимит на ассортимент. |

[Response 200](../_shared/examples/POST__v4_product_info_limit_200.json)

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
