# `POST` /content/v2/barcodes

**Tag:** [Creating Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Generation of SKUs**

Описание метода

Generates array of unique SKUs to create size of the product card


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
| `count` | integer |  | Number of SKUs to be generated, maximum 5,000 *Example: `100`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | array |  | An array of generated SKUs |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description. |
| `additionalErrors` | string |  | Any additional errors |

[Response 200](../_shared/examples/POST__content_v2_barcodes_200.json)

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
