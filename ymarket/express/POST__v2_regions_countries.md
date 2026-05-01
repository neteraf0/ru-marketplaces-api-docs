# `POST` /v2/regions/countries

**Tag:** [express](index.md)

**operationId:** `getRegionsCodes`

**Список допустимых кодов стран**

{% include notitle [access](../../_auto/method_scopes/getRegionsCodes.md) %}

Возвращает список стран с их кодами в формате :no-translate[ISO 3166-1 alpha-2].

Страна производства `countryCode` понадобится при продаже товаров из-за рубежа для бизнеса. [Инструкция](../../step-by-step/business-info.md)

{% include notitle [limit](../../_auto/method_limits/getRegionsCodes.md) %}

## Responses

### `200` Список стран с их кодами в формате :no-translate[ISO 3166-1 alpha-2].


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `countries` | array | ✓ | Список стран с их кодами в формате :no-translate[ISO 3166-1 alpha-2]. |

[Response 200](../_shared/examples/POST__v2_regions_countries_200.json)

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
