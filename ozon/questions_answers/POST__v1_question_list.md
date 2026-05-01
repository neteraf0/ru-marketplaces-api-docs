# `POST` /v1/question/list

**Tag:** [Questions&Answers](index.md)

**operationId:** `Question_List`

**Список вопросов**

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
| `filter` | v1QuestionListRequestFilter |  | Фильтр. |
| `last_id` | string |  | Идентификатор последнего значения на странице.   Оставьте это поле пустым при выполнении первого запроса. Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
| `limit` | integer |  | Количество значений в ответе. |
| `sort_dir` | question.v1.GetQuestionListRequest.SortDir.Enum |  | Направление сортировки: - `DESC` — по убыванию; - `ASC` — по возрастанию.  |

[Request example](examples/POST__v1_question_list_req.json)

## Responses

### `200` Список вопросов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `questions` |  |  | Вопросы. |
| `last_id` | string |  | Идентификатор последнего значения на странице.  Чтобы получить следующие значения, передайте полученное значение в следующем запросе в параметре `last_id`.  |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все вопросы.  |

[Response 200](../_shared/examples/POST__v1_question_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | string |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_question_answer_create_default.json)
