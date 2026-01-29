# Events

## Table of Contents

- [events/Account-Events](#events-account-events)
- [events/Cart-&-Checkout-Events](#events-cart-&-checkout-events)
- [events/Product-Events](#events-product-events)
- [events/Promotion-&-Coupon-Events](#events-promotion-&-coupon-events)
- [events/Wishlist-Events](#events-wishlist-events)

---

## events/Account-Events

# Account Events

This model defines the structure for events triggered when customers manage their accounts on the storefront.

## Available Events

- `Signed In` - When a user logs into their account
- `Signed Up` - When a user creates a new account
- `Signed Out` - When a user logs out of their account.
- `Profile Updated` - When a user modifies their profile information


## Common Use Cases

- Track user authentication
- Monitor registration conversions
- Analyze user engagement
- Trigger welcome campaigns
- Update marketing platforms

## Payload Object

<Tabs>
  <Tab title="Schema">
      


<DataSchema id="11143502" />

  </Tab>
  <Tab title="Example">

```json
{
    "type": "track",
    "event": "Signed Up",
    "properties": {
        "first_name": "string",
        "last_name": "string",
        "type": "string",
        "mobile": "string",
        "email": "string"
    },
    "anonymousId": "string",
    "sentAt": "string",
    "context": {
        "userAgent": "string",
        "locale": "string",
        "screen": {
            "width": 0,
            "height": 0,
            "innerWidth": 0,
            "innerHeight": 0,
            "density": 0
        },
        "traits": {
            "id": 0,
            "type": "string",
            "first_name": "string",
            "last_name": "string",
            "gender": "string",
            "name": "string",
            "mobile": 0,
            "mobile_code_country": "string",
            "email": "string",
            "created_at": "string",
            "wallet": null,
            "mahally_customer_wallet": null,
            "address": null,
            "country_code": "string",
            "shipping_mobile_number": {
                "country_code": null,
                "mobile": null,
                "mobile_code_country": null
            }
        },
        "page": {
            "path": "string",
            "referrer": "string",
            "referring_domain": "string",
            "host": "string",
            "search": "string",
            "title": "string",
            "url": "string",
            "encoding": "string",
            "name": "string"
        },
        "campaign": {
            "source": "string",
            "medium": "string",
            "content": "string",
            "referrer": "string"
        }
    }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track User Sign-Up

```typescript
import {
  SignedUpPayload,
  EcommerceEvents,
} from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.SIGNED_UP;

export default (payload: SignedUpPayload): void => {
  console.log("Signed UP Event:", payload);

  // Add your custom tracking logic here
};
```

---

## events/Cart-&-Checkout-Events

# Cart & Checkout Events

This model defines the structure for events triggered during the shopping cart and checkout process.

## Available Events

- `Product Added` - Customer adds a product to cart
- `Product Removed` - Customer removes a product from cart
- `Cart Viewed` - Customer views their shopping cart
- `Cart Updated` - Customer updates cart quantities
- `Checkout Started` - Customer begins checkout process
- `Checkout Step Viewed` - Customer views a checkout step
- `Checkout Step Completed` - Customer completes a checkout step
- `Payment Info Entered` - Customer enters payment information
- `Order Completed` - Customer completes an order

## Common Use Cases

- Track conversion funnels
- Implement cart recovery
- Analyze checkout abandonment
- Optimize checkout flow
- Trigger remarketing campaigns
- Monitor payment success rates

## Payload Object

<Tabs>
  <Tab title="Schema">
    


<DataSchema id="11143783" />

  </Tab>
  <Tab title="Example">

```json
{
    "type": "track",
    "event": "Cart Updated",
    "properties": {
        "cart_id": "string",
        "value": 0,
        "revenue": 0,
        "tax": 0,
        "discount": 0,
        "shipping": 0,
        "currency": "string",
        "products": [
            {
                "product_id": "string",
                "name": "string",
                "price": 0,
                "url": "string",
                "image_url": "string",
                "currency": "string",
                "quantity": 0
            }
        ]
    },
    "anonymousId": "string",
    "sentAt": "string",
    "context": {
        "userAgent": "string",
        "locale": "string",
        "screen": {
            "width": 0,
            "height": 0,
            "innerWidth": 0,
            "innerHeight": 0,
            "density": 0
        },
        "traits": {
            "id": 0,
            "type": "string",
            "first_name": "string",
            "last_name": "string",
            "gender": "string",
            "name": "string",
            "mobile": "string",
            "mobile_code_country": "string",
            "email": "string",
            "created_at": "string",
            "wallet": null,
            "mahally_customer_wallet": null,
            "address": null,
            "country_code": "string",
            "shipping_mobile_number": {
                "country_code": null,
                "mobile": null,
                "mobile_code_country": null
            },
            "language_code": "string",
            "currency_code": "string",
            "can_comment": true,
            "avatar": "string",
            "is_hidden_name": true,
            "is_notifiable": true,
            "fetched_at": "string",
            "birthday": "string",
            "phone": "string",
            "country": "string",
            "language": "string",
            "currency": "string"
        },
        "page": {
            "path": "string",
            "referrer": "string",
            "referring_domain": "string",
            "host": "string",
            "search": "string",
            "title": "string",
            "url": "string",
            "encoding": "string",
            "name": "string",
            "id": "string"
        },
        "campaign": {
            "source": "string",
            "medium": "string",
            "content": "string",
            "referrer": "string"
        }
    }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Cart Updated Event

```typescript
import {
  CartUpdatedPayload,
  EcommerceEvents,
} from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.CART_UPDATED;

export default (payload: CartUpdatedPayload): void => {
  console.log("Cart Updated Event:", payload);

  // Add your custom tracking logic here
};
```

---

## events/Product-Events

# Product Events

This model defines the structure for events triggered when customers interact with products on the storefront.

## Available Events

- `Products Searched` - When a customer searches for products
- `Product List Viewed` - When a customer views a collection of products
- `Product List Filtered` - When a customer applies filters to a product list
- `Product List Sorted` - When a customer sorts a product list
- `Product Viewed` - Customer views a product page
- `Product Clicked` - Customer clicks on a product
- `Product Shared` - Customer shares a product
- `Product Reviewed` - Customer submits a product review

## Common Use Cases

- Track product popularity and views
- Implement product recommendations
- Analyze search behavior
- Monitor conversion funnels
- Personalize user experience
- Trigger remarketing campaigns

## Payload Object


<Tabs>
  <Tab title="Schema">
   



<DataSchema id="11144906" />

  </Tab>
  <Tab title="Example">

```json
{
    "type": "track",
    "event": "Product Searched",
    "properties": {
        "query": "string"
    },
    "anonymousId": "string",
    "sentAt": "string",
    "context": {
        "userAgent": "string",
        "locale": "string",
        "screen": {
            "width": 0,
            "height": 0,
            "innerWidth": 0,
            "innerHeight": 0,
            "density": 0
        },
        "traits": {},
        "page": {
            "path": "string",
            "referrer": "string",
            "referring_domain": "string",
            "host": "string",
            "search": "string",
            "title": "string",
            "url": "string",
            "encoding": "string",
            "name": "string"
        },
        "campaign": {
            "source": "string",
            "medium": "string",
            "content": "string",
            "referrer": "string"
        },
        "scope": {
            "id": 0,
            "name": "string",
            "selected": true,
            "type": "string",
            "is_open": true,
            "display_as": "string",
            "languages": [
                "string"
            ],
            "currencies": [
                "string"
            ],
            "countries": [
                "string"
            ],
            "always_ask": true
        }
    }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track Product Views

```typescript
import {
  ProductSearchedPayload,
  EcommerceEvents,
} from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.PRODUCT_SEARCHED;

export default (payload: ProductSearchedPayload): void => {
  console.log("PRODUCT SEARCHED Event:", payload);

  // Add your custom tracking logic here
};
```

---

## events/Promotion-&-Coupon-Events

# Promotion & Coupon Events

This model defines the structure for events triggered when customers interact with promotions and coupons.

## Available Events

- `Promotion Viewed` - Customer views a promotion
- `Promotion Clicked` - Customer clicks on a promotion
- `Coupon Entered` - Customer enters a coupon code
- `Coupon Applied` - Coupon is successfully applied
- `Coupon Removed` - Customer removes a coupon
- `Coupon Denied` - Coupon is denied

## Common Use Cases

- Track promotion effectiveness
- Analyze coupon usage patterns
- Monitor discount impact
- Optimize promotion strategies
- Trigger follow-up campaigns

## Payload Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="11145437" />

  </Tab>
  <Tab title="Example">

```json
{
    "type": "track",
    "event": "Promotion Viewed",
    "properties": {
        "promotion_id": "string",
        "creative": "string",
        "name": "string",
        "position": 0
    },
    "anonymousId": "string",
    "sentAt": "string",
    "context": {
        "userAgent": "string",
        "locale": "string",
        "screen": {
            "width": 0,
            "height": 0,
            "innerWidth": 0,
            "innerHeight": 0,
            "density": 0
        },
        "traits": {
            "id": 0,
            "type": "string",
            "first_name": "string",
            "last_name": "string",
            "gender": "string",
            "name": "string",
            "mobile": "string",
            "mobile_code_country": "string",
            "email": "string",
            "created_at": "string",
            "wallet": null,
            "mahally_customer_wallet": null,
            "address": null,
            "country_code": "string",
            "shipping_mobile_number": {
                "country_code": null,
                "mobile": null,
                "mobile_code_country": null
            },
            "language_code": "string",
            "currency_code": "string",
            "can_comment": true,
            "avatar": "string",
            "is_hidden_name": true,
            "is_notifiable": true,
            "fetched_at": "string",
            "birthday": "string",
            "phone": "string",
            "country": "string",
            "language": "string",
            "currency": "string"
        },
        "page": {
            "path": "string",
            "referrer": "string",
            "referring_domain": "string",
            "host": "string",
            "search": "string",
            "title": "string",
            "url": "string",
            "encoding": "string",
            "name": "string",
            "id": "string"
        },
        "campaign": {
            "source": "string",
            "medium": "string",
            "content": "string",
            "referrer": "string"
        }
    }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track Promotion Usage

```typescript
import {
  PromotionViewedPayload,
  EcommerceEvents,
} from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.PROMOTION_VIEWED;

export default (payload: PromotionViewedPayload): void => {
  console.log("PROMOTION VIEWED Event:", payload);

  // Add your custom tracking logic here
};
```

---

## events/Wishlist-Events

# Wishlist Events

This model defines the structure for events triggered when customers interact with wishlists.

## Available Events

- `Product Added to Wishlist` - Customer adds a product to wishlist
- `Product Removed from Wishlist` - Customer removes a product from wishlist
- `Wishlist Product Added to Cart` - Customer adds a wishlist product to cart

## Common Use Cases

- Track wishlist behavior
- Send wishlist reminders
- Analyze product interest
- Trigger price drop notifications
- Monitor wishlist conversion rates

## Payload Object

<Tabs>
  <Tab title="Schema">
    



<DataSchema id="11148570" />

  </Tab>
  <Tab title="Example">

```json
{
    "type": "track",
    "event": "Product Added to Wishlist",
    "properties": {
        "wishlist_id": "string",
        "wishlist_name": "string",
        "product_id": "string",
        "sku": "string",
        "category": "string",
        "name": "string",
        "brand": "string",
        "variant": "string",
        "price": 0,
        "currency": "string",
        "image_url": "string",
        "url": "string"
    },
    "anonymousId": "string",
    "sentAt": "string",
    "context": {
        "userAgent": "string",
        "locale": "string",
        "screen": {
            "width": 0,
            "height": 0,
            "innerWidth": 0,
            "innerHeight": 0,
            "density": 0
        },
        "traits": {
            "id": 0,
            "type": "string",
            "first_name": "string",
            "last_name": "string",
            "gender": "string",
            "name": "string",
            "mobile": "string",
            "mobile_code_country": "string",
            "email": "string",
            "created_at": "string",
            "wallet": null,
            "mahally_customer_wallet": null,
            "address": null,
            "country_code": "string",
            "shipping_mobile_number": {
                "country_code": null,
                "mobile": null,
                "mobile_code_country": null
            },
            "language_code": "string",
            "currency_code": "string",
            "can_comment": true,
            "avatar": "string",
            "is_hidden_name": true,
            "is_notifiable": true,
            "fetched_at": "string",
            "birthday": "string",
            "phone": "string",
            "country": "string",
            "language": "string",
            "currency": "string"
        },
        "page": {
            "path": "string",
            "referrer": "string",
            "referring_domain": "string",
            "host": "string",
            "search": "string",
            "title": "string",
            "url": "string",
            "encoding": "string",
            "name": "string",
            "id": "string"
        },
        "campaign": {
            "source": "string",
            "medium": "string",
            "content": "string",
            "referrer": "string"
        }
    }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track Coupon Usage

```typescript
import {
  WishlistProductAddedPayload,
  EcommerceEvents,
} from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.WISHLIST_PRODUCT_ADDED;

export default (payload: WishlistProductAddedPayload): void => {
  console.log("WISHLIST PRODUCT ADDED Event:", payload);

  // Add your custom tracking logic here
};
```

---

