# `POST` /v1/businesses/{businessId}/goods-questions/update

**Tag:** [goods-questions](index.md)

**operationId:** `updateGoodsQuestionTextEntity`

**Создание, изменение и удаление ответа или комментария**

{% include notitle [access](../../_auto/method_scopes/updateGoodsQuestionTextEntity.md) %}

Создание, изменение и удаление ответа или комментария.

{% include notitle [limit](../../_auto/method_limits/updateGoodsQuestionTextEntity.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `entityId` | object |  | Идентификатор вопроса, ответа или комментария.  |
| `parentEntityId` | object |  | Идентификатор вопроса, ответа или комментария.  |
| `text` | string |  | Текстовое содержимое.  |
| `operationType` | string (enum: UPDATE, CREATE, DELETE) | ✓ | Операция над ответом или комментарием. * `UPDATE` — обновление. * `CREATE` — создание. * `DELETE` — удаление.  |
## Responses

### `200` Информация о созданном ответе или комментарии.

Возвращается только при операции создания (`operationType` = `CREATE`). При обновлении и удалении возвращается пустой ответ.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_businesses__businessId__goods_questions_update_200.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибке](../../concepts/error-codes.md#questions)


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
