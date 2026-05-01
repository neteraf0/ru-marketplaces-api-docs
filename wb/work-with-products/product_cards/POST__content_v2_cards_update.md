# `POST` /content/v2/cards/update

**Tag:** [Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Update Product Cards**

Описание метода

Edits product cards. Also use it to add new sizes.


  The product card is overwritten when updated. So the request must also include those card parameters that you are not going to update. To get their values, use Product Cards List and Product Cards in Trash List.


You cannot use this method to update or delete:
  - product size barcodes. You can only add additional barcodes
  - the `photos`, `video` and `tags` parameters
  - prices of goods. The price can only be set if you add new sizes

When adding a new size, specify its price using the `price` parameter. If no `price` is specified in the request, the size price will be `0`. In this case, you can update it using the methods:
  - [Set Prices and Discounts](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1upload~1task/post), if [product](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1list~1goods~1filter/get) has `"editablePriceSize":false`
  - [Set Size Prices](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1upload~1task~1size/post), if [product](./work-with-products#tag/Prices-and-Discounts/paths/~1api~1v2~1list~1goods~1filter/get) has `"editablePriceSize":true`

The dimensions of the products can only be specified in `centimeters`, and the weight of packed products must be specified in `kilograms`.

If this method response is Success (`200`) but product card was not updated, check errors using [list of failed product cards with errors](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1cards~1error~1list/post).
With one request you can edit maximum 3000 product cards (`nmID`). Maximum request size is 10 Mb.
The process of synchronizing data with services may take up to 30 minutes. During this time, you can't add inventory to warehouses and set prices.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 10 requests | 6 s | 5 requests |


## Request Body

Content-Type: `application/json`

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `nmID` | integer | ✓ | WB article |
  | `vendorCode` | string | ✓ | Seller's article |
  | `kizMarked` | boolean |  | Confirmation that required labeling code [Chestny ZNAK](https://chestnyznak.ru/en) is specified:   - `true` — the seller confirms that required labeling code is applied to the product.   - `false` — the seller does not confirm that required labeling code is applied to the product. Pass `true` in the request to confirm that the product has required labeling code. The item will not pass moderation if there is no confirmation from the seller that required labeling code is applied to the product.  To check if labeling code [Chestny ZNAK](https://chestnyznak.ru/en) is required, use the [Product Cards List](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1get~1cards~1list/post) method, the response field `needKiz`  |
  | `brand` | string |  | Brand |
  | `title` | string |  | Product title |
  | `description` | string |  | Product description The maximum number of characters depends on the product category Standard — 2000, minimum — 1000, maximum — 5000 More details about description rules in **Product card filling rules** in [Instructions](https://seller.wildberries.ru/help-center/article/A-113) category of sellers portal  |
  | `dimensions` | object |  | Dimensions and weight of the product `with packaging`.  Specify in `centimeters` and `kilograms` for any product.  The process of synchronizing new data with service may take up to 30 minutes  |
  | `characteristics` | array |  | Product characteristics  Use the [Subject characteristics](./work-with-products#tag/Categories-Subjects-and-Characteristics/paths/~1content~1v2~1object~1charcs~1%7BsubjectId%7D/get) method to get characteristics of the product  |
  | `sizes` | array | ✓ | Product sizes If product has no sizes, send only SKUs  |
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

[Response 400: MissingRequiredCharacteristics](../_shared/examples/POST__content_v2_cards_update_400_MissingRequiredCharacteristics.json)


[Response 400: NonUniqueCharacteristicsInOneGroupAdd](../_shared/examples/POST__content_v2_cards_update_400_NonUniqueCharacteristicsInOneGroupAdd.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 403](../_shared/examples/GET__content_v2_object_parent_all_403.json)

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
