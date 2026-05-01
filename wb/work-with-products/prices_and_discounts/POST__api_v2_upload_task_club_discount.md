# `POST` /api/v2/upload/task/club-discount

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Set WB Club Discounts**

Описание метода

Sets WB Club subscription discounts.


Request limit per one seller's account for all methods in the Prices and Discounts category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 6 s | 10 requests | 600 ms | 5 requests |
| Service | 6 s | 10 requests | 600 ms | 5 requests |
| Base | 1 h | 4 requests | 15 min | 1 request |


## Request Body

## Responses

- **200** OK
- **208**
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 400: CheckTheWBClubDiscount](../_shared/examples/POST__api_v2_upload_task_club_discount_400_CheckTheWBClubDiscount.json)


[Response 400: DiscountsAreTheSameAsThoseAlreadySet](../_shared/examples/POST__api_v2_upload_task_club_discount_400_DiscountsAreTheSameAsThoseAlreadySet.json)


[Response 400: AllItemNosAreSpecifiedIncorrectlyOrDiscounts](../_shared/examples/POST__api_v2_upload_task_club_discount_400_AllItemNosAreSpecifiedIncorrectlyOrDi.json)


[Response 400: InvalidDiscountValue](../_shared/examples/POST__api_v2_upload_task_400_InvalidDiscountValue.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 403: AccessDenied](../_shared/examples/POST__api_v2_upload_task_403_AccessDenied.json)

### `409` Error while switching currency


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 409: CurrencySwitchingError](../_shared/examples/POST__api_v2_upload_task_409_CurrencySwitchingError.json)

### `422` Unexpected result


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 422: UnexpectedResult](../_shared/examples/POST__api_v2_upload_task_422_UnexpectedResult.json)

- **429** Too Many Requests
