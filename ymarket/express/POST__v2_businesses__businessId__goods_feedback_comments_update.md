# `POST` /v2/businesses/{businessId}/goods-feedback/comments/update

**Tag:** [express](index.md)

**operationId:** `updateGoodsFeedbackComment`

**Добавление нового или изменение созданного комментария**

{% include notitle [access](../../_auto/method_scopes/updateGoodsFeedbackComment.md) %}

Добавляет новый комментарий магазина или изменяет комментарий, который магазин оставлял ранее.

Для создания комментария к отзыву передайте только идентификатор отзыва `feedbackId`.

Чтобы добавить комментарий к другому комментарию, передайте:

* `feedbackId` — идентификатор отзыва;
* `comment.parentId` — идентификатор родительского комментария.

Чтобы изменить комментарий, передайте:

* `feedbackId`— идентификатор отзыва;
* `comment.id` — идентификатор комментария, который нужно изменить.

Если передать одновременно `comment.parentId` и `comment.id`, будет изменен существующий комментарий.

{% include notitle [limit](../../_auto/method_limits/updateGoodsFeedbackComment.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `feedbackId` | integer | ✓ | Идентификатор отзыва.  |
| `comment` | object | ✓ | Комментарий к отзыву или другому комментарию. |
## Responses

### `200` Информация о добавленном или измененном комментарии.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_businesses__businessId__goods_feedback_comments_update_200.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибках при работе с отзывами о товарах](../../concepts/error-codes#feedback)


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
