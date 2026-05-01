# `POST` /content/v2/tag

**Tag:** [Tags](index.md)

**Server:** `https://content-api.wildberries.ru`

**Create a Tag**

Описание метода

Creates a tag.

It is possible to create 15 tags.

The maximum length of a tag is 15 characters


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
| `color` | string |  | Tag color.  Available colors:   - `D1CFD7` — grey   - `FEE0E0` — red   - `ECDAFF` — purple   - `E4EAFF` — blue   - `DEF1DD` — green   - `FFECC7` — yellow  *Example: `D1CFD7`* |
| `name` | string |  | Tag name *Example: `Sale`* |
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
| `additionalErrors` | object |  | Additional errors |

[Response 400: responseBodyContentError400](../_shared/examples/POST__content_v2_tag_400_responseBodyContentError400.json)


[Response 400: responseBody400LenName](../_shared/examples/POST__content_v2_tag_400_responseBody400LenName.json)


[Response 400: responseBodyLimitTag](../_shared/examples/POST__content_v2_tag_400_responseBodyLimitTag.json)


[Response 400: responseBodyNameNotExist](../_shared/examples/POST__content_v2_tag_400_responseBodyNameNotExist.json)

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
