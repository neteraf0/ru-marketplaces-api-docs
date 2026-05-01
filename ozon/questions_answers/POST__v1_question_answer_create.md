# `POST` /v1/question/answer/create

**Tag:** [Questions&Answers](index.md)

**operationId:** `QuestionAnswer_Create`

**Создать ответ на вопрос**

Доступно для продавцов с подпиской [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus).

Вы можете оставить обратную связь по этому методу в комментариях к обсуждению в [сообществе разработчиков Ozon for dev](https://dev.ozon.ru/community/1198-Metody-dlia-raboty-s-voprosami-otvetami).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `question_id` | string | ✓ | Идентификатор вопроса. |
| `sku` | integer | ✓ | Идентификатор товара в системе Ozon — SKU. |
| `text` | string | ✓ | Текст ответа объёмом от 2 до 3000 символов. |

[Request example](examples/POST__v1_question_answer_create_req.json)

## Responses

### `200` Идентификатор ответа на вопрос


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `answer_id` | string |  | Идентификатор ответа на вопрос. |

[Response 200](../_shared/examples/POST__v1_question_answer_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | string |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_question_answer_create_default.json)
