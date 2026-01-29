# Merchants Events  Invoice Events

## Table of Contents

- [merchants-events/Invoice-Events](#merchants-events-invoice-events)
- [merchants-events/Order-Events](#merchants-events-order-events)
- [merchants-events/Review-Events](#merchants-events-review-events)
- [merchants-events/Shipment-Events](#merchants-events-shipment-events)
- [merchants-events/Shipping-Company-Events](#merchants-events-shipping-company-events)
- [merchants-events/Shipping-Zone-Events](#merchants-events-shipping-zone-events)
- [merchants-events/Special-Offer-Events](#merchants-events-special-offer-events)
- [merchants-events/Store-Branch-Events](#merchants-events-store-branch-events)

---

## merchants-events/Invoice-Events

# Invoice Events

This model defines the structure for events triggered when an invoice is created.

## Available Events

- `invoice.created` - Triggered when an invoice is created for an order

## Event Type

:::note[]
    **Asynchronous Event** - Processed in the background.
:::

## Invoice Context Object

<Tabs>
  <Tab title="Schema">
    
<DataSchema id="10641070" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "invoice.created",
    "merchant": 1419273030,
    "created_at": "Thu Nov 06 2025 10:10:40 GMT+0300",
    "data": {
      "id": 1197159170,
      "invoice_number": 1,
      "uuid": "77d5bb30-1c79-4dee-b1c5-5bc1ce9bd1e8",
      "order_id": 1848408264,
      "invoice_reference_id": null,
      "type": "فاتورة ضريبية",
      "slug": 1,
      "date": "2025-11-06 10:10:40",
      "qr_code": null,
      "payment_method": "bank",
      "sub_total": { "amount": 588, "currency": "SAR" },
      "shipping_cost": { "amount": 0, "taxable": true, "currency": "SAR" },
      "cod_cost": { "amount": 0, "taxable": true, "currency": "SAR" },
      "discount": { "amount": 0, "currency": "SAR" },
      "tax": { "percent": 15, "amount": { "amount": 88.2, "currency": "SAR" } },
      "total": { "amount": 676.2, "currency": "SAR" },
      "shipping_cost_discount": { "amount": 0, "currency": "SAR" },
      "items": [
        {
          "id": 539313127,
          "item_id": 512764355,
          "product_id": 910573256,
          "name": "فستان",
          "sku": "15504449-300000237300-",
          "quantity": 1,
          "type": "product",
          "price": { "amount": 289, "currency": "SAR" },
          "discount": { "amount": 0, "currency": "SAR" },
          "tax": {
            "percent": 15,
            "amount": { "amount": 43.35, "currency": "SAR" }
          },
          "total": { "amount": 332.35, "currency": "SAR" },
          "options": [
            {
              "id": 1206242616,
              "product_option_id": 865493990,
              "name": "المقاس",
              "type": "radio",
              "value": {
                "id": 1778308410,
                "name": "38 - S",
                "price": { "amount": 0, "currency": "SAR" },
                "option_value": ""
              }
            },
            {
              "id": 297987129,
              "product_option_id": 226263783,
              "name": "اللون",
              "type": "radio",
              "value": {
                "id": 1737306629,
                "name": "بيج",
                "price": { "amount": 0, "currency": "SAR" },
                "option_value": ""
              }
            }
          ]
        },
        {
          "id": 1912759008,
          "item_id": 338130638,
          "product_id": 802593739,
          "name": "فستان",
          "sku": "15504448-30000024230-",
          "quantity": 1,
          "type": "product",
          "price": { "amount": 299, "currency": "SAR" },
          "discount": { "amount": 0, "currency": "SAR" },
          "tax": {
            "percent": 15,
            "amount": { "amount": 44.85, "currency": "SAR" }
          },
          "total": { "amount": 343.85, "currency": "SAR" },
          "options": [
            {
              "id": 1031023163,
              "product_option_id": 690405601,
              "name": "المقاس",
              "type": "radio",
              "value": {
                "id": 1985362445,
                "name": "40 - M",
                "price": { "amount": 0, "currency": "SAR" },
                "option_value": ""
              }
            }
          ]
        }
      ],
      "company": null,
      "customer": {
        "id": 2024468411,
        "first_name": "Osama",
        "last_name": "Khd",
        "mobile": 780865752,
        "mobile_code": "+962",
        "email": "osama.k@salla.sa",
        "avatar": "https://cdn.assets.salla.network/prod/admin/cp/assets/images/avatar_male.png",
        "gender": "male",
        "birthday": {
          "date": "1983-04-17 00:00:00.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        },
        "country_code": "JO",
        "currency": "SAR",
        "updated_at": {
          "date": "2025-11-05 20:26:46.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        },
        "address": {
          "country": "السعودية",
          "city": "الرياض",
          "district": null,
          "street_name": "olaya",
          "additional_number": null,
          "building_number": null,
          "postal_code": "1121",
          "description": "building 1"
        }
      }
    }
  },
  "settings": {},
  "merchant": {
    "id": 1419273030
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

```typescript
export default async (context: Invoice): Promise<Resp> => {
  console.log('Invoice created event triggered');
  
  const { payload, settings, merchant } = context;
  const { data: invoice } = payload;

  const response = await fetch(settings.accountingApiUrl, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      invoice_id: invoice.id,
      order_id: invoice.order_id,
      amount: invoice.amount,
      merchant_id: merchant.id
    })
  });
  
  return Resp.success();
};
```

---

## merchants-events/Order-Events

# Order Events

This model defines the structure for events triggered when a order is created, updated, or deleted in a merchant's store.

## Available Events

- `order.created` - Triggered when order is created
- `order.updated` - Triggered when order details are updated
- `order.status.updated` - Triggered when the order status changes
- `order.cancelled` - Triggered when an order is cancelled
- `order.refunded` - Triggered when an order is refunded
- `order.deleted` - Triggered when an order is deleted
- `order.products.updated` - Triggered when products within an order are updated
- `order.payment.updated` - Triggered when order payment details are updated
- `order.coupon.updated` - Triggered when an order coupon is applied, updated, or removed
- `order.total.price.updated` - Triggered when the total price of an order is updated

## Event Type
:::note[]
**Asynchronous Event** - Processed in the background after the order operation completes.
:::

## Common Use Cases

- Sync order information with external systems
- Track order status updates
- Track coupons applied to an order

## Order Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10785750" />

  </Tab>
    <Tab title="Example">
        <Tabs>
        <Tab title="Orders">

```json
{
  "payload": {
    "event": "order.created",
    "merchant": 1305146709,
    "created_at": "Sun Jun 26 2022 12:21:48 GMT+0300",
    "data": {
      "id": 2116149737,
      "reference_id": 41027662,
      "urls": {
        "customer": "https://salla.sa/dev-wofftr4xsra5xtlv/order/DXZbOz68qjnYaOw04oBa35wVELBpJyxo",
        "admin": "https://s.salla.sa/orders/order/DXZbOz68qjnYaOw04oBa35wVELBpJyxo",
        "rating": "https://store-test.com/rating-link",
        "checkout": "https://store-test.com/checkout"
      },
      "date": {
        "date": "2022-06-26 12:21:45.000000",
        "timezone_type": 3,
        "timezone": "Asia/Riyadh"
      },
      "draft": false,
      "read": true,
      "source": "store",
      "source_device": "desktop",
      "source_details": {
        "type": "direct",
        "value": null,
        "device": "desktop",
        "user-agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.0.0 Safari/537.36",
        "ip": "31.166.186.78"
      },
      "status": {
        "id": 566146469,
        "name": "بإنتظار المراجعة",
        "slug": "under_review",
        "customized": {
          "id": 986688842,
          "name": "بإنتظار المراجعة"
        }
      },
      "receipt_image": "https://cdn.salla.sa/jKxK/md4Pv5jeLEX52zWTboKSVr8VmlX5tNbiu9YF00C0.png",
      "payment_method": "bank",
      "currency": "SAR",
      "amounts": {
        "sub_total": {
          "amount": 186,
          "currency": "SAR"
        },
        "shipping_cost": {
          "amount": 15,
          "currency": "SAR"
        },
        "cash_on_delivery": {
          "amount": 0,
          "currency": "SAR"
        },
        "tax": {
          "percent": "0.00",
          "amount": {
            "amount": 0,
            "currency": "SAR"
          }
        },
        "discounts": [
          {
            "title": "new offer",
            "type": "special",
            "code": "new offer",
            "discount": "5.00",
            "discounted_shipping": 0
          }
        ],
        "total": {
          "amount": 196,
          "currency": "SAR"
        }
      },
      "shipping": {
        "id": 1833934431,
        "app_id": null,
        "company": "السعودية",
        "logo": "",
        "receiver": {
          "name": "Mohammed Ali",
          "email": "usertest@gmail.com",
          "phone": "999123456789"
        },
        "shipper": {
          "name": "Demo",
          "company_name": "dev-wofftr4xsra5xtlv",
          "email": "wofftr4xsra5xtlv@email.partners",
          "phone": "966500000000"
        },
        "pickup_address": {
          "country": "السعودية",
          "country_code": "SA",
          "city": "مكة",
          "shipping_address": "شارع عبدالله,السلام,23233, سنابل السلام, مكة,السعودية",
          "street_number": "شارع عبدالله",
          "block": "السلام",
          "postal_code": "23233",
          "geo_coordinates": {
            "lat": 21.3825905096851,
            "lng": 39.77319103068542
          }
        },
        "address": {
          "country": "SA",
          "country_code": "SA",
          "city": "جدة",
          "shipping_address": " شارع ابو امية الضمري، الحي الزهراء ،, جدة, السعودية",
          "street_number": "ابو امية الضمري",
          "block": "الزهراء",
          "postal_code": "",
          "geo_coordinates": {
            "lat": 0,
            "lng": 0
          }
        },
        "shipment": {
          "id": "0",
          "pickup_id": null,
          "tracking_link": "0",
          "label": []
        },
        "policy_options": []
      },
      "shipments": [
        {
          "id": 649964784,
          "created_at": null,
          "type": "shipment",
          "courier_id": 802226618,
          "courier_name": "أوتو",
          "courier_logo": "https://salla-dev-portal.s3.eu-central-1.amazonaws.com/uploads/LUZaDEGwzFRDJKO7XVLXtix71Zb8Z2vBt6xwHrwZ.png",
          "shipping_number": null,
          "tracking_number": null,
          "pickup_id": null,
          "trackable": false,
          "tracking_link": null,
          "label": null,
          "payment_method": "cod",
          "source": "store",
          "status": "in_progress",
          "total": {
            "amount": 175.47,
            "currency": "SAR"
          },
          "cash_on_delivery": {
            "amount": 0,
            "currency": "SAR"
          },
          "is_international": true,
          "total_weight": {
            "value": 0.2,
            "units": "kg"
          },
          "shipping_route": {
            "id": 1867988940,
            "name": "Default Route"
          },
          "packages": [
            {
              "item_id": 2077288690,
              "external_id": null,
              "quantity": 1,
              "weight": {
                "value": 0.2,
                "units": "kg"
              }
            }
          ],
          "ship_from": {
            "type": "branch",
            "name": "المستودع الرئيسي التجريبي",
            "email": "",
            "phone": "966555855555",
            "country": "السعودية",
            "city": "Medina",
            "region": {
              "id": 1473353380,
              "name": "منطقة الرياض",
              "code": "RD"
            },
            "address_line": "3391 حسين بين عبدلله بين ضميرا,مسجد الدرع,00000, 3391 حسين بين عبدلله بين ضميرا, الدرق موثق, مدينة 42313 8700, سعودي عربية, Medina,السعودية",
            "street_number": "3391 حسين بين عبدلله بين ضميرا",
            "block": "مسجد الدرع",
            "short_address": "RHSA3184",
            "building_number": "5436",
            "additional_number": "8976",
            "postal_code": "00000",
            "latitude": 24.524655575978006,
            "longitude": 39.56918120384216,
            "branch_id": 1790435930
          },
          "ship_to": {
            "type": "address",
            "name": "Test Username",
            "email": "user@gmail.com",
            "phone": "971501960991",
            "country": "الامارات",
            "city": "أبو ظبي",
            "region": {
              "id": 1473353380,
              "name": "منطقة الرياض",
              "code": "RD"
            },
            "address_line": " شارع ijaz street، الحي Shakhbout city 70633،, villa 24,, أبو ظبي, الامارات",
            "street_number": "ijaz street",
            "block": "Shakhbout city",
            "short_address": "RHMA3184",
            "building_number": "2846",
            "additional_number": "7556",
            "postal_code": "70633",
            "latitude": 0,
            "longitude": 0
          },
          "meta": {
            "app_id": 846904320,
            "policy_options": {
              "dimensions": {
                "length": "",
                "width": "",
                "height": ""
              }
            }
          }
        }
      ],
      "can_cancel": true,
      "show_weight": false,
      "can_reorder": true,
      "is_pending_payment": false,
      "pending_payment_ends_at": 172796,
      "total_weight": "٠٫٢٥ كجم",
      "shipment_branch": [],
      "customer": {
        "id": 225167971,
        "first_name": "Mohammed",
        "last_name": "Ali",
        "mobile": 501806978,
        "mobile_code": "+966",
        "email": "usertest@gmail.com",
        "urls": {
          "customer": "https://salla.sa/dev-wofftr4xsra5xtlv/profile",
          "admin": "https://s.salla.sa/customers/l7mYBdgXA9xJwWZRZK8WD42GNkZbjvRO"
        },
        "avatar": "https://cdn.salla.sa/customer_profiles/5i6SUhu9dlF1fvL3EcV98U644eOlG9jcEipz6dOo.jpg",
        "gender": "female",
        "birthday": {
          "date": "1997-06-03 00:00:00.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        },
        "city": "جدة",
        "country": "السعودية",
        "country_code": "SA",
        "currency": "SAR",
        "location": "",
        "updated_at": {
          "date": "2022-06-22 10:20:14.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        }
      },
      "items": [
        {
          "id": 70815337,
          "name": "بيتزا",
          "sku": "54534534",
          "quantity": 1,
          "currency": "SAR",
          "weight": 0.25,
          "weight_label": "٠٫٢٥ كجم",
          "amounts": {
            "price_without_tax": {
              "amount": 186,
              "currency": "SAR"
            },
            "total_discount": {
              "amount": 5,
              "currency": "SAR"
            },
            "tax": {
              "percent": "0.00",
              "amount": {
                "amount": 0,
                "currency": "SAR"
              }
            },
            "total": {
              "amount": 186,
              "currency": "SAR"
            }
          },
          "notes": "",
          "product": {
            "id": 720881993,
            "type": "food",
            "promotion": {
              "title": "اطلبها ساخنه",
              "sub_title": "بيتزا خضار مشكل"
            },
            "status": "sale",
            "is_available": true,
            "sku": "54534534",
            "name": "بيتزا",
            "price": {
              "amount": 66,
              "currency": "SAR"
            },
            "sale_price": {
              "amount": 45,
              "currency": "SAR"
            },
            "currency": "SAR",
            "url": "https://salla.sa/dev-wofftr4xsra5xtlv/بيتزا/p720881993",
            "thumbnail": "https://cdn.salla.sa/bYQEn/buItWZf4OLbaTmL7vTMlDUWLOn20hfpq3QUbD2AB.jpg",
            "has_special_price": false,
            "regular_price": {
              "amount": 66,
              "currency": "SAR"
            },
            "calories": "600.00",
            "mpn": null,
            "gtin": null,
            "favorite": null,
            "starting_price": null
          },
          "options": [
            {
              "id": 1197801866,
              "product_option_id": 60176141,
              "name": "SIZE",
              "type": "checkbox",
              "value": [
                {
                  "id": 408420634,
                  "name": "BIG",
                  "price": {
                    "amount": 120,
                    "currency": "SAR"
                  }
                }
              ]
            },
            {
              "id": 289546379,
              "product_option_id": 1674915438,
              "name": "الاضافات",
              "type": "checkbox",
              "value": [
                {
                  "id": 152115913,
                  "name": "بصل",
                  "price": {
                    "amount": 0,
                    "currency": "SAR"
                  }
                },
                {
                  "id": 1526610378,
                  "name": "فلفل",
                  "price": {
                    "amount": 0,
                    "currency": "SAR"
                  }
                }
              ]
            }
          ],
          "images": [],
          "codes": [],
          "files": []
        }
      ],
      "product_reservations": [
        {
          "id": 1289748598,
          "from": "01:10",
          "to": "01:40",
          "date": "2023-04-18"
        }
      ],
      "bank": {
        "id": 326553500,
        "bank_name": "البنك الأهلي التجاري",
        "bank_id": 1473353380,
        "account_name": "Demo Account",
        "account_number": "000000608010167519",
        "iban_number": "SA2380000382608010130308",
        "status": "active"
      },
      "tags": []
    }
  },
  "settings": {
    "syncEnabled": true,
    "webhookUrl": "https://api.example.com/brands",
    "apiKey": "your-api-key"
  },
  "merchant": {
    "id": 1419273030
  }
}
```

  </Tab>
  <Tab title="Order Status">
    ```
      {
  "payload": {
    "event": "order.status.updated",
    "merchant": 193718979,
    "created_at": "Wed Aug 17 2022 23:59:38 GMT+0300",
    "data": {
      "id": 198290473,
      "status": "تم التنفيذ",
      "customized": null,
      "note": "تم إرسال تفاصيل الطلب  إلى بريد العميل",
      "created_at": {
        "date": "2022-08-17 23:59:38.000000",
        "timezone_type": 3,
        "timezone": "Asia/Riyadh"
      },
      "order": {
        "id": 629263027,
        "reference_id": 42264,
        "urls": {
          "customer": "https://web-f71c00b38eb7308ff0ec2198afc21531.salla.group/test/order/P4GV9LQN3veZl1PV6AWBR6rJ5kzEoxYd",
          "admin": "https://dashboard-f71c00b38eb7308ff0ec2198afc21531.salla.group/orders/order/P4GV9LQN3veZl1PV6AWBR6rJ5kzEoxYd",
          "rating": "https://store-test.com/rating-link",
          "checkout": "https://store-test.com/checkout"
        },
        "date": {
          "date": "2022-08-17 20:59:36.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        },
        "source": "store",
        "source_device": "desktop",
        "source_details": {
          "type": "direct",
          "value": null,
          "device": "desktop",
          "user-agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.115 Safari/537.36",
          "ip": null
        },
        "first_complete_at": {
          "date": "2022-08-17 23:59:36.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        },
        "status": {
          "id": 1298199463,
          "name": "تم التنفيذ",
          "slug": "completed"
        },
        "payment_method": "cod",
        "currency": "SAR",
        "amounts": {
          "sub_total": {
            "amount": 246,
            "currency": "SAR"
          },
          "shipping_cost": {
            "amount": 33,
            "currency": "SAR"
          },
          "cash_on_delivery": {
            "amount": 1,
            "currency": "SAR"
          },
          "tax": {
            "percent": "0.00",
            "amount": {
              "amount": 0,
              "currency": "SAR"
            }
          },
          "discounts": [
            {
              "title": "منتج مجاني: عطر إترنتي مومنت من كالفن كلاين للنساء، او دي بارفان، 100 مل",
              "type": "loyalty_prize",
              "code": "FREE_PRODUCT",
              "discount": "126.00",
              "currency": "SAR"
            }
          ],
          "total": {
            "amount": 154,
            "currency": "SAR"
          }
        },
        "shipping": {
          "id": 147641223,
          "app_id": "618297749",
          "company": "محمول",
          "logo": "https://cdn.salla.sa/jKxK/y1fgSXdUBbKwKXb6jE3dbmx8zDozt5KuQJ9McXX9.png",
          "receiver": {
            "name": "User Name",
            "email": "test@user.name",
            "phone": "96652318526"
          },
          "shipper": {
            "name": "Mohammed Test",
            "company_name": "Test",
            "email": "Test@salla.sa",
            "phone": "96652318526"
          },
          "pickup_address": {
            "country": "السعودية",
            "country_code": "SA",
            "city": "المدينة المنورة",
            "shipping_address": "Macca,Macca,1111, Macca, المدينة المنورة,السعودية",
            "street_number": "Macca",
            "block": "Macca",
            "postal_code": "1111",
            "geo_coordinates": {
              "lat": 24.45196726,
              "lng": 39.587448815
            }
          },
          "address": {
            "country": "SA",
            "country_code": "SA",
            "city": "الرياض",
            "shipping_address": " شارع Macca، الحي Macca 1111،, Macca,, الرياض, السعودية",
            "street_number": "Macca",
            "block": "Macca",
            "postal_code": "1111",
            "geo_coordinates": {
              "lat": 0,
              "lng": 0
            }
          },
          "shipment": {
            "id": "SALLA000121",
            "pickup_id": "SALLA000121001",
            "tracking_link": "SALLA000121",
            "label": []
          },
          "policy_options": {
            "return_police": "0",
            "restore_items": "1",
            "refund_loyalty_prize_points": "on",
            "send_status_sms": true,
            "companyServiceType": "",
            "boxes": "1"
          }
        },
        "can_cancel": false,
        "show_weight": false,
        "can_reorder": false,
        "is_pending_payment": false,
        "pending_payment_ends_at": 0,
        "total_weight": "١ كجم",
        "shipment_branch": [
          {
            "id": 2019138561,
            "name": "الرئيسي",
            "status": "active",
            "is_default": true,
            "type": {}
          }
        ],
        "customer": {
          "id": 1779795066,
          "name": "Test Salla",
          "mobile": "+96652318526",
          "email": "Test.2022@salla.sa",
          "avatar": "https://dashboard-f71c00b38eb7308ff0ec2198afc21531.salla.group/cp/assets/images/avatar_male.png",
          "country": "السعودية",
          "city": "الرياض"
        },
        "items": [
          {
            "id": 2105258904,
            "product_id": 2047473815,
            "name": "سي كيه وان شوك من كالفن كلاين، فور هي، 100 مل",
            "sku": "",
            "quantity": 1,
            "weight": 0.5,
            "amounts": {
              "price_without_tax": {
                "amount": 120,
                "currency": "SAR"
              },
              "total_discount": {
                "amount": 0,
                "currency": "SAR"
              },
              "tax": {
                "percent": "0.00",
                "amount": {
                  "amount": 0,
                  "currency": "SAR"
                }
              },
              "total": {
                "amount": 120,
                "currency": "SAR"
              }
            }
          },
          {
            "id": 1329648281,
            "product_id": 674027926,
            "name": "عطر إترنتي مومنت من كالفن كلاين للنساء، او دي بارفان، 100 مل",
            "sku": "",
            "quantity": 1,
            "weight": 0.5,
            "amounts": {
              "price_without_tax": {
                "amount": 126,
                "currency": "SAR"
              },
              "total_discount": {
                "amount": 126,
                "currency": "SAR"
              },
              "tax": {
                "percent": "0.00",
                "amount": {
                  "amount": 0,
                  "currency": "SAR"
                }
              },
              "total": {
                "amount": 126,
                "currency": "SAR"
              }
            }
          }
        ],
        "total": {
          "amount": 154,
          "currency": "SAR"
        }
      }
    }
  },
  "settings": {
    "syncEnabled": true,
    "webhookUrl": "https://api.example.com/brands",
    "apiKey": "your-api-key"
  },
  "merchant": {
    "id": 1419273030
  }
}
      ```
  </Tab>
        </Tabs>
    </Tab>
  

</Tabs>

## Example Implementations

### Sync Order to External System

```typescript
export default async (context: Order): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: order } = payload;

  // Prepare order data for external system
  const externalOrderData = {
    external_id: order.id,
    status: order.status,
    synced_at: new Date().toISOString()
  };

  // Send to external API
  const response = await fetch(`https://api.mock.com/v1/order`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(externalOrderData)
  });

  const result = await response.json();
  
  const data = {
    order_id: order.id,
    external_id: result.id,
    synced_at: new Date().toISOString()
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionallly called. The default status is 200.
  * The .setMessage() is optional. 
  * Incase there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data)

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Navigate to Orders">
    Go to the Orders section in the demo store dashboard
  </Step>
  <Step title="Trigger the event">
    Create, update, or delete an Order
  </Step>
  <Step title="Test in preview">
    Use the order ID in the App Function preview panel and click "Save and Preview"
  </Step>
</Steps>

---

## merchants-events/Review-Events

# Review Events

This model defines the structure for events triggered when a customer adds a product review.

## Available Events

- `review.added` - Triggered when a customer submits a product review

## Event Type

:::note[]
    **Asynchronous Event** - Processed in the background.
:::

## Review Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10641077" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "review.added",
    "merchant": 1419273030,
    "created_at": "Wed Nov 05 2025 20:18:07 GMT+0300",
    "data": {
      "type": "rating",
      "rating": "4",
      "content": "Tamam",
      "customer": {
        "id": 2024468411,
        "name": "Osama K",
        "mobile": "+962780865752",
        "email": "osama.k@salla.sa",
        "avatar": "https://cdn.assets.salla.network/prod/stores/themes/default/assets/images/avatar_male.png",
        "country": "السعودية",
        "city": "الرياض"
      },
      "product": {
        "id": 802593739,
        "type": "product",
        "promotion": { "title": null, "sub_title": null },
        "quantity": null,
        "status": "sale",
        "is_available": true,
        "sku": "15504448-30000024230-",
        "name": "فستان",
        "price": { "amount": 149, "currency": "SAR" },
        "sale_price": { "amount": 149, "currency": "SAR" },
        "currency": "SAR",
        "url": "https://demostore.salla.sa/dev-fjb4uoys3xuhrgpb/فستان/p802593739",
        "thumbnail": "https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/ACknxzEIkcTdaFr1DETbQlXo5UwupBedJ9ZGyR8v.jpg",
        "has_special_price": true,
        "regular_price": { "amount": 299, "currency": "SAR" },
        "calories": null,
        "mpn": null,
        "gtin": null,
        "description": "المقاس36نصف محيط الخصر17الطول107الكم53818107540191095.542201095.544211126",
        "favorite": null,
        "features": { "availability_notify": null, "show_rating": true }
      },
      "order": {
        "id": 1848408264,
        "reference_id": 217268845,
        "urls": {
          "customer": "https://demostore.salla.sa/dev-fjb4uoys3xuhrgpb/order/gGxWqeV",
          "admin": "https://s.salla.sa/orders/order/gGxWqeV"
        },
        "total": { "amount": 676.2, "currency": "SAR" },
        "exchange_rate": {
          "base_currency": "SAR",
          "exchange_currency": "SAR",
          "rate": "1.00000000"
        },
        "date": {
          "date": "2025-11-05 19:17:50.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        },
        "source": "abandoned-cart",
        "status": {
          "id": 1025888376,
          "name": "تم الشحن",
          "slug": "shipped",
          "original": { "id": 814202285, "name": "تم الشحن" }
        },
        "draft": false,
        "read": true,
        "can_cancel": false,
        "can_reorder": false,
        "payment_method": "bank",
        "is_pending_payment": false,
        "pending_payment_ends_at": 71982,
        "features": {
          "shippable": true,
          "digitalable": false,
          "pickable": false,
          "has_suspicious_alert": false,
          "bullet_delivery": {
            "is_bullet_delivery": false,
            "bullet_countdown": -2717721
          }
        },
        "payment_actions": {
          "refund_action": {
            "has_refund_amount": false,
            "payment_method_label": "حوالة بنكية",
            "can_print_refund_invoice": false,
            "paid_amount": { "amount": 0, "currency": "SAR" },
            "refund_amount": { "amount": 0, "currency": "SAR" },
            "loyalty_point_programs": [],
            "can_send_sms": false,
            "can_send_sms_msg": "يرجى تفعيل احد مزودين خدمة SMS من صفحة ربط الخدمات",
            "can_refund_loyalty_prize_points": false,
            "can_restore_loyalty_buy_from_store_points": false
          },
          "remaining_action": {
            "has_remaining_amount": true,
            "payment_method_label": "حوالة بنكية",
            "paid_amount": { "amount": 0, "currency": "SAR" },
            "checkout_url": "https://pay.salla.sa/gateway/checkout/G21mbRaXWjKJ9YqArkZODleyvewAo1qaPnGoB82ELx6gz4N53w0MdV7B",
            "remaining_amount": { "amount": 676.2, "currency": "SAR" }
          }
        },
        "items": [
          {
            "name": "فستان",
            "quantity": 1,
            "thumbnail": "https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/m1JuFPTZeyNjtDm9pNK32leRr6m7zsetmFLlSw52.jpg"
          },
          {
            "name": "فستان",
            "quantity": 1,
            "thumbnail": "https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/ACknxzEIkcTdaFr1DETbQlXo5UwupBedJ9ZGyR8v.jpg"
          }
        ],
        "customer": {
          "id": 2024468411,
          "full_name": "Osama K",
          "first_name": "Osama",
          "last_name": "K",
          "mobile": 780865752,
          "mobile_code": "+962",
          "email": "osama.k@salla.sa",
          "urls": {
            "customer": "https://demostore.salla.sa/dev-fjb4uoys3xuhrgpb/profile",
            "admin": "https://s.salla.sa/customers/7Gey9lbm4DoV14zPzGmW5xK8ZrYREJjN"
          },
          "avatar": "https://cdn.assets.salla.network/prod/stores/themes/default/assets/images/avatar_male.png",
          "gender": "male",
          "birthday": {
            "date": "1983-04-17 00:00:00.000000",
            "timezone_type": 3,
            "timezone": "Asia/Riyadh"
          },
          "city": "الرياض",
          "country": "السعودية",
          "country_code": "JO",
          "currency": "SAR",
          "location": "building 1",
          "lang": "ar",
          "created_at": {
            "date": "2025-11-05 17:14:53.000000",
            "timezone_type": 3,
            "timezone": "Asia/Riyadh"
          },
          "updated_at": {
            "date": "2025-11-05 17:14:54.000000",
            "timezone_type": 3,
            "timezone": "Asia/Riyadh"
          },
          "type": "user",
          "groups": []
        }
      }
    }
  },
  "settings": {},
  "merchant": {
    "id": 1419273030
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

```typescript
export default async (context: Misc): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: review } = payload;

  if (settings.notifyMerchant && review.rating <= 2) {
    await fetch(settings.notificationUrl, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        type: 'low_rating_review',
        review_type: review.type,
        product_id: review.product.id,
        rating: review.rating,
        merchant_id: merchant.id
      })
    });
  }
  
  const data = { 
    reviewed_product_id: review.product.id,
    review_rating:review.rating 
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionallly called. The default status is 200.
  * The .setMessage() is optional. 
  * Incase there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data)

  return response;
}
```

---

## merchants-events/Shipment-Events

# Shipment Events

This model defines the structure for events triggered during the shipment lifecycle.

## Available Events

- `shipment.creating` - **Synchronous Action** - Triggered before a shipment is created (can modify shipment data)
- `shipment.created` - Triggered when a shipment is created
- `shipment.cancelled` - Triggered when a shipment is cancelled
- `shipment.updated` - Triggered when shipment details are updated

## Event Type

:::note[]
**Mixed Types:**
- `shipment.creating` is **Synchronous** - Executes immediately and can return data
- Other events are **Asynchronous** - Processed in the background
:::

## Common Use Cases

- Calculate custom shipping rates
- Generate shipping labels
- Send tracking notifications
- Update fulfillment systems
- Validate shipping addresses

## Shipment Context Object

<Tabs>
  <Tab title="Schema">
    
<DataSchema id="10641073" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
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
      "service_types": ["international", "normal", "fulfillment"],
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
        "address_line": "Mecca,السعودية",
        "street_number": null,
        "block": null,
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
        "address_line": " شارع 2345، الحي السلام 95128،, شارع عبدالله  سنابل السلام  مكة  السعوديه,, الرياض, السعودية",
        "street_number": "2345",
        "block": "السلام",
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
  },
  "settings": {},
  "merchant": {
    "id": 136409261
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

### Generate Shipping Label

```typescript
export default async (context: Shipments): Promise<Shipment> => {
  const { payload, settings, merchant } = context;
  const { data: shipment } = payload;

  const labelRequest = {
    shipment_id: shipment.id,
    order_id: shipment.order_id,
    tracking_number: shipment.tracking_number,
    origin_address: shipment.ship_from,
    shipping_address: shipment.ship_to,
    customer: {
      id: settings.customer_id,
    },
    label_options: {
      format: settings.label_format, // pdf
      size: settings.label_size, // A6
    },
  };

  const response = await fetch(`https://api.mock.com/label/generate`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify(labelRequest)
  });

  const result = await response.json();
  /*
  * The Shipment can be used to set multiple things based on the use
  * case. There are other setter methods available to set other things.
  * The setShipmentNumber() is required to be set to identiify shipment.
  * Use Shipment.error() incase an error needs to be returned.
  */
  return Shipment.success()
    .setShipmentNumber(shipment.id)
    .setLabel(result.label_url)
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Create shipment">
    Create a shipment for an order
  </Step>
  <Step title="Test in preview">
    Use the shipment ID in the App Function preview panel
  </Step>
</Steps>

---

## merchants-events/Shipping-Company-Events

# Shipping Company Events

This model defines the structure for events triggered when shipping companies are created, updated, or deleted.

## Available Events

- `shipping.company.created` - Triggered when a new shipping company is added
- `shipping.company.updated` - Triggered when shipping company details are updated
- `shipping.company.deleted` - Triggered when a shipping company is removed

## Event Type

:::note[]
**Asynchronous Events** - Processed in the background.
:::

## Shipping Company Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10641376" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "shipping.company.deleted",
    "merchant": 1305146709,
    "created_at": "Thu Apr 07 2022 13:48:22 GMT+0300",
    "data": {
      "id": 488260393,
      "name": "شركة سريع",
      "status": false
    }
  },
  "settings": {},
  "merchant": {
    "id": 1305146709
  }
}

```

  </Tab>
</Tabs>

## Example Implementations

```typescript
export default async (context: Shippings): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: company } = payload;

  const response = await fetch(settings.apiUrl, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      company_id: company.id,
      zone_code: company.zone_code,
      city: company.city,
      merchant_id: merchant.id,
      event_type: event
    })
  });

  const data = { company_id: company.id }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionallly called. The default status is 200.
  * The .setMessage() is optional. 
  * Incase there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data)

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Create shipping company">
    Create a shipping company
  </Step>
  <Step title="Test in preview">
    Use the shipping company ID in the App Function preview panel
  </Step>
</Steps>

---

## merchants-events/Shipping-Zone-Events

# Shipping Zone Events

This model defines the structure for events triggered when shipping zones are created or updated.

## Available Events

- `shipping.zone.created` - Triggered when a new shipping zone is created
- `shipping.zone.updated` - Triggered when a shipping zone is updated

## Event Type

:::note[]
    **Asynchronous Events** - Processed in the background.
:::

## Shipping Zone Context Object

<Tabs>
  <Tab title="Schema">

<DataSchema id="10641074" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
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
  },
  "settings": {
    "syncEnabled": true
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

```typescript
export default async (context: Shippings): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: zone } = payload;

  await fetch(settings.apiUrl, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      zone_id: zone.id,
      zone_code: zone.zone_code,
      country: zone.country,
      merchant_id: merchant.id
    })
  });
  
  const data = { zone_id: zone.id };
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionallly called. The default status is 200.
  * The .setMessage() is optional. 
  * Incase there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data)

  return response;
}; 
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Create shipping zone">
    Create a shipping zone
  </Step>
  <Step title="Test in preview">
    Use the shipping zone ID in the App Function preview panel
  </Step>
</Steps>

---

## merchants-events/Special-Offer-Events

# Special Offer Events

This model defines the structure for events triggered when special offers are created or updated.

## Available Events

- `specialoffer.created` - Triggered when a new special offer is created
- `specialoffer.updated` - Triggered when a special offer is updated

## Event Type

:::note[]
    **Asynchronous Events** - Processed in the background.
:::

## Special Offer Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10641075" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "specialoffer.updated",
    "merchant": 1419273030,
    "created_at": "Wed Nov 05 2025 16:26:10 GMT+0300",
    "data": {
      "id": 421868142,
      "name": "Osama Test Offer",
      "message": "اشتري قطعة واحصل على قطعة واحدة خصم 10%  من التصنيفات التالية",
      "start_date": "2025-11-13 16:08:06",
      "expiry_date": "2025-11-29 09:00:00",
      "formatted_date": "29 نوفمبر 2025",
      "offer_type": "buy_x_get_y",
      "status": "active",
      "buy": { "type": "product", "quantity": "1", "products": [] },
      "get": {
        "type": "category",
        "categories": [
          {
            "id": 260745659,
            "name": "الفساتين"
          },
          {
            "id": 1498925188,
            "name": "البلايز"
          }
        ],
        "discount_type": "percentage",
        "quantity": "1",
        "discount_amount": "10"
      }
    }
  },
  "settings": {},
  "merchant": {
    "id": 1305146709
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

```typescript
export default async (context: SpecialOffer): Promise<Resp> => {
  const { payload, settings } = context;
  const { data: offer, merchant } = payload;

  const response = await fetch(settings.marketingApiUrl, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      offer_id: offer.id,
      name: offer.name,
      offer_type: offer.offer_type,
      expiry_date: offer.expiry_date,
      merchant_id: merchant.id
    })
  });

  const data = { offer_id: offer.id }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionallly called. The default status is 200.
  * The .setMessage() is optional. 
  * Incase there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data)

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Create special offer">
    Create a special offer
  </Step>
  <Step title="Test in preview">
    Use the special offer ID in the App Function preview panel
  </Step>
</Steps>

---

## merchants-events/Store-Branch-Events

# Store Branch Events

This model defines the structure for events triggered when store branches or tax settings are managed.

## Available Events

- `store.branch.created` - Triggered when a new branch is created
- `store.branch.updated` - Triggered when branch details are updated
- `store.branch.deleted` - Triggered when a branch is deleted

## Event Type

:::note[]
**Asynchronous Events** - Processed in the background.
:::

## Store Branch Context Object

<Tabs>
  <Tab title="Schema">
    
<DataSchema id="10641076" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "store.branch.updated",
    "merchant": 1419273030,
    "created_at": "Thu Nov 13 2025 19:09:48 GMT+0300",
    "data": {
      "id": 1594346156,
      "name": "الفرع الرئيسي",
      "status": "active",
      "is_default": true,
      "location": { "lat": "21.3825905096851", "lng": " 39.77319103068542" },
      "short_address": null,
      "street": "Street",
      "address_description": "Adress",
      "additional_number": null,
      "building_number": null,
      "local": null,
      "postal_code": "24222",
      "contacts": {
        "phone": "+966920034002",
        "telephone": "+966920034002",
        "whatsapp": "+966920034002"
      },
      "preparation_time": null,
      "is_open": true,
      "closest_time": null,
      "working_hours": [
        { "name": "Thursday", "times": [{ "from": "10:00", "to": "21:00" }] }
      ],
      "is_cod_available": true,
      "is_stock": true,
      "type": "branch",
      "cod_cost": "0.00",
      "branch_code": "FFc",
      "country": {
        "id": 1473353380,
        "name": "Saudi Arabia",
        "name_en": "Saudi Arabia",
        "code": "SA",
        "mobile_code": "+966",
        "capital": null
      },
      "city": {
        "id": 1939592358,
        "name": "Mecca",
        "name_en": "Mecca",
        "country_id": 1473353380
      },
      "district": null
    }
  },
  "settings": {},
  "merchant": {
    "id": 1419273030
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

```typescript
export default async (context: Store): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: branch } = payload;

  const response = await fetch(settings.apiUrl, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({
      branch_id: branch.id,
      name: branch.name,
      city: branch.city,
      merchant_id: merchant.id,
      event_type: event,
    }),
  });

  const data = { branch_id: branch.id };
  /*
   * The .setData() should be called mandatorily. (Pass {} as default)
   * The .setStatus() is optionallly called. The default status is 200.
   * The .setMessage() is optional.
   * Incase there is any error invoke Resp.error().
   */
  const response = Resp.success().setData(data);

  return response;
};
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Create Branch">
    Create a branch
  </Step>
  <Step title="Test in preview">
    Use the branch ID in the App Function preview panel
  </Step>
</Steps>

---

