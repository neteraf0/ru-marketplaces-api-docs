# laas

[← API Яндекс Маркета для продавцов](../index.md)

## Endpoints

- [`POST` /v2/businesses/{businessId}/settings](POST__v2_businesses__businessId__settings.md) — Настройки кабинета
- [`GET` /v2/campaigns](GET__v2_campaigns.md) — Список магазинов пользователя
- [`GET` /v2/campaigns/{campaignId}](GET__v2_campaigns__campaignId.md) — Информация о магазине
- [`GET` /v2/campaigns/{campaignId}/settings](GET__v2_campaigns__campaignId__settings.md) — Настройки магазина
- [`GET` /v2/campaigns/{campaignId}/orders/{orderId}](GET__v2_campaigns__campaignId__orders__orderId.md) — Информация об одном заказе в магазине
- [`GET` /v2/campaigns/{campaignId}/orders](GET__v2_campaigns__campaignId__orders.md) — Информация о заказах в магазине
- [`POST` /v1/businesses/{businessId}/orders](POST__v1_businesses__businessId__orders.md) — Информация о заказах в кабинете
- [`PUT` /v2/campaigns/{campaignId}/orders/{orderId}/status](PUT__v2_campaigns__campaignId__orders__orderId__status.md) — Изменение статуса одного заказа
- [`POST` /v2/campaigns/{campaignId}/orders/status-update](POST__v2_campaigns__campaignId__orders_status_update.md) — Изменение статусов нескольких заказов
- [`POST` /v2/campaigns/{campaignId}/orders/{orderId}/identifiers/status](POST__v2_campaigns__campaignId__orders__orderId__identifiers_status.md) — Статусы проверки кодов маркировки
- [`POST` /v1/campaigns/{campaignId}/orders/create](POST__v1_campaigns__campaignId__orders_create.md) — Создание заказа
- [`POST` /v1/campaigns/{campaignId}/orders/update](POST__v1_campaigns__campaignId__orders_update.md) — Изменение заказа
- [`POST` /v1/campaigns/{campaignId}/orders/update-options](POST__v1_campaigns__campaignId__orders_update_options.md) — Получение временных интервалов для изменения заказа
- [`GET` /v2/campaigns/{campaignId}/returns](GET__v2_campaigns__campaignId__returns.md) — Список невыкупов и возвратов
- [`GET` /v2/campaigns/{campaignId}/orders/{orderId}/returns/{returnId}](GET__v2_campaigns__campaignId__orders__orderId__returns__returnId.md) — Информация о невыкупе или возврате
- [`POST` /v1/campaigns/{campaignId}/returns/create](POST__v1_campaigns__campaignId__returns_create.md) — Создание возврата
- [`POST` /v1/campaigns/{campaignId}/returns/cancel](POST__v1_campaigns__campaignId__returns_cancel.md) — Отмена возврата
- [`GET` /v2/regions](GET__v2_regions.md) — Поиск регионов по их имени
- [`GET` /v2/regions/{regionId}](GET__v2_regions__regionId.md) — Информация о регионе
- [`GET` /v2/regions/{regionId}/children](GET__v2_regions__regionId__children.md) — Информация о дочерних регионах
- [`POST` /v2/regions/countries](POST__v2_regions_countries.md) — Список допустимых кодов стран
- [`POST` /v2/businesses/{businessId}/offer-mappings/delete](POST__v2_businesses__businessId__offer_mappings_delete.md) — Удаление товаров из каталога
- [`POST` /v2/businesses/{businessId}/offer-mappings](POST__v2_businesses__businessId__offer_mappings.md) — Информация о товарах в каталоге
- [`POST` /v2/businesses/{businessId}/offer-mappings/update](POST__v2_businesses__businessId__offer_mappings_update.md) — Добавление товаров в каталог и изменение информации о них
- [`POST` /v1/businesses/{businessId}/offer-mappings/barcodes/generate](POST__v1_businesses__businessId__offer_mappings_barcodes_generate.md) — Генерация штрихкодов
- [`POST` /v2/businesses/{businessId}/offer-prices/updates](POST__v2_businesses__businessId__offer_prices_updates.md) — Установка цен на товары для всех магазинов
- [`POST` /v2/campaigns/{campaignId}/offer-prices/updates](POST__v2_campaigns__campaignId__offer_prices_updates.md) — Установка цен на товары в конкретном магазине
- [`POST` /v2/campaigns/{campaignId}/offer-prices](POST__v2_campaigns__campaignId__offer_prices.md) — Просмотр цен на указанные товары в конкретном магазине
- [`POST` /v2/businesses/{businessId}/offer-prices](POST__v2_businesses__businessId__offer_prices.md) — Просмотр цен на указанные товары во всех магазинах
- [`POST` /v2/campaigns/{campaignId}/offers/stocks](POST__v2_campaigns__campaignId__offers_stocks.md) — Информация об остатках и оборачиваемости
- [`POST` /v1/campaigns/{campaignId}/delivery-options](POST__v1_campaigns__campaignId__delivery_options.md) — Получение доступных вариантов доставки заказов
- [`POST` /v1/campaigns/{campaignId}/return-delivery-options](POST__v1_campaigns__campaignId__return_delivery_options.md) — Получение подходящих для возврата пунктов выдачи
- [`GET` /v2/reports/info/{reportId}](GET__v2_reports_info__reportId.md) — Получение заданного отчета или документа
- [`POST` /v2/reports/united-marketplace-services/generate](POST__v2_reports_united_marketplace_services_generate.md) — Отчет по стоимости услуг
- [`POST` /v2/reports/united-returns/generate](POST__v2_reports_united_returns_generate.md) — Отчет по невыкупам и возвратам
- [`POST` /v2/reports/stocks-on-warehouses/generate](POST__v2_reports_stocks_on_warehouses_generate.md) — Отчет по остаткам на складах
- [`POST` /v2/reports/goods-movement/generate](POST__v2_reports_goods_movement_generate.md) — Отчет по движению товаров
- [`POST` /v2/reports/closure-documents/generate](POST__v2_reports_closure_documents_generate.md) — Закрывающие документы
- [`POST` /v2/reports/closure-documents/detalization/generate](POST__v2_reports_closure_documents_detalization_generate.md) — Отчет по схождению с закрывающими документами
- [`POST` /v1/reports/documents/barcodes/generate](POST__v1_reports_documents_barcodes_generate.md) — Получение файла со штрихкодами
- [`POST` /v1/businesses/{businessId}/logistics-points](POST__v1_businesses__businessId__logistics_points.md) — Получение точек ПВЗ Маркета
- [`POST` /v2/campaigns/{campaignId}/offers](POST__v2_campaigns__campaignId__offers.md) — Информация о товарах, которые размещены в заданном магазине
- [`POST` /v2/campaigns/{campaignId}/offers/update](POST__v2_campaigns__campaignId__offers_update.md) — Изменение условий продажи товаров в магазине
- [`POST` /v2/campaigns/{campaignId}/offers/delete](POST__v2_campaigns__campaignId__offers_delete.md) — Удаление товаров из ассортимента магазина
- [`GET` /v2/warehouses](GET__v2_warehouses.md) — Идентификаторы фулфилмент-складов Маркета
- [`POST` /v2/category/{categoryId}/parameters](POST__v2_category__categoryId__parameters.md) — Списки характеристик товаров по категориям
- [`POST` /v2/businesses/{businessId}/offer-cards](POST__v2_businesses__businessId__offer_cards.md) — Получение информации о заполненности карточек магазина
- [`POST` /v2/businesses/{businessId}/offer-cards/update](POST__v2_businesses__businessId__offer_cards_update.md) — Редактирование категорийных характеристик товара
- [`POST` /v2/categories/tree](POST__v2_categories_tree.md) — Дерево категорий
- [`POST` /v2/campaigns/{campaignId}/supply-requests](POST__v2_campaigns__campaignId__supply_requests.md) — Получение информации о заявках на поставку, вывоз и утилизацию
- [`POST` /v2/campaigns/{campaignId}/supply-requests/items](POST__v2_campaigns__campaignId__supply_requests_items.md) — Получение товаров в заявке на поставку, вывоз или утилизацию
- [`POST` /v2/campaigns/{campaignId}/supply-requests/documents](POST__v2_campaigns__campaignId__supply_requests_documents.md) — Получение документов по заявке на поставку, вывоз или утилизацию
- [`POST` /v2/auth/token](POST__v2_auth_token.md) — Получение информации о токене авторизации
- [`POST` /v1/businesses/{businessId}/operations](POST__v1_businesses__businessId__operations.md) — Получение статусов операций
