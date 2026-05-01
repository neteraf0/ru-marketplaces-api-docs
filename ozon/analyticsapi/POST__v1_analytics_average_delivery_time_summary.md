# `POST` /v1/analytics/average-delivery-time/summary

**Tag:** [AnalyticsAPI](index.md)

**operationId:** `AverageDeliveryTimeSummary`

**Получить общую аналитику по среднему времени доставки**

Метод позволяет получить общую аналитику по среднему времени доставки товара до покупателя. Соответствует разделу **Аналитика → Локальность продаж → Среднее время доставки** в личном кабинете.

Детальную аналитику по каждому кластеру можно получить с помощью метода [/v1/analytics/average-delivery-time/details](#operation/AnalyticsAPI_AverageDeliveryTimeDetails).
Чтобы получить аналитику по среднему времени доставки, используйте метод [/v1/analytics/average-delivery-time](#operation/AnalyticsAPI_AverageDeliveryTime).

[Подробнее о среднем времени доставки в Базе знаний продавца](https://seller-edu.ozon.ru/analytics-and-metrics/graphs/srednee-vremya-dostavki)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Общая аналитика


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `average_delivery_time` | integer |  | Среднее время доставки до покупателя. |
| `current_tariff` | AverageDeliveryTimeSummaryResponseTariff |  | Информация о тарифе. |
| `lost_profit` | number |  | Переплата за логистику FBO. |
| `perfect_delivery_time` | integer |  | Рекомендуемое среднее время доставки до покупателя. |
| `updated_at` | string |  | Дата и время последнего обновления данных. |

[Response 200](../_shared/examples/POST__v1_analytics_average_delivery_time_summary_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
