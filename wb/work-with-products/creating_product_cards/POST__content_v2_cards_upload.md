# `POST` /content/v2/cards/upload

**Tag:** [Creating Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Create Product Cards**

Описание метода

Creates products cards. You can specify product description and characteristics.

How to create a card:

  1. Get [parent categories list](./work-with-products#tag/Categories-Subjects-and-Characteristics/paths/~1content~1v2~1object~1parent~1all/get)
  2. Get [the category and get all subjects](./work-with-products#tag/Categories-Subjects-and-Characteristics/paths/~1content~1v2~1object~1all/get)
  3. Choose [the subject and get all available characteristics](./work-with-products#tag/Categories-Subjects-and-Characteristics/paths/~1content~1v2~1object~1charcs~1%7BsubjectId%7D/get). For `Color`, `Gender`, `Country of origin`, `Season`, `VAT rate`, `HS-code` characteristics use values from [category](./work-with-products#tag/Categories-Subjects-and-Characteristics).
  4. Send the request. If the response is Success (`200`) but the card was not created, check errors using [list of failed product card with errors](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1cards~1error~1list/post).

The dimensions of the products can only be specified in `centimeters`, and the weight of packed products must be specified in `kilograms`.

With one request you can create maximum 100 individual product cards or 100 groups of merged product cards, 30 product cards (`nmID`) in each. Maximum request size is 10 Mb.

Product cards are created asynchronously. The process of synchronizing a new card with services may take up to 30 minutes. During this time, you can't add inventory to warehouses and set prices.


  If there were errors during queue processing, the product card is considered invalid


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 10 requests | 6 s | 5 requests |


## Request Body

Content-Type: `application/json`

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `subjectID` | integer | ✓ | Subject ID |
  | `variants` | array | ✓ | Merged product cards.To create individual card, pass only one object. |

[Request: creatingOneCard](examples/POST__content_v2_cards_upload_req_creatingOneCard.json)


[Request: creatingMergedCards](examples/POST__content_v2_cards_upload_req_creatingMergedCards.json)


[Request: creatingGroupOfIndividualCards](examples/POST__content_v2_cards_upload_req_creatingGroupOfIndividualCards.json)

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


[Response 400: NonUniqueCharacteristicsInOneGroupCreate](../_shared/examples/POST__content_v2_cards_upload_400_NonUniqueCharacteristicsInOneGroupCreate.json)

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
