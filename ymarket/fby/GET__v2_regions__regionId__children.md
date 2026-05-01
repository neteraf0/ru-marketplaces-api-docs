# `GET` /v2/regions/{regionId}/children

**Tag:** [fby](index.md)

**operationId:** `searchRegionChildren`

**Информация о дочерних регионах**

{% include notitle [access](../../_auto/method_scopes/searchRegionChildren.md) %}

Возвращает информацию о регионах, являющихся дочерними по отношению к региону, идентификатор которого указан в запросе.

{% include notitle [limit](../../_auto/method_limits/searchRegionChildren.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `regionId` | path | integer | ✓ | Идентификатор региона.  Идентификатор региона можно получить c помощью запроса [GET v2/regions](../../reference/regions/searchRegionsByName.md).  |
| `pageToken` | query | string |  | Идентификатор страницы c результатами.  Если параметр не указан, возвращается первая страница.  Передавайте значение выходного параметра `nextPageToken`, полученное при последнем запросе.  |
| `limit` | query | integer |  |   {% note warning %}  У данного лимита нет значения по умолчанию.  {% endnote %}  |
| `page` | query | integer |  | {% note warning "Устаревший параметр" %}  Вместо `page` и `pageSize` используйте пагинацию по `pageToken` и `limit`.  [Подробнее о типах пагинации и их использовании](../../concepts/pagination.md)  {% endnote %}  Номер страницы результатов.  Используется вместе с параметром `pageSize`.  |
| `pageSize` | query | integer |  | {% note warning "Устаревший параметр" %}  Вместо `page` и `pageSize` используйте пагинацию по `pageToken` и `limit`.  [Подробнее о типах пагинации и их использовании](../../concepts/pagination.md)  {% endnote %}  Размер страницы.  Используется вместе с параметром `page`.  |

## Responses

### `200` Регионы, являющиеся дочерними к указанному в запросе.


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `pager` | object |  | Модель для пагинации. |
| `paging` | object |  | Идентификатор следующей страницы.  |
| `regions` | object |  | Информация о родительском и дочерних регионах. |

[Response 200](../_shared/examples/GET__v2_regions__regionId__children_200.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибке](../../concepts/error-codes.md#400)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 400](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

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
