# `POST` /content/v3/media/file

**Tag:** [Media Files](index.md)

**Server:** `https://content-api.wildberries.ru`

**Upload Media File**

Описание метода

Uploads and adds one media file for the product card.

Requirements for images:

  * maximum images for each product card  — 30,
  * minimal resolution – 700 × 900 pixels,
  * maximum size — 32 МB,
  * minimal quality — 65%,
  * formats — JPG, PNG, BMP, GIF (static), WebP.

Requirements for video:

  * maximum one video for each product card
  * maximum size — 50 MB
  * formats — MOV, MP4


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
| `X-Nm-Id` | header | string | ✓ | Wildberries article *Example: `213864079`* |
| `X-Photo-Number` | header | integer | ✓ | Number of media file, starting from `1`. To add the video set `1`.  To add the image to the uploaded ones, set file the number more then number of uploaded files.  *Example: `2`* |

## Request Body

Content-Type: `multipart/form-data`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `uploadfile` | string |  |  |
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


[Response 400](../_shared/examples/POST__content_v3_media_file_400_1.json)

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

- **429** Too Many Requests
