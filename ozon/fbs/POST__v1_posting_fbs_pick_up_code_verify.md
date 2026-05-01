# `POST` /v1/posting/fbs/pick-up-code/verify

**Tag:** [FBS](index.md)

**operationId:** `PostingAPI_PostingFBSPickupCodeVerify`

**Проверить код курьера**

Метод позволяет проверить код курьера при передаче отправлений realFBS Express. Подробнее о передаче отправлений в [Базе знаний продавца](https://seller-edu.ozon.ru/contract-for-sellers/regulations-fbs-realfbs/reglament-prodaji-so-svoego-sklada-fbs-express#7-порядок-передачи-отправлении-через-партнёров-ozon-при-экспресс-доставке).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `pickup_code` | string | ✓ | Код курьера. |
| `posting_number` | string | ✓ | Номер отправления. |

[Request example](examples/POST__v1_posting_fbs_pick_up_code_verify_req.json)

## Responses

### `200` Результат проверки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `valid` | boolean |  | `true`, если код корректный.  |

[Response 200](../_shared/examples/POST__v1_posting_fbs_pick_up_code_verify_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
