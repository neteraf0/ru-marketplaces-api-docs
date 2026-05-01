# `PUT` /v2/campaigns/{campaignId}/orders/{orderId}/delivery/shipments/{shipmentId}/boxes

**Tag:** [orders](index.md)

**operationId:** `setOrderShipmentBoxes`

**Передача количества грузовых мест в заказе**

{% include notitle [access](../../_auto/method_scopes/setOrderShipmentBoxes.md) %}

Отгружаемый Маркету заказ может не влезть в одну коробку или упаковку — в этом случае получается, что он занимает несколько грузовых мест.

Количество грузовых мест нужно обязательно передавать Маркету, если оно не равно 1. Это делается перед переводом его в статус **Готов к отгрузке**. Подробно о том, что в какой момент нужно передавать, рассказано в [пошаговой инструкции](../../step-by-step/fbs.md).

Метод устроен немного нестандартно: количество задается длиной массива пустых объектов.

Раньше метод требовал передачи большего количества данных. Запросы, оформленные по старому образцу, работают, но лучше делать по-новому.

{% cut "Как было раньше" %}

Структура тела PUT-запроса:

```text translate=no
{
  "boxes":
  [
    {
      "fulfilmentId": "{string}",
      "weight": {int64},
      "width": {int64},
      "height": {int64},
      "depth": {int64},
      "items":
      [
        {
          "id": {int64},
          "count": {int32}
        },
        ...
      ]
    },
    ...
  ]
}
```
| **Параметр**  | **Тип**  | **Значение**  |
| ----------- | ----------- | ----------- |
| `boxes`       |           | Список грузовых мест.       |

**Параметры, вложенные в `boxes`**
| **Параметр**  | **Тип**  | **Значение**  |
| ----------- | ----------- | ----------- |
| `fulfilmentId`       |  :no-translate[String]   | Идентификатор грузового места в системе магазина. Сформируйте идентификатор по шаблону: `номер заказа на Маркете-номер грузового места`. Например, `7206821‑1, 7206821‑2` и т. д. |
| `weight`       | :no-translate[Int64]        | Масса брутто грузового места (суммарная масса упаковки и содержимого) в граммах. |
| `width`       | :no-translate[Int64]   | Ширина грузового места в сантиметрах.       |
| `height`       | :no-translate[Int64]   | Высота грузового места в сантиметрах.       |
| `depth`       | :no-translate[Int64]   | Глубина грузового места в сантиметрах.        |
| `items`       | :no-translate[Int64]   | Список товаров в грузовом месте.       |

**Параметры, вложенные в `items`**
| **Параметр**  | **Тип**  | **Значение**  |
| ----------- | ----------- | ----------- |
| `id`       | :no-translate[Int64]     | Идентификатор товара в рамках заказа.   |
| `count`    | :no-translate[Int32]     | Количество единиц товара в грузовом месте.       |

{% endcut %}

{% include notitle [limit](../../_auto/method_limits/setOrderShipmentBoxes.md) %}

> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `orderId` | path | integer | ✓ | Идентификатор заказа. |
| `shipmentId` | path | integer | ✓ | { % note warning "Параметр больше не используется" % }  Передайте любое число, чтобы получился корректный URL.  { % endnote % }  Идентификатор грузового места.  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
## Responses

### `200` Имеет значение только тип ответа. Если ответ `ОК`, количество грузомест записано.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/PUT__v2_campaigns__campaignId__orders__orderId__delivery_shipments__shipmentId.json)

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
