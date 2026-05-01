# `POST` /v1/analytics/average-delivery-time/details

**Tag:** [AnalyticsAPI](index.md)

**operationId:** `AnalyticsAPI_AverageDeliveryTimeDetails`

**Получить детальную аналитику по среднему времени доставки**

Метод является аналогом вкладки **Аналитика → Локальность продаж → Среднее время доставки** в личном кабинете продавца.
[Подробнее о среднем времени доставки в Базе знаний продавца](https://seller-edu.ozon.ru/analytics-and-metrics/graphs/srednee-vremya-dostavki).

Чтобы получить общую аналитику по кластерам, используйте метод /v1/analytics/average-delivery-time.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cluster_id` | integer | ✓ | Идентификатор кластера. |
| `filters` | AverageDeliveryTimeDetailsRequestFilters |  | Фильтры. |
| `limit` | integer | ✓ | Количество элементов в ответе.  |
| `offset` | integer | ✓ | Количество элементов, которое будет пропущено в ответе.  Например, если `offset=10`, ответ начнётся с 11-го найденного элемента.  |

[Request example](examples/POST__v1_analytics_average_delivery_time_details_req.json)

## Responses

### `200` Детальная аналитика


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | array |  | Информация о кластере. |
| `total_rows` | integer |  | Всего записей. |

[Response 200](../_shared/examples/POST__v1_analytics_average_delivery_time_details_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
