# `POST` /content/v2/cards/moveNm

**Tag:** [Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Merging or Separating of Product Cards**

Описание метода

The method merges and separates product cards. Product cards are merged if they have the same `imtID`.

To merge product cards, make a request **specifying** the `imtID`. You can merge up to 30 product cards at a time.

To separate product cards, make a request **without specifying** the `imtID`. New `imtID`s will be generated for the separated cards.

If you separate multiple product cards simultaneously, these cards will merge into one and receive a new `imtID`.

To assign a unique `imtID` to each product card, you need to send one product card per request.

The maximum request size is 10 MB.


  It is possible to merge product cards containing only the same subjects


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


## Request Body

Content-Type: `application/json`


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


[Response 400: responseExceededLimit](../_shared/examples/POST__content_v2_cards_moveNm_400_responseExceededLimit.json)


[Response 400: responseCombining](../_shared/examples/POST__content_v2_cards_moveNm_400_responseCombining.json)


[Response 400: responseIncorrectRequestFormat](../_shared/examples/POST__content_v2_cards_moveNm_400_responseIncorrectRequestFormat.json)


[Response 400: responseNonExistentNmId](../_shared/examples/POST__content_v2_cards_moveNm_400_responseNonExistentNmId.json)


[Response 400: responseNonExistentImt](../_shared/examples/POST__content_v2_cards_moveNm_400_responseNonExistentImt.json)


[Response 400: responseCardCreate1](../_shared/examples/POST__content_v2_cards_moveNm_400_responseCardCreate1.json)


[Response 400: responseDuplicateRequests](../_shared/examples/POST__content_v2_cards_moveNm_400_responseDuplicateRequests.json)


[Response 400: responseAllCardsInSameGroup](../_shared/examples/POST__content_v2_cards_moveNm_400_responseAllCardsInSameGroup.json)


[Response 400: responseIncorrectBeginDate](../_shared/examples/POST__content_v2_cards_moveNm_400_responseIncorrectBeginDate.json)


[Response 400: responseIncorrectEndDate](../_shared/examples/POST__content_v2_cards_moveNm_400_responseIncorrectEndDate.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Response data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` |  |  | Any additional errors |

[Response 403](../_shared/examples/POST__content_v2_cards_moveNm_403.json)

### `413` The request body size exceeds the given limit

`string`

[Response 413: BodySizeExceedsTheGivenLimit](../_shared/examples/POST__content_v2_cards_moveNm_413_BodySizeExceedsTheGivenLimit.json)

- **429** Too Many Requests
