# Webhooks Store Events  Product Webhook Events Model Salla Merchant Api Salla Docs

## Table of Contents

- [webhooks-store-events/Product-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-product-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Review-Added-Webhook-Event-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-review-added-webhook-event-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Shipments-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-shipments-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Shipping-Zone-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-shipping-zone-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Special-Offer-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-special-offer-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Store-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-store-webhook-events-model-salla-merchant-api-salla-docs)

---

## webhooks-store-events/Product-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Product

Below are the webhook store events paired with their respective data schema related to the [Product webhook events](https://docs.salla.dev/doc-421119):

## Product Price Updated Webhook Events Model

This event is triggered when a product price has been updated, includes updates in regular price, sale price, cost and tax.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="8346513" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.price.updated",
  "merchant": 546096831,
  "created_at": "Sun Dec 14 2025 11:41:40 GMT+0300",
  "data": {
    "id": 1462551237,
    "sku": "PRO-7644",
    "mpn": "MPN888",
    "gtin": "38374622",
    "cost": 60,
    "starting_price": null,
    "price": 150,
    "sale_price": {
      "amount": 85,
      "expired_at": "2025-12-01"
    },
    "tax": 22.5,
    "taxed_price": 172.5,
    "regular_price": 150,
    "currency": "SAR",
    "with_tax": true
  }
}
```
  </Tab>
</Tabs>


## Product Status Updated Webhook Events Model

This event is triggered when a product status has been changed.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="8346866" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.status.updated",
  "merchant": 546096831,
  "created_at": "Mon Nov 17 2025 15:32:59 GMT+0300",
  "data": {
    "id": 799860060,
    "sku": "SKU122",
    "mpn": "MPN-093",
    "gtin": "88840002",
    "status": "hidden"
  }
}
```
  </Tab>
</Tabs>


## Product Image Updated Webhook Event Model

This event is triggered when a product image has been updated.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="8346974" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.image.updated",
  "merchant": 546096831,
  "created_at": "Sun Dec 14 2025 12:04:05 GMT+0300",
  "data": {
    "id": 1462551237,
    "sku": "PRO-7644",
    "mpn": "MPN888",
    "gtin": "38374622",
    "main_image": {
      "id": 247197971,
      "url": "https://cdn.salla.sa/AzqOeQ/RsoIlcNiVFOaXRsyQU9rBT05yWQeiQ4CzIMHAh5m.png",
      "video_url": null,
      "type": "image"
    },
    "images": [
      {
        "id": 247197971,
        "url": "https://cdn.salla.sa/AzqOeQ/RsoIlcNiVFOaXRsyQU9rBT05yWQeiQ4CzIMHAh5m.png",
        "main": true,
        "three_d_image_url": null,
        "alt": "test55",
        "video_url": null,
        "type": "image",
        "sort": 2
      },
      {
        "id": 1807371374,
        "url": "https://cdn.salla.sa/AzqOeQ/srxtcyQPVFeLjo8UTcZpClHnlcaMVQwwkybTRSyf.jpg",
        "main": false,
        "three_d_image_url": null,
        "alt": "test55",
        "video_url": null,
        "type": "image",
        "sort": 3
      }
    ]
  }
}
```
  </Tab>
</Tabs>


## Product Category Updated Webhook Events Model

This event is triggered when a product category has been updated.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="8347044" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.category.updated",
  "merchant": 546096831,
  "created_at": "Wed Nov 19 2025 13:45:17 GMT+0300",
  "data": {
    "id": 1234540307,
    "barcode": null,
    "sku": "P-7337",
    "mpn": "PP8938",
    "gtin": "99987653",
    "categories": [
      {
        "id": 601049212,
        "name": "العطور"
      }
    ]
  }
}
```
  </Tab>
</Tabs>


## Product Brand Updated Webhook Events Model

This event is triggered when a product brand has been updated.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="8347098" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.brand.updated",
  "merchant": 546096831,
  "created_at": "Wed Nov 19 2025 13:47:44 GMT+0300",
  "data": {
    "id": 1234540307,
    "barcode": null,
    "sku": "P-7337",
    "mpn": "PP8938",
    "gtin": "99987653",
    "brand": {
      "id": 1972405558,
      "name": "Brand1"
    }
  }
}
```
  </Tab>
</Tabs>


## Product Tags Updated Webhook Events Model

This event is triggered when a product tags have been updated.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="8347105" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.tags.updated",
  "merchant": 546096831,
  "created_at": "Wed Nov 19 2025 13:53:50 GMT+0300",
  "data": {
    "id": 1234540307,
    "barcode": null,
    "sku": "P-7337",
    "mpn": "PP8938",
    "gtin": "99987653",
    "tags": [
      {
        "id": 1133150248,
        "name": "tag1"
      },
      {
        "id": 1866255914,
        "name": "tag2"
      }
    ]
  }
}
```
  </Tab>
</Tabs>

## Products Channel Changed Webhook Event Model

This event is triggered when a product channel has been changed.


<Tabs>
  <Tab title="Data Schema">

<DataSchema id="4212181" />
  </Tab>
  <Tab title="Example">
```json
{
  "event": "product.channels.changed",
  "merchant": 1328842359,
  "created_at": "Mon Nov 18 2024 13:21:36 GMT+0300",
  "data": {
    "id": 710434693,
    "channels": [
      "app",
      "Vendors"
    ]
  }
}
```
  </Tab>
</Tabs>

## Product Webhook Events Model

The following includes 5 product webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab.

:::danger[Deprecation Notice]
Following two webhook events `product.updated`, `product.available`  are being deprecated. We recommend to use the new webhook events, as mentioned below: 
- product.price.updated
- product.status.updated
- product.image.updated
- product.category.updated
- product.brand.updated
- product.tags.updated
:::

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307419" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "product.created",
  "merchant": 1305146709,
  "created_at": "Mon Apr 17 2023 12:14:21 GMT+0300",
  "data": {
    "id": 1025569331,
    "promotion": {
      "title": null,
      "sub_title": null
    },
    "sku": "",
    "mpn": null,
    "gtin": null,
    "type": "booking",
    "name": "Product-Booking-API-Date-and-Time",
    "short_link_code": "aezvrRn",
    "urls": {
      "customer": "https://salla.sa/dev-wofftr4xsra5xtlv/product-booking-api-date-and-time/p1025569331",
      "admin": "https://s.salla.sa/products/1025569331"
    },
    "price": {
      "amount": 299,
      "currency": "SAR"
    },
    "taxed_price": {
      "amount": 343.85,
      "currency": "SAR"
    },
    "pre_tax_price": {
      "amount": 299,
      "currency": "SAR"
    },
    "tax": {
      "amount": 44.85,
      "currency": "SAR"
    },
    "description": "",
    "quantity": 20,
    "status": "hidden",
    "is_available": false,
    "views": 0,
    "sale_price": {
      "amount": 0,
      "currency": "SAR"
    },
    "sale_end": null,
    "require_shipping": false,
    "cost_price": null,
    "weight": 0,
    "weight_type": null,
    "with_tax": true,
    "url": "https://salla.sa/dev-wofftr4xsra5xtlv/product-booking-api-date-and-time/p1025569331",
    "main_image": null,
    "images": [],
    "sold_quantity": 0,
    "rating": {
      "total": 0,
      "count": 0,
      "rate": 0
    },
    "regular_price": {
      "amount": 299,
      "currency": "SAR"
    },
    "max_items_per_user": 1,
    "maximum_quantity_per_order": null,
    "show_in_app": false,
    "notify_quantity": null,
    "hide_quantity": true,
    "unlimited_quantity": false,
    "managed_by_branches": false,
    "services_blocks": {
      "installments": []
    },
    "calories": null,
    "customized_sku_quantity": false,
    "channels": [],
    "starting_price": null,
    "metadata": {
      "title": null,
      "description": null
    },
    "booking_details": {
      "id": 231783151,
      "type": "date_time",
      "session_duration": 50,
      "session_gap": 3,
      "sessions_count": 10,
      "location": "Medina",
      "time_strict_type": "days",
      "time_strict": 5,
      "overrides": [
        {
          "id": 1476756183,
          "date": "2023-04-23"
        },
        {
          "id": 904045008,
          "date": "2023-04-24"
        }
      ],
      "availabilities": [
        {
          "day": "sunday",
          "is_available": true,
          "times": [
            {
              "from": "09:30",
              "to": "13:00"
            },
            {
              "from": "12:00",
              "to": "22:00"
            }
          ]
        },
        {
          "day": "monday",
          "is_available": true,
          "times": [
            {
              "from": "10:00",
              "to": "12:00"
            }
          ]
        }
      ]
    },
    "allow_attachments": false,
    "is_pinned": false,
    "pinned_date": "2023-04-17 12:14:20",
    "sort": 0,
    "enable_upload_image": false,
    "updated_at": "2023-04-17 12:14:21",
    "options": [],
    "skus": [],
    "categories": [],
    "brand": null,
    "tags": []
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Review-Added-Webhook-Event-Model-Salla-Merchant-API-Salla-Docs

# Miscellaneous

Below are the webhook store events paired with their respective data schema related to the [Review Added webhook events](doc-421119):

## Review Added Webhook Event Model

This event is triggered when a product's review has been added.

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307410" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "review.added",
  "merchant": 1029864349,
  "created_at": "Wed Jul 7 2021 14:50:48 GMT+0300",
  "data": {
    "type": "rating",
    "rating": "5",
    "content": "Nice",
    "customer": {
      "id": "2107468057",
      "name": "Mohammed Ali",
      "mobile": "+28364687236547523745",
      "avatar": "https://i.ibb.co/jyqRQfQ/avatar-male.webp",
      "country": "السعودية",
      "city": "الرياض"
    },
    "product": {
      "id": "1653503260",
      "type": "codes",
      "promotion": {
        "title": null,
        "sub_title": null
      }
    },
    "status": {
      "id": "1298199463",
      "name": "تم التنفيذ",
      "customized": {
        "id": "1693817923",
        "name": "تم التنفيذ"
      },
      "can_cancel": false
    },
    "is_available": false,
    "sku": " ",
    "name": "FW180017",
    "price": {
      "amount": 1600,
      "currency": "SAR"
    },
    "sale_price": {
      "amount": "0",
      "currency": "SAR"
    },
    "currency": "SAR",
    "url": "https://store.test/nabilanazer/dpXnr",
    "thumbnail": null,
    "has_special_price": false,
    "regular_price": {
      "amount": "1600",
      "currency": "SAR"
    },
    "favorite": null,
    "order": {
      "id": "1289663293",
      "reference_id": "27290",
      "total": {
        "amount": "3732",
        "currency": "SAR"
      }
    },
    "date": [
      "2022-12-31"
    ],
    "items": [
      {
        "name": "FW180016",
        "quantity": "1"
      }
    ]
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Shipments-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Shipments

Below are the webhook store events paired with their respective data schema related to the [Shipments webhook events](https://docs.salla.dev/doc-421119):

## Shipments Webhook Events Model

The following includes 4 shipments webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307439" />
      
  </Tab>
  <Tab title="Example">
    
```js
{
  "event": "shipment.creating",
  "merchant": 136409261,
  "created_at": "Sun Jan 29 2023 21:16:38 GMT+0300",
  "data": {
    "id": 362985662,
    "order_id": 560695738,
    "order_reference_id": 48927,
    "reference": {
      "external_id": "34567898",
      "external_additional_id": "OM656545543"
    },
    "created_at": {
      "date": "2023-01-29 21:16:38.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "type": "shipment",
    "courier_id": 1927161457,
    "courier_name": "Shipping App",
    "courier_logo": "https://company.com/logo.png",
    "shipping_number": "846984645",
    "tracking_number": "4324233",
    "pickup_id": null,
    "trackable": true,
    "tracking_link": "https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345",
    "label": {
      "format": "pdf",
      "url": "https://company.com/lable.pdf"
    },
    "payment_method": "cod",
    "source": "api",
    "status": "delivered",
    "total": {
      "amount": 25.5,
      "currency": "SAR"
    },
    "cash_on_delivery": {
      "amount": 10.7,
      "currency": "SAR"
    },
    "is_international": false,
    "total_weight": {
      "value": 5,
      "units": "kg"
    },
    "billing_account": "merchant",
    "description": "Fashion Apparel - 3 T-Shirts",
    "remarks": "Customer requested delivery after 5 PM",
    "shipping_route": {
       "id": 1867988940,
       "name": "Default Route"
    },
    "service_types": [
        "international",
        "normal",
        "fulfillment"
    ],
    "packages": [
      {
        "item_id": 2077288690,
        "external_id": null,
        "name": "منتج تجريبي",
        "sku": "6ytrrhrhr",
        "price": {
          "amount": 25.5,
          "currency": "SAR"
        },
        "quantity": 1,
        "weight": {
          "value": 5,
          "unit": "kg"
        }
      }
    ],
    "ship_from": {
      "type": "branch",
      "name": "الفرع الرئيسي",
      "email": "",
      "phone": "966920034002",
      "country": "السعودية",
      "city": "Mecca",
      "region": {
        "id": 1473353380,
        "name": "منطقة الرياض",
        "code": "RD"
      },
      "address_line": "Mecca,السعودية",
      "street_number": null,
      "block": "العمل",
      "short_address": "RHSA3184",
      "building_number": "5436",
      "additional_number": "8976",
      "postal_code": null,
      "latitude": 21.3825905096851,
      "longitude": 39.77319103068542,
      "branch_id": 1987977866
    },
    "ship_to": {
      "type": "address",
      "name": "Username",
      "email": "username@email.com",
      "phone": "966501806978",
      "country": "السعودية",
      "city": "الرياض",
      "region": {
        "id": 1473353380,
        "name": "منطقة الرياض",
        "code": "RD"
      },
      "address_line": " شارع 2345، الحي السلام 95128،, شارع عبدالله  سنابل السلام  مكة  السعوديه,, الرياض, السعودية",
      "street_number": "2345",
      "block": "السلام",
      "short_address": "RHMA3184",
      "building_number": "2846",
      "additional_number": "7556",
      "postal_code": "95128",
      "latitude": 21.382590509685,
      "longitude": 39.773191030685
    },
    "meta": {
      "app_id": 1222362158,
      "policy_options": {
        "boxes": 1
      }
    }
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Shipping-Zone-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Shippings

Below are the webhook store events paired with their respective data schema related to the [Shipping Companies & Shipping Zones webhook events](doc-421119):

## Shipping Zone Webhook Events Model

The following includes 2 shipping zone webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307427" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "shipping.zone.created",
  "merchant": 1305146709,
  "created_at": "Thu Apr 14 2022 11:21:47 GMT+0300",
  "data": {
    "id": 870442223,
    "zone_code": ".AE.ajman-city",
    "company": {
      "id": 488260393,
      "slug": null
    },
    "country": {
      "id": 566146469,
      "name": "الامارات",
      "name_en": "United Arab Emirates",
      "code": "AE",
      "mobile_code": "+971"
    },
    "city": {
      "id": 374975390,
      "name": "مدينة عجمان",
      "name_en": "AJMAN CITY"
    },
    "cities_excluded": [
      {
        "id": 257742554,
        "name": "أبو حليفة",
        "name_en": "ABU HALIFA"
      },
      {
        "id": 81998629,
        "name": "الأحمدي",
        "name_en": "AHMADI"
      }
    ],
    "fees": {
      "amount": "30",
      "currency": "SAR",
      "type": "rate",
      "weight_unit": "kg",
      "up_to_weight": "15",
      "amount_per_unit": "2",
      "per_unit": "1"
    },
    "cash_on_delivery": {
      "status": true,
      "fees": "12"
    },
    "duration": "3-5"
  }
}
```
      
  </Tab>
</Tabs>

## Shipping Company Webhook Events Model

The following includes 3 shipping company webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307428" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "shipping.company.deleted",
  "merchant": 1305146709,
  "created_at": "Thu Apr 07 2022 13:48:22 GMT+0300",
  "data": {
    "id": 488260393,
    "name": "شركة سريع",
    "status": false
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Special-Offer-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Special Offer

Below are the webhook store events paired with their respective data schema related to the [Special Offer webhook events](https://docs.salla.dev/doc-421119):

## Special Offer Webhook Events Model

The following includes 2 special offer webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">
      
<DataSchema id="11412295" />
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "specialoffer.updated",
  "merchant": 1305146709,
  "created_at": "Tue Jan 25 2022 13:26:20 GMT+0300",
  "data": {
    "id": 1649524234,
    "name": "اشتري 1 واحصل على الاخر مجانا",
    "message": "اشتري قطعة واحصل على قطعة واحدة مجاناً من التصنيفات التالية",
    "expiry_date": null,
    "offer_type": "buy_x_get_y",
    "status": "inactive",
    "buy": {
      "type": "category",
      "quantity": "1",
      "categories": [
        {
          "id": 1548056,
          "name": "البلايز",
          "avatar": "sicon-store",
          "created_at": "2021-11-01 16:46:06",
          "updated_at": "2022-01-16 15:35:55",
          "deleted_at": null,
          "store_id": 577778,
          "parent_id": 0,
          "products_counts": 3,
          "show_in_menu": 0,
          "sort_order": 2,
          "status": "active",
          "has_hidden_products": 0,
          "show_in_app": 1,
          "extra_attributes": [],
          "custom_url": null
        }
      ]
    },
    "get": {
      "categories": [
        {
          "id": 256950451,
          "name": "البلايز",
          "urls": {
            "customer": "https://salla.sa/dev-wofftr4xsra5xtlv/category/zvawao",
            "admin": "https://s.salla.sa/categories"
          },
          "items": [],
          "parent_id": 0,
          "status": "active",
          "sort_order": 2,
          "sub_categories": []
        }
      ],
      "type": "category",
      "discount_type": "free-product"
    }
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Store-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Store

Below are the webhook store events paired with their respective data schema related to the [Store webhook events](https://docs.salla.dev/doc-421119):

## Store Webhook Events Model

The following includes 5 store webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307409" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "store.branch.updated",
  "merchant": "1029864349",
  "created_at": "Wed Jun 30 2021 15:24:18 GMT+0300",
  "data": {
    "id": "1866839222",
    "name": "Riyadh Branch",
    "status": "active",
    "location": {
      "lat": "21.4267",
      "lang": "39.8261"
    },
    "contacts": {
      "telephone": "0555555555",
      "phone": "+96652318526",
      "whatsapp": "+96652318526"
    },
    "preparation_time": "2",
    "is_open": false,
    "closest_time": {
      "from": "07:00",
      "to": "12:00"
    },
    "working_hours": [
      {
        "name": "الثلاثاء",
        "times": [
          {
            "from": "07:00",
            "to": "12:00"
          }
        ]
      }
    ],
    "is_cod_available": true,
    "is_default": false,
    "type": {},
    "cod_cost": "10.00",
    "country": {
      "id": 1473353380,
      "name": "السعودية",
      "name_en": "Saudi Arabia",
      "code": "SA",
      "mobile_code": "+966"
    },
    "city": {
      "id": 1473353380,
      "name": "الرياض",
      "name_en": "Riyadh",
      "country_id": 1473353380
    }
  }
}
```
      
  </Tab>
</Tabs>

## Store Tax Webhook Events Model

This event is triggered when a store tax has been created.

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307413" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "storetax.created",
  "merchant": 814202285,
  "created_at": "Tue Aug 03 2021 09:35:16 GMT+0300",
  "data": {
    "id": 5541564,
    "tax": "5",
    "status": "active",
    "country": "All Countries"
  }
}
```
      
  </Tab>
</Tabs>

## Store Owner Changed Webhook Event Model

This event is triggered when a store owner is changed to another user.

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="9554130" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "store.owner.changed",
  "merchant": 1234509876,
  "created_at": "Wed Sep 17 2025 14:57:43 GMT+0300",
  "data": {
    "id": 8114012345,
    "name": "User",
    "mobile": "555555555",
    "mobile_code": "+966",
    "email": "test@gmail.com",
    "avatar": "https://i.ibb.co/jyqRQfQ/avatar-male.webp",
    "role": "user",
    "status": "active",
    "enabled": true
  }
}
```
      
  </Tab>
</Tabs>

---

