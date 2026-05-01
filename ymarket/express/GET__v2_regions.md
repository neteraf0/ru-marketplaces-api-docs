# `GET` /v2/regions

**Tag:** [express](index.md)

**operationId:** `searchRegionsByName`

**Поиск регионов по их имени**

{% include notitle [access](../../_auto/method_scopes/searchRegionsByName.md) %}

Возвращает информацию о регионе, удовлетворяющем заданным в запросе условиям поиска.

Если найдено несколько регионов, удовлетворяющих условиям поиска, возвращается информация по каждому найденному региону (но не более десяти регионов) для возможности определения нужного региона по родительским регионам.

{% include notitle [limit](../../_auto/method_limits/searchRegionsByName.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `name` | query | string | ✓ | Название региона.  Важно учитывать регистр: первая буква должна быть заглавной, остальные — строчными. Например, `Москва`.  |
| `pageToken` | query | string |  | Идентификатор страницы c результатами.  Если параметр не указан, возвращается первая страница.  Передавайте значение выходного параметра `nextPageToken`, полученное при последнем запросе.  |
| `limit` | query | integer |  |   |

## Responses

### `200` Список найденных регионов.


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `regions` | array | ✓ | Регион доставки. |
| `paging` | object |  | Идентификатор следующей страницы.  |

[Response 200](../_shared/examples/GET__v2_regions_200.json)

### `401` В запросе не указаны данные для авторизации. [Подробнее об ошибке](../../concepts/error-codes.md#401)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 401](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `403` Данные для авторизации неверны или доступ к ресурсу запрещен. [Подробнее об ошибке](../../concepts/error-codes.md#403)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 403](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `420` Превышено ограничение на доступ к ресурсу. [Подробнее об ошибке](../../concepts/error-codes.md#420)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 420](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
