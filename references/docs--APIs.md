# Docs  Apis

## Table of Contents

- [docs/APIs](#docs-apis)
- [docs/AWB-Getting-Started-Salla-Merchants-APIs-Salla-Docs](#docs-awb-getting-started-salla-merchants-apis-salla-docs)
- [docs/App-Details-Builder](#docs-app-details-builder)
- [docs/App-Events-Partners-Apps-APIs-Salla-Docs](#docs-app-events-partners-apps-apis-salla-docs)
- [docs/Authorization](#docs-authorization)

---

## docs/APIs

# APIs

## Docs

- [Update Payment Method](https://docs.salla.dev/24950109e0.md): Updates payment method for an active subscription
- [Charge Subscription](https://docs.salla.dev/21070946e0.md): Manually trigger a charge for an active subscription. On success, it creates a cart from the subscription items, generates an invoice, processes payment via the configured gateway, creates a final order, and emits webhooks.
- [Cancel Subscription](https://docs.salla.dev/21076365e0.md): Cancel an active subscription immediately. This stops all future automatic charges. Existing orders/invoices remain unchanged. A webhook `subscription.cancelled` is emitted.

---

## docs/AWB-Getting-Started-Salla-Merchants-APIs-Salla-Docs

# Getting Started

App Functions give shipping companies a faster and simpler way to join the Salla AWB flow. Developers can write their logic directly inside Salla Partners without building or maintaining a backend. This reduces development time, removes infrastructure work, and makes it easier to connect shipment creation, AWB generation, and tracking with Salla Stores.

By running your logic inside Salla, you gain direct access to Salla APIs, automatic execution on key events, and a native presence in the merchant’s AWB creation screen. This creates a smooth, predictable, and fully integrated experience for both the shipping provider and the merchant.

## Benefits of Integrating With Salla Using App Functions


<CardGroup cols={2}>
<Card title="Faster Integration" icon="material-two-tone-bolt">
    Shipping providers can connect to Salla without building or maintaining a backend system. All logic runs directly inside Salla Partners, which shortens development time and removes the need for external services.
  </Card>

  <Card title="Lower Development Overhead" icon="material-two-tone-settings">
    There is no need for servers, deployments, infrastructure monitoring, or scaling. App Functions are fully managed by Salla, which reduces operational cost and complexity.
  </Card>

  <Card title="Direct Access to Salla APIs" icon="material-two-tone-link">
    Developers can call the Salla Shipping API from inside the function environment, making it easier to work with orders, shipments, and merchant data in one place.
  </Card>

  <Card title="Automatic Execution on Key Events" icon="material-two-tone-autorenew">
    Functions run automatically when specific store events occur, such as when a merchant creates, cancells, or returns an AWB. This removes the need for polling or custom triggers outside Salla.
  </Card>

</CardGroup>

  <Card title="Native Presence Inside the AWB Flow" icon="material-two-tone-dashboard">
    Your shipping service appears directly in the Salla AWB creation screen. Merchants can choose your company and process shipments without leaving the Salla dashboard.
  </Card>


## Salla AWB

This guide brings together everything needed to set up an AWB Shipping App with Salla. It explains how the app is created, how it is configured, and how it handles the app functions. It also outlines how AWB labels are generated and how shipment creation, returns, and cancellations are managed.

| Section | Description |
| -- | -- |
| **Create Shipping App** | Learn how to create the Shipping App inside Salla Partners and prepare it for integration. |
| **Setup Shipping App** | Configure webhook URLs, permissions, and App Functions to connect the Shipping App with your shipping system. |
| **Core App Functions** | Core App Functions handle the main lifecycle events that Salla triggers for shipping. <br><br>• **Shipment Creating** – Triggered when a shipment is created. Used to generate the AWB label, tracking link, and tracking number. <br>• **Shipment Cancelled** – Triggered when a shipment is cancelled. Allows the shipping system to update or confirm the cancellation status. |
| **AWB Processing Flows** | AWB Processing Flows describe how AWB labels and tracking details are generated and updated across various shipping scenarios. <br><br>• **Shipment AWB** – Standard process for generating AWB labels for new shipments. <br>• **Shipment Return AWB** – Flow for generating AWB labels and tracking info for return shipments. <br>• **Shipment Cancelled AWB** – How AWB and shipment status behave during a cancellation. |




## Community

The [Salla Developer Community](https://t.me/salladev) is a dynamic hub for developers to explore Salla products, including APIs, open-source projects, and Twilight. It is a space to collaborate, build , and ask qeustions about apps and themes, as well as create end-to-end solutions for Salla Merchants with Salla Products (such as Services, Influencers, and Affiliates). Visit the [Knowledge Base Portal](https://salla.dev) for developer-focused blogs and tutorials.

## Support

The support team is available during working hours via the following channels:


<CardGroup cols={2}>
  <Card title="Email" href="mailto:support@salla.dev" icon="material-two-tone-email">
  </Card>
  <Card title="Developers Community" href="https://t.me/salladev" icon="material-two-tone-people">
    
  </Card>
</CardGroup>

---

## docs/App-Details-Builder

# App Details Builder

## Docs

- [Get Started](https://docs.salla.dev/1524263m0.md): ### Intro
- [Components](https://docs.salla.dev/4811956f0.md):

---

## docs/App-Events-Partners-Apps-APIs-Salla-Docs

# App Events

This walkthrough is to introduce you to the partner portal events, where you can easily interact with the portal using webhooks and get real-time updates about the apps you develop using Salla Partner Portal.

| Event Name                  | Description                                                                                                   |
| --------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `app.store.authorize`       | This event is triggered whenever an App scope is authorized by the store.                                     |
| `app.installed`             | This event is triggered whenever an app is installed on a merchant store.                                     |
| `app.updated`               | This event is triggered whenever an app is updated.                                                           |
| `app.uninstalled`           | This event is triggered whenever an app is uninstalled from a merchant store.                                 |
| `app.trial.started`         | This event is triggered whenever an app's trial starts in a merchant's store.                                 |
| `app.trial.expired`         | This event is triggered whenever an app's trial subscription expires in a merchant's store.                         |
| `app.trial.canceled`         | This event is triggered whenever an app's trial subscription is cancelled in a merchant's store.                         |
| `app.subscription.started`  | This event is triggered whenever an App’s subscription starts on the merchant’s store.                        |
| `app.subscription.expired`  | This event is triggered whenever an app’s subscription ends on the merchant’s store.                          |
| `app.subscription.canceled` | This event is triggered whenever an app’s subscription is canceled on the merchant’s store.                   |
| `app.subscription.renewed`  | This event is triggered whenever an App’s subscription is renewed on the merchant’s store.                    |
| `app.feedback.created`      | This event is triggered whenever an App feedback is created by a merchant.                                    |
| `app.settings.updated`      | This event is triggered whenever a merchant activates and/or updates an app's settings in a merchant's store. |


:::tip[Test App Events]
To test the app events in demo stores, save the app as a draft after setting the [app price(s)](https://salla.dev/blog/ultimate-app-pricing-strategies-guide/). You can then proceed to test the app events in your demo stores as shown below:


![photo_2024-10-09 15.18.30.jpg](https://api.apidog.com/api/v1/projects/451700/resources/345872/image-preview)
:::

## App Store Authorize

Once a merchant installs an application on a store, the event - `app.store.authorize` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.store.authorize",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "access_token": "KGsnBcNNkR2AgHnrd0U9lCIjrUiukF_-Fb8OjRiEcog.NuZv_mJaB46jA2OHaxxxx",
    "expires": 1634819484,
    "refresh_token": "fWcceFWF9eFH4yPVOCaYHy-UolnU7iJNDH-dnZwakUE.bpSNQCNjbNg6hTxxxx",
    "scope": "settings.read branches.read offline_access",
    "token_type": "bearer"
  }
}
```

## App Installation

Once a merchant installs an app, the event - `app.installed` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

``` json
{
  "event": "app.installed",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Shipping app",
    "description": "App Description"
    "app_type": "app",
    "app_scopes": [
      "settings.read",
      "customers.read_write",
      "orders.read_write",
      "carts.read",
      "branches.read_write",
      "categories.read_write",
      "brands.read_write",
      "products.read_write",
      "webhooks.read_write",
      "payments.read",
      "taxes.read_write",
      "specialoffers.read_write",
      "countries.read",
      "metadata.read_write",
      "offline_access"
    ],
    "installation_date": "2021-09-28 06:06:56",
    "store_type": "development"
  }
}    
```

## App Update

Once the developer updates the app, the event - `app.updated` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.updated",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Shipping app",
    "description": "App Description"
    "app_type": "app",
    "categories": [
      "Accounting & Finance"
    ],
    "app_scopes": [
      "settings.read",
      "branches.read",
      "offline_access"
    ],
    "installation_date": "2021-10-06 16:16:49",
    "update_date": "2021-10-07 12:31:24",
    "store_type": "demo"
  }
}
```

## App Uninstall

Once a merchant uninstalls an app, the event - `app.uninstalled` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.uninstalled",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Cool app",
    "app_description": "This App provides a seamless, on-the-go shipping experience for businesses and individuals.",
    "app_type": "shipping",
    "categories": [
      "Shipping and Delivery"
    ],
    "installation_date": "2021-10-06 16:16:49",
    "uninstallation_date": "2021-10-07 12:46:07",
    "refunded": false,
    "store_type": "live"
  }
}
```

## App Trial Start

Once a merchant starts using an app in its trial version, the event - `app.trial.started` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.trial.started",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Shipping app",
    "app_description": "App Description"
   "app_type": "app",
    "categories": [
      "Accounting & Finance"
    ],
    "plan_name": "Diamond Plan",
    "plan_type": "one_time",
    "start_date": "2023-07-27",
    "end_date": "2023-07-28",
    "created_at": "2023-07-27 12:23:19",
    "features": [],
    "store_type": "development"
  }
}
```

## App Trial Expire

Once a merchant uses an app in its trial version has expired, the event - `app.trial.expired` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.trial.expired",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Shipping app",
    "description": "App Description"
    "app_type": "app",
    "categories": [
      "Accounting & Finance"
    ],
    "plan_name": "Diamond Plan",
    "plan_type": "one_time",
    "start_date": "2021-10-06T21:00:00.000000Z",
    "end_date": "2021-10-07T21:00:00.000000Z",
    "store_type": "demo"
  }
}
```

## App Trial Canceled

Once a merchant cancels the usage of an app in its trial version, the event - `app.trial.started` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.trial.canceled",
  "merchant": 74955415,
  "created_at": "2023-07-27 12:32:17",
  "data": {
    "id": 2114981050,
    "app_name": "Shipping App",
    "app_description": "App Description",
    "app_type": "public",
    "categories": [
      "Accounting & Finance"
    ],
    "plan_type": "recurring",
    "plan_name": null,
    "start_date": "2023-07-27",
    "end_date": "2023-07-28",
    "subscription_at": "2023-07-27 12:13:58",
    "created_at": "2023-07-27 12:32:17",
    "features": [],
    "store_type": "live"
  }
}
```

## App Subscription Start

Once a merchant’s subscription starts using an app, the event - `app.subscription.started` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.subscription.started",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "subscription_id": 1510766049,
    "app_name": "Shipping app",
    "description": "App Description"
    "app_type": "app",
    "categories": [
      "Marketing"
    ],
    "plan_type": "recurring",
    "plan_name": null,
    "plan_period": "1",
    "start_date": "2021-10-09T21:00:00.000000Z",
    "end_date": "2022-10-09T21:00:00.000000Z",
    "coupon": {
      "name": "SPZGRDFS",
      "amount": "0.15"
    },
    "initialization_cost": 10,
    "price_before_discount": 5,
    "price": "20.00",
    "tax": "0.15",
    "tax_value": "3.00",
    "total": "23.00",
    "subscription_balance": "null",
    "features": [
        {
          "key": "Feature1",
          "quantity": 1
        },
        {
          "key": "Feature3",
          "quantity": 5
        }
      ],
      "store_type": "development",
      "promotion": {
          "id": 98784255,
          "requirement": 1, // required number of months or years
          "reward": 1 // number of months or years for the reward
      }
  }
}
```



## App Subscription Canceled

Once a merchant’s subscription is canceled, the event - `app.subscription.canceled` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.subscription.canceled",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "subscription_id": 1510766049,
    "app_name": "Shipping app",
    "description": "App Description"
    "app_type": "app",
    "categories": [
      "Marketing"
    ],
    "plan_type": "recurring",
    "plan_name": null,
    "plan_period": "1",
    "start_date": "2021-10-09T21:00:00.000000Z",
    "end_date": "2021-11-09T21:00:00.000000Z",
    "coupon": {
      "name": "SPZGRDFS",
      "amount": "0.15"
    },
    "initialization_cost": 10,
    "price_before_discount": 5,
    "price": "20.00",
    "tax": "0.15",
    "tax_value": "3.00",
    "total": "23.00",
    "subscription_balance": "null",
    "features": [
      {
        "key": "Feature1",
        "quantity": 1
      },
      {
        "key": "Feature3",
        "quantity": 5
      }
    ],
    "store_type": "demo"
  }
}
```

## App Subscription Expire

Once a merchant’s subscription expires using an app, the event - `app.subscription.expired` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.subscription.expired",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "subscription_id": 1510766049,
    "app_name": "Shipping app",
    "description": "App Description"
    "app_type": "app",
    "categories": [
      "Marketing"
    ],
    "plan_type": "recurring",
    "plan_name": null,
    "plan_period": "1",
    "start_date": "2021-10-09T21:00:00.000000Z",
    "end_date": "2021-11-09T21:00:00.000000Z",
    "coupon": {
      "name": "SPZGRDFS",
      "amount": "0.15"
    },
    "initialization_cost": 10,
    "price_before_discount": 5,
    "price": "20.00",
    "tax": "0.15",
    "tax_value": "3.00",
    "total": "23.00",
    "subscription_balance": "null",
    "features": [
      {
        "key": "Feature1",
        "quantity": 1
      },
      {
        "key": "Feature3",
        "quantity": 5
      }
    ],
    "store_type": "live"
  }
}
```

## App Subscription Renew

Once a merchant’s subscription is renewed using an app, the event - `app.subscription.renewed` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.subscription.renewed",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "subscription_id": 1510766049,
    "app_name": "Shipping app",
    "description": "App Description"
   "app_type": "app",
    "categories": [
      "Marketing"
    ],
    "plan_type": "recurring",
    "plan_name": null,
    "plan_period": "1",
    "start_date": "2021-10-09T21:00:00.000000Z",
    "renew_date": "2021-11-09T21:00:00.000000Z",
    "end_date": "2021-12-09T21:00:00.000000Z",
    "coupon": {
      "name": "SPZGRDFS",
      "amount": "0.15"
    },
    "initialization_cost": 10,
    "price_before_discount": 5,
    "price": "20.00",
    "tax": "0.15",
    "tax_value": "3.00",
    "total": "23.00",
    "subscription_balance": "null",
    "features": [
      {
        "key": "Feature1",
        "quantity": 1
      },
      {
        "key": "Feature3",
        "quantity": 5
      }
    ],
    "store_type": "development"
  }
}
```

## App Feedback Created

Once a merchant writes a review for an application, the event - `app.feedback.created` - will be triggered. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.feedback.created",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Shipping app",
    "description": "App Description"
   "app_type": "app",
    "categories": [
      "Marketing"
    ],
    "rating": "5",
    "rated_by": "الإخلاص-تعديل",
    "comment": "No Comments"
  }
}
```
## App Settings Updated

Once a merchant either activates and/or updates your applciation's settings on a store, the event - `app.settings.updated` - will be triggered. You can customize the variables below using the drag & drop functionality on your app's settings. Afterward, you will receive a similar payload to the following:

### Payload

```json
{
  "event": "app.settings.updated",
  "merchant": 1234509876,
  "created_at": "2022-12-31 12:31:25",
  "data": {
    "id": 6789012345,
    "app_name": "Shipping app",
    "app_description": "App Description",
    "app_type": "public",
    "settings": {
      "name": "Mohammed",
      "email": "Mohammed@Gmail.com",
      "subscription_num": 375853796,
      "door_to_door": true,
      "pickup_time": "09:00:00",
      "box_size": [
        "25x25",
        "10x10"
      ],
      "ads_activated": "true"
    }
  }
}
```

---

## docs/Authorization

# Authorization

OAuth is a widely adopted authorization framework that allows you to consent to an App interacting with another on your behalf without having to reveal Merchant's sensitive data, such as passwords.

If you are building integrations that require access to Salla on behalf of other Salla Merchants, you should utilize [OAuth 2.0 Protocol for Salla](https://salla.dev/blog/oauth-2-0-in-action-with-salla/). You can use OAuth in gaining access to Merchants' stores with either [Easy Mode](https://salla.dev/blog/oauth-2-0-in-action-with-salla/) or [Custom Mode](https://salla.dev/blog/oauth-2-0-in-action-with-salla/), using access tokens via the Apps built on [Salla Partners Portal](https://salla.partners/), which will be published on
[Salla App Store](http://apps.salla.sa/).

:::check[]
**Salla OAuth Format**
All calls to the Merchant Public APIs require an Authorization header in this format:
**Authorization:** Bearer `<ACCESS_TOKEN>`
:::

# What You will Need Before You Start:

<Steps>
  <Step title="First Step">
    Open and verify account on [Salla Partners](https://salla.partners/).
  </Step>
  <Step title="Second Step">
    Either use a sample App you [created](https://salla.dev/blog/create-your-first-app-on-salla-developer-portal/) previously or build a new one from the scratch.
  </Step>
  <Step title="Third Step">
    Choose an OAuth method, [Easy Mode](https://salladev.hashnode.dev/review-on-salla-merchants-apis#heading-generate-access-token-using-salla-app-and-demo-store) or Custom Mode Authorization.
  </Step>
  <Step title="Fourth Step">
    Set up the scopes of your App to specify the needed access level.
  </Step>
  <Step title="Fifth Step">
    Generate a [demo store](https://salla.dev/blog/how-to-test-your-app-using-salla-demo-stores/), so no sensitive data is compromised.
  </Step>
  <Step title="Sixth Step">
    [Install](https://salla.dev/blog/how-to-test-your-app-using-salla-demo-stores/) the App on the demo store for real-world mockup test.
  </Step>
</Steps>

<!-- ## Main Requirements for Authentication

TBD -->

# Salla OAuth Benefits

<CardGroup cols={3}>
  <Card title="🔐 Authorized Access">
Apps are given authorized access, which means they can only access resources that the Merchant has authenticated.
  </Card>
  <Card title="⛓️‍💥 Revoke Access">
   The App's authorized access can be revoked at any time by the Merchant by disconnecting the App from the dashboard on Salla Partners.
  </Card>
  <Card title="⌛️ Time Limit">
  OAuth 2.0 access tokens have a time limit. Merchant data will be compromised only until the access token is valid if the App encounters a security breach.
  </Card>
</CardGroup>

# Salla’s OAuth2.0 Flow

The **OAuth 2.0** authorization flow is the **initial step in installing an App on the Salla platform**. By requiring the merchant to grant permission for the App to access their data within specific scope, this process helps to ensure that the store's data is safe and private. The OAuth 2.0 authorization procedure can be started by one of the following URLs:

<CardGroup cols={2}>
  <Card>
   The Authorization URL: <CopyToClipboard> `https://accounts.salla.sa/oauth2/auth` </CopyToClipboard>
  </Card>
  <Card>
   The Installation URL: <CopyToClipboard> `https://s.salla.sa/apps/install/{app-id}` </CopyToClipboard>
  </Card>
</CardGroup>

## The authorization Flow

The **OAuth 2.0** authentication flow for _installing an App on a Salla Store_ includes crucial URLs and endpoints that enable permission granting, code-to-token exchange, redirection, and token refreshing. The process involves the merchant's redirection to the **Salla Authorization Server**, login, granting permission, and obtaining an access token for API requests and accessing store data.

The following table summarize these and endpoints:

| URL                    | Description                                                                                                                                                                                                            |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization Endpoint | <CopyToClipboard> `https://accounts.salla.sa/oauth2/auth` </CopyToClipboard> <br> This URL initiates the process of obtaining the merchant's permission for the App to access their store data on Salla.               |
| Token Endpoint         | <CopyToClipboard> `https://accounts.salla.sa/oauth2/token` </CopyToClipboard> <br> After the merchant grants permission, the App exchanges the authorization code for an access token at this endpoint.                |
| Redirect URI           | <CopyToClipboard>`https://client-app.com/callback`</CopyToClipboard> <br> Once the authentication process is complete, the authorization server redirects the user's browser to the registered redirect URI.           |
| Refresh Token Endpoint | <CopyToClipboard> `https://accounts.salla.sa/oauth2/token` </CopyToClipboard> <br> If a refresh token is granted, this endpoint allows the client to obtain a new access token when the current one expires.           |
| User Info Endpoint     | <CopyToClipboard>`https://accounts.salla.sa/oauth2/user/info`</CopyToClipboard> <br> Once the authentication process is completed successfully, the Merchant details can be received via [this endpoint](api-5394260). |

:::tip[]
To use the Authorization Endpoint **<CopyToClipboard>https://accounts.salla.sa/oauth2/auth</CopyToClipboard>** in your code, you will typically need to make an HTTP request to that URL.
:::

In addition to the base URLs mentioned above, **OAuth 2.0 also uses query parameters** to pass information during the authentication process. These query parameters serve different purposes and are included in the URLs when making requests to the authorization and token endpoints. Here are some common query parameters used in OAuth 2.0:

| Query Parameter | Description                                                                                                                           | Example                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `client_id`     | Identifies the client application making the request, which values can be fetched from your application on the Salla Partners Portal. | `1311508470xxx`                                                      |
| `client_secret` | Identifies the client application making the request, which values can be fetched from your application on the Salla Partners Portal. | `362985662xxx`                                                       |
| `response_type` | Specifies the desired response type from the authorization server.                                                                    | <CopyToClipboard>`code`</CopyToClipboard>                            |
| `redirect_uri`  | Indicates the URI for user redirection after completing the authorization process.                                                    | <CopyToClipboard>https://your-app.com/callback-url</CopyToClipboard> |
| `scope`         | Specifies the requested permissions or access levels.                                                                                 | <CopyToClipboard>`offline_access`</CopyToClipboard>                  |
| `state`         | Used to maintain state between the authorization request and the callback to prevent cross-site request forgery attacks.              | `1234xxxx`                                                           |
| `code`          | The authorization code returned by the authorization endpoint.                                                                        | xxxxxxxx                                                             |
| `grant_type`    | Specifies the type of grant being used to authenticate the client.                                                                    | <CopyToClipboard>`authorization_code`</CopyToClipboard>              |

<Container>

#### Including the client ID as a query parameter

It is common practice **to include the client ID as a query parameter in the authorization URL** for OAuth 2.0 authentication. This inclusion allows the authorization server _to associate the authentication request with the specific client_, ensuring client identification and authentication during the process. Here's an example of how the client ID can be included in the authorization URL:

<CopyToClipboard>
```json
https://accounts.salla.sa/oauth2/auth?client_id=your_client_id&response_type=code&redirect_uri=https://client-app.com/callback&scope=read write&state=random_value
```
</CopyToClipboard>

In the example above, `client_id=your_client_id` is appended to the authorization URL, where _your_client_id_ should be replaced with the actual client ID issued by the authorization server.

:::check[]
Including the **client ID as a query parameter** in the authorization URL ensures authentication and identification of the client during **OAuth 2.0**. _If the App has been previously approved_, _scope approval steps may be skipped_, streamlining the process.
:::

</Container>
    
## The installation URL

On the other hand, **the installation URL** allows for the immediate installation of the App to the merchant store. Unlike the typical authorization URL, the installation URL simplifies the app installation process by providing a direct URL with the `app-id` as a parameter. This URL can be used to initiate the app installation process. When the merchant clicks on the installation URL, the App will be automatically installed into their Salla Store.

The following diagram explains the flow of OAuth 2.0 in Salla, which will eventually result in access token generation.

<!-- focus: true-->

![OAuth](https://cdn.salla.network/docs/MerchantAPI/Intro-Auth-04.jpeg)

# Types of OAuth 2.0 in Salla

On [Salla Partners Portal](https://salla.partners/), and when you are creating your [App](https://salla.dev/blog/create-your-first-app-on-salla-developer-portal/), inside the App page details within the App Keys section, you will be provided with two methods for the OAuth protocol:

- **Easy Mode**, which is a simplified version of the protocol that requires minimal setup.
- **Custom Mode**, which allows for more advanced, manual configuration and the use of callback URLs.

<!--focus: false -->

![Modes Image](https://cdn.salla.network/docs/MerchantAPI/Intro-Auth-05.png?v)

## Easy Mode (Recommended)

<!--focus: false -->
<!-- ![Easy Mode Image](https://i.ibb.co/vHZ4tZS/Clean-Shot-2022-02-13-at-12-04-32-2x.png) -->

One of the foremost options of authorization via OAuth 2.0 in [Salla Partners](https://salla.partners) is Easy Mode Authorization. Utilizing Salla’s easy mode option, you can get the “[access token](https://docs.salla.dev/doc-421413#app-store-authorize)” in one step automatically. It allows you to listen to the event, [`app.store.authorize`](https://docs.salla.dev/doc-421413#app-store-authorize), and then the process of generating the “[access token](https://docs.salla.dev/doc-421413#app-store-authorize)” will be handled automatically at Salla‘s side back to you via the [Webhook URL](https://docs.salla.dev/doc-421119#set-up-troubleshooting-environment) specified in the Webhooks/Notifications your of your App.

By selecting the Easy Mode Authorization option, Salla will handle everything, including extracting the authorization code and providing the client id and secret key together with the auth code to generate an access token. In the end, you will receive all of the above data in the form of a payload that contains a new access token generated for you, **as the life validity of access tokens with Salla is 2 weeks**.

:::check[]
Find more on how to further setup the easy mode by reading [this article](https://salladev.hashnode.dev/review-on-salla-merchants-apis#heading-generate-access-token-using-salla-app-and-demo-store).
:::

### Generate Access Token using Salla App and Demo Store

The access token can be obtained from a [demo store](https://salla.dev/blog/how-to-test-your-app-using-salla-demo-stores/) using a Salla App where both are linked to your Partners Account .

<Steps>
  <Step title="Salla Partners Dashboard | Application">

On the Partners dashboard, go to Apps and choose any App you developed.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe5UNeVgRpvVI5W3bfT9gdL0uJ-DFiG2AXRJIqIfEgR2CkHbQS73RzJJGL2KDCBo_4o0Yu6CdmMYlalP4tqlFcQKY5riPb5o_KVFu9hqGzw_GyePXh6tKCyh3trBRpatJc9lkNjS-P68FE8Dv4BtUMlGmoi?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
  <Step title="App Scopes Setup">

Set up the App Scope and check the boxes that matches your app scope, such as Product, Order and Webhooks, then click **Update Scope**.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdQ2K280YNeorPLHNQp7lq0hhhkw1dbOowi6kc6huOhvChYLFDBujb10Xf1IsnRalaJd1-h-m-0Ze-wgnRDpp3iaIa7O7aOVPOdzcrVSxt5grKF8GcL7E4X8Yz-2ChQt62X0gsC73ZRMiO29K1nR_-JQ3Ks?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
  <Step title="Webhook Setup">

Set up the App Webhooks details using [Webhook.site](http://Webhook.site). Copy the Webhook link from the page.

:::warning[]
It is best to use your own webhook, since [webhook.site](https://webhook.site) is only for demonstration purposes.
:::

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeldb1eUNQos3v610U-6P1A6RRUDzlz6iy30S6OKCHGk5vgz602XfBFrUtI-_DSqDnNTqZMFHY2KKZJaR_J2vjw5H4sV02o3BNADRp8dzYBCwnF8O_dMWJUDD5LfesXDQRn8DIeKzmDirwAjan8GSo8eeI_?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
  <Step title="Add Webhook on Salla Partners">

Then add it as a Webhook URL for the App.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfSMUy-2TdzXVS60Pnx4SEBqB3xBsysk02hYVXcS-6gBTUGRG5qFm1YN6P7swWC4q4vPe023dEcAAGxnz2sbjJbF2vLZkwI6Rzb9zqfK50-kNSWLSWVMKpFVNO40BXam0PBEdZNU-IrO1WhQm9AwqqNQWY?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
  <Step title="Install App using Demo Stores">

Scroll down to the Test App section and install the App on a demo store by clicking the **Install App** button next to the demo store.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd_LGbQo-8JPNHi6-3XVLzGeB0jJ2FrXX4zBNoQDrAj2qEdmYkeV_qNJIxuWWmM1zlERTmqigPsK0t1htmzIQ4QfU4GyUkk_JAaIKZut15TzlgDB7ieNhAg9TB7Xb9e_1UxolN-qPRZP_JPk4j_8KEa5XC_?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
  <Step title="App Approval as a Store Owner">

This will redirect you to the store dashboard page where you can approve the App installment. Approve the installment request to proceed.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdkw7LCQhjDa4L4P7DcPpKjFBz1tUZbASmPw031UgvU6fEZ6I3PTHzjSosWJiND0nwaZtCRArYTZXz9If3nZteMEQ6OPpzsS1Csp-XYmAtYaKgMt54uiqT9TFinWtEQvrYGS3sD-ekmiCtPHqB9zI9Ig4Jx?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
    
      <Step title="Retrieve Access Token from Webhook">

After that, go back to the [Webhook.site](http://Webhook.site) and get the Access Token from the `app.store.authorize` event.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdhWejEXoVP2Q0sSfhsYkG4h9oZPja9n_e_b-u8gE_3Mo8ZI8DGe0L-Y-9KoMiCyYI8rkp84VhT5b6B6txXyyN3hp3iAoRRfUxrYpGVBUOoUD0Xd9SEvjQBsRM5CZR1bh2Wjs2Dwklq7q8Z6A__l-V1Ef8?key=z6sib4CQioMEBm7IjT__cQ)

  </Step>
    
</Steps>

<br>

:::tip[App Update]
In the easy mode, when the Merchant updates the app, Salla sends you the [`app.updated`](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ) event. After that, Salla sends you the [`app store.authorized`](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ) event, which provides you with the new access token and refresh token. This information will be delivered to you via webhook. Accordingly, you are required to update the access token and refresh token in your database.
:::

 
:::warning
The `expires` variable is returned as a unix timestamp value for the app event `app.store.authorize`.
:::


## Custom Mode

When implementing an OAuth flow or any other third-party API that needs to redirect to the App after authentication or authorization, a callback URL should be set. The App will use this URL to reroute back to the App after the login and App scopes' permission procedures are finished. This cycle of authentication is called Custom Mode authentication.

### Custom Mode Use Cases:

<CardGroup cols={3}>
  <Card>
    App for online grocery stores that redirect users back to the store after they log in with their Google account.
  </Card>
  <Card>
   App for onlines store that redirects customers back to the product page after they sign up for a newsletter
  </Card>
  <Card>
  App for bookstores that redirects customers back to their reading list after they rate a book. 
  </Card>
</CardGroup>

There are two steps that we need to follow in order to successfully set up a Custom Mode OAuth in Salla:

### 1. User Authorization

A Merchant has to authorize your App, with the set of App scopes, to be able to proceed with the process of obtaining the access token. Direct the Merchant to the callback URL you used while setting up your App on [Salla Partner Portal](https://salla.partners). If this is the first time that you are requesting authorization from a Merchant, the merchant will be asked to log in to his/her Salla Store.

To obtain the access token for your App, the Merchant needs to authorize it with the App scopes.
Once the Merchant has logged in to their Salla Store account, they will be prompted by Salla to authorize access to your App. The merchant will be asked to grant authorization for your App to access their store data with the defined scopes.

<!--
focus: false
-->

![Intro to OAuth image](https://cdn.salla.network/docs/MerchantAPI/Intro-Auth-01-02.png)

<br>

If the access has been authorized, the user will be redirected to the Callback URL with the authorization code in the code query parameter, which you can fetch to continue the process of obtaining the access token:

<CopyToClipboard>
`https://yourapp.com/callback?code={code-value}&scope={app-scopes}+offline_access&state={state-value}
`
</CopyToClipboard>

### 2. Access Token Generation

When the Merchant authorizes the App, Salla returns the Merchant to your Callback URL with a code parameter containing an authorization code. Use the code in your access token request, which is a `POST` request with the required parameters to the token endpoint.

<Tabs>
  <Tab title="Access Token Request">

Easily run the request straight from Postman by providing the required data to generate an access token

<br> [![Run in Postman](https://run.pstmn.io/button.svg)](https://www.postman.com/salla-app/workspace/salla-e-commerce-platform/request/17687195-9d1a55a9-514d-43ef-abe9-4870e266b696?ctx=documentation)

:::warning
Easy Mode is the only way allowed for published apps on the [Salla App Store](https://apps.salla.sa). Since Postman uses custom mode, you can implement that in your app for testing purposes only.
:::

  </Tab>

  <Tab title="Access Token Response">

```json
{
    "access_token": "ory_at_xqk9wODumvYyX8pIJVR-K2awBTsgE2IRZvRDOCHZ03Y.fkxXqRAmLEY_vZZnqD-iY67pvoZvPurYxEm-SoFl9MM",
    "expires": 1209599,
    "refresh_token": "ory_rt_nXjleNBPjVvTvch3SGJwtv28HOTX6FetRewPSrNJkq0.-M1SGikK7r4or6RjdiH_agZZBp22mW8EGdOZh-PUsRM",
    "scope": "settings.read customers.read_write orders.read_write carts.read branches.read_write categories.read_write brands.read_write products.read_write webhooks.read_write payments.read taxes.read_write specialoffers.read_write shippings.read_write marketing.read_write metadata.read_write offline_access",
    "token_type": "bearer"
}
```

  </Tab>
</Tabs>

### Body Definition

The following enlists the values that are sent to the User Authorization endpoint to generate an access token:

<DataSchema id="1447895" />

<br>

:::highlight gray

<h3>Important Notes</h3>

|                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| • Access tokens expire after 2 weeks (14 days).                                                                                                                                                                                                        |
| • If you want to generate the refresh token, set the scope value as `offline_access`. E.G: `scope = offline_access`.                                                                                                                                   |
| • The `expires` variable is returned as `seconds` timestamp value                                                                                                                                                                                      |
| • Upon obtaining the access token, developers can utilize the [User Info endpoint](https://docs.salla.dev/api-5394260) URL, `https://accounts.salla.sa/oauth2/user/info`, to retrieve the Merchant details and store them alongside the access tokens. |

:::

### Refresh Access Token

A typical reason for refreshing a token is that the original access token has expired, which lasts for only 14 days (2 weeks). If you would like to request a new access token, you may do so by sending Salla’s authorization server a token refresh request. Refresh tokens are single-use only, meaning they become invalid after the first use.

Every time a developer uses a refresh token to request a new access token, a new refresh token is issued, and the previous token is invalidated. This mechanism adds an extra layer of security, making it more difficult for attackers to use stolen refresh tokens. A refresh token lasts for 1 month, and attempting to use it twice invalidates the associated access token.

<!--
:::highlight gray 📝

### Important Notes

<CardGroup cols={2}>
  <Card title="">
Refresh tokens expire after 1 month. The latest refresh token must always be used for the next refresh request. 
  </Card>
  <Card title="">
The `expires` variable is returned as `seconds` timestamp value
  </Card>
</CardGroup>

::: -->

:::danger[Warning: Refresh Token Reuse]
Reusing refresh tokens in parallel processes or making multiple simultaneous refresh requests can lead to complete authentication failure. When a refresh token is used more than once, Salla's OAuth server will:

- Invalidate the refresh token
- Revoke all access tokens obtained with it
- Reject all subsequent authentication attempts using that refresh token
- Requires the Merchant to reinstall the application from the [Salla App Store](https://apps.salla.sa) for you to regain access to their data.

This security measure is implemented in accordance with [RFC 6819 Section 5.2.2.3](https://datatracker.ietf.org/doc/html/rfc6819#section-5.2.2.3) to prevent replay attacks.

<TipGood> **Recommended Implementation**: To prevent refresh token reuse in your application, implement a mutex/locking mechanism for token refresh operations </TipGood>

:::

### Body Definition

The following enlists the values that are sent to the Token endpoint to Refreshing Access Tokens:

<Tabs>
  <Tab title="Refresh Access Token Request">
 
Easily run the request straight from Postman by providing the required data to generate an access token

<br> [![Run in Postman](https://run.pstmn.io/button.svg)](https://www.postman.com/salla-app/workspace/salla-e-commerce-platform/request/17687195-852c447f-1cd0-4124-af80-560e41df918d?ctx=documentation)

  </Tab>
  <Tab title="Refresh Access Token Response">
    
```json
{
    "access_token": "ory_at_xqk9wODumvYyX8pIJVR-K2awBTsgE2IRZvRDOCHZ03Y.fkxXqRAmLEY_vZZnqD-iY67pvoZvPurYxEm-SoFl9MM",
    "expires_in": 1209599, //this is returned as `seconds` timestamp value
    "refresh_token": "ory_rt_nXjleNBPjVvTvch3SGJxxxx",
    "scope": "settings.read customers.read_write orders.read_write carts.read branches.read_write categories.read_write brands.read_write products.read_write webhooks.read_write payments.read taxes.read_write specialoffers.read_write shippings.read_write marketing.read_write metadata.read_write offline_access",
    "token_type": "bearer"
}
```
  </Tab>

</Tabs>

<br>

<CardGroup cols={2}>
    
#### Important Notes
    
  <Card >
Refresh tokens expire after 1 month. The latest refresh token must always be used for the next refresh request. 
  </Card>
  <Card >
The `expires` variable 
  </Card>
</CardGroup>

# Access Token Usage Example

Now you may use the access token to make requests, on behalf of the Merchant, from the resource server via the API _(base endpoint url: <CopyToClipboard>https://api.salla.dev/admin/v2/</CopyToClipboard>)_. For more information about making API requests, the full API documentation is available [here](https://docs.salla.dev/doc-421117).

<!-- After obtaining the Merchant's authorization and upon receiving the access token, we can put that into practical example by consuming any of [Salla's API endpoints](https://docs.salla.dev/docs/merchant/fccf7c395e5d2-get-started).  -->

<!-- If the access token isn't working, this might be because it expired and is invalid to be used unless refreshed within a 1-month time period.  -->

With the access token and the authroized App scopes to the App, you may start consuming any of [Salla's API endpoints](https://docs.salla.dev/doc-421117), such as fetching a list of [brands](https://docs.salla.dev/api-5394213)

[<img src="https://run.pstmn.io/button.svg" alt="Run In Postman" style="width: 128px; height: 32px;" />](https://god.gw.postman.com/run-collection/17687195-dc776b52-482b-4dec-ae7b-9659b71a62aa?action=collection%2Ffork&source=rip_markdown&collection-url=entityId%3D17687195-dc776b52-482b-4dec-ae7b-9659b71a62aa%26entityType%3Dcollection%26workspaceId%3D0e589b64-253f-44c2-b947-7508724ec833)

# IP Whitelisting

[IP whitelisting](https://salla.dev/blog/secure-your-apps-with-the-trusted-ip-address-now/) is a security feature that restricts access to an App to only the IP addresses that are included on the whitelist. This can be used to restrict unwanted access and protect critical data from potential compromise.

It works by denying all IP addresses, except for those specifically listed as "whitelisted," thereby limiting the access to only approved users. This way, developers can better protect their private data from potential outside threats, such as hackers and malware, by reducing the attack surface area.

IP Whitelisting can also be used for other purposes such as controlling bandwidth usage or limiting access to certain services. You may reach the App setup page by going to the Partners Dashboard and selecting the "My Apps" tab:

<!--focus: false -->

![Image1](https://cdn.salla.network/docs/MerchantAPI/Intro-Auth-02.png)

From this page, you can add the permitted IP addresses in the following area, which is labeled "App Trusted IPs":

<!--focus: false -->

![image2](https://cdn.salla.network/docs/MerchantAPI/Intro-Auth-03.png)

<br>

:::note
Get additional information about App Trusted IPs by visiting **[this article](https://salla.dev/blog/secure-your-apps-with-the-trusted-ip-address-now/).**
:::

# Open-Source Libraries

Salla developed various clients and OAuth-specific libraries, such as:

<CardGroup cols={3}>
  <Card href="https://github.com/SallaApp/oauth2-merchant">
PHP Client | OAuth2 Merchant
  </Card>
  <Card href="https://github.com/SallaApp/passport-strategy">
JavaScript Client | Passport Strategy
  </Card>
  <Card href="https://github.com/SallaApp/laravel-starter-kit/blob/master/app/Http/Controllers/OAuthController.php">
Laravel Starter Kit | OAuth Controller
  </Card>
</CardGroup>

These open-source libraries, powered by Salla, are here to assist in bootstrapping your development journey with Salla by providing code snippets easily accessible, readable, and maintainable by Salla’s own experts as well as the Global Community of developers.

---

