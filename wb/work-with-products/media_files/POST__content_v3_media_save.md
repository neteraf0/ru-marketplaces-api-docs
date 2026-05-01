# `POST` /content/v3/media/save

**Tag:** [Media Files](index.md)

**Server:** `https://content-api.wildberries.ru`

**Upload Media Files via Links**

Описание метода

The method uploads a set of media files to a product card by specifying links in the request.


  New media files (data) replace old ones (mediaFiles). To add new files, set links both to new and old files.


Requirements for links:
  * the link must directly lead to the file. Ensure the link does not lead to a preview or authorization page. If the link leads to TXT or HTML page, it is considered incorrect
  * no authorization is required to access the file via the link

Requirements for images:
  * maximum images for each product card — 30
  * minimal resolution – 700 × 900 pixels
  * maximum size — 32 MB
  * minimal quality — 65%
  * formats — JPG, PNG, BMP, GIF (static), WebP


Requirements for video:
  * maximum one video for each product card
  * maximum size — 50 MB
  * formats — MOV, MP4


If one or several images or a video do not meet the requirements, no images and a video will be uploaded even if you have the success response (`200`)


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
| `nmId` | integer |  | Wildberries article |
| `data` | array |  | Links to images in the order that they are on the card, and a video at any position of the array |

[Request example](examples/POST__content_v3_media_save_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | object |  | Additional errors |

[Response 200](../_shared/examples/POST__content_v3_media_file_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `additionalErrors` | object |  | Additional errors |
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 400](../_shared/examples/POST__content_v3_media_file_400.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `additionalErrors` | object |  | Additional errors |
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 403](../_shared/examples/POST__content_v3_media_file_400.json)

### `409` Error saving some of the links


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `additionalErrors` | object |  | Additional errors |
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 409](../_shared/examples/POST__content_v3_media_file_400.json)

### `422` The parameter nmId is missing


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `additionalErrors` | object |  | Additional errors |
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |

[Response 422](../_shared/examples/POST__content_v3_media_file_400.json)

- **429** Too Many Requests
