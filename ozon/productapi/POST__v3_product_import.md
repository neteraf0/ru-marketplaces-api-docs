# `POST` /v3/product/import

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_ImportProductsV3`

**Создать или обновить товар**

Метод для создания товаров и обновления информации о них.

В сутки можно создать или обновить определённое количество товаров. Чтобы узнать лимит, используйте
[/v4/product/info/limit](#operation/ProductAPI_GetUploadQuota). Если количество загрузок и обновлений товаров
превысит лимит, появится ошибка `item_limit_exceeded`.

У метода есть лимит на количество операций c товарами в минуту. Если вы превысите лимит, вернётся ошибка `429` с описанием в поле `message` и заголовками:
- `Item-Retry-After` — время в минутах до обновления лимита. Для суточного лимита — время до 03:00 по московскому времени.
- `Item-Rate-Limit-Remaining` — остаток операций до следующего сброса лимита.

В одном запросе можно передать до 100 товаров. Каждый товар — это отдельный элемент в массиве `items`. Укажите
всю информацию о товаре: его характеристики, штрихкод, изображения, габариты, цену и валюту цены.

При обновлении товара передайте в запросе всю информацию о нём.

Указанная валюта должна совпадать с той, которая установлена в настройках личного кабинета. По умолчанию передаётся `RUB` — российский рубль.
Например, если у вас установлена валюта юань, передавайте значение `CNY`, иначе вернётся ошибка.

Товар не будет создан или обновлён, если вы заполните неправильно или не укажете:
   - **Обязательные характеристики**: характеристики отличаются для разных категорий — их можно посмотреть в [Базе знаний продавца](https://docs.ozon.ru/global/products/requirements/product-info/product-characteristics/#обязательные-характеристики) или получить методом [/v1/description-category/attribute](#operation/DescriptionCategoryAPI_GetAttributes).
   - **Реальные объёмно-весовые характеристики**: `depth`, `width`, `height`, `dimension_unit`, `weight`, `weight_unit`. Не пропускайте эти параметры в запросе и не указывайте 0.

Для некоторых характеристик можно использовать HTML-теги.

После модерации товар появится в вашем личном кабинете, но не будет виден пользователям, пока вы не выставите его
на продажу.

Каждый товар в запросе — отдельный элемент массива `items`.

Чтобы объединить две карточки, для каждой передайте `9048` в массиве `attributes`. Все атрибуты в этих карточках, кроме размера или цвета, должны совпадать.

## Загрузка изображений

Для загрузки передайте в запросе ссылки на изображения в общедоступном облачном хранилище.
Формат изображения по ссылке — JPG или PNG.

Изображения в массиве `images` располагайте в соответствии с желаемым порядком на сайте. Для загрузки главного
изображения товара используйте параметр `primary_image`. Если не передать значение `primary_image`, главным будет
первое изображение в массиве `images`.

Чтобы загрузить главное изображение для Ozon Селект:
1. Проверьте, что в ответе метода [/v1/description-category/attribute](#operation/DescriptionCategoryAPI_GetAttributes) возвращается характеристика с `result.id = 23500`.
2. Передайте ссылку на изображение в параметре `items.attributes.values.value` с `id = 23500`.

Для каждого товара вы можете загрузить до 30 изображений, включая главное.
Если передать значение `primary_image`, максимальное количество изображений в `images` — 29.
Если параметр `primary_image` пустой, то в `images` можно передать до 30 изображений.

Для загрузки изображений 360 используйте поле `images360`, для загрузки маркетингового цвета — `color_image`.

Если вы хотите изменить состав или порядок изображений, получите информацию с помощью метода
[/v3/product/info/list](#operation/ProductAPI_GetProductInfoList) — в нём отображается текущий порядок и
состав изображений. Скопируйте данные полей `images`, `images360`, `color_image`, измените и дополните состав или
порядок в соответствии с необходимостью.

## Загрузка видео

Для загрузки передайте в запросе ссылки на видео.

Для этого в параметре `complex_attributes` передайте объект. В нём в массиве `attributes` передайте 2 объекта с `complex_id = 100001`:

- В первом укажите `id = 21841` и в массиве `values` передайте объект с ссылкой на видео.

  __Пример__:

  ```
  {
    "complex_id": 100001,
    "id": 21841,
    "values": [
      {
        "value": "https://www.youtube.com/watch?v=ZwM0iBn03dY"
      }
    ]
  }
  ```

- Во втором укажите значение `id = 21837` и в массиве `values` передайте объект с названием видео.

  __Пример__:

  ```
  {
    "complex_id": 100001,
    "id": 21837,
    "values": [
      {
        "value": "videoName_1"
      }
    ]
  }
  ```

Если вы хотите загрузить несколько видео, передавайте значения для каждого видео в разных объектах массива `values`.

  __Пример__:

  ```
  {
    "complex_id": 100001,
    "id": 21837,
    "values": [
      {
        "value": "videoName_1"
      },
      {
        "value": "videoName_2"
      }
    ]
  },
  {
    "complex_id": 100001,
    "id": 21841,
    "values": [
      {
        "value": "https://www.youtube.com/watch?v=ZwM0iBn03dY"
      },
      {
        "value": "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
      }
    ]
  }
```

## Загрузка таблицы размеров
Вы можете добавить в карточку товара таблицу размеров, созданную с помощью [конструктора](https://table-constructor.ozon.ru/visual-editor). Передайте её в массиве `attributes` в формате JSON как Rich-контент `id = 13164`.
[Конструктор в формате JSON](https://table-constructor.ozon.ru/schema.json)
[Подробнее о конструкторе в Базе знаний продавца](https://docs.ozon.ru/global/products/requirements/size-table-constructor/)

## Загрузка видеообложки

Вы можете загрузить видеообложку через `complex_attributes`.

__Пример__:

```
"complex_attributes": [
  {
    "attributes": [
      {
        "id": 21845,
        "complex_id": 100002,
        "values": [
          {
          "dictionary_value_id": 0,
          "value": "https://v.ozone.ru/vod/video-10/01GFATWQVCDE7G5B721421P1231Q7/asset_1.mp4"
          }
        ]
      }
    ]
  }
]
```

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Массив данных. |

[Request: withoutVideo](examples/POST__v3_product_import_req_withoutVideo.json)


[Request: withVideo](examples/POST__v3_product_import_req_withVideo.json)

## Responses

### `200` Создан новый товар / Информация о товаре обновлена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v3ImportProductsResponseResult |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v3_product_import_200.json)

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

### `429` Слишком много запросов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 429](../_shared/examples/POST__v3_product_import_429.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
