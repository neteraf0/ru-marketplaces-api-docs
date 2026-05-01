# `POST` /v1/question/answer/list

**Tag:** [Questions&Answers](index.md)

**operationId:** `QuestionAnswer_List`

**Список ответов на вопрос**

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
| `last_id` | None |  | Идентификатор последнего значения на странице.   Если запрос первый, оставьте поле пустым. Для следующих значений указывайте `last_id` из ответа предыдущего запроса.  |
| `question_id` | string | ✓ | Идентификатор вопроса. |
| `sku` | integer | ✓ | Идентификатор товара в системе Ozon — SKU. |

[Request example](examples/POST__v1_question_answer_list_req.json)

## Responses

### `200` Список ответов на вопрос


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `answers` |  |  | Ответы. |
| `last_id` | string |  | Идентификатор последнего значения на странице.  Чтобы получить следующие значения, передайте полученное значение в следующем запросе в параметре `last_id`.  |

[Response 200](../_shared/examples/POST__v1_question_answer_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | string |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_question_answer_create_default.json)
