# `POST` /v1/product/pictures/import

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_ProductImportPictures`

**Загрузить или обновить изображения товара**

Метод для загрузки или обновления изображений товара.

При каждом вызове метода передавайте все изображения, которые должны быть на карточке товара. Например, если вы вызвали метод и загрузили 10 изображений, а затем вызвали метод второй раз и загрузили ещё одно,
то все 10 предыдущих сотрутся.

Для загрузки передайте адрес ссылки на изображение в общедоступном облачном хранилище.
Формат изображения по ссылке — JPG или PNG.

Изображения в массиве `images` располагайте в соответствии с желаемым порядком на сайте. Главным будет
первое изображение в массиве.

Для каждого товара вы можете загрузить до 30 изображений.

Для загрузки изображений 360 используйте поле `images360`, для загрузки маркетингового цвета — `color_image`.

Если вы хотите изменить состав или порядок изображений, получите информацию с помощью метода
[/v3/product/info/list](#operation/ProductAPI_GetProductInfoList) — в нём отображается текущий порядок и
состав изображений. Скопируйте данные полей `images`, `images360`, `color_image`, измените и дополните состав или
порядок в соответствии с необходимостью.

У метода есть лимит на количество операций c товарами в минуту. Если вы превысите лимит, вернётся ошибка `429` с описанием в поле `message` и заголовками:
- `Item-Retry-After` — время в минутах до обновления лимита. Для суточного лимита — время до 03:00 по московскому времени.
- `Item-Rate-Limit-Remaining` — остаток операций до следующего сброса лимита.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `color_image` | string |  | Маркетинговый цвет. |
| `images` |  |  | Массив ссылок на изображения. До 30 штук. Изображения в массиве расположены в порядке их расположения на сайте.  Первое изображение в массиве будет главным.  |
| `images360` |  |  | Массив изображений 360. До 70 штук.  Формат: адрес ссылки на изображение в общедоступном облачном хранилище. Формат изображения по ссылке — JPG.  |
| `product_id` | integer | ✓ | Идентификатор товара в системе Ozon — `product_id`. |

[Request example](examples/POST__v1_product_pictures_import_req.json)

## Responses

### `200` Предварительный результат работы метода


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | productv1ProductInfoPicturesResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_product_pictures_import_200.json)

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
