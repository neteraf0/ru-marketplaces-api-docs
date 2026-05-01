# `POST` /content/v2/cards/upload/add

**Tag:** [Creating Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Create Product Cards with Merge**

Описание метода

The method creates product cards by merging it with existing individual cards and groups of merged cards. There can be no more than 30 cards in one group of merged product cards, respectively, you can create no more than 29 product cards in one request.

The dimensions of the products can only be specified in `centimeters`, and the weight of packed products must be specified in `kilograms`.
If this method response is Success (`200`) but product card was not updated, check errors using [list of failed nomenclature with errors](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1cards~1error~1list/post).
Product cards are created asynchronously. The process of synchronizing a new card with services may take up to 30 minutes. During this time, you can't add inventory to warehouses and set prices.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 10 requests | 6 s | 5 requests |
| Service | 1 min | 10 requests | 6 s | 5 requests |
| Base | 2 h | 1 request | 2 h | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `imtID` | integer |  | `imtID` of an individual product card or group of merged product cards to which the created cards are added  |
| `cardsToAdd` | array |  | Added product cards |

[Request example](examples/POST__content_v2_cards_upload_add_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Response data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` |  |  | Any additional errors |

[Response 200](../_shared/examples/POST__content_v2_cards_update_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | object |  | Additional errors |

[Response 400: InvalidRequestFormatContent](../_shared/examples/POST__content_v2_cards_upload_400_InvalidRequestFormatContent.json)


[Response 400: CardCreatedWithoutVendorCode](../_shared/examples/POST__content_v2_cards_upload_400_CardCreatedWithoutVendorCode.json)


[Response 400: CardsVendorCodeUsedInOtherCards](../_shared/examples/POST__content_v2_cards_upload_400_CardsVendorCodeUsedInOtherCards.json)


[Response 400: ThisCategoryDoesNotExist](../_shared/examples/POST__content_v2_cards_upload_400_ThisCategoryDoesNotExist.json)


[Response 400: MissingRequiredCharacteristics](../_shared/examples/POST__content_v2_cards_update_400_MissingRequiredCharacteristics.json)


[Response 400: NonUniqueCharacteristicsInOneGroupAdd](../_shared/examples/POST__content_v2_cards_update_400_NonUniqueCharacteristicsInOneGroupAdd.json)

- **401** Unauthorized
- **402** Payment Required
### `413` The request body size exceeds the given limit


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title |
| `detail` | string |  | Error details |
| `code` | string |  | Internal error code |
| `requestId` | string |  | Unique request ID |
| `origin` | string |  | WB internal service ID |
| `status` | number |  | HTTP status code |
| `statusText` | string |  | Text of the HTTP status code |

[Response 413](../_shared/examples/POST__content_v2_cards_update_413.json)

- **429** Too Many Requests
