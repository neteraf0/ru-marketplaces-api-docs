# `POST` /adv/v1/stats

**Tag:** [Statistics](index.md)

**Server:** `https://advert-media-api.wildberries.ru`

**Media Campaign Statistics**

Описание метода

The method allows to get statistics of [WB Media](https://cmp.wildberries.ru/cmpf/statistics) campaigns


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 10 requests | 100 ms | 10 requests |
| Service | 1 s | 10 requests | 100 ms | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

Content-Type: `application/json`

*Array of:*


[Request: RequestWithDate](examples/POST__adv_v1_stats_req_RequestWithDate.json)


[Request: RequestWithInterval](examples/POST__adv_v1_stats_req_RequestWithInterval.json)


[Request: RequestWithoutParam](examples/POST__adv_v1_stats_req_RequestWithoutParam.json)


[Request: RequestAggregate](examples/POST__adv_v1_stats_req_RequestAggregate.json)

## Responses

### `200` Success

*Array of:*


[Response 200: RespStatMediaInterval](../_shared/examples/POST__adv_v1_stats_200_RespStatMediaInterval.json)


[Response 200: RespStatMediaDates](../_shared/examples/POST__adv_v1_stats_200_RespStatMediaDates.json)


[Response 200: RespStatMediaWithoutParam](../_shared/examples/POST__adv_v1_stats_200_RespStatMediaWithoutParam.json)


[Response 200: RespStatMediaAggregate](../_shared/examples/POST__adv_v1_stats_200_RespStatMediaAggregate.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | string |  |  |

[Response 400: invalidAdvert](../_shared/examples/POST__adv_v1_stats_400_invalidAdvert.json)

- **401** Unauthorized
- **429** Too Many Requests
