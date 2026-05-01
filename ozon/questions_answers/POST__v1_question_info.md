# `POST` /v1/question/info

**Tag:** [Questions&Answers](index.md)

**operationId:** `Question_Info`

**Информация о вопросе**

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

[Request example](examples/POST__v1_question_info_req.json)

## Responses

### `200` Информация о вопросе


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `answers_count` | integer |  | Количество ответов на вопрос. |
| `author_name` | string |  | Автор вопроса. |
| `id` | string |  | Идентификатор вопроса. |
| `product_url` | string |  | Ссылка на товар. |
| `published_at` | timestamp |  | Дата публикации вопроса. |
| `question_link` | string |  | Ссылка на вопрос. |
| `sku` | integer |  | Идентификатор товара в системе Ozon — SKU. |
| `status` | enum |  | Статус вопроса:   - `NEW` — новый,   - `ALL` — все вопросы,   - `VIEWED` — просмотренный,   - `PROCESSED` — обработанный,   - `UNPROCESSED` — необработанный.  |
| `text` | string |  | Текст вопроса. |

[Response 200](../_shared/examples/POST__v1_question_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | string |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_question_answer_create_default.json)
