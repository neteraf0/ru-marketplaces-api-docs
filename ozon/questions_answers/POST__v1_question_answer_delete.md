# `POST` /v1/question/answer/delete

**Tag:** [Questions&Answers](index.md)

**operationId:** `QuestionAnswer_Delete`

**Удалить ответ на вопрос**

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
| `answer_id` | string | ✓ | Идентификатор ответа. |
| `sku` | integer | ✓ | Идентификатор товара в системе Ozon — SKU. |

[Request example](examples/POST__v1_question_answer_delete_req.json)

## Responses

- **200** Ответ удалён
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | string |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_question_answer_create_default.json)
