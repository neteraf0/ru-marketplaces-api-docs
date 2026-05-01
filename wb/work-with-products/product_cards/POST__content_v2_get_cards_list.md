# `POST` /content/v2/get/cards/list

**Tag:** [Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**Product Cards List**

Описание метода


  The method is available with the token of the Promotion category


Returns the list of created product cards.


  Product cards from the trash are not provided in the method response. You can get these product cards via different method


To get **more than 100** product cards, use pagination:
  1. Make the first request:

        {
          "settings": {
            "sort": {
              "ascending": true
            },
            "cursor": {
              "limit": 100
            },
            "filter": {
              "withPhoto": -1
            }
          }
        }
     To get only new or updated product cards after data export, use ascending sorting: `"sort":{"ascending":true}`.
  2. Copy `"updatedAt": "***","nmID":"***"` from the `cursor` in the response and insert into the `cursor` of your next request.
  3. Make the next request.
  4. Repeat 2 and 3 until `total` value in the response is less than the `limit` value in the request. This will mean you got all cards.

To get only product cards that were created or updated after the previous data export:
  1. Save the `"cursor":{"updatedAt":"***","nmID":"***"}` fields from the last response of the previous data export. When exporting the data, use ascending sorting: `"sort":{"ascending":true}`.
  2. Specify the saved `"cursor":{"updatedAt":"***","nmID":"***"}` fields in the first request. Keep using ascending sorting.
  3. Save the `"cursor":{"updatedAt":"***","nmID":"***"}` fields from the last response of the current data export.


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
| `locale` | query | string |  | Language for response of the `name`, `value` and `object` fields:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  Not used in the sandbox  *Example: `ru`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `settings` | object |  | Settings |

[Request example](examples/POST__content_v2_get_cards_list_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cards` | array |  | Product cards |
| `cursor` | object |  | Paginator |

[Response 200](../_shared/examples/POST__content_v2_get_cards_list_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | object |  | Additional errors |

[Response 400](../_shared/examples/GET__content_v2_object_parent_all_400.json)


[Response 400](../_shared/examples/POST__content_v2_get_cards_list_400.json)

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
