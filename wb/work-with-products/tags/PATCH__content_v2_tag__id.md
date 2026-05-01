# `PATCH` /content/v2/tag/{id}

**Tag:** [Tags](index.md)

**Server:** `https://content-api.wildberries.ru`

**Update the Tag**

Описание метода

Changes tag data: name and color


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


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | path | integer | ✓ | Numeric tag ID *Example: `1`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `color` | string |  | Tag color *Example: `D1CFD7`* |
| `name` | string |  | Tag name *Example: `Sale`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 200: responseNotFound200](../_shared/examples/PATCH__content_v2_tag__id_200_responseNotFound200.json)

### `400` Bad request


[Response 400: responseBodyContentError400](../_shared/examples/POST__content_v2_tag_400_responseBodyContentError400.json)


[Response 400: responseBody400LenName](../_shared/examples/POST__content_v2_tag_400_responseBody400LenName.json)

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
