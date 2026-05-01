# `POST` /api/v2/upload/task

**Tag:** [Prices and Discounts](index.md)

**Server:** `https://discounts-prices-api.wildberries.ru`

**Set Prices and Discounts**

Описание метода

Sets prices and discounts.


Request limit per one seller's account for all methods in the Prices and Discounts category:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 6 s | 10 requests | 600 ms | 5 requests |


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

[Response 400: UploadLimitExceeded](../_shared/examples/POST__api_v2_upload_task_400_UploadLimitExceeded.json)


[Response 400: DuplicateItemNos](../_shared/examples/POST__api_v2_upload_task_400_DuplicateItemNos.json)


[Response 400: TheSpecifiedPricesAndDiscountsAreAlreadySet](../_shared/examples/POST__api_v2_upload_task_400_TheSpecifiedPricesAndDiscountsAreAlreadySet.json)


[Response 400: InvalidDataFormat](../_shared/examples/POST__api_v2_upload_task_400_InvalidDataFormat.json)


[Response 400: PriceShouldBeAWholeNumber](../_shared/examples/POST__api_v2_upload_task_400_PriceShouldBeAWholeNumber.json)


[Response 400: InvalidPriceValue](../_shared/examples/POST__api_v2_upload_task_400_InvalidPriceValue.json)


[Response 400: InvalidDiscountValue](../_shared/examples/POST__api_v2_upload_task_400_InvalidDiscountValue.json)


[Response 400: InvalidItemNo](../_shared/examples/POST__api_v2_upload_task_400_InvalidItemNo.json)


[Response 400: PriceAndDiscountNotSpecified](../_shared/examples/POST__api_v2_upload_task_400_PriceAndDiscountNotSpecified.json)


[Response 400: EmptyData](../_shared/examples/POST__api_v2_upload_task_400_EmptyData.json)


[Response 400: AllItemNosAreSpecifiedIncorrectlyOrPricesAndDiscounts](../_shared/examples/POST__api_v2_upload_task_400_AllItemNosAreSpecifiedIncorrectlyOrPricesAndDiscoun.json)

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
