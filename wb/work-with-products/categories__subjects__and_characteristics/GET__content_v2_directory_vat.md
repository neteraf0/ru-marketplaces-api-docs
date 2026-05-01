# `GET` /content/v2/directory/vat

**Tag:** [Categories, Subjects, and Characteristics](index.md)

**Server:** `https://content-api.wildberries.ru`

**VAT Rate**

Описание метода

Returns a list of values for the **VAT rate** characteristic


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
| `locale` | query | string |  | Language for response of the `subjectName` and `name` fields:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  Not used in the sandbox  *Example: `ru`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | array |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 200](../_shared/examples/GET__content_v2_directory_vat_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | object |  | Additional errors |

[Response 400](../_shared/examples/GET__content_v2_object_parent_all_400.json)

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
