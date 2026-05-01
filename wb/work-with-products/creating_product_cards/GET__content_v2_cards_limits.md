# `GET` /content/v2/cards/limits

**Tag:** [Creating Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Limits for the Product Cards**

Описание метода

The method allows to get separately free and paid vendor limits for creating product cards.
To calculate the number of cards that can be created, use the formula: (freeLimits + paidLimits) - Number of cards created.
All cards that can be obtained using the [product cards list](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1get~1cards~1list/post) and [list of product cards that are in the trash](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1get~1cards~1trash/post) methods are considered created.


Request limit per one seller's account for all methods in the Content category:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 100 requests | 600 ms | 5 requests |

Exceptions are the methods:

    creating product cards
    creating product cards with merge
    editing product cards
    getting failed product cards with errors
    transfering product card to trash
    recovering product card from trash


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | string |  | Additional errors |

[Response 200](../_shared/examples/GET__content_v2_cards_limits_200.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 403](../_shared/examples/GET__content_v2_object_parent_all_403.json)

- **429** Too Many Requests
