# `POST` /content/v2/tag/nomenclature/link

**Tag:** [Tags](index.md)

**Server:** `https://content-api.wildberries.ru`

**Tag Management in the Product Card**

Описание метода

The method allows to add tags to the product card and remove tags from the product card.
When removing a tag from a product card, the tag itself is not removed.
It is possible to add 15 tags to a product card.


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


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nmID` | integer |  | WB article |
| `tagsIDs` | array |  | An array of numeric tag IDs. When removing a tag from a product card, the tag itself is not removed. To add tags to existing ones in the product card, you need to specify in the request the new tags and the tags that are already exist in the product card.  |

[Request example](examples/POST__content_v2_tag_nomenclature_link_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 200](../_shared/examples/POST__content_v2_tag_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 400: IncorrectRequestNm](../_shared/examples/PATCH__content_v2_tag__id_200_responseNotFound200.json)

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
