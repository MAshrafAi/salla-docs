# Docs  Changelog Merchant Api Salla Docs

## Table of Contents

- [docs/Changelog-Merchant-API-Salla-Docs](#docs-changelog-merchant-api-salla-docs)

---

## docs/Changelog-Merchant-API-Salla-Docs

# Change Log

In this page, you will find all about Salla APIs' hot fixes, frequent updates, bug fixes, speed improvement, and deprecated endpoints and requests. We will be displaying both the unreleased and released updates on [Salla's API](https://docs.salla.dev/doc-421117)

:::warning[Alert]
Stay updated by visiting this page often and joining the [API Changelog Telegram Channel](https://t.me/SallaAPI). Notable changes will be documented here for your reference.
:::


:::info[Information]
We recommend that you use Salla APIs' version of V2. This API, <CopyToClipboard>`https://api.salla.dev/admin/v2`</CopyToClipboard> has no breaking changes so far, and we suggest you use it for production.
:::

:::check[Postman Collection]
If you are using an API Request Builder, such as [Postman](https://www.postman.com/salla-app), we are regularly updating the [Postman Collection](https://www.postman.com/salla-app) whenever there is an update mentioned in [ChangeLog page](https://docs.salla.dev/doc-421127). 

🧨 **Recent Release is [V2.7.5](https://www.postman.com/salla-app/salla-e-commerce-platform/collection/17687195-15628a8c-ffc5-412c-9f53-07afec12d383)**

[![Run in Postman](https://run.pstmn.io/button.svg)](https://www.postman.com/salla-app/)
:::

:::note[]
The format of this ChangeLog page is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) standard.
:::

## [2.10.64] - 25-01-2026

### Changed

- Added new variables in [`Create Special Offer`](https://docs.salla.dev/5394217e0), [`List Special Offers`](https://docs.salla.dev/5394218e0), [`Special Offers Details`](https://docs.salla.dev/5394219e0) and [`Update Special Offers`](https://docs.salla.dev/5394220e0) endpoints:

    - `countries`
    - `customer_groups`
    - `select_by`
    - `applied_to`
    - `options`
    - `based_on`
    - `tiers`
    - `apply_type`
    - `with_current_cart`
    - `special_price`
    - `applied_with_coupon`
    - `scopes`
    - `exclude_sale_products`
    - `excluded_buy_products_ids`
    - `excluded_buy_categories_ids`

### Request body:
Support new `offer_type` in the request body of [`Create Special Offer`](https://docs.salla.dev/5394217e0) and [`Update Special Offers`](https://docs.salla.dev/5394220e0) endpoints:
- `special_price`
- `cart_offer`
- `tiered_offer`



## [2.10.63] - 05-01-2026
### Changed
-   **Effective January 5th, 2026**, the [National Address](https://splonline.com.sa/en/national-address-1/) details are **mandatory** with the `ship_to` object variables in your implementations in [Create Order](https://docs.salla.dev/5394145e0), [Update Order](https://docs.salla.dev/5751605e0) and [Create Shipment](https://docs.salla.dev/api-5394231):

    - `country`
    - `city`
    - `address_line`
    - `street_number`
    - `block`
    - `short_address`
    - `building_number`
    - `additional_number`
    - `postal_code`
    - `geo_coordinates`

## [2.10.62] - 04-01-2026
### Added
- Six new endpoints are added:
    - [List Feedbacks](https://docs.salla.dev/5394279e0)
    - [Feedback Details](https://docs.salla.dev/5394280e0)
    - [Update Feedback](https://docs.salla.dev/5394281e0)
    - [Store Feedback](https://docs.salla.dev/12250711e0)
    - [Feedback Reply](https://docs.salla.dev/11160591e0)
    - [Update Feedback Reply](https://docs.salla.dev/11160744e0)

## [2.10.61] - 15-12-2025
### Added
- Six new events in [Product Webhooks](https://docs.salla.dev/433805m0) store events :
    - [`product.price.updated`](https://docs.salla.dev/433805m0#product-price-updated-webhook-events-model)
    - [`product.status.updated`](https://docs.salla.dev/433805m0#product-status-updated-webhook-events-model)
    - [`product.image.updated`](https://docs.salla.dev/433805m0#product-image-updated-webhook-event-model)
    - [`product.category.updated`](https://docs.salla.dev/433805m0#product-category-updated-webhook-events-model)
    - [`product.brand.updated`](https://docs.salla.dev/433805m0#product-brand-updated-webhook-events-model)
    - [`product.tags.updated`](https://docs.salla.dev/433805m0#product-tags-updated-webhook-events-model)

### Depricated 
- The following two webhook events [`product.updated`](https://docs.salla.dev/433805m0#product-webhook-events-model), [`product.available`](https://docs.salla.dev/433805m0#product-webhook-events-model) are being deprecated. We recommend to use the new webhook events, as mentioned below:
        - [`product.price.updated`](https://docs.salla.dev/433805m0#product-price-updated-webhook-events-model)
    - [`product.status.updated`](https://docs.salla.dev/433805m0#product-status-updated-webhook-events-model)
    - [`product.image.updated`](https://docs.salla.dev/433805m0#product-image-updated-webhook-event-model)
    - [`product.category.updated`](https://docs.salla.dev/433805m0#product-category-updated-webhook-events-model)
    - [`product.brand.updated`](https://docs.salla.dev/433805m0#product-brand-updated-webhook-events-model)
    - [`product.tags.updated`](https://docs.salla.dev/433805m0#product-tags-updated-webhook-events-model)

## [2.10.60] - 08-12-2025
### Added
- Two new endpoints added:
    -  [Deposit to Wallet](https://docs.salla.dev/24839928e0).
    -  [Withdraw from Wallet](https://docs.salla.dev/24850516e0).

## [2.10.59] - 30-11-2025

### Added
- Introduced subscription payments in the [Create Order](https://docs.salla.dev/5394145e0) endpoint through the `products.recurring` object.
- A new boolean field, `payment.recurring`, has been added to the [Create Order](https://docs.salla.dev/5394145e0) endpoint to support recurring payments.

### Changed
- The field `store_bank_id` has been renamed to `reference_id` in the order create endpoint.

## [2.10.58] - 19-11-2025

### Added
- New endpoint, [Relocate Order Stock](https://docs.salla.dev/18575329e0).

### Modified

- [Order Option Details](https://docs.salla.dev/13121125e0) endpoint response updates:
  - `time_strict_value` has been renamed to `time_strict`.
  - Added `options.is_default`.
  - The `type` field now supports four enum values: `text`, `number`, `checkbox`, `date`.
  - Included four new response examples corresponding to each `type` enum.

- [Create Order Option](https://docs.salla.dev/13121125e0) and [Update Order Option](https://docs.salla.dev/12918611e0) endpoints have the following adjustments:

  **Request Body**
  - Added `options.is_default`.
  - Updated `type` to include the four enum values: `text`, `number`, `checkbox`, `date`.

  **Response Body**
  - Added `options.is_default`.
  - Updated `type` to include the four enum values: `text`, `number`, `checkbox`, `date`.
  - Added four new examples reflecting each `type` option.

## [2.10.57] - 12-11-2025

### Added
- New endpoint, [List Affiliate Links](https://docs.salla.dev/13902666e0)

### Deprecated
- The following variables are no longer supported in the [Create Affiliate](https://docs.salla.dev/5394269e0) and [Update Affiliate](https://docs.salla.dev/5394272e0) body requests:
    - `code`
    - `marketer_name`
    - `marketer_city`
    - `notes`

- The following variables are no longer supported in the [List Affiliates](https://docs.salla.dev/5394270e0) and [Affiliate Details](https://docs.salla.dev/5394271e0) body responses:
    - `code`
    - `marketer_name`
    - `marketer_city`
    - `notes`
    - `links.affiliate`, which is now accessible using the [List Affiliate Links](https://docs.salla.dev/13902666e0) endpoint
    - `links.statistics`

### Changed

- The following variables are now under objects in the [Create Affiliate](https://docs.salla.dev/5394269e0) and [Update Affiliate](https://docs.salla.dev/5394272e0) body requests:
    - `commission_type` moved to `commission.type` object
    - `amount` moved to `commission.amount` object

- The following variables are no longer supported in the [List Affiliates](https://docs.salla.dev/5394270e0) and [Affiliate Details](https://docs.salla.dev/5394271e0) body responses:
    - `commission_type` moved to `commission.type` object
    - `amount.amount` moved to `statistics.sales.amount` object
    - `amount.currency` moved to `statistics.profit.currency` object
    - `profit.amount` moved to `statistics.sales.amount` object
    - `profit.currency` moved to `statistics.profit.currency` object

## [2.10.56] - 08-10-2025

### Added

- Six new endpoints, [Branch Allocations](https://docs.salla.dev/4145150f0), used to assign shipping companies to specific branches based on location, so customers only see relevant options when ordering.

- Five new endpoints,[ Branch Delivery Zones](https://docs.salla.dev/5101844f0), used to configure delivery zone.

## [2.10.55] - 05-10-2025

### Added

- New endpoint, [List Ditsricts](https://docs.salla.dev/21655021), which lists all available districts for a specific city. 

### Changed

- Added new variable, ship_to.district, to the body requests of [Create Order](https://docs.salla.dev/5394145e0) and [Update Order](https://docs.salla.dev/5751605e0) endpoints.



## [2.10.54] - 31-08-2025

### Changed

- Added the `promotion` object in the [`app.subscription.started`](https://docs.salla.dev/421413m0#app-subscription-start) App webhook event response, which applies *only* to recurring plans (monthly or yearly) where:
    - **Monthly:** Partners can set promotions where `requirement` = `1–9` months and `reward` ≤ `requirement` (in months).
    - **Yearly:** Fixed case where the Merchant can buy 1 year and get 1 year. This is what the response will include to indicate the yearly subscription `(requirement: 1, reward: 1)`.

## [2.10.53] - 03-08-2025

### Changed

- New query parameter, `with`, has been added to the [Branch Details](https://docs.salla.dev/api-5394225) endpoint. When used, it fetches an additional `translations` object in the response, reflecting the store’s enabled locales.

- New query parameter, `fields`, has been added to the [List Customers](https://docs.salla.dev/5394121e0) and [Customer Details](https://docs.salla.dev/5394122e0) endpoints as well as the [Customer Webhook Events](https://docs.salla.dev/433808m0#customer-webhook-events-model) (`customer.created`, `customer.updated`, `customer.login`). When used, it fetches extra customer attributes such as "`is_blocked`" or "`is_notifications_enabled`" using the query parameter (`?fields[]=is_blocked&fields[]=block_reason`) and that will be included in the response.



## [2.10.52] - 29-07-2025

### Added

- Six new endpoints, [Shipping Routes](https://docs.salla.dev/4399607f0), used to manage the store’s shipping routes.

## [2.10.51] - 20-07-2025

### Added

- Five new endpoints, [Branch Allocations](https://docs.salla.dev/4145150f0), used to assign shipping companies to specific branches based on location, so customers only see relevant options when ordering. 

## [2.10.50] - 07-07-2025
### Deprecated

- The following variables in the [Create Shipment](https://docs.salla.dev/5394231e0) endpoint's request body are deprecated:
    - `ship_to.country_id` → instead, use the `ship_to.country` variable
    - `ship_to.city_id ` → instead, use the `ship_to.city` variable
    - `ship_to.country_code` → instead, use the `ship_to.country` variable
    - `ship_from.country_id` → instead, use the `ship_to.country` variable
    - `ship_from.city_id ` → instead, use the `ship_to.city` variable

### Changed

- The [Create Shipment](https://docs.salla.dev/5394231e0) endpoint's request body now includes the following variables:
    - `external_id`
    - `external_additional_id `
    - `description `
    - `remarks `
    - `service_types `
    - `ship_to.country `
    - `ship_to.city `
- The [Update Shipment Details](https://docs.salla.dev/5394233e0) endpoint's request body includes:
    - `policy_options.boxes`
    - `policy_options.number_of_delivery_attempts`
    - `policy_options.shipment_content_type`
- The [Create Shipment](https://docs.salla.dev/5394231e0), [Shipment Details](https://docs.salla.dev/5394234e0), and [Update Shipment Details](https://docs.salla.dev/5394233e0) endpoints' response body includes:
    - `reference.external_id`
    - `reference.external_additional_id`
    - `description`
    - `remarks`
    - `service_types`
- The [Shipments Webhook Store Events](https://docs.salla.dev/433807m0) response body includes:
    - `reference.external_id`
    - `reference.external_additional_id`
    - `description`
    - `remarks`
    - `service_types`

## [2.10.49] - 01-07-2025
### Added

- New endpoint, [Print Transaction Invoice](https://docs.salla.dev/11716492e0)

## [2.10.48] - 17-06-2025
### Changed

- The `status` variable in [List Shipments](https://docs.salla.dev/5394232e0) and [Update Shipment Details](https://docs.salla.dev/5394233e0) endpoints now supports the following new shipment statuses:
    - `in_transit`
    - `reattempted`
    - `lost`
    - `damaged`
    - `return_to_origin`
    - `to_be_reattempted`
    - `unable_to_deliver`
    - `return_in_progress`
    - `partially_delivered`
    - `received_at_final_hub`

## [2.10.47] - 19-05-2025
### Changed

- The [`invoice.created`](https://docs.salla.dev/doc-433813) webhook store event includes the `data.company` and `data.customer.address` objects in its response.

## [2.10.46] - 08-05-2025

### Deprecated

- Effective **May 25, 2025**, the variables `data.checkout_url` and `data.rating_link` will be **deprecated** and replaced by `data.urls.checkout` and `data.urls.rating`, respectively in the following endpoints / webhooks:
    - [Create Order](https://docs.salla.dev/5394145e0)  
    - [Update Order](https://docs.salla.dev/5751605e0)  
    - [Order Details](https://docs.salla.dev/5394147e0)  
    - [Order Webhook Store Events](https://docs.salla.dev/433804m0#orders-webhook-events-model)  
    - [Order Shipments Webhook Store Events](https://docs.salla.dev/433804m0#order-shipments-webhook-events-model) 

## [2.10.45] - 01-05-2025

### Changed

- The [Create Order Item](https://docs.salla.dev/5751402e0) endpoint supports the `sku` as an enum value in the `identifier_type` variable.
- The Order ID variable is no longer supported in the [Update Order Item](https://docs.salla.dev/5751555e0)'s body request.

## [2.10.44] - 23-04-2025

### Changed

- The [List Abandoned Cart](https://docs.salla.dev/5394138e0) endpoint supports the `keyword` query parameter.
- The [Available Payment Methods](https://docs.salla.dev/5394164e0) endpoint supports the `status` query parameter.
- The `per_page` query parameter is now supported on all [pagination-enabled]((https://docs.salla.dev/doc-421124)) endpoints.

## [2.10.43] - 14-04-2025

### Changed

- The `keyword` variable is added as a query parameter in the [List Abandoned Carts](https://docs.salla.dev/api-5394138) endpoint.

## [2.10.42] - 28-03-2025

### Changed

- New variable, `status`, added to the [Abandoned Cart Details](https://docs.salla.dev/5394139e0) endpoint's response.
- Two new webhook store events, [`abandoned.cart.status.changed`](https://docs.salla.dev/433812m0#abandoned-cart-status-changed-webhook-event-model) and [`abandoned.cart.purchased`](https://docs.salla.dev/433812m0#abandoned-cart-purchased-webhook-event-model).

## [2.10.41] - 05-02-2025

### Deprecated

- The variables, `items.codes` and `items.files`, are set to deprecated from the following endpoint / webhook responses:
    - [Create Order](https://docs.salla.dev/5394145e0)
    - [Update Order](https://docs.salla.dev/5751605e0)
    - [Duplicate Order](https://docs.salla.dev/7102947e0)
    - [Order Webhook Events](https://docs.salla.dev/433804m0):
        - `order.created`
        - `order.updated`
        - `order.refunded`
        - `order.deleted`
        - `order.products.updated`
        - `order.payment.updated`
        - `order.coupon.updated`
        - `order.total.price.updated`
        - `order.shipping.address.updated`
        - `order.cancelled`
        - `order.customer.updated`
        - [`order.status.updated`](https://docs.salla.dev/433804m0#order-status-updated-webhook-event-model)
- The variables `codes` and `files` are set to be deprecated from the following endpoint responses:
    - [Create Order Item](https://docs.salla.dev/5751402e0)
    - [List Order Items](https://docs.salla.dev/5565737e0)
    - [Update Order Item](https://docs.salla.dev/5751555e0)

### Changed

- New variable, `digital_content`, has been added to the `urls` object to replace the deprecated variables mentioned above.
- Moved the `rating_link` variable into the `urls` object.

## [2.10.40] - 05-02-2025

### Changed

- The `billing_account` variable has been added to the following endpoints' responses:
    - [Create Order](https://docs.salla.dev/5394145e0?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
    - [Order Details](https://docs.salla.dev/5394147e0?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
    - [Update Order](https://docs.salla.dev/5751605e0?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
    - [Duplicate Order](https://docs.salla.dev/7102947e0?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
    - [Order webhook events](https://docs.salla.dev/433804m0?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB):
        - `order.created`
        - `order.updated`
        - `order.refunded`
        - `order.deleted`
        - `order.products.updated`
        - `order.payment.updated`
        - `order.coupon.updated`
        - `order.total.price.updated`
        - `order.shipping.address.updated`
        - `order.cancelled`
        - `order.customer.updated`
        - `order.shipment.creating`
        - `order.shipment.created`
        - `order.shipment.return.creating`
        - `order.shipment.return.created`
        - `order.status.updated`
    - [Create Shipment](https://docs.salla.dev/5578808e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [List Shipments](https://docs.salla.dev/5578809e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Shipment Details](https://docs.salla.dev/5578811e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Update Shipment Details](https://docs.salla.dev/5578810e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Cancel Shipment](https://docs.salla.dev/5578812e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Return Shipment](https://docs.salla.dev/5578813e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Shipments Webhook events]((https://docs.salla.dev/433807m0?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)):
        - `shipment.creating`
        - `shipment.created`
        - `shipment.updated`
        - `shipment.cancelled`

## [2.10.39] - 21-01-2025

### Changed

- The `is_apply_with_offer` variable has been added to the request bodies for the [Create Coupon](https://docs.salla.dev/api-5394274) and [Update Coupon](https://docs.salla.dev/api-5394277) endpoints. Additionally, it is included in the response bodies of the following endpoints:
  - [Create Coupon](https://docs.salla.dev/api-5394274)
  - [List Coupons](https://docs.salla.dev/api-5394275)
  - [Coupon Details](https://docs.salla.dev/api-5394276)
  - [Update Coupon](https://docs.salla.dev/api-5394277)

## [2.10.38] - 09-01-2025

### Changed

- The variable, `external_company_name`, has been added to the following endpoints' responses and body requests:
    - [Create Shipment](https://docs.salla.dev/api-5394231)
    - [List Shipments](https://docs.salla.dev/api-5394232)
    - [Shipment Details](https://docs.salla.dev/api-5394234)
    - [Update Shipment Details](https://docs.salla.dev/api-5394233)
    - [Cancel Shipment](https://docs.salla.dev/api-5394235)
    - [Return Shipment](https://docs.salla.dev/api-5394236)

## [2.10.37] - 30-12-2024

### Changed

- 🛑 **Starting from January 20th, 2025**, the `status` variable is **required** in the [Update Shipment Details](https://docs.salla.dev/5578810e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K) endpoint's body request. **Recommended** adapting to this change so as not to face any break change in your production environment. 


## [2.10.36] - 29-12-2024

### Changed

- The variable, `options` is added within the `package` object in the following endpoints:
    - [List Shipments](https://docs.salla.dev/5394232e0)
    - [Shipment Details](https://docs.salla.dev/5394234e0)
    - [Update Shipment Details](https://docs.salla.dev/5394233e0)
    - [Create Shipment](https://docs.salla.dev/5394231e0)
    - [Cancel Shipment](https://docs.salla.dev/5394235e0)
    - [Return Shipment](https://docs.salla.dev/5394236e0)
    - [Shipments Webhook Events Model](https://docs.salla.dev/433807m0#shipments-webhook-events-model)

## [2.10.35] - 18-12-2024

### Added

- Two new endpoints for Customer Loyalty Points, [Customer Loyalty Points](https://docs.salla.dev/12250577e0) and [Update Customer Loyalty Points](https://docs.salla.dev/12250579e0).

## [2.10.34] - 08-12-2024

### Changed

- The [Create Special Offer](https://docs.salla.dev/api-5394217) and [Update Special Offer](https://docs.salla.dev/api-5394220) endpoints have a new body request object example, Discount Table Offer Type.

## [2.10.33] - 04-12-2024

### Changed

- The [Create Special Offer](https://docs.salla.dev/api-5394217) and [Update Special Offer](https://docs.salla.dev/api-5394220) endpoints have the variables `message` and `start_date` added in the body request.

## [2.10.32] - 01-12-2024

### Changed

- The [Setting Details](https://docs.salla.dev/api-6965781) has a new object added, `channels_status`, in the Product Notify Availability response.
- The [Setting Details](https://docs.salla.dev/api-6965781) has a new response example, Size Guide.
- The [Export Products](https://docs.salla.dev/api-9796006) has changed the API pathway  from `/products/export` to `/exports/products`.

## [2.10.31] - 28-11-2024

### Added

- Three new endpoints:
    - [Export Customers](https://docs.salla.dev/api-10774701)
    - [Import Custom URLs](https://docs.salla.dev/api-10393771)
    - [Export Custom URLs](https://docs.salla.dev/api-10393831)

### Changed

- The [Settings List](https://docs.salla.dev/api-6965777) endpoint has a new response example, Marketing Response
- The [Setting Details](https://docs.salla.dev/api-6965781) has new response examples, Product Inventory & Brand Options Responses

## [2.10.30] - 26-11-2024

### Changed

- New variable, `subscription_id`, added in the response of the following App Events:
    - [`app.subscription.started`](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ#app-subscription-start)
    - [`app.subscription.canceled`](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ#app-subscription-canceled)
    - [`app.subscription.expired`](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ#app-subscription-expire)
    - [`app.subscription.renewed`](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ#app-subscription-renew)

## [2.10.29] - 20-11-2024

### Added

- New webhook in Products, [`product.channels.changed`](https://docs.salla.dev/doc-433805#product-channels-changed-webhook-events-model)

## [2.10.28] - 18-11-2024

### Added

- New endpoint, [List Category Products](https://docs.salla.dev/api-11055135).

### Changed

- The following endpoints include the variables `image`, `show_in`, `update_at`, and `sub_categories` in the response body:
    - [List Categories](https://docs.salla.dev/api-5394207)
    - [Category Details](https://docs.salla.dev/api-5394208)
    - [Create Category](https://docs.salla.dev/api-5394206)
    - [Update Category](https://docs.salla.dev/api-5394209)

- The [Create Category](https://docs.salla.dev/api-5394206) and [Update Category](https://docs.salla.dev/api-5394209) include the `image` and `show_in` variables in the request body.


## [2.10.27] - 17-11-2024

### Added

- New endpoint, [List Trashed Products](https://docs.salla.dev/api-10450948)

### Changed

- New body request variable, `select_all`,  added to the [Bulk Product Actions](https://docs.salla.dev/api-9613153)

## [2.10.26] - 12-11-2024

### Added

- Five new endpoints:
    - [List Option Templates](https://docs.salla.dev/api-9633869)
    - [Option Template Details](https://docs.salla.dev/api-9634609)
    - [Create Option Template](https://docs.salla.dev/api-9634676)
    - [Update Option Template](https://docs.salla.dev/api-9634567)
    - [Delete Option Template](https://docs.salla.dev/api-9634526)

## [2.10.25] - 10-11-2024

### Deprecated

- The [Update Bulk Quantities By SKU](https://docs.salla.dev/api-5394193), [Update Quantity](https://docs.salla.dev/api-5394191), and [Update Quantity By SKU](https://docs.salla.dev/api-5394190) endpoints are to be deprecated soon. It is recommended to adapt using the [Update Bulk Quantities](https://docs.salla.dev/api-5394192) endpoint.


## [2.10.24] - 06-11-2024

### Changed
- The [Settings List](https://docs.salla.dev/api-6965777?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB) endpoint has the following changes:
    - The `entity` variable is used as a query parameter and instead is removed from the path parameter.
    - Allowed values for `entity` query  parameter includes: `products`, `orders`, `customers`, `reports`, `blogs`, `mahally` and `feedbacks`. 


## [2.10.23] - 03-11-2024

### Added

- New endpoint, [Products Bulk Editor](https://docs.salla.dev/api-10156264)

## [2.10.22] - 30-10-2024

### Changed

- The [Update Category](https://docs.salla.dev/api-5394209) endpoint has a new object variable, `product`, in its body request which allows for assigning products and specifying the sort order.
- New query parameter, `with`, has been added to the [Update Category](https://docs.salla.dev/api-5394209) endpoint. When used, it fetches an additional `translations` object in the response, reflecting the store’s enabled locales.

## [2.10.21] - 29-10-2024

### Changed

- New query parameter, `keyword`, added to the [List Branches](https://docs.salla.dev/api-5394224) endpoint

## [2.10.20] - 28-10-2024

### Changed

- New body request variable, `mode`, added to the following endpoints:
    - [Update Quantity](https://docs.salla.dev/api-5394191)
    - [Update Quantity By SKU](https://docs.salla.dev/api-5394190)
    - [Update Bulk Quantities](https://docs.salla.dev/api-5394192)

## [2.10.19] - 24-10-2024

### Changed

- The query parameters `created_before` and `created_after` have changed to `date_from` and `date_to` respectively in the [List Customers](https://docs.salla.dev/api-5394121) endpoint

## [2.10.18] - 20-10-2024

### Added

- Four new endpoints:
    - [Bulk Product Actions](https://docs.salla.dev/api-9613153)
    - [List Product Quantities](https://docs.salla.dev/api-9612796)
    - [List Quantity Audit](https://docs.salla.dev/api-9613070)
    - [List Quantity Change Reasons](https://docs.salla.dev/api-10094923)

### Changed

- [Update Bulk Quantities](https://docs.salla.dev/api-5394192) has new body request variables, which are `branch` and `reason_id`
- Two new query parameters, `created_before` and `created_after`, added to the [List Customers](https://docs.salla.dev/api-5394121) endpoint

## [2.10.17] - 17-10-2024

 ### Changed

- New query parameter, `per_page`, added to the [List Abanonded Carts](https://docs.salla.dev/api-5394138) endpoint

<!-- ### Added

- Three new webhook events for [Cart](https://docs.salla.dev/doc-433812), which are:
    - `abandoned.cart.status.changed`
    - `abandoned.cart.purchased`
    - `abandoned.cart.expired` -->



## [2.10.16] - 10-10-2024

### Added

- Two new endpoints, [List Deleted Products](https://docs.salla.dev/api-10450948) and [Restore Products](https://docs.salla.dev/api-10450958)

## [2.10.15] - 09-10-2024

### Added

- Three new endpoints:
    - [Settings List](https://docs.salla.dev/api-6965777)
    - [Setting Details](https://docs.salla.dev/api-6965781)
    - [Update Setting Slug](https://docs.salla.dev/api-6965780)

### Changed

- [Order Details](https://docs.salla.dev/api-5394147) endpoint support two new objects, `actions` and `features`

## [2.10.14] - 07-10-2024

### Added

- New endpoint, [Category Search](https://docs.salla.dev/api-10309545)

## [2.10.13] - 06-10-2024

### Added

- Two new endpoints, [Import Products](https://docs.salla.dev/api-5394178) and [Export Products](https://docs.salla.dev/api-9796006)

### Changed

- New query parameter, `with`, has been added. When used, it fetches an additional `translations` object in the response, reflecting the store’s enabled locales for the following endpoints:
   - [List Categories](https://docs.salla.dev/api-5394207)
   - [Category Details](https://docs.salla.dev/api-5394208)
   - [List Brands ](https://docs.salla.dev/api-5394213)
   - [Brand Details](https://docs.salla.dev/api-5394214)
- New query parameter, `format=light`, is added to the [List Products](https://docs.salla.dev/api-5394168) endpoint. When used, it fetches a mninimal response to the list of products.


## [2.10.12] - 02-10-2024

### Changed

- The variable, `name`, is set as `optional` where it was previously set to be `required` in the [Create Customer Group](https://docs.salla.dev/api-5394128) endpoint

## [2.10.11] - 26-09-2024

### Changed

- [Create Customer](https://docs.salla.dev/api-5394120) and [Update Customer](https://docs.salla.dev/api-5394123) endpoints have the following body request variables as `optional`, where they were previously set to be `required`:
    - `first_name`
    - `last_name`
    - `mobile`

## [2.10.10] - 16-09-2024

### Changed

- The webhook event, [`customer.otp.request`](https://docs.salla.dev/doc-433808#customers-otp-one-time-password-webhook-event-model), will only be triggered if both the email and SMS attempts to send the OTP to the customer have failed. This behaviour will be official starting from **September 24, 2024**

## [2.10.9] - 15-09-2024

### Deprecated
- All Apps created after **15th of August, 2024** will not be able to use the `expanded ` query parameter in the [List Orders](https://docs.salla.dev/api-5394146) endpoint.

## [2.10.8] - 08-09-2024

### Changed

- The [List Orders](https://docs.salla.dev/api-5394146) endpoint supports the `features` object in the body response

## [2.10.7] - 28-08-2024

### Changed

- The [List Shipments](https://docs.salla.dev/api-5394232) endpoint supports the `per_page` query parameter


## [2.10.6] - 08-08-2024
### Changed

- The paths for the endpoints [List Transactions](https://docs.salla.dev/api-8382471), [Transaction Details](https://docs.salla.dev/api-8385183), and [Update Transaction](https://docs.salla.dev/api-8385232) have been updated from `/payment/transaction` to `/transaction`. Additionally, their scopes have been revised to `transactions.read` and `transactions.read_write`.

## [2.10.5] - 07-08-2024

### Added

- New endpoint, [List Coupon Codes](https://docs.salla.dev/api-9185252)

### Changed
- [Order Action](https://docs.salla.dev/api-7549669/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB) endpoint has new `value` object variables


## [2.10.4] - 29-07-2024
### Added

- New endpoints added to `"Payments"`, which are:
    - [List Transactions](https://docs.salla.dev/api-8382471/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
    - [Transaction Details](https://docs.salla.dev/api-8385183/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
    - [Update Transaction](https://docs.salla.dev/api-8385232/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)

## [2.10.3] - 28-07-2024
### Deprecated
- The [Order Details](https://docs.salla.dev/api-5394147) endpoint's current response is set to be deprecated soon. The new default response will be what you receive when consuming the [Order Details](https://docs.salla.dev/api-5394147) endpoint with the `format=light` query parameter. As that will be the new response, it is **recommended** to adapt to this change so as not to face any break change in your production environment.


## [2.10.2] - 22-07-2024

### Changed

- The `branch_id` variable has been added to the body request of the [Create Order Item](https://docs.salla.dev/api-5751402) and [Update Order Item](https://docs.salla.dev/api-5751555) endpoints
- The following endpoints have the `shipping_details_id` variable added under the `shipping` object in the body response:
    - [Order Details](https://docs.salla.dev/api-5394147)
    - [Create Order](https://docs.salla.dev/api-5394145)
    - [Duplicate Order](https://docs.salla.dev/api-7102947)
    - [Update Order](https://docs.salla.dev/api-5751605)

### Added

- New endpoints added:
    - Order Assignment
        - [Order Assigned Employees Details](https://docs.salla.dev/api-6930855)
    - Shipping Companies
        - [List Estimate Rates](https://docs.salla.dev/api-6899590)

## [2.10.1] - 14-07-2024
### Changed

- The `"exchange_rate"` object has been added to the body responses of the following endpoints:

    - [List Orders](https://docs.salla.dev/api-5394146)
    - [Order Details](https://docs.salla.dev/api-5394147)
    - [Create Order](https://docs.salla.dev/api-5394145)
    - [Duplicate Order](https://docs.salla.dev/api-7102947)
    - [Update Order](https://docs.salla.dev/api-5751605)

## [2.10.0] - 04-07-2024
### Changed

- The `entity` variable is used as a query parameter in both [List Export Templates](https://docs.salla.dev/api-5593165?nav=1) and [List Export Columns](https://docs.salla.dev/api-5607986?nav=1 ) endpoints.

## [2.9.9] - 03-07-2024
### Changed

- The base URL for the [User Information](https://docs.salla.dev/api-8330089?nav=1) endpoint will be soon updated from `https://api.salla.dev/admin/v2` to `https://accounts.salla.sa/`. However, the response body remains unchanged. **Recommended** adapting to this change so as not to face any break change in your production environment.

## [2.9.8] - 11-06-2024
### Changed

- [List Orders](https://docs.salla.dev/api-5394146) endpoint has new query parameter, `created_by`

## [2.9.7] - 06-06-2024
### Changed

- [List Product Variant](https://docs.salla.dev/api-5394202/?nav=1), [Product Variant Details](https://docs.salla.dev/api-5394203/?nav=1), [Update Product Variant](https://docs.salla.dev/api-5394204/?nav=1), [Update Product Variant Quantity](https://docs.salla.dev/api-5394205/?nav=1) endpoints have the `updated_at` object variable added to its body response

## [2.9.6] - 05-06-2024
### Changed

- The [List Orders](https://docs.salla.dev/api-5394146), [Order Details](https://docs.salla.dev/api-5394147), [Create Order](https://docs.salla.dev/api-5394145), and [Duplicate Order](https://docs.salla.dev/api-7102947)  endpoints' response body have the following changes
    - Added three new variables:
        - `read`
        - `draft`
        - `receipt_image`
    - Removed the `first_complete_at` variable

- The [Update Order](https://docs.salla.dev/api-5751605) endpoint added the `employees` array of integers variable in its body request

## [2.9.5] - 30-05-2024
### Added

- New endpoint, [Order Bulk Actions](https://docs.salla.dev/api-7549669/?nav=1)

## [2.9.4] - 06-05-2024
### Changed
- [List Invoices](https://docs.salla.dev/api-5394157) endpoint has the following changes:
    - Added new variables 
        - `invoice_number`
        - `uuid`
        - `invoice_refrence_id`
        - `qr_code`
        - `payment_method`
    - The `item` variable is removed 

- [List Orders](https://docs.salla.dev/api-5394146) endpoint no longer includes orders with the `draft` and `deleted` statuses

- [Invoice Details](https://docs.salla.dev/api-5394158) endpoint has new variables, which are:
      - `invoice_number`
      - `uuid`
      - `invoice_refrence_id`
      - `qr_code`
      - `payment_method`

- [Order Details](https://docs.salla.dev/api-5394147), [Create Order](https://docs.salla.dev/api-5394145), [Update Order](https://docs.salla.dev/api-5751605) and [Update Order Shipment](https://docs.salla.dev/api-5394161) endpoints have the following changes:
    - Added
       - `updated_at` object
       - `is_price_qoute` variable
       - `receipt_image` variable
       - `reservations` and `product_reservations` variables in `customer` object
       - `store` object
    - Removed
        - `pick_up_branch` object
        - Query parameter, `receiver_details`
          
- [List Orders](https://docs.salla.dev/api-5394146) endpoint has the following changes
    - Added
        - `draft` variable
        - `read` variable
        - `payment_method` variable
        - `pending_payment_ends_at` variable
        - `thumbnail` variable in the `items` array
        - `customer` object

## [2.9.3] - 05-05-2024

### Changed 
- [Category Webhook Events model](https://docs.salla.dev/doc-433809/?nav=1#Un1595catgeory-webhook-events-model) includes the variable `updated_at`.
- The [Category Webhook Events model](https://docs.salla.dev/doc-433809/?nav=1#Un1595catgeory-webhook-events-model), [Category Details](https://docs.salla.dev/api-5394208) endpoint, [Create Category](https://docs.salla.dev/api-5394206) endpoint and [Update Category](https://docs.salla.dev/api-5394209) endpoint  include the following variables: 
    - `metadata-title` 
    - `metadata-description`
    - `metadata-url`
- [List Order Status](https://docs.salla.dev/api-5394150) endpoint variable `sort` has the data type of `number`.
- [List Order Histories](https://docs.salla.dev/api-5394162) endpoint includes the following variables:
    -  `avatar` in the `created_at` object.
    -  `type` variable
### Removed
- The variable `country_id` is not supported in [List Cities](https://docs.salla.dev/api-5394230/?nav=1) endpoint.
- The variables `created_by` and `type` are not supported [List Order Histories](https://docs.salla.dev/api-5394162) endpoint.

## [2.9.2] - 22-04-2024
### Changed
- The  [List Orders](https://docs.salla.dev/api-5394146/?nav=1) endpoint includes new query parameters which are `sort_by`, `accounting_services`, `unread`, `assign_empolyee`, and `selling_channel`.
- The [Order Details](https://docs.salla.dev/api-5394147/?nav=1) endpoint, includes a new query parameter, `format`, which returns Order Details without the following objects; `"Shipments"`,  `"Items"`,  `"Pickup Branch"`,  "`Customer Groups"`, and "`Receiver Details`".
- The [List Order Histories](https://docs.salla.dev/api-5394162) endpoint includes the object variable, `created_by`.

### Added 
- New endpoints added:
    - Order
        - [Update Order](https://docs.salla.dev/api-5751605?nav=1)
        - [Create Drafted Order](https://docs.salla.dev/api-5750257?nav=1)

    - Order Invoice
        - [Create Order Invoice](https://docs.salla.dev/api-6339631?nav=1)
        - [Send Order Invoice](https://docs.salla.dev/api-6336820?nav=1)
    - Order Status
        - [Update Bulk Order Statuses](https://docs.salla.dev/api-5588886?nav=1)
        - [Sort Order Statuses](api-5607770?nav=1)
    - Order Items
        - [List Order Items](https://docs.salla.dev/api-5565737?nav=1)
        - [Create Order Items](https://docs.salla.dev/api-5751402?nav=1)
        - [Update Order Items](https://docs.salla.dev/api-5751555?nav=1)
        - [Delete Order Item](https://docs.salla.dev/api-5751557?nav=1)
    - Order Assignments
        - [List Auto Assignment Rules](https://docs.salla.dev/api-5576999?nav=1)
        - [Update Auto Assignment Rules](https://docs.salla.dev/api-5581833?nav=1)
        - [Create Auto Assignment Rules](https://docs.salla.dev/api-5677301?nav=1)
    - Order Reservations
        - [List Order Reservations](https://docs.salla.dev/api-5579097?nav=1)
    - Exports
        - [Export Orders](https://docs.salla.dev/api-5590305?nav=1)
        - [List Export Columns](https://docs.salla.dev/api-5607986?nav=1)
        - [List Export Templates](https://docs.salla.dev/api-5593165?nav=1)
        - [Create Export Template](https://docs.salla.dev/api-5593686?nav=1)
        - [Update Export Template](https://docs.salla.dev/api-5593689?nav=1)
        - [Delete Export Template](https://docs.salla.dev/api-5593835?nav=1)

## [2.9.1] - 2024-04-16
### Added

We have set rate limitation on all the Customers endpoints, `/admin/v2/customers*`, to boost the Partners’ performance and streamline interactions with Salla’s servers. Each IP address is individually restricted to not more than **500** requests every **10** minutes for the Customers endpoints. IPs exceeding this limit will face restrictions.

## [2.9.0] - 2024-03-31
### Changed

- Major updates occured on the following webhooks' schema:
   - The `country` object includes the variable `capital` in the [Store Webhook Events Model](https://docs.salla.dev/doc-433811#store-webhook-events-model)
   - The [Special Offer Webhook Events Model](https://docs.salla.dev/doc-433814#special-offer-webhook-events-model) includes the following changes:
    - The `buy` object variable includes:
       - `type`
       - `categories`
       - `products`
    - The `get` object variable includes:
       - `discount_type`
       - `type`
       - `categories`
       - `products`
   - The `source` object variable is included in the [Customer Webhook Events Model](https://docs.salla.dev/doc-433808#customer-webhook-events-model)
   - The `customer` object includes the variable `email` in the [Abandoned Cart Webhook Events Model](https://docs.salla.dev/doc-433812#abandoned-cart-webhook-events-model)
   - The `type` variable in the [Shipping Zone Webhook Events Model](https://docs.salla.dev/doc-433806#shipping-zone-webhook-events-model) includes the following enum values:
     - `fixed`
     - `rate`
     - `distance`
   - The `order` object variable in the [Order Status Update Events Model](https://docs.salla.dev/doc-433804#order-status-updated-webhook-event-model) has the following objects removed:
     - `bank`
     - `product_reservations`
     - `tags`
   - The `status` variable in the [Shipments Webhook Events Model](https://docs.salla.dev/doc-433807#shipments-webhook-events-model) has the following changes in its enum values:
      - `pending` and `returned` has been removed
      - `shipped` has been added
- The following Merchant API endpoints: [Create Order](https://docs.salla.dev/api-5394145), [Order Details](https://docs.salla.dev/api-5394147), [Update Order Shipment](https://docs.salla.dev/api-5394161), and [Orders Webhook Event Model](https://docs.salla.dev/doc-433804#orders-webhook-events-model):
      - includes the following variables:
        - `cart_reference_id` variable
        - `ship_to` object includes:
          - `country_id`
          - `city_id`
        - `ship_from` object includes:
          - `country_id`
          - `country_code`
          - `city_id` 
        - `meta` object includes the `diemnsions` object
  - The [Shipments Webhook Event Model](https://docs.salla.dev/doc-433807/?nav=1#shipments-webhook-events-model) includes the following variables:
    - `ship_to` object includes:
        - `country_id`
        - `city_id`
    - `ship_from` object includes:
        - `country_id`
        - `country_code`
        - `city_id` 
    - `meta` object includes the `diemnsions` object

## [2.8.9] - 2024-03-26
### Changed

- The endpoint [List Cities](https://docs.salla.dev/api-5394230/?nav=1) include the `country_id` variable in its body response.
- The endpoints [List Countries](api-5394228/?nav=1) and [Country Details](https://docs.salla.dev/api-5394229/?nav=1) include the `capital` variable in their body responses

## [2.8.8] - 2024-03-14
### Changed

- The variables `formatted_price`, `advance`, `translations`, `is_out_of_stock`, `has_special_price`, and `is_user_suibscribed` has been added to the body responses of the following endpoints:
    - [Create Product](https://docs.salla.dev/api-5394167)
    - [List Products](https://docs.salla.dev/api-5394168)
    - [Product Details](https://docs.salla.dev/api-5394169)
    - [Update Product](https://docs.salla.dev/api-5394170)
    - [Product Details by SKU](https://docs.salla.dev/api-5394173)
    - [Update Product by SKU](https://docs.salla.dev/api-5394174)
    - [Update Product Option](https://docs.salla.dev/api-5394196)
    - [Update Product Price by SKU](https://docs.salla.dev/api-5394174)

## [2.8.7] - 2024-02-26
### Added
- New endpoint for [Update Language](https://docs.salla.dev/api-5738833)

### Changed
- The endpoints [Add Language](https://docs.salla.dev/api-5394254) and [List Languages](https://docs.salla.dev/api-5738815) support `sort_order` in both body request and response.

## [2.8.6] - 2024-02-25
### Changed

- The endpoint [List Order Statuses](https://docs.salla.dev/api-5394150/?nav=1) include the variables `sort`, `message`, `icon`, and `is_active` in its body response.

## [2.8.5] - 2024-02-06
### Added

- New body request for the [Create Order](https://docs.salla.dev/api-5394145) endpoint. **Recommended** adapting to this change so as not to face any break change in your production environment.


## [2.8.4] - 2024-01-25
### Added

- The endpoint [List Active Webhooks](https://docs.salla.dev/api-5394135) now supports the variable `pagination`. 

## [2.8.3] - 2024-01-23
### Added

- Two new endpoints for [List Banks](https://docs.salla.dev/api-5394165) and [Banks Details](api-5394166)

### Changed

- Updated body requests for both [Create Option](https://docs.salla.dev/api-5394194) and [Update Product Option](https://docs.salla.dev/api-5394196) endpoints

## [2.8.2] - 2024-01-03
### Changed

- The variable `type` with its enum values (`"development", "live", and "demo"`) has been added to the [Store Info Details](https://docs.salla.dev/api-5394261) endpoint

## [2.8.1] - 2023-11-05
### Removed

- The variable `parent_id` is no longer supported in the [Update Statuses](https://docs.salla.dev/api-5394152) endpoint
- The variables `name` and `message` are no longer required in the body request of the [Update Statuses](https://docs.salla.dev/api-5394152) endpoint.


## [2.8.0] - 2023-11-02
### Added

- Three new endpoints for [List Reviews](https://docs.salla.dev/api-5394279), [Review Details](api-5394280), [Update Review](https://docs.salla.dev/api-5394281)

## [2.7.9] - 2023-09-26
### Changed

- The body response in both [List Abandoned Carts](https://docs.salla.dev/api-5394138) and [Abandoned Cart Details](https://docs.salla.dev/api-5394139) have new enumerated values support within the `coupon.status` variable.

## [2.7.8] - 2023-09-21
### Changed

- The [List Orders](https://docs.salla.dev/api-5394146) Endpoint supports a new query parameter, `source` which lists the source of the order.
- The object variable, `features`, has been deprecated from the [Create Group](https://docs.salla.dev/api-5394128) Endpoint
- New endpoint for [Abandoned Cart Details](https://docs.salla.dev/api-5394139)

## [2.7.7] - 2023-09-03
### Changed

- The variables `name` and `message` have [multi-language](https://docs.salla.dev/doc-421122) support in the following endpoints:
  - [Create Custom Sub Status](https://docs.salla.dev/api-5394149)
  - [List Order Status](https://docs.salla.dev/api-5394150)
  - [Order Status Detail](https://docs.salla.dev/api-5394151)
  - [Update Status](https://docs.salla.dev/api-5394152)

## [2.7.6] - 2023-08-30
### Changed

- The variables `name` and `message` have [multi-language](https://docs.salla.dev/api-5394218) support in the following endpoints:
  - [List Special Offer](https://docs.salla.dev/api-5394218)
  - [Special Offer Details](https://docs.salla.dev/api-5394219)
  - [Update Special Offer](https://docs.salla.dev/api-5394220)

## [2.7.5] - 2023-08-29

### Changed

- The variables `metadata.title`, `metadata.description`, and `metadata.url` have [multi-language](https://docs.salla.dev/doc-421122) support in the following endpoints' body responses:

  - [Create Product](https://docs.salla.dev/api-5394167)
  - [List Product](https://docs.salla.dev/api-5394168)
  - [Product Details](https://docs.salla.dev/api-5394169)
  - [Update Product](https://docs.salla.dev/api-5394170)
  - [Product Details by SKU](https://docs.salla.dev/api-5394173)
  - [Update Product by SKU](https://docs.salla.dev/api-5394176)
- The variables `metadata_title`, `metadata_description`, and `metadata_url` have [multi-language](https://docs.salla.dev/doc-421122) support in the following endpoints' body requests:

  - [Update Product](https://docs.salla.dev/api-5394170)
  - [Update Product by SKU](https://docs.salla.dev/api-5394174)

## [2.7.4] - 2023-08-16
### Changed

- The variables `item_id` and `external_id` have been added to the following endpoints' / webhooks' response:

  - [Create Order](https://docs.salla.dev/api-5394145)
  - [Order Details](https://docs.salla.dev/api-5394147)
  - [Update Order Shipment](https://docs.salla.dev/api-5394161)

  - [Create Shipment](https://docs.salla.dev/api-5435733)
  - [List Shipments](https://docs.salla.dev/api-5435734)
  - [Update Shipment Details](https://docs.salla.dev/api-5435735)
  - [Shipment Details](https://docs.salla.dev/api-5435736)
      
  - [Orders Webhook Event Model](schema-1307433)
  - [Shipments Webhook Event Model](schema-1307433)

## [2.7.3] - 2023-08-15
### Changed

- The [Update Product Quantity](https://docs.salla.dev/api-5394191) endpoint's body request has support to the `branches_quantities` object variable.

## [2.7.2] - 2023-08-06
### Changed

- The following [App Events](https://docs.salla.dev/doc-421413) includes a new variable, `"store_type"`, which indicates the status of a store being either `"development"`, `"demo"`, or `"live"`:
  - `app.installed `
  - `app.uninstalled `
  - `app.updated `
  - `app.trial.started `
  - `app.trial.expired `
  - `app.trial.canceled `
  - `app.subscription.started `
  - `app.subscription.expired `
  - `app.subscription.canceled `
  - `app.subscription.renewed `

## [2.7.1] - 2023-08-03
### Added

- New App Event for [Cancelling Trial App Subscriptions](https://docs.salla.dev/doc-421413#app-subscription-canceled). 

## [2.7.0] - 2023-07-31
### Changed

- The variables `name`, `address_description`, `street`, and `local` have [multi-language](https://docs.salla.dev/doc-421122) support in the following endpoints:

  - [List Branches Endpoint](https://docs.salla.dev/api-5394224)
  - [Branch Details Endpoint](https://docs.salla.dev/api-5394225)
  - [Update Branch Endpoint](https://docs.salla.dev/api-5394226)


## [2.6.9] - 2023-07-25
### Changed

- The variables `metadata.title`, `metadata.description`, and `metadata.url` have [multi-language](https://docs.salla.dev/doc-421122) support in the following endpoints:

  - [List Brands Endpoint](https://docs.salla.dev/api-5394213)
  - [Brand Details Endpoint](https://docs.salla.dev/api-5394214)
  - [Update Brand Endpoint](https://docs.salla.dev/api-5394215)

## [2.6.8] - 2023-07-20

### Changed

- The [Update Branch Endpoint](https://docs.salla.dev/api-5394215) body request has been enhanced, in which all variables are now marked as `Optional`.

## [2.6.7] - 2023-07-16
### Changed

- [Update Variant](https://docs.salla.dev/api-5394204) Endpoint support the `cost_price` variable in its body request, which replaces the `regular_price` variable.
- [Update Variant](https://docs.salla.dev/api-5394204) new variables have beed added `gtin`, `mpn`, and `notify_low`.


## [2.6.6] - 2023-07-13
### Changed

- A new value `delivering` has been added to the variable `status` of the following models:
  - [Shipments Response](https://docs.salla.dev/schema-1307438)
  - [Shipment Response](https://docs.salla.dev/schema-1307438)
  - [Shipments Webhook Events](https://docs.salla.dev/schema-1307439)

## [2.6.5] - 2023-06-19
### Changed

- [Create Order](https://docs.salla.dev/api-5394145) Endpoint support the `coupon` variable in its body request.

## [2.6.4] - 2023-06-18
### Changed

- The variables `shipment_content_type` and `packaging_type` have been added to the following endpoints:
  - [Create Shipment](https://docs.salla.dev/api-5394231)
  - [List Shipments](https://docs.salla.dev/api-5394232)
  - [Update Shipment Details](api-5394233)
  - [Shipment Details](https://docs.salla.dev/api-5394234)
  - [Cancel Shipments](https://docs.salla.dev/api-5394235)
  - [Return Shipments](https://docs.salla.dev/api-5394236)
  - All [Shipments Webhook Event Model](https://docs.salla.dev/schema-1307439)

## [2.6.3] - 2023-06-07
### Added

- New Endpoint for [Update Image](https://docs.salla.dev/api-5394188)

## [2.6.2] - 2023-06-06
### Changed

- The variable, `groups`, has been added to [Create Customer](https://docs.salla.dev/api-5394120), [List Customer](https://docs.salla.dev/api-5394121), [Customer Details](https://docs.salla.dev/api-5394122), [Update Customer](https://docs.salla.dev/api-5394123), as well as the [Customer Webhook Events Model](https://docs.salla.dev/schema-1307420).
- The variables `gender` and `birthday` have been added to the [Create Customer](https://docs.salla.dev/api-5394120) and [Update Customer](https://docs.salla.dev/api-5394123).

- The object metadata and its variables, title, description and URL, have been added to [Create Category](https://docs.salla.dev/api-5394206), and [Update Category](https://docs.salla.dev/api-5394209) endpoints as well as the [Category Webhook Event Model](https://docs.salla.dev/schema-1307421).


## [2.6.1] - 2023-05-23
### Changed

- The variable `subscription_balance` has been added to the following endpoint/app events:
  - [App Subscription Details](https://docs.salla.dev/api-5401098) Endpoint
  - [App Subscription Start](https://docs.salla.dev/doc-421413#app-subscription-start) Event
  - [App Subscription Canceled](https://docs.salla.dev/doc-421413#app-subscription-canceled) Event
  - [App Subscription Expire](https://docs.salla.dev/doc-421413#app-subscription-expire) Event
  - [App Subscription Renew](https://docs.salla.dev/doc-421413#app-subscription-renew) Event

## [2.6.0] - 2023-05-17
### Changed
- The object `metadata` and its variables, `title`, `description` and `URL`, have been added to the [Create Product](https://docs.salla.dev/api-5394167), [List Products](https://docs.salla.dev/api-5394168), [Product Details](https://docs.salla.dev/api-5394169), [Product Details By SKU](https://docs.salla.dev/api-5394173), [Update Product](https://docs.salla.dev/api-5394173), [Update Product By SKU](https://docs.salla.dev/api-5394174), and [Update Product Price By SKU](https://docs.salla.dev/api-5394176) endpoints as well as Product Webhook Event Model.


## [2.5.9] - 2023-05-08
### Changed

- The object `metadata` and its variables, `title`, `description` and `URL`, have been added to [Create Brand](https://docs.salla.dev/api-5394212), [List Brands](https://docs.salla.dev/api-5394213), [Brand Details](https://docs.salla.dev/api-5394214), and [Update Brand](https://docs.salla.dev/api-5394215) endpoints as well as the Brand Webhook Event Model.

## [2.5.8] - 2023-05-04
### Changed

- The variable `order_reference_id` has been added to the following:
  - [Create Shipment](https://docs.salla.dev/api-5394231)
  - [List Shipments](https://docs.salla.dev/api-5394232)
  - [Update Shipment Details](https://docs.salla.dev/api-5394233)
  - [Shipment Details](https://docs.salla.dev/api-5394234)
  - [Cancel Shipments](https://docs.salla.dev/api-5394235)
  - [Return Shipments](https://docs.salla.dev/api-5394236)
  - All Shipments Webhook Events
- New Endpoint for [Shipment Tracking](https://docs.salla.dev/api-5394237).
- [Update Shipment Details](https://docs.salla.dev/api-5394233) supports the variable `status_note` in its body request.

## [2.5.7] - 2023-04-17
### Changed

- The following Endpoints supports the object variable `booking_details`, where it is added to:
    - [Create Product](https://docs.salla.dev/api-5394167)
    - [Update Product](https://docs.salla.dev/api-5394170)
    - [Product Details](https://docs.salla.dev/api-5394169)
    - All Product Webhook events
- [Order Details](api-5394147) and All Order Webhook events supports the object variable `product_reservations`.

## [2.5.6] - 2023-04-11
### Changed

- [Create Product](https://docs.salla.dev/api-5394167), [Update Product](https://docs.salla.dev/api-5394170), and [Update Product by SKU](https://docs.salla.dev/api-5394174) endpoints supports the following variables:
  - `channels`
  - `show_in_web`

## [2.5.5] - 2023-03-15
### Changed

- [Update Bulk Quantities](https://docs.salla.dev/api-5394192) endpoint supports the `unlimited_quantity` variable in the Body Request.

## [2.5.4] - 2023-03-13
### Added

- New Apps Endpoint for [Updating Apps Subscription Balance](https://docs.salla.dev/api-5401099).

## [2.5.3] - 2023-03-12
### Added

- New Endpoint for [Creating](https://docs.salla.dev/api-5394252), [Listing](https://docs.salla.dev/api-5394251), and [Deleting](https://docs.salla.dev/api-5394253) DNS Records.


## [2.5.2] - 2023-03-09
### Changed

- [Order Details](https://docs.salla.dev/api-5394147) supports the `shipments` array of object, aka `Object[Array]`
- The following [Order Webhook Events](https://docs.salla.dev/doc-421119#order) supports the `shipments` array of object, aka `Object[Array]`
  - `order.created`
  - `order.updated`
  - `order.refunded`
  - `order.deleted`
  - `order.products.updated`
  - `order.payment.updated`
  - `order.coupon.updated`
  - `order.total.price.updated`
  - `order.shipping.address.updated`
  - `order.cancelled`

## [2.5.1] - 2023-03-08
### Changed

- Adding the `is_default` field as a boolean query parameter to the [List Branches](https://docs.salla.dev/api-5394224) endpoint.

## [2.5.0] - 2023-02-28
### Changed

- There are new variables added to the [List Branches](https://docs.salla.dev/api-5394224) endpoint, which are:
  - `street`
  - `address_description`
  - `additional_number`
  - `building_number`
  - `local`
  - `postal_code`
  - `working_hours`
- New Endpoint Operation for `POST`ing [Add Note to Order Histories](https://docs.salla.dev/api-5394163)
- New Webhook for [`invoice.created`](https://docs.salla.dev/apis/api-5394156)
- New Endpoint for [Store Info Details](https://docs.salla.dev/api-5394261)

## [2.4.9] - 2023-02-06
### Changed

- The App Event `app.uninstall` includes the field `refunded` as boolean.

## [2.4.8] - 2023-01-15
### Changed

- [List Orders](https://docs.salla.dev/api-5394146) supports three new query parameters:
  - `customer_id`
  - `coupon`
  - `shipping.app_id`

## [2.4.7] - 2023-01-08
### Changed

- [Order Invoice Details](https://docs.salla.dev/api-5394158) supports two identification keys, `items[].id` & `items[].item_id`.

## [2.4.6] - 2022-12-25
### Changed
<!-- - Customer Groups - [Create Group](https://docs.salla.dev/docs/merchant/e4ec63f032126-create-group)
	- Change `conditions` type from object to an array of object Object[Array]
- Customer Groups - [Update Group](https://docs.salla.dev/docs/merchant/e16d604536c36-update-group)
	- Change `conditions` type from object to an array of object Object[Array] -->
- [Create Customer Groups](https://docs.salla.dev/api-5394128) and [Update Customer Group](https://docs.salla.dev/api-5394132) changed the variable `conditions` type from object to an array of object, aka `Object[Array]`

## [2.4.5] - 2022-12-09
### Added

- New App Event for [Cancelling App Subscriptions](https://docs.salla.dev/doc-421413#app-subscription-canceled).
## [2.4.4] - 2022-11-08
### Added

- New Endpoint for [Adding Customers to a Customer Group](https://docs.salla.dev/api-5394130)

## [2.4.3] - 2022-10-03
### Removed

- The variable `pagination` is no longer supported in all the [`catgeories endpoint`](https://docs.salla.dev/api-5394206).

## [2.4.2] - 2022-09-26
### Changed
- [User Information](https://docs.salla.dev/api-5394260) endpoint returns the following variables in its response:
  - `tax_number`
  - `commercial_number`

## [2.4.1] - 2022-09-14
### Changed
- [Attach Image](https://docs.salla.dev/api-5394184) endpoint supports the following variables in its `application/json` body request:
  - `sort`
  - `alt`
  - `default`

## [2.4.0] - 2022-08-23

### Changed

- [Update Variant](https://docs.salla.dev/api-5394204), [Show Variant](https://docs.salla.dev/api-5394203), [List Product Variants](https://docs.salla.dev/api-5394202), [Update Product Variant Quantity](https://docs.salla.dev/api-5394205), and Product Webhook Events have the variables `weight`, `weight_type`, and `weight_label` in its body requests and responses.
- [Order Details](https://docs.salla.dev/api-5394147), [List Orders](https://docs.salla.dev/api-5394146), [Update Order Shipment](https://docs.salla.dev/api-5394161), and Order Webhook Events have the variable `rating_link` in its body response.

## [2.3.9] - 2022-07-9

### Changed

- [Update Order Status](https://docs.salla.dev/api-5394148) endpoint supports the `note` variable in its body request.

## [2.3.8] - 2022-07-8

### Changed

- [Update Bulk Product Prices](https://docs.salla.dev/api-5394177) endpoint supports the following variables:
  - `cost_price`
  - `sale_price`
  - `sale_end`

## [2.3.7] - 2022-07-6

### Changed

- [Update Order Shipment](api-5394161) endpoint supports the `cost` variable in its body request.

## [2.3.6] - 2022-06-8

### Changed

- [Order Details](https://docs.salla.dev/api-5394147), [Create Order](https://docs.salla.dev/api-5394145), and all Order Webhook events endpoints and  have support to the `source_details` object where details about the source of order is appended.
- [Order Details](https://docs.salla.dev/api-5394147), and all Order Webhook eventshave the variable `slug` in its `status` object.


### Deprecated

- The variables `source` and `source_device` will be deprecated from all the Order [endpoints](https://docs.salla.dev/api-5394145) and webhook events. Instead, use the newly adapted object, `source_details`.

## [2.3.5] - 2022-05-24

### Added

- Multipule Language Support as Header in certain Endpoints, such as the following:
  - [List Products](https://docs.salla.dev/api-5394168)
  - [Product Details](https://docs.salla.dev/api-5394169)
  - [Update Product](https://docs.salla.dev/api-5394170)
  - [List Categories](https://docs.salla.dev/api-5394207)
  - [Category Details](https://docs.salla.dev/api-5394208)
  - [Update Category](https://docs.salla.dev/api-5394209)
  - [List Brands](https://docs.salla.dev/api-5394213)
  - [Brand Details](https://docs.salla.dev/api-5394214)
  - [Update Brand](https://docs.salla.dev/api-5394215)
  - [List Advertisements](https://docs.salla.dev/api-5394265)
  - [Advertisements Details](https://docs.salla.dev/api-5394266)
  - [Update Advertisement](https://docs.salla.dev/api-5394267)
  - [List SEO Settings](https://docs.salla.dev/api-5394262)
  - [Update SEO Settings](https://docs.salla.dev/api-5394263)
Checkout the subsection [article](https://docs.salla.dev/doc-421122) regarding the multi-language support.

### Changed

- The variables `calories`, `mpn`, and `gtin` have been added to the following Endpoints:
  - [Create Order](https://docs.salla.dev/api-5394145)
  - [List Orders](https://docs.salla.dev/api-5394146)
  - [Order Details](https://docs.salla.dev/api-5394147)
  - [Update Order Shipment](https://docs.salla.dev/api-5394161)
  - [Create Special Offer](https://docs.salla.dev/api-5394217)
  - [List Special Offers](https://docs.salla.dev/api-5394218)
  - [Special Offer Details](https://docs.salla.dev/api-5394219)
  - [Update Special Offer](https://docs.salla.dev/api-5394220)

## [2.3.4] - 2022-05-24

### Changed

- [App Subscription endpoint](https://docs.salla.dev/api-5401098) has support for the following new variables:
  - `initialization_cost`
  - `price_before_discount`
  - `coupon`
  - `features`

- App Events, specifically [`app.subscription.started`](https://docs.salla.dev/doc-421413#app-subscription-start), [`app.subscription.expired`](doc-421413#app-subscription-expire), and [`app.subscription.renewed`](https://docs.salla.dev/doc-421413#app-subscription-renew) events have support of the `coupon` variable. Check out the payloads for more.
## [2.3.3] - 2022-05-23

### Added

- Introducing New Endpoints/Operations for the following Endpoints:
  - [Create Custom Sub-status](https://docs.salla.dev/api-5394149)
  - [Order Status Details](https://docs.salla.dev/api-5394151)
  - [Update Statuses](https://docs.salla.dev/api-5394152)

- In the [Update Order Status](https://docs.salla.dev/api-5394152) Endpoint, you can update an order status using either the `slug` or `status_id` variables. Check the endpoint for more.

### Changed

- The variables `calories`, `mpn`, and `gtin` have been added to the following Endpoints:
  - [Create Product](https://docs.salla.dev/api-5394167)
  - [List Products ](https://docs.salla.dev/api-5394168)
  - [Product Details ](https://docs.salla.dev/api-5394169)
  - [Update Product ](https://docs.salla.dev/api-5394170)
  - [Product Details By SKU](https://docs.salla.dev/api-5394173)
  - [Update Product By SKU](https://docs.salla.dev/api-5394174)
  - [Update Product Price By SKU](https://docs.salla.dev/api-5394176)

## [2.3.2] - 2022-05-18
### Changed

- App Events, specifically [`app.subscription.started`](https://docs.salla.dev/doc-421413#app-subscription-start), [`app.subscription.expired`](doc-421413#app-subscription-expire), and [`app.subscription.renewed`](https://docs.salla.dev/doc-421413#app-subscription-renew) events have support of the `initialization_cost` and `price_before_discount` variables. Check out the payloads for more.

## [2.3.1] - 2022-05-10

### Changed

- App Events, specifically [`app.subscription.started`](https://docs.salla.dev/doc-421413#app-subscription-start), [`app.subscription.expired`](doc-421413#app-subscription-expire), and [`app.subscription.renewed`](https://docs.salla.dev/doc-421413#app-subscription-renew) events have support of the `features` array variable. Check out the payloads for more.

## [2.3.1] - 2022-04-28

### Added

- New Endpoint for Viewing Details of [App Subscriptions](https://docs.salla.dev/api-5401098).

## [2.3.0] - 2022-04-24

### Added

- New Endpoint for [Listing](https://docs.salla.dev/api-5394239), [Creating](https://docs.salla.dev/api-5394238), [Viewing Details](https://docs.salla.dev/api-5394240), [Updating](https://docs.salla.dev/api-5394241), and [Deleting](https://docs.salla.dev/api-5394242) Custom Shipping Zones. 

### Changed

- `metadata` Object added in the following Endpoints:
  - [List Products](https://docs.salla.dev/api-5394168)
  - [Product Details](https://docs.salla.dev/api-5394169)
  - [Product Details By SKU](https://docs.salla.dev/api-5394173)
  - [Update Product](https://docs.salla.dev/api-5394170)
  - [Update Product By SKU](https://docs.salla.dev/api-5394174)
  - [Update Product Price By SKU](https://docs.salla.dev/api-5394176)
- [Update Product Option](https://docs.salla.dev/api-5394196) Endpoint has the ability to pass the Product ID when updating a product details' options. __Note__ that old values will be deleted when updating its values with new ones. 

## [2.2.9] - 2022-04-17

### Added

- New Endpoint for [Listing Active Webhooks](https://docs.salla.dev/api-5394135).
- New Set of API Collection in regards to Salla Apps. Checkout the Endpoint for [Controlling App Settings](https://docs.salla.dev/api-5401096). 
- New Operations Support for Shipping Companies, such as [Creating](https://docs.salla.dev/api-5394238), [Updating](https://docs.salla.dev/api-5394241), and [Deleting](https://docs.salla.dev/api-5394242) Shipping Companies.
- Support for `5` New Webhook Events in regards to Shipping Companies. 

### Changed

- [Creating Coupon](https://docs.salla.dev/api-5394274) supports creating `Group` and `Marketing Coupns`
- List SEO Settings have newly supported variables, such as `Sitemap URL`, `Refresh Sitemap` and more. Check the [endpoint](https://docs.salla.dev/api-5394262) for more details.

### Removed

- The variable `sub_categories` has been removed from the [`/categories`](https://docs.salla.dev/api-5394207), [`/categories/{category}`](https://docs.salla.dev/api-5394208) and [`/categories/{category}/children`](https://docs.salla.dev/api-5394211) endpoints. 

## [2.2.8] - 2022-03-24

### Changed

- [List Invoices](https://docs.salla.dev/api-5394157), [Invoice Details](https://docs.salla.dev/api-5394158), and [Create Invoice](https://docs.salla.dev/api-5394156) Endpoints have support for the `order_id` variable.


## [2.2.8] - 2022-03-20

### Added

- New Endpoint for [Creating Invoices](https://docs.salla.dev/api-5394156) via Third-Party Service Providers.
- New Endpoint for [Creating](https://docs.salla.dev/apis/api-5394264), [Listing](https://docs.salla.dev/api-5394265), [Viewing Details](https://docs.salla.dev/api-5394266), [Updating](https://docs.salla.dev/api-5394267), and [Deleting](https://docs.salla.dev/api-5394268) Advertisements.
- New Endpoint for [Updating Bulk Product Prices](https://docs.salla.dev/api-5394177).
- New Operation for [Updating SEO Settings](https://docs.salla.dev/api-5394263).

### Changed

- While creating a new product, you are able to add images to the product. Check the [endpoint's payload](https://docs.salla.dev/api-5394167) for details.
- [Listing Shipping Companies](https://docs.salla.dev/api-5394239) and [Order Details](https://docs.salla.dev/api-5394147) endpoints contain the `app_id` variable that identifies the shipping company's Application ID.  

## [2.2.7] - 2022-02-21
### Changed

- The variable `maximum_quantity_per_order` has been changed from `boolean` to `integer` datatype when [Creating a product](https://docs.salla.dev/api-5394167). 

## [2.2.7] - 2022-02-13

### Deprecated
- The obtainment of the API Key directly from the Merchant's Dashboard has been deprecated. To acquire an Access Token, follow up the OAuth 2.0 Protocol by exploring this [article](https://salla.dev/blog/oauth-2-0-in-action-with-salla/).

## [2.2.7] - 2022-02-02

### Added

- New Endpoint for [Creating](https://docs.salla.dev/api-5394269), [Updating](https://docs.salla.dev/api-5394272), [Viewing Details](https://docs.salla.dev/api-5394271), and [Deleting](https://docs.salla.dev/api-5394273) Marketing Affiliates.
- New Endpoint to query [Available Currencies](https://docs.salla.dev/api-5394258).

### Changed

- All [Product endpoints](https://docs.salla.dev/api-5394168) has a variable, namely boolean `main`, that ensures whether or not the product has an image as a `main` attribute.

## [2.2.6] - 2022-01-25

### Added

- New Endpoints for [Attaching Image File](https://docs.salla.dev/api-5394184) and [Attaching Video URL](https://docs.salla.dev/api-5394185) to a Product SKU.

## [2.2.5] - 2022-01-19

### Added

- New Enpoint for [Listing](https://docs.salla.dev/api-5394157), [Viewing Details](https://docs.salla.dev/api-5394158), and [Generating](https://docs.salla.dev/api-5394156) Invoices.
- Operation Support for Coupon, as such in [Creating](https://docs.salla.dev/api-5394274), [Viewing Details](https://docs.salla.dev/api-5394276), [Updating](https://docs.salla.dev/api-5394277), and [Deleting](https://docs.salla.dev/api-5394278) Coupons.

## [2.2.4] - 2022-01-17

### Changed

- There are `new` updates when Listing Abandoned Carts. Check this [endpoint](https://docs.salla.dev/api-5394138) for more.

## [2.2.4] - 2022-01-11

### Changed 

- [List Product Variants (SKUs)](https://docs.salla.dev/api-5394202) and [Show Variant (SKU)](https://docs.salla.dev/api-5394203) have a deprecated variable which is `related_options`. The new value is `related_option_values`.  

## [2.2.4] - 2021-12-27

### Added

Supporting new Endpoints such as:

- [Listing](https://docs.salla.dev/api-5394255) and [Activating/Deactivating](https://docs.salla.dev/api-5394254) for Languages. 
- [Listing](https://docs.salla.dev/api-5394257) and [Activating](https://docs.salla.dev/api-5394256) Currencies.
- [Listing](https://docs.salla.dev/api-5394275) Coupons.
- [Listing](https://docs.salla.dev/api-5394270) Marketing Affiliates.
- [Listing](https://docs.salla.dev/api-5394259) Employees.
- [Listing](https://docs.salla.dev/api-5394262) SEO Settings.
- [Importing](https://docs.salla.dev/api-5394178) Products from an Excel file.
- [Importing](https://docs.salla.dev/api-5394127) Customers from an Excel file.
- [Showing](https://docs.salla.dev/api-5394260) User and Store information.
<!-- - [Creating](https://docs.salla.dev/docs/merchant/b3A6MzMyMjI2NTc-create-advertisement) Advertisments. -->

### Changed

- There is a `new` update on the Product Request, where we support `Consisted Products`. Check this [endpoint](https://docs.salla.dev/api-5394167) for more.
- The Order Shipment contains a label object. Check this [endpoint](https://docs.salla.dev/api-5394161) for more.

## [2.2.3] - 2021-11-21

### Added

- New Endpoint for [Listing](https://docs.salla.dev/api-5394243) Shipping Rules as well as [Showing](https://docs.salla.dev/api-5394244), and [Deleting](https://docs.salla.dev/api-5394245) Shipping Rule Details.

## [2.2.2] - 2021-10-19

### Added

- New Endpoint for [Listing](https://docs.salla.dev/api-5394180) and [Creating](https://docs.salla.dev/api-5394179) Product Tags.

### Changed

- We have updated the [payload of Product Details](https://docs.salla.dev/api-5394168) to contain correspondent responses as queried, such as `notify_quantity`, `show_in_app` and more variables/responses.

## [2.2.2] - 2021-09-21

### Changed

- We have updated the [order.shipment.creating](https://docs.salla.dev/api-5394231) and order.shipment.created payload to include customer and items data
- Similarly, we have updated the order.shipment.return.creating and order.shipment.return.created payload to include customer and items data

## [2.2.2] - 2021-09-13

### Added

- New Endpoint for [Cancelling Order Shipments](https://docs.salla.dev/api-5394159)

## [2.2.2] - 2021-08-20

### Added

- New Endpoint for [Listing Order Shipments](https://docs.salla.dev/api-5394160)

## [2.2.2] - 2021-08-03

### Changed

- There are `new` and `updated` webhook events that have been added to [Webhook](https://docs.salla.dev/api-5394136)

## [2.2.2] - 2021-08-02

### Changed

- Rules and Version have been added to Webhook in its Version 2 when [registering a webhook](https://docs.salla.dev/api-5394134)

## [2.2.2] - 2021-07-26

### Changed

- Coupon Code has been dropped out from the [abandoned cart](https://docs.salla.dev/api-5394139) Response
- Coupon Details, such as Coupon Items and Checkout URL have been added to the [abandoned cart](https://docs.salla.dev/api-5394139) response
- Product Response contains `with_tax` boolean variable, when either fetching a Product Response Updating a product details

## [2.2.2] - 2021-06-03

### Added

- ** Update Order Shippment Endpoint**
  - We have added new endpoint that provides support for Merchants and shipment companies who wants to update shippment details.
    [Endpoint Link](https://docs.salla.dev/api-5394161)

## [2.2.1] - 2021-05-25

### Added

- ** List Shipping Companies Endpoint**
  - We have added new endpoint that helps merchants to list all active shipping companies in their store.
    [Endpoint Link](https://docs.salla.dev/api-5394239)
- ** Shipment card model added to list orders responses :**
  - In list orders with expanded = true parameter you will receive Shipment branch details in case of order is being shipped from a branch.

## [2.2.0] - 2021-04-14

### Added

- ** URLs Applied To Different Modules**
  - To help companies and merchants, Salla provides a “urls” attribute that has been added to different modules to guide the merchants to have the full URL of this module from both scopes, the dashboard scope as a store admin, and as a customer. Those modules are:
    - Order Module
    - Customer Module
    - Product Module
    - Category Module
  - **NOTE:**
    - In some modules that extend others, such as order payload which includes an instance of the product details payload, customer details payload, and category details payload, it will return the URLs of each one on its own payload section.

## [2.1.0] - 2021-02-22

### Added

- List product variants endpoint
- Show variant endpoint
- Update variant endpoint
- Update variant quantity endpoint
- Update bulk quantities by skus endpoint

### Changed

- Show Product Option details
- Create Product Option
- Update Product Option
- Add unlimited_quantity to product create, update and responses.

### Removed

- Product type from product update request
- Quantity from produt option values requests and responses

## [2.0.0] - 2021-02-09

**API Version 2.0.0 publish**

- Added initial commit for API version 2.

---

