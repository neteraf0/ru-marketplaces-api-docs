# `POST` /content/v2/cards/recover

**Tag:** [Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Recover Product Card from Trash**

Описание метода

Returns the product card from trash


  When restoring the product card from the trash, its imtID  — merged product cards ID — doesn't remain the same as it was for the product card in the trash


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 5 requests |
| Service | 1 min | 3 requests | 20 s | 5 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `nmIDs` | array |  | Wildberries articles |

[Request example](examples/POST__content_v2_cards_recover_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | object |  | Additional errors |

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
