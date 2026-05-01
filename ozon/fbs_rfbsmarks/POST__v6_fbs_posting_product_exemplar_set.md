# `POST` /v6/fbs/posting/product/exemplar/set

**Tag:** [FBS&rFBSMarks](index.md)

**operationId:** `PostingAPI_FbsPostingProductExemplarSetV6`

**Проверить и сохранить данные экземпляров**

Асинхронный метод:
- для проверки наличия экземпляров в обороте в системе «Честный ЗНАК»;
- для сохранения данных экземпляров.

Чтобы получить результаты проверок, используйте метод [/v5/fbs/posting/product/exemplar/status](#operation/PostingAPI_FbsPostingProductExemplarStatusV5).
Для получения данных о созданных экземплярах, используйте метод [/v6/fbs/posting/product/exemplar/create-or-get](#operation/PostingAPI_FbsPostingProductExemplarCreateOrGetV6).

Если у вас несколько одинаковых товаров в отправлении, укажите один `product_id` и массив `exemplars` для каждого товара из отправления.

Всегда передавайте полный набор данных по экземплярам и продуктам.

Например, в вашей системе 10 экземпляров.
Вы передали их для проверки и сохранения.
Потом добавили в своей системе ещё 60 экземпляров.
При повторной передаче экземпляров для проверки и сохранения укажите все экземпляры: и старые, и только что добавленные.

Код ответа 200 не гарантирует, что данные об экземплярах приняты.
Он указывает, что создана задача для добавления информации.
Чтобы проверить статус задачи, используйте метод [/v5/fbs/posting/product/exemplar/status](#operation/PostingAPI_FbsPostingProductExemplarStatusV5).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `multi_box_qty` | integer |  | Количество коробок, в которые упакован товар. |
| `posting_number` | string | ✓ | Номер отправления. |
| `products` | array | ✓ | Список товаров. |
## Responses

- **200** Запрос обработан
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
