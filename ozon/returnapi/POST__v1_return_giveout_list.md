# `POST` /v1/return/giveout/list

**Tag:** [ReturnAPI](index.md)

**operationId:** `ReturnAPI_GiveoutList`

**Список возвратных отгрузок**

Метод для получения списка активных возвратов.
Возвратная отгрузка становится активной после сканирования штрихкода.
После сканирования штрихкода второй раз активная выдача переходит в статус неактивной.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `last_id` | integer |  | Идентификатор последнего значения на странице. |
| `limit` | integer | ✓ | Количество элементов в ответе. |

[Request example](examples/POST__v1_return_giveout_list_req.json)

## Responses

### `200` Список возвратных отгрузок


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `giveouts` | array |  | Идентификатор отгрузки. |

[Response 200](../_shared/examples/POST__v1_return_giveout_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
