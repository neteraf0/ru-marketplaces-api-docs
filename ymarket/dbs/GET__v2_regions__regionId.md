# `GET` /v2/regions/{regionId}

**Tag:** [dbs](index.md)

**operationId:** `searchRegionsById`

**Информация о регионе**

{% include notitle [access](../../_auto/method_scopes/searchRegionsById.md) %}

Возвращает информацию о регионе.

{% include notitle [limit](../../_auto/method_limits/searchRegionsById.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `regionId` | path | integer | ✓ | Идентификатор региона.  Идентификатор региона можно получить c помощью запроса [GET v2/regions](../../reference/regions/searchRegionsByName.md).  |

## Responses

### `200` Найденный регион.


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `regions` | array |  | Регион доставки.  {% note warning %}  В массиве всегда возвращается один регион, используйте поле `region` вместо него.  {% endnote %}  |
| `region` | object | ✓ | Регион доставки. |

[Response 200](../_shared/examples/GET__v2_regions__regionId_200.json)

### `401` В запросе не указаны данные для авторизации. [Подробнее об ошибке](../../concepts/error-codes.md#401)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 401](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `403` Данные для авторизации неверны или доступ к ресурсу запрещен. [Подробнее об ошибке](../../concepts/error-codes.md#403)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 403](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `404` Запрашиваемый ресурс не найден. [Подробнее об ошибке](../../concepts/error-codes.md#404)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 404](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `420` Превышено ограничение на доступ к ресурсу. [Подробнее об ошибке](../../concepts/error-codes.md#420)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 420](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
