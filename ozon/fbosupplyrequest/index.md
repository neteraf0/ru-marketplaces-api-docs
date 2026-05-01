# FboSupplyRequest

[← Документация Ozon Seller API](../index.md)

## Endpoints

- [`POST` /v1/cluster/list](POST__v1_cluster_list.md) — Информация о кластерах и их складах
- [`POST` /v1/warehouse/fbo/list](POST__v1_warehouse_fbo_list.md) — Поиск точек для отгрузки поставки
- [`POST` /v1/draft/create](POST__v1_draft_create.md) — Создать черновик заявки на поставку
- [`POST` /v1/draft/crossdock/create](POST__v1_draft_crossdock_create.md) — Создать черновик заявки на поставку кросс-докингом
- [`POST` /v1/draft/direct/create](POST__v1_draft_direct_create.md) — Создать черновик заявки на прямую поставку
- [`POST` /v1/draft/multi-cluster/create](POST__v1_draft_multi_cluster_create.md) — Создать черновик заявки на поставку для нескольких кластеров
- [`POST` /v1/draft/create/info](POST__v1_draft_create_info.md) — Информация о черновике заявки на поставку
- [`POST` /v1/draft/timeslot/info](POST__v1_draft_timeslot_info.md) — Доступные таймслоты
- [`POST` /v2/draft/create/info](POST__v2_draft_create_info.md) — Получить информацию о черновике заявки на поставку
- [`POST` /v1/draft/supply/create](POST__v1_draft_supply_create.md) — Создать заявку на поставку по черновику
- [`POST` /v1/draft/supply/create/status](POST__v1_draft_supply_create_status.md) — Информация о создании заявки на поставку
- [`POST` /v2/draft/timeslot/info](POST__v2_draft_timeslot_info.md) — Получить список доступных таймслотов
- [`POST` /v1/cargoes/create](POST__v1_cargoes_create.md) — Установка грузомест
- [`POST` /v1/cargoes/create/info](POST__v1_cargoes_create_info.md) — Получить информацию по установке грузомест
- [`POST` /v2/cargoes/create/info](POST__v2_cargoes_create_info.md) — Получить информацию по установке грузомест
- [`POST` /v1/cargoes/get](POST__v1_cargoes_get.md) — Получить информацию о грузоместах
- [`POST` /v1/cargoes/delete](POST__v1_cargoes_delete.md) — Удалить грузоместо в заявке на поставку
- [`POST` /v1/cargoes/delete/status](POST__v1_cargoes_delete_status.md) — Информация о статусе удаления грузоместа
- [`POST` /v1/cargoes/rules/get](POST__v1_cargoes_rules_get.md) — Чек-лист по установке грузомест FBO
- [`POST` /v1/cargoes-label/create](POST__v1_cargoes_label_create.md) — Сгенерировать этикетки для грузомест
- [`POST` /v1/cargoes-label/get](POST__v1_cargoes_label_get.md) — Получить идентификатор этикетки для грузомест
- [`GET` /v1/cargoes-label/file/{file_guid}](GET__v1_cargoes_label_file__file_guid.md) — Получить PDF с этикетками грузовых мест
- [`POST` /v1/supply-order/cancel](POST__v1_supply_order_cancel.md) — Отменить заявку на поставку
- [`POST` /v1/supply-order/cancel/status](POST__v1_supply_order_cancel_status.md) — Получить статус отмены заявки на поставку
- [`POST` /v1/supply-order/content/update](POST__v1_supply_order_content_update.md) — Редактирование товарного состава
- [`POST` /v1/supply-order/content/update/status](POST__v1_supply_order_content_update_status.md) — Информация о статусе редактирования товарного состава
- [`POST` /v1/supply-order/content/update/validation](POST__v1_supply_order_content_update_validation.md) — Проверить новый товарный состав
- [`POST` /v2/draft/supply/create](POST__v2_draft_supply_create.md) — Создать заявку на поставку по черновику
- [`POST` /v2/draft/supply/create/status](POST__v2_draft_supply_create_status.md) — Получить информацию о создании заявки на поставку
- [`POST` /v1/warehouse/fbo/seller/list](POST__v1_warehouse_fbo_seller_list.md) — Получить список складов продавца
