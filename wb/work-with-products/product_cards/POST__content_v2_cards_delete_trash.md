# `POST` /content/v2/cards/delete/trash

**Tag:** [Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Transfer Product Card to Trash**

Описание метода

Transfers the product card to the trash. In doing so, the product card would not be deleted.


  When transferring product cards to the trash, this product card is removed from the product card, meaning it is assigned a new imtID — merged product cards ID


After 30 days in the trash the product card would be deleted automatically. The trash is cleared every night according to Moscow time.
The product card can be deleted at any time in [personal account](https://seller.wildberries.ru/new-goods/basket-cards).

A card will remain for sale as long as there is any inventory left, even if moved to the trash. To completely remove the card from sale, set its inventory to zero.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 3 requests | 20 s | 5 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nmIDs` | array |  | Wildberries articles |

[Request example](examples/POST__content_v2_cards_delete_trash_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | object |  | Any additional errors |

[Response 200](../_shared/examples/POST__content_v2_cards_update_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | object |  | Additional errors |

[Response 400](../_shared/examples/GET__content_v2_object_parent_all_400.json)

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

- **429** Too Many Requests
