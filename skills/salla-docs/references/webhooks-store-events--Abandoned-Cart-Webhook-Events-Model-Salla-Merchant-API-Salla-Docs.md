# Webhooks Store Events  Abandoned Cart Webhook Events Model Salla Merchant Api Salla Docs

## Table of Contents

- [webhooks-store-events/Abandoned-Cart-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-abandoned-cart-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Brand-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-brand-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Catgeory-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-catgeory-webhook-events-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Communication-Webhooks-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-communication-webhooks-salla-merchant-api-salla-docs)
- [webhooks-store-events/Customer-Webhook-Events-Model](#webhooks-store-events-customer-webhook-events-model)
- [webhooks-store-events/Invoice-Created-Webhook-Event-Model-Salla-Merchant-API-Salla-Docs](#webhooks-store-events-invoice-created-webhook-event-model-salla-merchant-api-salla-docs)
- [webhooks-store-events/Orders-Webhook-Events-Model](#webhooks-store-events-orders-webhook-events-model)

---

## webhooks-store-events/Abandoned-Cart-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Cart

Below are the webhook store events paired with their respective data schema related to the [Store webhook events](https://docs.salla.dev/doc-421119):

## Abandoned Cart Webhook Events Model

This event is triggered when an abandoned cart has been created or updated.

<Tabs>
  <Tab title="Data Schema">


<DataSchema id="1307423" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "abandoned.cart",
  "merchant": 1305146709,
  "created_at": "Tue Jan 21 2025 18:00:32 GMT+0300",
  "data": {
    "id": 1097962121,
    "total": {
      "amount": 100,
      "currency": "SAR"
    },
    "subtotal": {
      "amount": 60,
      "currency": "SAR"
    },
    "total_discount": {
      "amount": 10,
      "currency": "SAR"
    },
    "checkout_url": "https://salla.sa/dev-wofftr4xsra5xtlv/checkout/1097962121",
    "age_in_minutes": 83,
    "created_at": {
      "date": "2025-01-21 17:09:39.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "updated_at": {
      "date": "2025-01-21 17:09:39.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "customer": {
      "id": 225167971,
      "name": "User Name",
      "mobile": "+977612917082",
      "email": "customer@email.com",
      "avatar": "https://i.ibb.co/jyqRQfQ/avatar-male.webp",
      "country": "السعودية",
      "city": "الرياض"
    },
    "coupon": {
      "id": 2036833834,
      "code": "wizefriend",
      "status": "active",
      "type": "percentage",
      "amount": 20,
      "minimum_amount": 0,
      "expiry_date": "2025-04-13 00:00:00",
      "start_date": null,
      "created_at": "Tue Jan 21 2025 17:00:00 GMT+0300",
      "free_shipping": true
    },
    "items": [
      {
        "id": 1793843311,
        "product_id": 401511871,
        "quantity": 2
      },
      {
        "id": 239847784,
        "product_id": 64738276,
        "quantity": 1
      }
    ]
  }
}
```
      
  </Tab>
</Tabs>

## Abandoned Cart Status Changed Webhook Event Model

This event is triggered when an abandoned cart's status has been changed.

<Tabs>
  <Tab title="Data Schema">


<DataSchema id="3632393" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "abandoned.cart.status.changed",
  "merchant": 935918575,
  "created_at": "Tue Mar 25 2025 11:59:37 GMT+0300",
  "data": {
    "id": 1305879817,
    "status": "purchased"
  }
}
```
      
  </Tab>
</Tabs>

## Abandoned Cart Purchased Webhook Event Model

This event is triggered when an abandoned cart has been purchased, where the status is set to `purchased`.

<Tabs>
  <Tab title="Data Schema">


<DataSchema id="3632400" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "abandoned.cart.purchased",
  "merchant": 935918575,
  "created_at": "Tue Mar 25 2025 11:59:37 GMT+0300",
  "data": {
    "id": 1305879817,
    "status": "purchased",
    "currency": "SAR",
    "total": 34.99,
    "subtotal": 30.43,
    "total_discount": 0
  }
}
```
      
  </Tab>
</Tabs>



## Coupon Applied Webhook Event Model

This event is triggered when a coupon has been applied.

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307411" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "coupon.applied",
  "merchant": 847769313,
  "created_at": "Wed Jan 26 2022 22:38:30 GMT+0300",
  "data": {
    "cart": {
      "id": 746780865,
      "total": {
        "amount": 2910,
        "currency": "SAR"
      },
      "subtotal": {
        "amount": 3000,
        "currency": "SAR"
      },
      "total_discount": {
        "amount": 100,
        "currency": "SAR"
      },
      "checkout_url": "https://robbama.com/checkout/746780865",
      "age_in_minutes": 3517,
      "created_at": {
        "date": "2022-01-24 12:01:24.000000",
        "timezone_type": 3,
        "timezone": "Asia/Riyadh"
      },
      "updated_at": {
        "date": "2022-01-26 22:38:30.000000",
        "timezone_type": 3,
        "timezone": "Asia/Riyadh"
      },
      "customer": {
        "id": 1448307086,
        "name": "Nabil Mohammed",
        "mobile": "+251944130250",
        "avatar": "https://i.ibb.co/jyqRQfQ/avatar-male.webp",
        "country": "السعودية",
        "city": "جدة"
      },
      "coupon": {
        "id": 2036833834,
        "code": "wizefriend",
        "status": "active",
        "type": "percentage",
        "amount": {
          "amount": 20,
          "currency": "SAR"
        },
        "minimum_amount": {
          "amount": 0,
          "currency": "SAR"
        },
        "expiry_date": "2022-04-13 00:00:00",
        "created_at": {
          "date": "2022-01-24 13:47:47.000000",
          "timezone_type": 3,
          "timezone": "Asia/Riyadh"
        }
      },
      "items": [
        {
          "id": 2093591642,
          "product_id": 91502809,
          "quantity": 2
        }
      ]
    }
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Brand-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Brand

Below are the webhook store events paired with their respective data schema related to the [Brand webhook events](doc-421119):

## Brand Webhook Events Model

The following includes 3 brands webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307422" />
      
  </Tab>
  <Tab title="Example">
    
```
{
    "event": "brand.created",
    "merchant": 596493488,
    "created_at": "Sun Mar 24 2024 16:09:48 GMT+0300",
    "data": {
      "id": 190175156,
      "name": "test1212",
      "description": "test",
      "banner": "https://cdn.salla.sa/image/banner1.png",
      "logo": "https://cdn.salla.sa/image/logo1.png",
      "status": true,
      "ar_char": "ت",
      "en_char": "T",
      "metadata": {
        "title": "1231",
        "description": "123",
        "url": "123"
      }
    }
  }
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Catgeory-Webhook-Events-Model-Salla-Merchant-API-Salla-Docs

# Category

Below are the webhook store events paired with their respective data schema related to the [Category webhook events](https://docs.salla.dev/doc-421119):

## Catgeory Webhook Events Model

The following includes 2 category webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">
      
<DataSchema id="11412296" />
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "category.created",
  "merchant": 1029864349,
  "created_at": "Wed Jun 30 2021 14:21:57 GMT+0300",
  "data": {
    "id": 1429120554,
    "name": "test category",
    "urls": {
      "customer": "https://store.test/nabilanazer/category/neje",
      "admin": "/categories"
    },
    "items": [
      "string"
    ],
    "parent_id": 99911771,
    "status": "hidden",
    "sort_order": "7",
    "sub_categories": [
      "string"
    ]
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Communication-Webhooks-Salla-Merchant-API-Salla-Docs

# Communication Webhooks

The Communication webhooks provide notifications for all outgoing store communications, including SMS, email and whatsapp messages. They cover key events such as order updates, payment reminders, product availability alerts, marketing broadcasts, and customer engagement messages, ensuring developers can track and act on customer interactions in real time.

:::warning[]
These webhook events are allowed only for Communication applications.
:::


<Tabs>
  <Tab title="Data Schema">
    
<DataSchema id="8806995" />
  </Tab>
    <Tab title="Type Details">
    
| Type | Supported Entity Type | Meta | Description |
| --- | --- | --- | --- |
| `auth.otp.verification`      | N/A | `code`: A 4-digit numeric one-time password (OTP) code. | Triggered when an OTP is sent to the customer. |
| `order.status.confirmation`  | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when an order is created and pending payment *(either created by merchant for customer to pay, or created by customer with delayed payment)*. |
| `order.status.updated`       | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when the status of an order is changed. |
| `order.invoice.issued`       | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when an invoice is issued and sent to the customer. |
| `order.shipment.created`     | `shipment` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a shipment is created for an order. |
| `order.refund.processed`     | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when an order is refunded *(due to cancellation or failed order)*. |
| `order.gift.placed`          | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a customer places a gift order. |
| `payment.reminder.due`       | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a reminder is sent to the customer for completing payment. |
| `product.availability.alert` | `product` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a product is back in stock and the customer is notified. |
| `product.digital.code`       | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a customer purchases a digital code product or requests a resend of the code. |
| `customer.cart.abandoned`    | `cart` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a reminder is sent to the customer for an abandoned cart. |
| `customer.loyalty.earned`    | N/A | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when loyalty points are awarded to the customer. |
| `customer.feedback.reply`    | `feedback` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a merchant replies to customer feedback. |
| `customer.rating.request`    | `order` | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a merchant requests the customer to rate an order. |
| `marketing.campaign.broadcast` | N/A |  | Triggered when a marketing campaign is broadcast to customers. |
| `system.alert.general`       | N/A | `customer_id`: Unique identifier of the customer targeted by this notification. | Default type triggered when no specific event type is defined. |
| `system.message.custom`      | N/A | `customer_id`: Unique identifier of the customer targeted by this notification. | Triggered when a custom message is sent to the customer. |
   

    </Tab>
    
    <Tab title="Entity Type Details">
    
| Type | ID Description |
| --- | --- |
| `order`      | A unique alphanumeric code or identifier assigned to a specific order. List of orders can be found [here](https://docs.salla.dev/api-5394146) |
| `cart`      | A unique identifier associated with a shopping cart. List of abandond carts can be found [here](https://docs.salla.dev/api-5394138) |
| `shipment`      | A unique identifier for the shipment. Shipment list can be found [here](https://docs.salla.dev/api-5394232). |
| `product`      | A unique identifier for a specific product within a database. |
| `feedback`      | A unique identifier associated with a specific review. List of reviews can be found [here](https://docs.salla.dev/16603963e0). |

    </Tab>

</Tabs>

<Card title="Examples" icon="material-two-tone-assignment">
Below are some examples of the webhook events:


<AccordionGroup>

<Accordion title="Example #1" icon="material-two-tone-sms" defaultOpen={true}>
```json
{
  "event": "communication.sms.send",
  "merchant": 292111819,
  "created_at": "Mon Nov 10 2025 17:18:13 GMT+0300",
  "data": {
    "notifiable": [
      "+96656000000"
    ],
    "type": "product.digital.code",
    "content": "أصبحت حالة طلبك #218103278 [تم التنفيذ]",
    "entity": {
      "id": 1741773897,
      "type": "order"
    },
    "meta": {
      "customer_id": 239462497,
    }
  }
}
```
</Accordion>


<Accordion title="Example #2" icon="material-two-tone-email" defaultOpen={false}>
```json
{
  "event": "communication.email.send",
  "merchant": 54112478,
  "created_at": "Thu Aug 14 2025 15:44:55 GMT+0300",
  "data": {
    "notifiable": [
      "email@example.com"
    ],
    "type": "message",
    "content": "Hello World",
    "entity": null,
    "meta": {
      "customer_id": 1110699905
    }
  }
}
```
</Accordion>

<Accordion title="Example #3" icon="material-two-tone-email" defaultOpen={false}>
```json
{
  "event": "communication.whatsapp.send",
  "merchant": 292111819,
  "created_at": "Tue Nov 11 2025 18:30:37 GMT+0300",
  "data": {
    "notifiable": [
      "+96656000000"
    ],
    "type": "customer.rating.request",
    "content": "أهلاً Name \nنتمنى أن تجربة الشراء قد نالت على استحسانك.\nويسرنا معرفة تقييمك للطلب من خلال الرابط:",
    "entity": {
      "id": 148470821,
      "type": "order"
    },
    "meta": {
      "customer_id": 698792337
    }
  }
}
```
</Accordion>
<Accordion title="Example #4" icon="material-two-tone-chat" defaultOpen={false}>
```json
{
  "event": "communication.sms.send",
  "merchant": 5511124,
  "created_at": "Sun Aug 17 2025 16:46:18 GMT+0300",
  "data": {
    "notifiable": [
      "+96656000000"
    ],
    "type": "otp",
    "content": "كود التفعيل الخاص بك: 0000\n احرص على عدم مشاركته لتستمتع بتسوَّق آمن.",
    "entity": null,
    "meta": {
      "code": "0000"
    }
  }
}
```
</Accordion>
</AccordionGroup>
    </Card>

---

## webhooks-store-events/Customer-Webhook-Events-Model

# Customer

Below are the webhook store events paired with their respective data schema related to the [Customer webhook events](https://docs.salla.dev/doc-421119):

## Customer Webhook Events Model

The following includes 3 customer webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307420" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "customer.login",
  "merchant": 1305146709,
  "created_at": "Tue Jan 25 2022 12:36:49 GMT+0300",
  "data": {
    "id": 225167971,
    "first_name": "User",
    "last_name": "Mohammed",
    "mobile": 555555555,
    "mobile_code": "+966",
    "email": "test@gmail.com",
    "urls": {
      "customer": "https://salla.sa/dev-wofftr4xsra5xtlv/profile",
      "admin": "https://s.salla.sa/customers/l7mYBdgXA9xJwWZRZK8WD42GNkZbjvRO"
    },
    "avatar": "https://i.ibb.co/jyqRQfQ/avatar-male.webp",
    "gender": "female",
    "birthday": {
      "date": "1997-06-03 00:00:00.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "city": "الرياض",
    "country": "السعودية",
    "country_code": "SA",
    "currency": "AED",
    "location": "14",
    "updated_at": {
      "date": "2022-01-24 14:26:55.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "groups": [],
    "source": {
      "device": "desktop",
      "user-agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/138.0.0.0 Safari/537.36",
      "ip": "127.0.0.1"
    },
      "is_notifications_enabled": true
  }
}
```
      
  </Tab>
</Tabs>

## Customers OTP (One-Time Password) Webhook Event Model

This event is triggered when a customer's One-Time Password has been requested.

:::warning[Important Note]
This webhook event will only be triggered if both the email and SMS attempts to send the OTP to the customer have failed.
::: 

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307405" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "customer.otp.request",
  "merchant": 1029864349,
  "created_at": "Wed Jun 30 2021 12:09:11 GMT+0300",
  "data": {
    "code": "5331",
    "contact": "+96652318526"
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Invoice-Created-Webhook-Event-Model-Salla-Merchant-API-Salla-Docs

# Invoice

Below is the webhook store event paired with its respective data schema related to the [Invoice webhook events](doc-421119):

## Invoice Created Webhook Event Model

This event is triggered when the order status is either completed or restored.

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307440" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "id": 500681815,
  "invoice_number": "633544",
  "uuid": "39273ccf-ee77-4ca1-8df9-c93526ee17eb",
  "order_id": 1783506836,
  "invoice_reference_id": null,
  "type": "Tax Invoice",
  "date": "2025-05-19 12:05:05",
  "qr_code": null,
  "payment_method": "credit_card",
  "sub_total": {
    "amount": 834.76,
    "currency": "SAR"
  },
  "shipping_cost": {
    "amount": 0,
    "taxable": true,
    "currency": "SAR"
  },
  "cod_cost": {
    "amount": 0,
    "taxable": true,
    "currency": "SAR"
  },
  "discount": {
    "amount": 41.74,
    "currency": "SAR"
  },
  "tax": {
    "percent": 15,
    "amount": {
      "amount": 118.95,
      "currency": "SAR"
    }
  },
  "total": {
    "amount": 911.97,
    "currency": "SAR"
  },
  "shipping_cost_discount": {
    "amount": 0,
    "currency": "SAR"
  },
  "items": [
    {
      "id": 87236180,
      "item_id": 1114617540,
      "product_id": 515303061,
      "name": "زيت زيتون بكر قطفة أولى 4لتر",
      "sku": "PRO-001",
      "quantity": 4,
      "type": "product",
      "price": {
        "amount": 208.69,
        "currency": "SAR"
      },
      "discount": {
        "amount": 41.74,
        "currency": "SAR"
      },
      "tax": {
        "percent": 15,
        "amount": {
          "amount": 118.95,
          "currency": "SAR"
        }
      },
      "total": {
        "amount": 911.97,
        "currency": "SAR"
      }
    }
  ],
"company": {
 "name": "my company",
 "tax_number": "311111231231233",
 "commercial_number": "1233212235"
},
  "customer": {
    "id": 396470115,
    "first_name": "بدر",
    "last_name": "المطيري",
    "mobile": 555317835,
    "mobile_code": "+966",
    "email": "Abubadr512@gmail.com",
    "avatar": "https://cdn.assets.salla.network/prod/admin/cp/assets/images/avatar_male.png",
    "gender": "male",
    "birthday": {
      "date": "1980-08-12 00:00:00.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "country_code": "SA",
    "currency": "SAR",
    "updated_at": {
      "date": "2025-05-19 12:01:31.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "address": {
      "country": "السعودية",
      "city": "المدينة المنورة",
      "district": null,
      "street_name": "شاكر بن مكي",
      "additional_number": null,
      "building_number": null,
      "postal_code": "42251",
      "description": "بعد سوبرماركت الريم"
    }
  }
}
```
      
  </Tab>
</Tabs>

---

## webhooks-store-events/Orders-Webhook-Events-Model

# Order

Below are the webhook store events paired with their respective data schema related to the [Order webhook events](https://docs.salla.dev/doc-421119#order?nav=1):

## Orders Webhook Events Model

The following includes 10 order webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab


:::danger[Deprecation Notice]
- The variables `data.checkout_url` and `data.rating_link` will be *deprecated* by **May 25, 2025**. Moving forward, they will be accessible under the `urls` object as `data.urls.checkout` and `data.urls.rating`.
- The variables, `items.codes` and `items.files`, are deprecated. We recommend using instead the `data.urls.digital_content` variable.
:::

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307433" />
      
  </Tab>
  <Tab title="Example">
    
```
{
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
  },
  "pickup_branch": {
    "id": 1345871747,
    "name": "Branch",
    "status": "active",
    "location": {
      "lat": "37.78044939",
      "lng": "-97.8503951"
    },
    "contacts": {
      "phone": "+201099999999",
      "whatsapp": "+201099999999",
      "telephone": "+201099999999"
    },
    "preparation_time": "ساعة 30 دقيقة",
    "is_open": false,
    "closest_time": {
      "from": "08:00",
      "to": "17:00"
    },
    "working_hours": [
      {
        "name": "الأحد",
        "times": [
          {
            "from": "08:00",
            "to": "17:00"
          },
          {
            "from": "19:00",
            "to": "23:30"
          }
        ]
      }
    ],
    "is_cod_available": true,
    "is_default": true,
    "type": [],
    "cod_cost": "15",
    "country": {
      "id": 1473353380,
      "name": "السعودية",
      "name_en": "Saudi Arabia",
      "code": "SA",
      "mobile_code": "+966"
    },
    "city": {
      "id": 1,
      "name": "الرياض",
      "name_en": "Riyadh"
    }
  }
}
```
      
  </Tab>
</Tabs>

## Order Shipments Webhook Events Model

The following includes 4 order shipment webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

:::danger[Deprecation Notice]
- The variables `data.checkout_url` and `data.rating_link` will be *deprecated* by **May 25, 2025**. Moving forward, they will be accessible under the `urls` object as `data.urls.checkout` and `data.urls.rating`.
- The variables, `items.codes` and `items.files`, are deprecated. We recommend using instead the `data.urls.digital_content` variable.
:::

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307434" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "order.shipment.creating",
  "merchant": 1305146709,
  "created_at": "Sun Jun 26 2022 13:29:51 GMT+0300",
  "data": {
    "id": 1427738113,
    "reference_id": 41030566,
    "urls": {
      "customer": "https://salla.sa/dev-wofftr4xsra5xtlv/order/AB3exRyLdXv5Wp8KwZ9WrGg4p7Ej8ZKl",
      "admin": "https://s.salla.sa/orders/order/AB3exRyLdXv5Wp8KwZ9WrGg4p7Ej8ZKl"
      "rating": "https://store-test.com/rating-link",
      "checkout": "https://store-test.com/checkout"
    },
    "date": {
      "date": "2022-06-26 13:29:43.000000",
      "timezone_type": 3,
      "timezone": "Asia/Riyadh"
    },
    "source": "dashboard",
    "source_device": "desktop",
    "source_details": {
      "type": "dashboard",
      "value": null,
      "device": "desktop",
      "user-agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.0.0 Safari/537.36",
      "ip": null
    },
    "first_complete_at": null,
    "status": {
      "id": 566146469,
      "name": "بإنتظار المراجعة",
      "slug": "under_review",
      "customized": {
        "id": 986688842,
        "name": "بإنتظار المراجعة"
      }
    },
    "payment_method": "bank",
    "currency": "SAR",
    "amounts": {
      "sub_total": {
        "amount": 79,
        "currency": "SAR"
      },
      "shipping_cost": {
        "amount": 35,
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
      "discounts": [],
      "total": {
        "amount": 114,
        "currency": "SAR"
      }
    },
    "shipping": {
      "id": 1935030040,
      "app_id": "2032004508",
      "company": "usertest@gmail.com",
      "logo": "https://salla-dev-portal.s3.eu-central-1.amazonaws.com/uploads/T3GFoIZXP7BsIKMEfdL3XoT9rxSXZN9WpKoFifa8.png",
      "receiver": {
        "name": "Del Don",
        "email": "user@gmail.com",
        "phone": "971555555555"
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
        "shipping_address": " شارع Abu tamimah، الحي az zahraa 23233،, 5,, جدة, السعودية",
        "street_number": "Abu tamimah",
        "block": "az zahraa",
        "postal_code": "23233",
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
      "policy_options": {
        "boxes": "2"
      }
    },
    "can_cancel": true,
    "show_weight": false,
    "can_reorder": true,
    "is_pending_payment": false,
    "pending_payment_ends_at": 172791,
    "total_weight": "٠٫٢٥ كجم",
    "shipment_branch": [
      {
        "id": 731280709,
        "name": "الفرع الرئيسي",
        "status": "active",
        "is_default": true,
        "type": {}
      }
    ],
    "customer": {
      "id": 1550968832,
      "name": "Del Don",
      "mobile": "+971555555555",
      "email": "user@gmail.com",
      "avatar": "https://store-test.com/cp/assets/images/avatar_male.png",
      "country": "الامارات",
      "city": ""
    },
    "items": [
      {
        "id": 1907902809,
        "product_id": 1994210129,
        "name": "تنورة",
        "sku": "2400409-20000012660-",
        "quantity": 1,
        "weight": 0.25,
        "amounts": {
          "price_without_tax": {
            "amount": 79,
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
            "amount": 79,
            "currency": "SAR"
          }
        }
      }
    ]
  }
}
```
      
  </Tab>
</Tabs>

## Order Shipment Cancelled Webhook Event Model

The following includes 2 order shipment cancelled webhook events that share the same model, which are mentioned in the `event` enum value under the Data Schema tab

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307435" />
      
  </Tab>
  <Tab title="Example">
    
```
{
  "event": "order.shipment.cancelled",
  "merchant": 1305146709,
  "created_at": "Sun Jun 26 2022 14:41:11 GMT+0300",
  "data": {
    "id": 1427738113,
    "reference_id": 41030566,
    "shipping_number": "846984645"
  }
}
```
      
  </Tab>
</Tabs>

## Order Status Updated Webhook Event Model

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="1307436" />
      
  </Tab>
  <Tab title="Example">
    
```
{
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
}
```
      
  </Tab>
</Tabs>

---

