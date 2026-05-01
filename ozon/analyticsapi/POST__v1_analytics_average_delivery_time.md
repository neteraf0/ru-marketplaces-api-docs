# `POST` /v1/analytics/average-delivery-time

**Tag:** [AnalyticsAPI](index.md)

**operationId:** `AnalyticsAPI_AverageDeliveryTime`

**Получить аналитику по среднему времени доставки**

Метод позволяет получить аналитику по среднему времени доставки товара до покупателя. Соответствует разделу **Аналитика → Локальность продаж → Среднее время доставки** в личном кабинете. Детальную аналитику по каждому кластеру можно получить с помощью метода [/v1/analytics/average-delivery-time/details](#operation/AnalyticsAPI_AverageDeliveryTimeDetails).

[Подробнее о среднем времени доставки в Базе знаний продавца](https://seller-edu.ozon.ru/analytics-and-metrics/graphs/srednee-vremya-dostavki)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `delivery_schema` | v1AverageDeliveryTimeRequestDeliverySchema | ✓ | Схема доставки: - `ALL` — все; - `FBO` — доставка со склада Ozon; - `FBS` — доставка со своего склада; - `UNKNOWN` — неизвестное значение.  |
| `sku` | array |  | Идентификатор товара в системе Ozon — SKU. |
| `supply_period` | v1AverageDeliveryTimeRequestSupplyPeriod | ✓ | Период поставки в неделях: - `ONE_WEEK` — 1; - `TWO_WEEKS` — 2; - `FOUR_WEEKS` — 4; - `EIGHT_WEEKS` — 8.  |

[Request example](examples/POST__v1_analytics_average_delivery_time_req.json)

## Responses

### `200` Аналитика по среднему времени доставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | array |  | Информация о кластере. |
| `total` | AverageDeliveryTimeResponseTotal |  | Общие данные. |

[Response 200](../_shared/examples/POST__v1_analytics_average_delivery_time_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
