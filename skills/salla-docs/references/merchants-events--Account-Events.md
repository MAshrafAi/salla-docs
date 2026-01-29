# Merchants Events  Account Events

## Table of Contents

- [customers-events/Account-Events](#customers-events-account-events)
- [customers-events/Cart-&-Checkout-Events](#customers-events-cart-&-checkout-events)
- [customers-events/Product-Events](#customers-events-product-events)
- [customers-events/Promotion-&-Coupon-Events](#customers-events-promotion-&-coupon-events)
- [customers-events/Wishlist-Events](#customers-events-wishlist-events)
- [merchants-events/Brand-Events](#merchants-events-brand-events)
- [merchants-events/Cart-Events](#merchants-events-cart-events)
- [merchants-events/Category-Events](#merchants-events-category-events)
- [merchants-events/Communication-Events](#merchants-events-communication-events)
- [merchants-events/Customer-Events](#merchants-events-customer-events)

---

## customers-events/Account-Events

# Account Events

This model defines the structure for events triggered when customers manage their accounts on the storefront.

## Available Events

- `Signed In` - When a user logs into their account
- `Signed Up` - When a user creates a new account
- `Signed Out` - When a user logs out of their account.
- `Profile Updated` - When a user modifies their profile information

## Event Type


:::note[]
**Asynchronous Events** - All customer events are processed in the background.
:::

## Common Use Cases

- Track user authentication
- Monitor registration conversions
- Analyze user engagement
- Trigger welcome campaigns
- Update marketing platforms

## Context Object

<Tabs>
  <Tab title="Schema">
      

<DataSchema id="10818983" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "Signed Up",
    "merchant": 101,
    "created_at": "2024-01-15T14:30:00Z",
    "data": {
      "user_id": "user_98765",
      "email": "ahmed@example.com",
      "name": "Ahmed Mohammed"
    }
  },
  "settings": {
    "trackAuth": true
  }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track User Authentication

```typescript
export default async (context: SignedInEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: user } = payload;

  // Prepare a normalized analytics event from the incoming payload
  const authData = {
    event_type: event,
    user_id: user.user_id,
    email: user.email,
    name: user.name,
    merchant_id: merchant,
    timestamp: new Date().toISOString()
  };

  // Send to your analytics endpoint (make sure settings contain URL and API key)
  await fetch(settings.analyticsUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(authData)
  });

  // Always set response data to help with observability and debugging
  const data = {
    user_id: user.user_id,
    tracked: true
  };
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data);

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Sign up/in">
    Create an account or sign in as a customer
  </Step>
  <Step title="Test in preview">
    Use the user ID in the App Function preview panel
  </Step>
</Steps>

## Related Events

- [Checkout Events](https://docs.salla.dev/1726822m0.md) - Shopping cart interactions

---

## customers-events/Cart-&-Checkout-Events

# Cart & Checkout Events

This model defines the structure for events triggered during the shopping cart and checkout process.

## Available Events

- `Product Added` - Customer adds a product to cart
- `Product Removed` - Customer removes a product from cart
- `Cart Viewed` - Customer views their shopping cart
- `Cart Updated` - Customer updates cart quantities
- `Cart Shared` - When a customer shares their cart
- `Checkout Started` - Customer begins checkout process
- `Checkout Step Viewed` - Customer views a checkout step
- `Checkout Step Completed` - Customer completes a checkout step
- `Payment Info Entered` - Customer enters payment information
- `Payment Failed` - Customer completes an order
- `Order Updated` - Customer completes an order
- `Order Completed` - Customer completes an order
- `Order Refunded` - Customer completes an order
- `Order Cancelled` - Customer completes an order

## Event Type

:::note[]
**Asynchronous Events** - All customer events are processed in the background.
:::

## Common Use Cases

- Track conversion funnels
- Implement cart recovery
- Analyze checkout abandonment
- Optimize checkout flow
- Trigger remarketing campaigns
- Monitor payment success rates

## Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10822315" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "Product Added",
    "merchant": 101,
    "created_at": "2024-01-15T14:30:00Z",
    "data": {
      "cart_id": "cart_abc123",
      "total": 198.00,
      "currency": "SAR",
      "products": [
        {
          "product_id": "5001",
          "name": "Premium Cotton T-Shirt",
          "price": 99.00,
          "quantity": 2
        }
      ]
    }
  },
  "settings": {
    "analyticsEnabled": true
  }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Checkout Started Event

```typescript
export default async (context: CheckoutStepCompletedEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: checkout } = payload;

  // Normalize the checkout start event
  const analyticsData = {
    event_type: event,
    checkout_id: checkout.checkout_id,
    step: checkout.step,
    total: checkout.total,
    currency: checkout.currency,
    merchant_id: merchant
  };

  await fetch(settings.analyticsUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(analyticsData)
  });

  const data = { checkout_id: checkout.checkout_id };
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  return Resp.success().setData(data);
};
```

### Track Cart Events

```typescript
export default async (context: Checkout): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: cart } = payload;

  // Prepare cart analytics payload
  const analyticsData = {
    event_type: event,
    cart_id: cart.cart_id,
    total: cart.total,
    currency: cart.currency,
    items_count: cart.products?.length || 0,
    merchant_id: merchant,
    timestamp: new Date().toISOString()
  };

  await fetch(settings.analyticsUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(analyticsData)
  });

  const data = {
    cart_id: cart.cart_id,
    tracked: true
  };
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  return Resp.success().setData(data);
}
```

### Track Checkout Funnel

```typescript
export default async (context: CheckoutStepCompletedEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: checkout } = payload;

  // Track checkout step completion
  const funnelData = {
    event_type: event,
    checkout_id: checkout.checkout_id,
    step: checkout.step,
    total: checkout.total,
    merchant_id: merchant
  };

  await fetch(`${settings.analyticsUrl}/funnel`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(funnelData)
  });

  const data = {
      checkout_id: checkout.checkout_id,
      step: checkout.step
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data);

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Add to cart">
    Add products to cart as a customer
  </Step>
  <Step title="Start checkout">
    Begin the checkout process
  </Step>
  <Step title="Test in preview">
    Use the cart/checkout ID in the App Function preview panel
  </Step>
</Steps>

## Related Events

- [Product Events](https://docs.salla.dev/1726820m0.md) - Product views and clicks
- [Promotion Events](https://docs.salla.dev/1726821m0.md) - Coupon usage

---

## customers-events/Product-Events

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


## Event Type

:::note[]
**Asynchronous Events** - All customer events are processed in the background and do not block the user experience.
:::

## Common Use Cases

- Track product popularity and views
- Implement product recommendations
- Analyze search behavior
- Monitor conversion funnels
- Personalize user experience
- Trigger remarketing campaigns

## Context Object


<Tabs>
  <Tab title="Schema">
   

<DataSchema id="10624691" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "Product Viewed",
    "merchant": 101,
    "created_at": "2024-01-15T14:30:00Z",
    "data": {
      "product_id": "12345",
      "sku": "TSH-BLK-L-001",
      "category": "Clothing/T-Shirts",
      "name": "Premium Cotton T-Shirt",
      "brand": "Urban Style",
      "variant": "Black / Large",
      "price": 99.00,
      "currency": "SAR",
      "quantity": 1,
      "url": "https://store.example.com/products/premium-cotton-tshirt",
      "image_url": "https://cdn.example.com/products/tshirt-black.jpg"
    }
  },
  "settings": {
    "analyticsEnabled": true,
    "trackingApiUrl": "https://analytics.example.com"
  }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track Product Views

```typescript
export default async (context: ProductViewedEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: product } = payload;

  // Build a normalized product view event
  const analyticsEvent = {
    event_type: 'product_view',
    timestamp: new Date().toISOString(),
    merchant_id: merchant,
    product: {
      id: product.product_id,
      name: product.name,
      category: product.category,
      brand: product.brand,
      price: product.price,
      currency: product.currency
    },
    page_url: product.url
  };

  await fetch(settings.trackingApiUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.trackingApiKey
    },
    body: JSON.stringify(analyticsEvent)
  });
  
  const data = {
    product_id: product.product_id,
    tracked: true
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data);

  return response;
}
```

### Track Search Behavior

```typescript
export default async (context: ProductsSearchedEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: searchData } = payload;

  // Track product search queries and result counts
  const searchAnalytics = {
    merchant_id: merchant,
    query: searchData.query,
    results_count: searchData.products?.length || 0,
    has_results: (searchData.products?.length || 0) > 0,
    timestamp: new Date().toISOString()
  };

  await fetch(`${settings.analyticsApiUrl}/search`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(searchAnalytics)
  });

  if (!searchAnalytics.has_results) {
    console.log(`No results for search query: "${searchData.query}"`);
  }
  
  const data = {
    query: searchData.query,
    results: searchAnalytics.results_count
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data);

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Visit storefront">
    Visit the storefront as a customer
  </Step>
  <Step title="Interact with products">
    View, click, or search for products
  </Step>
  <Step title="Test in preview">
    Use the product ID in the App Function preview panel
  </Step>
</Steps>

## Related Events

- [Cart & Checkout Events](cart-checkout-events.md) - Shopping cart interactions
- [Wishlist Events](wishlist-events.md) - Wishlist management

---

## customers-events/Promotion-&-Coupon-Events

# Promotion & Coupon Events

This model defines the structure for events triggered when customers interact with promotions and coupons.

## Available Events

- `Promotion Viewed` - Customer views a promotion
- `Promotion Clicked` - Customer clicks on a promotion
- `Coupon Entered` - Customer enters a coupon code
- `Coupon Applied` - Coupon is successfully applied
- `Coupon Removed` - Customer removes a coupon

## Event Type

:::note[]
**Asynchronous Events** - All customer events are processed in the background.
:::

## Common Use Cases

- Track promotion effectiveness
- Analyze coupon usage patterns
- Monitor discount impact
- Optimize promotion strategies
- Trigger follow-up campaigns

## Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10760670" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "Coupon Applied",
    "merchant": 101,
    "created_at": "2024-01-15T14:30:00Z",
    "data": {
      "promotion_id": "promo_123",
      "coupon": "WELCOME10",
      "discount": 44.70,
      "order_id": "order_xyz789"
    }
  },
  "settings": {
    "trackPromotions": true
  }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track Coupon Usage

```typescript
export default async (context: CouponAppliedEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: promotion } = payload;

  // Normalize coupon usage for analytics
  const couponData = {
    event_type: event,
    coupon_code: promotion.coupon,
    discount_amount: promotion.discount,
    order_id: promotion.order_id,
    merchant_id: merchant,
    timestamp: new Date().toISOString()
  };

  await fetch(settings.analyticsUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(couponData)
  });
  
  const data = {
    coupon: promotion.coupon,
    tracked: true
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data);

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Apply coupon">
    Enter and apply a coupon code during checkout
  </Step>
  <Step title="Test in preview">
    Use the promotion ID in the App Function preview panel
  </Step>
</Steps>

## Related Events

- [Checkout Events](https://docs.salla.dev/1726822m0.md) - Checkout process

---

## customers-events/Wishlist-Events

# Wishlist Events

This model defines the structure for events triggered when customers interact with wishlists.

## Available Events

- `Product Added to Wishlist` - Customer adds a product to wishlist
- `Product Removed from Wishlist` - Customer removes a product from wishlist
- `Wishlist Product Added to Cart` - Customer adds a wishlist product to cart

## Event Type

:::note[]
**Asynchronous Events** - All customer events are processed in the background.
:::

## Common Use Cases

- Track wishlist behavior
- Send wishlist reminders
- Analyze product interest
- Trigger price drop notifications
- Monitor wishlist conversion rates

## Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10757964" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "Product Added to Wishlist",
    "merchant": 101,
    "created_at": "2024-01-15T14:30:00Z",
    "data": {
      "wishlist_id": "wishlist_abc123",
      "wishlist_name": "My Favorites",
      "product_id": "5001",
      "name": "Premium Cotton T-Shirt",
      "price": 99.00
    }
  },
  "settings": {
    "trackWishlist": true,
    "analyticsUrl": "https://analytics.example.com/events",
    "analyticsApiKey": settings.analyticsApiKey
  }
}
```

  </Tab>
</Tabs>

## Example Implementation

### Track Wishlist Activity

```typescript
export default async (context: ProductAddedToWishlistEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: wishlist } = payload;

  // Normalize wishlist event fields
  const wishlistData = {
    event_type: event,
    wishlist_id: wishlist.wishlist_id,
    product_id: wishlist.product_id,
    product_name: wishlist.name,
    price: wishlist.price,
    merchant_id: merchant,
    timestamp: new Date().toISOString()
  };

  await fetch(settings.analyticsUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.analyticsApiKey
    },
    body: JSON.stringify(wishlistData)
  });
  
  const data = {
      wishlist_id: wishlist.wishlist_id,
      product_id: wishlist.product_id
  }
  /*
  * The .setData() should be called mandatorily. (Pass {} as default)
  * The .setStatus() is optionally called. The default status is 200.
  * The .setMessage() is optional.
  * In case there is any error invoke Resp.error().
  */
  const response = Resp.success().setData(data);

  return response;
}
```

## Testing

<Steps>
  <Step title="Install your app">
    Install your app on a demo store
  </Step>
  <Step title="Add to wishlist">
    Add products to wishlist as a customer
  </Step>
  <Step title="Test in preview">
    Use the wishlist ID in the App Function preview panel
  </Step>
</Steps>

## Related Events

- [Product Events](https://docs.salla.dev/1726820m0.md) - Product
- [Checkout Events](https://docs.salla.dev/1726822m0.md) - Checkout & Cart

---

## merchants-events/Brand-Events

# Brand Events

This model defines the structure for events triggered when a brand is created, updated, or deleted in a merchant's store.

## Available Events

- `brand.created` - Triggered when a new brand is created
- `brand.updated` - Triggered when brand details are updated  
- `brand.deleted` - Triggered when a brand is deleted

## Event Type
:::note[]
**Asynchronous Event** - Processed in the background after the brand operation completes.
:::

## Common Use Cases

- Sync brand information with external systems
- Update brand pages on external platforms
- Manage brand assets and media
- Track brand catalog changes
- Update search indexes with brand data

## Brand Context Object

<Tabs>
  <Tab title="Schema">
    

<DataSchema id="10641065" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "brand.created",
    "merchant": 1419273030,
    "created_at": "Wed Nov 05 2025 11:56:07 GMT+0300",
    "data": {
      "id": 100165769,
      "name": "Apple",
      "label": "Apple",
      "description": "<p>Apple brand</p>",
      "banner": null,
      "logo": "https://cdn.salla.sa/grmrz/brands/WG5rnabz0eMPHTPYjSrYZSNY1IxSZESFsqR2cLzL.png",
      "status": null,
      "ar_char": "أ",
      "en_char": "A",
      "metadata": { "title": null, "description": null, "url": "" }
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

## Example Implementations

### Sync Brand to External System

```typescript
export default async (context: Brand): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: brand } = payload;

  // Prepare brand data for external system
  const externalBrandData = {
    external_id: brand.id,
    name: brand.name.en,
    name_ar: brand.name.ar,
    description: brand.description.en,
    logo_url: brand.logo,
    banner_url: brand.banner,
    website: brand.metadata.url,
    merchant_id: merchant.id,
    event_type: event,
    synced_at: new Date().toISOString()
  };

  // Send to external API
  const response = await fetch(`https://api.mock.com/v1/brand`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(externalBrandData)
  });

  const result = await response.json();
  
  const data = {
    brand_id: brand.id,
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

### Update Search Index

```typescript
export default async (context: Brand): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: brand } = payload;

  // Prepare search document
  const searchDocument = {
    id: brand.id,
    type: 'brand',
    name_en: brand.name.en,
    name_ar: brand.name.ar,
    description_en: brand.description.en,
    description_ar: brand.description.ar,
    logo: brand.logo,
    url: brand.metadata.url,
    searchable_text: `${brand.name.en} ${brand.name.ar} ${brand.description.en} ${brand.description.ar}`,
    updated_at: new Date().toISOString()
  };

  // Update search index
  const response = await fetch(`https://api.mock.com/v1/brand/index`, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(searchDocument)
  });
  
  const data = {
    brand_id: brand.id,
    indexed: true
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
  <Step title="Navigate to Brands">
    Go to the Brands section in the demo store dashboard
  </Step>
  <Step title="Trigger the event">
    Create, update, or delete a brand
  </Step>
  <Step title="Test in preview">
    Use the brand ID in the App Function preview panel and click "Save and Preview"
  </Step>
</Steps>

## Related Events

- [Category Events](https://docs.salla.dev/1726827m0.md) - Categories and brands organize products

---

## merchants-events/Cart-Events

# Cart Events

This model defines the structure for events triggered when a shopping cart is abandoned.

## Available Events

- `abandoned.cart` - Triggered when a customer abandons their shopping cart
- `abandoned.cart.updated` - Triggered when a customer abandons their shopping cart
- `abandoned.cart.status.changed` - Triggered when a customer abandons their shopping cart
- `coupon.applied` - Triggered when a coupon is applied to an order

## Event Type


:::note[]
**Asynchronous Event** - Processed in the background.
:::

## Common Use Cases

- Send cart recovery emails
- Track abandoned cart analytics
- Trigger remarketing campaigns
- Offer discounts to recover carts

## Abandoned Cart Context Object

<Tabs>
  <Tab title="Schema">


<DataSchema id="10684699" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
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
  },
  "settings": {
    "emailApiUrl": "https://api.email.com",
    "recoveryEnabled": true
  },
  "merchant": {
    "id": 1305146709
  }
}
```

  </Tab>
</Tabs>

## Abandoned Cart Status Changed Context Object

<Tabs>
  <Tab title="Data Schema">



<DataSchema id="10684709" />
      
  </Tab>
  <Tab title="Example">
    
```json
{
    "payload": {
        "event": "abandoned.cart.status.changed",
        "merchant": 935918575,
        "created_at": "Tue Mar 25 2025 11:59:37 GMT+0300",
        "data": {
          "id": 1305879817,
          "status": "purchased"
        }
    },
    "settings": {},
    "merchant": {
        "id": 935918575
    }
}
```
  </Tab>
</Tabs>

## Abandoned Cart Purchased Context Object

<Tabs>
  <Tab title="Data Schema">



<DataSchema id="10684724" />
      
  </Tab>
  <Tab title="Example">
    
```json
{
    "payload": {
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
    },
    "settings": {},
    "merchant": {
        "id": 935918575
    }
}
```
      
  </Tab>
</Tabs>

## Coupon Applied Context Object

<Tabs>
  <Tab title="Data Schema">

<DataSchema id="10687017" />
      
  </Tab>
  <Tab title="Example">
    
```json
{
  "payload": {
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
    },
    "settings": {},
    "merchant": {
        "id": 847769313
    }
}
```
      
  </Tab>
</Tabs>

## Example Implementations

### Send Cart Recovery Email

```typescript
export default async (context: Cart): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: cart } = payload;

  if (!settings.recoveryEnabled) {
    return Resp.success().setData({ skipped: true });
  }

  const emailData = {
    to: cart.customer.email,
    template: 'cart_recovery',
    data: {
      cart_id: cart.id,
      items: cart.items,
      total: cart.total
    }
  };

  await fetch(settings.emailApiUrl, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(emailData)
  });
  
  const data = { cart_id: cart.id, email_sent: true }
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

## Sync Coupons

```typescript
export default async (context: Cart): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: coupon } = payload;

  const response = await fetch(settings.analyticsUrl, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      coupon_code: coupon.code,
      discount_amount: coupon.amount,
      order_id: coupon.order_id,
      merchant_id: merchant.id
    })
  });
  
  
  const data = { coupon_code: coupon.code }
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

## merchants-events/Category-Events

# Category Events

This model defines the structure for events triggered when categories are created or updated.

## Available Events

- `category.created` - Triggered when a new category is created
- `category.updated` - Triggered when category details are updated

## Event Type

:::note[]
**Asynchronous Events** - Processed in the background.
:::

## Category Context Object

<Tabs>
  <Tab title="Schema">

<DataSchema id="10641068" />

  </Tab>
  <Tab title="Example">

```json
{
  "payload": {
    "event": "category.updated",
    "merchant": 1419273030,
    "created_at": "Thu Nov 13 2025 12:05:09 GMT+0300",
    "data": {
      "id": 1576087344,
      "name": "Osama Sub Category",
      "image": "https://cdn.salla.sa/grmrz/categories/QsPuPsEYKwSV8buzbCcciTPlKYFmSmCHwmbzrp1S.png",
      "urls": {
        "customer": "https://demostore.salla.sa/ar/dev-fjb4uoys3xuhrgpb/osama-sub-category/c1576087344",
        "admin": "https://s.salla.sa/categories"
      },
      "parent_id": 700413444,
      "sort_order": 0,
      "status": "active",
      "show_in": { "app": true, "salla_points": false },
      "has_hidden_products": false,
      "update_at": "2025-11-13 12:05:09",
      "metadata": { "title": "title", "description": "desc", "url": null }
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
export default async (context: Category): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: category } = payload;

  const response = await fetch(`https://api.mock.com/v1/alert`, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      category_id: category.id,
      name: category.name,
      merchant_id: merchant.id
    })
  });
  
  const data = { category_id: category.id }
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
  <Step title="Navigate to Categories">
    Go to the Categories section in the demo store dashboard
  </Step>
  <Step title="Trigger the event">
    Create, update, or delete a category
  </Step>
  <Step title="Test in preview">
    Use the category ID in the App Function preview panel and click "Save and Preview"
  </Step>
</Steps>

---

## merchants-events/Communication-Events

# Communication Events

This model defines the structure for events triggered when communication is established through sms, email and WhatsApp.

## Available Events

- `communication.sms.send` - Triggered when a sms is sent to a customer
- `communication.email.send` - Triggered when a email is sent to a customer
- `communication.whatsapp.send` - Triggered when a whatsApp message is sent to a customer

## Event Type

:::note[]
**Asynchronous Events** - All communication events are processed in the background.
:::

## Communication Context Object

<Tabs>
  <Tab title="Schema">
    
<DataSchema id="10760250" />

  </Tab>
  <Tab title="Example 1">

```json
{
  "payload": {
    "event": "communication.sms.send",
    "merchant": 292111819,
    "created_at": "Mon Nov 10 2025 17:18:13 GMT+0300",
    "data": {
      "notifiable": ["+96656000000"],
      "type": "product.digital.code",
      "content": "أصبحت حالة طلبك #218103278 [تم التنفيذ]",
      "entity": {
        "id": 1741773897,
        "type": "order"
      },
      "meta": {
        "customer_id": 239462497
      }
    }
  },
  "settings": {
    "apiKey": "settings.apiKey"
  },
  "merchant": {
    "id": 292111819
  }
}
```

  </Tab>

  <Tab title="Example 2">
  ```json
  {
  "payload": {
    "event": "communication.email.send",
    "merchant": 54112478,
    "created_at": "Thu Aug 14 2025 15:44:55 GMT+0300",
    "data": {
      "notifiable": ["email@example.com"],
      "type": "message",
      "content": "Hello World",
      "entity": null,
      "meta": {
        "customer_id": 1110699905
      }
    }
  },
  "settings": {
    "apiKey": "settings.apiKey"
  },
  "merchant": {
    "id": 292111819
  }
}
````
  </Tab>

  <Tab title="Example 3">
  ```json
  {
  "payload": {
    "event": "communication.whatsapp.send",
    "merchant": 292111819,
    "created_at": "Tue Nov 11 2025 18:30:37 GMT+0300",
    "data": {
      "notifiable": ["+96656000000"],
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
  },
  "settings": {
    "apiKey": settings.apiKey
  },
  "merchant": {
    "id": 292111819
  }
}
````
  </Tab>

  <Tab title="Example 4">
  ```json
{
  "payload": {
    "event": "communication.sms.send",
    "merchant": 5511124,
    "created_at": "Sun Aug 17 2025 16:46:18 GMT+0300",
    "data": {
      "notifiable": ["+96656000000"],
      "type": "otp",
      "content": "كود التفعيل الخاص بك: 0000\n احرص على عدم مشاركته لتستمتع بتسوَّق آمن.",
      "entity": null,
      "meta": {
        "code": "0000"
      }
    }
  },
  "settings": {
    "apiKey": settings.apiKey,
  },
  "merchant": {
    "id": 292111819
  }
}
````
  </Tab>
</Tabs>

## Example Implementations

### SMS example

```typescript
export default async (context: CommunicationEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: customer } = payload;

  const crmData = {
    mobile_number: customer.notifiable[0],
  };

  const response = await fetch(settings.crmApiUrl, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Authorization: `Bearer ${settings.crmApiKey}`,
    },
    body: JSON.stringify(crmData),
  });

  const result = await response.json();

  const data = { customer_id: customer.id, crm_id: result.id };
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

### Email example

```typescript
export default async (context: CommunicationEvent): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: customer } = payload;

  console.log("Send Email event triggered");

  // Build mock email request body
  const emailRequest = {
    to: customer.email,
    subject: `Your order update from ${merchant.name}`,
    body: `Hello ${customer.first_name},\n\nYour order with ${merchant.name} is being processed.\nThank you for shopping with us!\n\nBest regards,\n${merchant.name}`,
    from: settings.emailFrom || `no-reply@${merchant.domain}`,
  };

  // Simulate sending Email via mock API
  const response = await fetch(`${settings.emailApiUrl}/send`, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Authorization: `Bearer ${settings.emailApiKey}`,
    },
    body: JSON.stringify(emailRequest),
  });

  const result = await response.json();

  const data = {
    email_id: result.id || "mock-email-id",
    status: result.status || "queued",
    to: emailRequest.to,
  };
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

---

## merchants-events/Customer-Events

# Customer Events

This model defines the structure for events triggered when customers create accounts, update profiles, or authenticate.

## Available Events

- `customer.created` - Triggered when a new customer account is created
- `customer.updated` - Triggered when customer profile is updated
- `customer.login` - Triggered when a customer logs in
- `customer.otp.request` - Triggered when a customer requests OTP

## Event Type

:::note[]
**Asynchronous Events** - All customer account events are processed in the background.
:::

## Common Use Cases

- Sync customer data with CRM
- Send welcome emails
- Track customer authentication
- Update marketing platforms
- Implement custom authentication flows

## Customer Context Object

<Tabs>
  <Tab title="Schema">
    
<DataSchema id="10641069" />

  </Tab>
  <Tab title="Example 1">

```json
{
  "payload": {
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
  },
  "settings": {
    "crmApiUrl": "https://api.crm.com",
    "crmApiKey": "your-api-key"
  }
}
```

  </Tab>

  <Tab title="Example 2">

```json
{
  "payload": {
    "event": "customer.otp.request",
    "merchant": 1029864349,
    "created_at": "Wed Jun 30 2021 12:09:11 GMT+0300",
    "data": {
      "code": "5331",
      "contact": "+96652318526"
    }
  },
  "settings": {
    "crmApiUrl": "https://api.crm.com",
    "crmApiKey": "your-api-key"
  },
  "merchant": {
    "id": 1029864349
  }
}
```

  </Tab>
</Tabs>

## Example Implementations

### Sync Customer to CRM

```typescript
export default async (context: Customer): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { event, data: customer } = payload;

  const crmData = {
    external_id: customer.id,
    first_name: customer.first_name,
    last_name: customer.last_name,
    email: customer.email,
    phone: `${customer.mobile_code}${customer.mobile}`,
    merchant_id: merchant.id,
    event_type: event
  };

  const response = await fetch(settings.crmApiUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'Authorization': `Bearer ${settings.crmApiKey}`
    },
    body: JSON.stringify(crmData)
  });

  const result = await response.json();
  
  const data = { customer_id: customer.id, crm_id: result.id }
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

### Send Welcome Email

```typescript
export default async (context: Customer): Promise<Resp> => {
  const { payload, settings, merchant } = context;
  const { data: customer } = payload;

  const emailData = {
    to: customer.email,
    template: 'welcome',
    data: {
      name: `${customer.first_name} ${customer.last_name}`,
      customer_id: customer.id
    }
  };

  await fetch(settings.emailApiUrl, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'X-API-Key': settings.emailApiKey
    },
    body: JSON.stringify(emailData)
  });
  
  const data = { customer_id: customer.id, email_sent: true }
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
  <Step title="Create customer">
    Create a new customer account or update an existing one
  </Step>
  <Step title="Test in preview">
    Use the customer ID in the App Function preview panel
  </Step>
</Steps>

---

