# `POST` /v1/question/count

**Tag:** [Questions&Answers](index.md)

**operationId:** `Question_Count`

**Количество вопросов по статусам**

Доступно для продавцов с подпиской [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus).

Вы можете оставить обратную связь по этому методу в комментариях к обсуждению в [сообществе разработчиков Ozon for dev](https://dev.ozon.ru/community/1198-Metody-dlia-raboty-s-voprosami-otvetami).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Количество вопросов по статусам


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `all` | integer |  | Всего вопросов. |
| `new` | integer |  | Новые вопросы. |
| `processed` | integer |  | Обработанные вопросы. |
| `unprocessed` | integer |  | Необработанные вопросы. |
| `viewed` | integer |  | Просмотренные вопросы. |

[Response 200](../_shared/examples/POST__v1_question_count_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | string |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_question_answer_create_default.json)
