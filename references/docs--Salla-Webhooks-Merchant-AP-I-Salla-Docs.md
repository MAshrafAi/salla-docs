# Docs  Salla Webhooks Merchant Ap I Salla Docs

## Table of Contents

- [docs/Salla-Webhooks-Merchant-AP-I-Salla-Docs](#docs-salla-webhooks-merchant-ap-i-salla-docs)
- [docs/Security-Considerations-Merchant-API-Salla-Docs](#docs-security-considerations-merchant-api-salla-docs)
- [docs/Settings](#docs-settings)
- [docs/Settlements](#docs-settlements)
- [docs/Setup-Shipping-App-AWB-Salla-Merchants-APIs-Salla-Docs](#docs-setup-shipping-app-awb-salla-merchants-apis-salla-docs)
- [docs/Shipments](#docs-shipments)
- [docs/Shipping-Companies](#docs-shipping-companies)
- [docs/Shipping-Management](#docs-shipping-management)
- [docs/Shipping-Routes](#docs-shipping-routes)
- [docs/Shipping-and-Fulfilment-API-Change-Log](#docs-shipping-and-fulfilment-api-change-log)
- [docs/Subscriptions](#docs-subscriptions)
- [docs/Support-Merchant-API-Salla-Docs](#docs-support-merchant-api-salla-docs)
- [docs/Supported-Events-App-Functions-Documentation-Salla-Docs](#docs-supported-events-app-functions-documentation-salla-docs)
- [docs/Testing-App-Functions-Documentation-Salla-Docs](#docs-testing-app-functions-documentation-salla-docs)

---

## docs/Salla-Webhooks-Merchant-AP-I-Salla-Docs

# Webhooks

Salla's Webhooks allows you to easily set up fully automated notifications, as you get to be notified whenever your App receives payload/data from a merchant store. They are triggered when:

- A merchant installs an App 
- An order or product is created in the merchant store.
- A coupon is applied, and much more

You can then use the information sent via webhooks to trigger other actions or integrate with external systems. This makes it simple to customize your notifications and keep track of all changes occurring within your Salla account.

<!-- Find more about webhooks in this [introductory article](https://site.salla.dev/blog/webhooks-101/). A full-fledged API Documentation regarding webhooks is on the official [Salla online documentation](http://docs.salla.dev) -->

## Security Implementation

<hr>

**Salla** secures webhook communication using headers. When an event occurs, Salla will send these headers and the relevant details to the specified App along with the token or signature verifies that the request is from Salla. Alternately, you can create a customized key and value to use with Salla's payload.

The following image illustrates how the Webhook communication is conducted in a secured vs insecured environment.  


![](https://cdn.salla.network/docs/Intro-Webhooks-00.png)

You can easily authenticate webhook calls using Salla's built-in options, which are **Signature**, and **Token**. The strategies are described in depth in the section that follows.


:::warning
Using Salla's tokens or signatures while `POST`ing data, allows you to authenticate the sender. Otherwise, deny any other suspicious requests.
:::



### Regsiter Webhooks

<hr>

There are noticeable, interchangeable parameters in the latest Salla API update. Let us take a look at the structures in both [versions](https://docs.salla.dev/doc-421126) as we get responses from a webhook

When sending the parameters using any endpoints from Salla, there are common properties they share, although having different structure. For more on the hows to register a webhook, check either the [previous section](#security-implementation) or this [API](https://docs.salla.dev/api-5394134).

| Parameter     | Type          | Description                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------- | ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name          | string        | Webhook Name                                                                                                                                                                                                                                                                                                                                                                                 |
| event         | string        | Webhook Event [From Event List](https://docs.salla.dev/doc-421119#list-of-salla-store-events)                                                                                                                                                                                                                                                                                |
| version       | number        | [Webhook Version](https://docs.salla.dev/doc-421126); of the webhook; either valued as `1` or `2`.                                                                                                                                                                                                                                                               |
| rule          | string        | Operations, expressions and conditions to your webhook. For example, you may use `=`,`!=`,`AND`,`OR` etc in such a menner: `payment_method = YOUR_PAYMENT_METHOD` or in combination `payment_method = mada OR price < 50`. That adds more capbility to filter the response based on conditions                                                                                               |
| url           | string        | Webhook URL where you will receive the webhook calls                                                                                                                                                                                                                                                                                                                                         |
| headers       | array[object] | Webhook headers containing security info                                                                                                                                                                                                                                                                                                                                                     |
| headers.key   | string        | Any haeder key, which its value is sent in the post request to the webhook URL                                                                                                                                                                                                                                                                                                               |
| headers.value | string        | The value sent to the webhook; for example: `cf-ray: 669af54ecf55dfcb-FRA`                                                                                                                                                                                                                                                                                                                   |  | security_strategy | string | Adapted security strategy. Value can either be `signature`, `token`, or `none` |
| secret        | string        | Secret Token value                                                                                                                                                                                                                                                                                                                                                                           |
| version       | string        | [Webhook Version](doc-421126); either valued as `1` or `2`.                                                                                                                                                                                                                                                                               |
| rule          | string        | Operations, expressions and conditions to your webhook. For example, you may use `=`,`!=`,`AND`,`OR` etc in such a menner: `payment_method = YOUR_PAYMENT_METHOD` or in combination `payment_method = mada OR price < 50`. That adds more capbility to filter the response based on conditions. Read more [here](https://docs.salla.dev/doc-421120) |


:::warning
Salla currently uses [API Version `2`](https://docs.salla.dev/doc-421126). By default, all new registered webhooks will be set as version `2`. If you want to use version `1` of the webhook, pass that in your request parameter. Additionally, Salla will assign the Security Strategy to `Signature` by default in case you registered a webhook with no security strategy defined in your body request.
:::



### Security Strategies


<Tabs>
  <Tab title="✍️ Using Signature">

For all created [Partner Apps](https://salla.partners/apps), Salla will assign the `signature` security strategy by default, as Salla will hash payloads via an auto-generated, reproducable signature token. It will also append two headers to the webhook payload; the security startegy used as in `X-Salla-Security-Strategy` which is in this context `Signature` , and a hashed token signature as in `4d7dac8e688eca1c1xxxx`

| Security Startegy | Header                    | Token Suffix      |
| ----------------- | ------------------------- | ----------------- |
| Signature         | X-Salla-Security-Strategy | X-Salla-Signature |

<!-- focus: top
bg: "#5fd5c5"
-->
![signature](https://cdn.salla.network/docs/MerchantAPI/Intro-Webhooks-02.png 'Signature Representation on Salla Partners')
      
### Register Endpoint

Following is the expected request payload for the `Signature` security strategy:


<DataSchema id="1383997" />

<!-- where in details:

| Key Name                    | Value Description                                                                                    |
| --------------------------- | ---------------------------------------------------------------------------------------------------- |
| Authorization               | A secret token that is generated. It will be used to check the request coming from Salla             |
| Accept-Language             | This sets to which languages the client is able to understand, and which locale variant is preferred |
| X-Custom-Header Key & Value | Where you can write Custom header keys & values                                                      |  | -->
<br>

### Verify Webhooks Using Signature

Once merchants install the app in their stores, Salla uses the Siganture secret startegy (or the default one on app settings) to automatically assign webhook events.

A value for Secret must be given when establishing the webhook in order to allow webhook verification. The request body's 64 character SHA256 hash, which you may find via your partner's dashboard, will then be appended to the X-salla-signature header (e.g. x-salla-signature: `ac3ea83628cccf2e98afc34223e4eeb5b41800b77737938aeed4e109f0a0xxxx`).

You can also create your own SHA256 hash of the request body using the Secret value to check the signature. Then, using a timing-safe equality function, compare the header value to your own calculated value. Here is an example of how you might accomplish this using Node.js.

```js
const express = require("express");
const crypto = require("crypto");

const app = express();

// Base Endpoint URL: https://api.salla.dev/admin/v2
app.post('/webhooks/subscribe', (req, res) => {
  const requestHMAC = req.header("x-salla-signature");
  const secret = process.env.WEBHOOK_SECRET;
  const computedHMAC = crypto.createHmac('sha256', secret).update(JSON.stringify(req.body)).digest('hex');
  const signatureMatches = requestHMAC === computedHMAC;
  
    if (!signatureMatches) {
      res.sendStatus(401);
  }

  // do stuff

  res.sendStatus(200);
```
Another demonstration can be done using the PHP language to verify a webhook header when receiving a payload. Once the webhook is received, your server can verify it from Salla in the following way:

```php
<?php

$secret = getenv('WEBHOOK_SECRET');
$requestHMAC = $_SERVER['HTTP_X_SALLA_SIGNATURE'];
$requestBody = file_get_contents('php://input');
$computedHMAC = hash_hmac('sha256', $requestBody, $secret);

if ($requestHMAC === $computedHMAC) {
  // do stuff
}

http_response_code($requestHMAC === $computedHMAC ? 200 : 401);
```
  </Tab>
  <Tab title="🔑 Using Token">


As of token, [Salla](https://salla.partners) will reserve an auto-generated, reproducable token that you can use to confirm received payloads. Two headers will be appended to your webhook response; the security startegy adapted, as in `X-Salla-Security-Strategy` which is in this context `Token`, and the token value itself, as in `Authorization`.

| Security Startegy | Header                    | Token Suffix |
| ----------------- | ------------------------- | ------------ |
| Token             | X-Salla-Security-Strategy | Authorizaion |

<!-- focus: top
bg: "#5fd5c5"
-->
![token](https://cdn.salla.network/docs/MerchantAPI/Intro-Webhooks-06.png 'Token Representation on Salla Partners')

### Register Endpoint

Following is the expected request payload for the `Token` security strategy:

<DataSchema id="1383997" />

<!-- where in details:

| Key Name                    | Value Description                                                                                    |
| --------------------------- | ---------------------------------------------------------------------------------------------------- |
| Authorization               | A secret token that is generated. It will be used to check the request coming from Salla             |
| Accept-Language             | This sets to which languages the client is able to understand, and which locale variant is preferred |
| X-Custom-Header Key & Value | Where you can write Custom header keys & values                                                      | --> 
<br>


### Verify Webhooks Using Token

Once Merchants install the app in their stores, Salla assigns webhook events using the Token secret startegy. By adding a token to each event's x-salla-signature header, Salla signs the webhook events. This enables you to confirm that Salla supplied the events, and not someone else.

A value for Secret must be provided when establishing the webhook in order to allow webhook verification. The 32 character SHA256 hash of the request body, which you may acquire via your partner's dashboard, will then be appended to the X-salla-signature header (e.g. x-salla-signature: `9b8f5e05c7d107d49bd443bf2428xxxx`).

Use the Secret value to generate your own SHA256 hash of the request body to validate the token. Then, employ a timing-safe equality function to compare the value of the header with the value you computed yourself. Here is an example of how you might accomplish this using Node.js.

```js
const express = require("express");
const crypto = require("crypto");

const app = express();

// Base Endpoint URL: https://api.salla.dev/admin/v2
app.post('/webhooks/subscribe', (req, res) => {
  const requestHMAC = req.header("x-salla-signature");
  const secret = process.env.WEBHOOK_SECRET;
  const computedHMAC = crypto.createHmac('sha256', secret).update(JSON.stringify(req.body)).digest('hex');
  const signatureMatches = requestHMAC === computedHMAC;
  
    if (!signatureMatches) {
      res.sendStatus(401);
  }

  // do stuff

  res.sendStatus(200);
```
Another demonstration can be done using the PHP language to verify a webhook header when receiving a payload. Once the webhook is received, your server can verify it from Salla in the following way:

```php
<?php

$secret = getenv('WEBHOOK_SECRET');
$requestHMAC = $_SERVER['HTTP_X_SALLA_SIGNATURE'];
$requestBody = file_get_contents('php://input');
$computedHMAC = hash_hmac('sha256', $requestBody, $secret);

if ($requestHMAC === $computedHMAC) {
  // do stuff
}

http_response_code($requestHMAC === $computedHMAC ? 200 : 401);
```

<!-- .NET


```C#
TBD
``` -->
<!-- 
Salla automatically assigns webhook events using the Token secret startegy, once merchants install the app in their store. In other words, Salla will spontaneously deploy your webhooks based on the events you select on the portal. -->

  </Tab>
</Tabs>



## Timeout
The timeout indicates the amount of time the client must establish the connection. Salla will wait for the HTTP response and the initiation of the connection for around 30 seconds.


:::caution
If Salla did not get a successful response from the webhook endpoint, it would trigger the webhook event three times during the event. The interval between each trial will be around five minutes. In the case of receiving a successful response, no further requests will be sent.
:::


## List of Salla Store Events

<hr>



### Order

| Name                                            | Description                                                                 |
| ----------------------------------------------- | --------------------------------------------------------------------------- |
| [`order.created`](https://docs.salla.dev/doc-433804)                   | This is triggered when an order has been created.                           |
| [`order.updated`](https://docs.salla.dev/doc-433804)                   | This is triggered when an order has been updated.                           |
| [`order.status.updated`](https://docs.salla.dev/doc-433804)            | This is triggered when an order status has been updated.                    |
| [`order.cancelled`](https://docs.salla.dev/doc-433804)                 | This is triggered when an order has been cancelled.                         |
| [`order.refunded`](https://docs.salla.dev/doc-433804)                  | This is triggered when an order has been refunded.                          |
| [`order.deleted`](https://docs.salla.dev/doc-433804)                   | This is triggered when an order has been deleted.                           |
| [`order.products.updated`](https://docs.salla.dev/doc-433804)          | This is triggered when an order products have been updated.                 |
| [`order.payment.updated`](https://docs.salla.dev/doc-433804)           | This is triggered when an order payment has been updated.                   |
| [`order.coupon.updated`](https://docs.salla.dev/doc-433804)            | This is triggered when an order coupon has been updated.                    |
| [`order.total.price.updated`](https://docs.salla.dev/doc-433804)       | This is triggered when an order total price has been updated.               |
| [`order.shipment.creating`](https://docs.salla.dev/doc-433804)         | This is triggered when an order shipment is being created.                  |
| [`order.shipment.created`](https://docs.salla.dev/doc-433804)          | This is triggered when an order shipment return has been created.           |
| [`order.shipment.cancelled`](https://docs.salla.dev/doc-433804)        | This is triggered when an order shipment return has been cancelled.         |
| [`order.shipment.return.creating`](https://docs.salla.dev/doc-433804)  | This is triggered when an order shipment return is being created.           |
| [`order.shipment.return.created`](https://docs.salla.dev/doc-433804)   | This is triggered when an order shipment return has been created.           |
| [`order.shipment.return.cancelled`](https://docs.salla.dev/doc-433804) | This is triggered when an order shipment return has been cancelled.         |
| [`order.shipping.address.updated`](https://docs.salla.dev/doc-433804)  | This is triggered when an order shipment shipping address has been updated. |

### Product

| Name                                 | Description                                                        |
| ------------------------------------ | ------------------------------------------------------------------ |
| [`product.created`](https://docs.salla.dev/doc-433805)      | This event is triggered when a product has been created.           |
| [~~`product.updated`~~](https://docs.salla.dev/doc-433805#product-webhook-events-model)      | ~~This event is triggered when a product has been updated.~~           |
| [`product.deleted`](https://docs.salla.dev/doc-433805)      | This event is triggered when a product has been deleted.           |
| [~~`product.available`~~](https://docs.salla.dev/doc-433805)    | ~~This event is triggered when a product's stock has been available.~~ |
| [`product.quantity.low`](https://docs.salla.dev/doc-433805#product-webhook-events-model) | This event is triggered when a product's stock is of low quantity. |
| [`product.price.updated`](https://docs.salla.dev/433805m0#product-price-updated-webhook-events-model) | This event is triggered when a product price has been updated. |
| [`product.status.updated`](https://docs.salla.dev/433805m0#product-status-updated-webhook-events-model) | This event is triggered when a product status has been changed. |
| [`product.image.updated`](https://docs.salla.dev/433805m0#product-image-updated-webhook-event-model) | This event is triggered when a product image has been updated. |
| [`product.category.updated`](https://docs.salla.dev/433805m0#product-category-updated-webhook-events-model) | This event is triggered when a product category has been updated. |
| [`product.brand.updated`](https://docs.salla.dev/433805m0#product-brand-updated-webhook-events-model) | This event is triggered when a product brand has been updated. |
| [`product.tags.updated`](https://docs.salla.dev/433805m0#product-tags-updated-webhook-events-model) | This event is triggered when a product tags have been updated. |


### Shipping Companies

| Name                                     | Description                                                                            |
| ---------------------------------------- | -------------------------------------------------------------------------------------- |
| [`shipping.zone.created`](https://docs.salla.dev/doc-433806)    | This is triggered when a shipping zone has been created for a custom shipping company. |
| [`shipping.zone.updated`](https://docs.salla.dev/doc-433806)    | This is triggered when a shipping zone has been updated for a custom shipping company. |
| [`shipping.company.created`](https://docs.salla.dev/doc-433806) | This is triggered when a custom shipping company has been created.                     |
| [`shipping.company.updated`](https://docs.salla.dev/doc-433806) | This is triggered when a custom shipping company has been updated.                     |
| [`shipping.company.deleted`](https://docs.salla.dev/doc-433806) | This is triggered when a custom shipping company has been deleted.                     |

### Shipments

| Name                               | Description                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------- |
| [`shipment.creating`](https://docs.salla.dev/doc-433807)  | This is triggered when a shipment is assigned to a shipping company.                   |
| [`shipment.created`](https://docs.salla.dev/doc-433807)   | This is triggered when shipment is updated by the shipping company for the first time. |
| [`shipment.cancelled`](https://docs.salla.dev/doc-433807) | This is triggered when a shipment is cancelled.                                        |
| [`shipment.updated`](https://docs.salla.dev/doc-433807)   | This is triggered when a shipment is updated after creation.                           |

### Customer

| Name                                 | Description                                                                     |
| ------------------------------------ | ------------------------------------------------------------------------------- |
| [`customer.created`](https://docs.salla.dev/doc-433808)     | This event is triggered when a customer has been created.                       |
| [`customer.updated`](https://docs.salla.dev/doc-433808)     | This event is triggered when a customer has been updated.                       |
| [`customer.login`](https://docs.salla.dev/doc-433808)       | This event is triggered when a customer has logged in to their account.         |
| [`customer.otp.request`](https://docs.salla.dev/doc-433808) | This event is triggered when a customer's One-Time Password has been requested. |

### Category

| Name                             | Description                                               |
| -------------------------------- | --------------------------------------------------------- |
| [`category.created`](https://docs.salla.dev/doc-433809) | This event is triggered when a category has been created. |
| [`category.updated`](https://docs.salla.dev/doc-433809) | This event is triggered when a category has been updated. |

### Brand

| Name                          | Description                                            |
| ----------------------------- | ------------------------------------------------------ |
| [`brand.created`](https://docs.salla.dev/doc-433810) | This event is triggered when a brand has been created. |
| [`brand.updated`](https://docs.salla.dev/doc-433810) | This event is triggered when a brand has been updated. |
| [`brand.deleted`](https://docs.salla.dev/doc-433810) | This event is triggered when a brand has been deleted. |

### Store

| Name                                    | Description                                                                        |
| --------------------------------------- | ---------------------------------------------------------------------------------- |
| [`store.branch.created`](https://docs.salla.dev/doc-433811)    | This event is triggered when a store branch has been created.                      |
| [`store.branch.updated`](https://docs.salla.dev/doc-433811)    | This event is triggered when a store branch has been updated.                      |
| [`store.branch.setDefault`](https://docs.salla.dev/doc-433811) | This event is triggered when a store branch has been set to be the default branch. |
| [`store.branch.activated`](https://docs.salla.dev/doc-433811)  | This event is triggered when a store branch has been activated.                    |
| [`store.branch.deleted`](https://docs.salla.dev/doc-433811)    | This event is triggered when a store branch has been deleted.                      |
| [`storetax.created`](https://docs.salla.dev/doc-433811)        | This event is triggered when a store tax has been created.                         |

### Cart

| Name                           | Description                                                      |
| ------------------------------ | ---------------------------------------------------------------- |
| [`abandoned.cart`](https://docs.salla.dev/doc-433812) | This event is triggered when an abandoned cart has been created. |
| [`coupon.applied`](https://docs.salla.dev/doc-433812) | This event is triggered when a coupon has been applied.          |

### Invoice

| Name                            | Description                                                                        |
| ------------------------------- | ---------------------------------------------------------------------------------- |
| [`invoice.created`](https://docs.salla.dev/doc-433813) | This event is triggered when the order status is either `completed` or `restored`. |

### Special Offer

| Name                                 | Description                                                    |
| ------------------------------------ | -------------------------------------------------------------- |
| [`specialoffer.created`](https://docs.salla.dev/doc-433814) | This event is triggered when a special offer has been created. |
| [`specialoffer.updated`](https://docs.salla.dev/doc-433814) | This event is triggered when a special offer has been updated. |

### Miscellaneous

| Name                         | Description                                                     |
| ---------------------------- | --------------------------------------------------------------- |
| [`review.added`](https://docs.salla.dev/doc-433815) | This event is triggered when a product's review has been added. |

## Troubleshooting

This section will go through why webhooks fail and what are the different scenarios you can do to troubleshoot such issues.
<hr>

## Why Webhook Fails
Abnormally, your webhook might not return any results after receiving a payload, and therefore Salla considers that as a failure request/response.

There are two possible explanations for why you are not receiving webhooks for your transactions:

A - Because the webhook URL is not specified or the transaction is not in a final state, Salla is not delivering data to your hook URL (success or failed), or

B - The requests are not being accepted by your webhook server.
The initial step in troubleshooting, regardless of the issue, would be to test for the situations.

## Set Up Troubleshooting Environment

To troubleshoot for Salla webhooks, we will construct a workable URL from https://webhook.site/. This will act as our server, listening for Salla webhooks.

When an event occurs, the webhook data should be shown on the URL. This confirms that webhooks are being delivered to the developer's server.

Please follow the 4 parts instructions below to carry out this test:

### Part 1 | Set Up the Webhook Settings in Partners Portal

- Start with logging in to your [Salla Partners](https://portal.salla.partners/) account.
- Then, go to the “My Apps” menu item on the left side of the page

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-01.png)
</Frame>

- You will be redirected to the Apps. Choose the App you want to test the webhook with.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-02.png)
</Frame>

- This will redirect you to the App details page.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-03.png)
</Frame>

- Scroll down to the App Scope section and make sure to tick the "Read and Write" option for Webhooks scope.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-04.png)
</Frame>

- Then click on the “Update Scope” button.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-05.png)
</Frame>

- After that, go to [webhook.site](https://webhook.site/#!/view/3fc7c2a7-2846-4d4c-9066-a75b56a9b5b2) and copy the auto-generated Webhook URL

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-06.png)
</Frame>

- Back in the Partners Portal, scroll down to the "≥Webhooks/Notification" section and add the Webhook URL. Make sure to click on the outer side of the input box to save the changes.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-07.png)
</Frame>

- Next, in the same section, click on the “Add Events” button in the [Store Events](https://docs.salla.dev/907544f0) subsection.


<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-08.png)
</Frame>

- On the “Product” tab, select the events you want to test, in this example we will select the “Product Updated" event and click the “save” button.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-09.png)
</Frame>

### Part 2 | Install the App in the demo store
- On the App details page, scroll down to the App testing section and click on the “Install App”

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-10.png)
</Frame>

- You will be redirected to the store dashboard page where you can authorize App accessibility.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-11.png)
</Frame>

:::info[Note]
If the app is already installed on the demo store, you can reinstall it by first uninstalling it. To do this, navigate to the "Webhooks/Notifications" section and go to Dashboard > Menu Bar “More” > Installed Apps. 

<Frame caption="">
![](https://i.ibb.co/gbdyz2nq/Clean-Shot-2025-02-13-at-23-59-54-2x.png)
</Frame>

Then, choose your app from the list of installed apps and uninstall it.


<Frame caption="">
  ![](https://i.ibb.co/wr0KfPyd/Clean-Shot-2025-02-14-at-00-07-22-2x.png)
</Frame>


:::

- Go back to [webhook.site](https://webhook.site) to check if you received any events from Salla after installing the app. You should see [App Events](https://docs.salla.dev/421413m0?nav=01HNA8M216X4HFNGWM9TWSTCKQ) displayed as shown below. 

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-12.png)
</Frame>

### Part 3 | Test the Webhook using the Store dashboard
- On the App details page, scroll down to the "App Testing" section and click on the Store dashboard where the App was previously installed. 

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-13.png)
</Frame>

:::info[Note]
In case you were asked for email and password, use the auto-generated partners email given in the App testing section and the password can be reset from the Partners side menu bar “Stores” > Demo Stores. More details in the Demo Stores [article](https://salla.dev/blog/how-to-test-your-app-using-salla-demo-stores/).
:::

- After getting on the store dashboard, go to the Products page.


<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-14.png)
</Frame>
- Make some changes in one of the existing products.


<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-15.png)
</Frame>
- After making the changes, click on the “Save” button to confirm the changes.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-16.png)
</Frame>
- On the [webhook.site](https://webhook.site) you will find the [“product.updated”](https://docs.salla.dev/433805m0) event.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-17.png)
</Frame>

### Part 4| Check Webhooks events with Salla Webhooks Log
 Another way to check the event is using Salla Webhooks log in the Partners Portal. Read more about [Webhooks Log](https://salla.dev/blog/the-new-salla-apps-events-activity-log/) in this article.

<Frame caption="">
  ![](https://cdn.salla.network/docs/Intro-Webhooks-troubleshoot-18.png)
</Frame>


If the webhook data is shown as in the screenshot above, it means that Salla is delivering the webhooks correctly and that the problem is most likely with your server.


:::info[note]
You may also provide your header request parameters on the same page. Additionally, to build webhooks, you may use any API Request Builder, such as [Hoppscotch](https://hoppscotch.io/) or [Postman](https://www.postman.com/).
Check out the [Salla Webhooks doc page](https://docs.salla.dev/docs/merchent/b3A6NTU1NzcxMw-register-webhook) for additional information.
:::


After the Webhook environment is well-suited to start the troubleshooting, we will go through the following scenarios:
- [Webhook Server Troubleshooting](#webhook-server-troubleshooting) 
- [URL Endpoint Access Troubleshooting](#url-endpoint-access-troubleshooting) 
- [POST Data Troubleshooting](#post-data-troubleshooting)

#### 🔍 Webhook Server Troubleshooting 

Following that, we will see if your server is allowing requests to the webhook endpoint and whether you're receiving the provided `POST` data correctly.

Make sure to adjust the webhook URL to your own test endpoint from the Salla dashboard's [Webhooks](https://s.salla.sa/settings/component/webhooks). And that would show you results based on that URL.

:::warning
 Please verify that the activities performed in the testing endpoint do not affect your actual data.
:::

#### 🔍 URL Endpoint Access Troubleshooting 

This test will help you determine whether your webhook endpoint accepts requests from Salla. For this examination:

- Create a `POST` endpoint that, whenever a request is submitted to it, adds a timestamp to a log file.

- Create an event (for example: order) (if your webhook was setup for order creation).

- Examine the log file a few seconds after the request is done to see if it includes the written timestamp.
- Check for any TLS/SSL handshake failure
- Send and Inspect a `POST` request over to Salla
- Examine the receiving endpoint for errors

If a request log is there after the request attempt, it confirms that your server granted access to the endpoint as intended.

If it did not write to your log, there is a good probability that the request did not reach the endpoint or that your server rejected it; to resolve this, follow these steps:

- Ensure that the URL in the Salla webhook settings is correct and you can check [Life active webhooks](https://docs.salla.dev/doc-421119#list-of-salla-store-events).

- Examine any responses from the `POST` call.

#### 🔍 POST Data Troubleshooting

The following step is to ensure that you are receiving the **POST Data** appropriately.

This troubleshooting mechanism is quite similar to the one mentioned above. In this example, we'll obtain the content of the `POST` request and save it to a file.

Here's an example of a successful webhook body from the `order.created` event:

<Tabs>
  <Tab title="V2">
   
 <DataSchema id="1470798" />

  </Tab>

  <Tab title="V1">
    
<DataSchema id="1470799" />

  </Tab>

</Tabs>

---

## docs/Security-Considerations-Merchant-API-Salla-Docs

# Security Considerations

The Salla API offers a straightforward RESTful interface with lightweight JSON-formatted responses, enabling the use of various features within the Salla system. This document provides essential security information for developers integrating with the Salla API.

REST APIs utilize HTTP and support Transport Layer Security (TLS) encryption. TLS is a standard that ensures a private internet connection and verifies that the data exchanged between systems (whether between servers or between a server and a client) is encrypted and unaltered.

## OAuth

[OAuth](https://docs.salla.dev/doc-421118) is designed to allow third-party applications to access APIs without requiring users to share their passwords. Merchants are asked to authorize you, as the service provider, to access only specific portions of their account. Salla currently supports OAuth 2.0 as the primary method for authorization and authentication.

:::tip[]
Read more about OAuth in the [documentation](https://docs.salla.dev/doc-421118).
:::

## APIs

API requests must be made using HTTPS; HTTP requests are not permitted. Salla API prevents anonymous users from accessing sensitive information, ensuring that access is granted only through [Salla Partners Portal](https://portal.salla.partners) applications using OAuth.


<!-- ### **Required Headers for API**

There are two required headers for most calls:

- Content-Type: application/json
- Authorization: Bearer + {ACCESS_TOKEN}

We need those two to understand and authenticate your call. 

However, all requests (or technical communication) will be validated by Salla Team and all types of actions will be logged. -->

---

## docs/Settings

# Settings

## Docs

- [App Setting Details](https://docs.salla.dev/5401096e0.md): This endpoint allows you to fetch details of App Settings per [Salla Store](http://s.salla.sa/).
- [Update App Settings](https://docs.salla.dev/5401097e0.md): This endpoint allows you to update App Settings per [Salla Store](http://s.salla.sa/).

---

## docs/Settlements

# Settlements

## Docs

- [List Instant Settlements](https://docs.salla.dev/8548913e0.md): This endpoint lists all the instant settlements including details such as amount and status that are associated with the store.
- [Create Instant Settlement](https://docs.salla.dev/8548925e0.md): This endpoint allows you to temporarily withhold a specific amount of money for settlement from the Merchant's wallet.
- [Update Instant Settlement](https://docs.salla.dev/8549773e0.md): This endpoint allows you to update the status and the amount of a specific settlment by by passing the `id` as a path parameter.
- [Instant Settlement Details](https://docs.salla.dev/9798033e0.md): This endpoint allows you to fetch the details for a specific settlement by passing the `id` as a path parameter.

---

## docs/Setup-Shipping-App-AWB-Salla-Merchants-APIs-Salla-Docs

# Setup Shipping App 

After successfully creating a [Shipping App](?nav=01HNA8MH78MVX1S0DRXDHE3A1Kdoc-422995) it is now ready to have a few tweaks to become a fully functioning AWB Shipping App using App Functions.

## What you'll learn:
In this article we will walk you through the steps of setting up the App for shipping service providers.

- [Setup the Shipping App](#setup-the-shipping-apps)

## Setup the Shipping App

The Shipping App settings done through the *App details* page. To get there, click on *My Apps* menu item on the left side of [Partners Portal](https://salla.partners/)  main page.  
<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-03.png?)

The *App Details* page is where the developer can manage the [App's Scopes](#app-scope), [Webhooks/Notifications](#webhooksnotifications) and [Shipping Setting](#shipping-settings).

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-04.png?)



:::caution[Alert]
We highly recommend selecting the Easy mode option when setting up the authorization mode for your shipping app, as it is not only easier to use, but also offers more features compared to the custom mode. By choosing the Easy mode, you can ensure optimal functionality and take advantage of the additional upcoming features and benefits.
:::


### App Scope
App scope section allows the developer to determine the information needed by the App from the store in order to function correctly, by identifying and restricting accessibility to certain features and services. 

:::note[]
The developer can simply enable or disable accessibility by clicking on the option to *Read Only* or *Read and Write*.
:::
<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-05.png?v)


The scopes needed for a functional AWB App are:
- Shippings: Read and Write
- Webhooks: Read and Write


After assigning the scopes, click on *Update the scopes* to save the changes. Continue reading to set up [Webhooks](https://docs.salla.dev/doc-421119) of the App.

### Webhooks/Notifications
[Webhooks](https://docs.salla.dev/doc-421119) are used to exchange messages between Apps and the Salla store whereby they are also used to notify developers about store events. 

Specify the webhook URL where Salla will send all app events, such as authorization details with the access token, and store events, such as order updates.

![SCR-20251118-jexs.png](https://api.apidog.com/api/v1/projects/451700/resources/366101/image-preview)

By reaching here, the developer have finished setting up the Store Events in the Webhook Notifications section. Next is Shipping Settings.


### Shipping Settings
Shipping settings are what appear to the store customers when they finish placing their orders in the store and proceed the check out, a summary of the order will be displayed along with shipping details. The shipping details will be explained here.

<Steps>
  <Step title="First Step">
On the *App details* page, scroll down to the *Shipping Settings* section and click on `View Rates` to display the rates.

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-08.png?v)
  </Step>
  <Step title="Second Step">
Then click on *Add a New Rate* to start adding rates of the Shipping by completing the form.

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-09.png?v)

      Form details are explained in the following table.

Item |Description
-----|-----------
Country| The country that the Shipping App offers its services in.
City|The city in the country the Shipping App offers its services.
Excluded Cities(Optional)| The cities excluded from the rate being set.
Rate Type| The developer can choose either Fixed or Rate. 
Cost| Cost of the shipping for fixed Rate Type.
Delivery Duration| The time required to deliver the parcel.
Cash on Delivery| The developer can enable this option to offer COD payment type.
      
      



#### Examples
Next we will be listing in detail two different examples where developers can gain real-world scenario experience while building and developing Shipping Rates for their Shipping Apps.

      
<Tabs>
  <Tab title="Example 1">
Following is an example of a completed form for a rate offered to Saudi Arabia Country, in two Cities; Riyadh and Jeddah, *Fixed* Rate Type, Cost of 50 SAR, Delivery Duration of 7 days, and option of Cash on Delivery enabled with zero fees.

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-10.png?v)

  </Tab>
  <Tab title="Example 2">
Another example of a completed Rate form with Rate Type of *Rate*. 
The shipping rate is for the Country Saudi Arabia with Dammam, and Al Khobar Cities, Rate type of Rate where the initial cost is 10 SAR for the first 1 kg and an additional cost of 5 SAR for each 1 kg. At this rate, Cash on Delivery is not enabled and the delivery duration is 4 days.

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-11.png?v)


  </Tab>
</Tabs>

      

The developer also has the option to add a rate for a country and exclude a few cities, like shown below.
This option will exclude the city Almuzaylif from the rate being set.

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-12.png?v)

Click on Add after filling in the Rate details to save the rates. A notification will be displayed to confirm saving change and the newly added rate will be displayed.

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-13.png?v)


Moreover, you can add shipping policy options straight from the Partners Portal by selecting from the drop down menu list

![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-14.png?v)

  </Step>
  <Step title="Third Step">

Finally, customize the shipment features with what accomplies with your shipping service

![image](https://cdn.salla.network/docs/shipping_orders_api/shipping-15.png?v)
  </Step>
</Steps>

---

## docs/Shipments

# Shipments

## Docs

- [Create Shipment](https://docs.salla.dev/5578808e0.md): This endpoint allows you to create a shipment related to your store directly from this endpoint.
- [List Shipments](https://docs.salla.dev/5578809e0.md): You can list all shipments related to your store directly from this endpoint. Also, it allows you to filter them using by shipping company slug.
- [Update Shipment Details](https://docs.salla.dev/5578810e0.md): This endpoint allows you to update specific Shipment Details by providing the ID of the shipment you want to update its details.
- [Shipment Details](https://docs.salla.dev/5578811e0.md): This endpoint allows you to return the complete details for a specific shipment by providing the ID of the shipment you want to get its details in the shipment path parameter.
- [Cancel Shipments](https://docs.salla.dev/5578812e0.md): You can cancel specific Shipment by providing the ID of the shipment you want to cancel.
- [Return Shipments](https://docs.salla.dev/5578813e0.md): You can return specific Shipment by providing the ID of the shipment you want to return.
- [Shipment Tracking](https://docs.salla.dev/5578814e0.md): This endpoint allows you to fetch tracking details for a specific shipment by providing the ID of the shipment the path parameter.

---

## docs/Shipping-Companies

# Shipping Companies

## Docs

- [List Shipping Companies](https://docs.salla.dev/5578815e0.md): This endpoint allows you to list all active shipping companies associated with the store. 
- [Shipping Company Details](https://docs.salla.dev/5578816e0.md): This endpoint allows you to fetch details of shipping companies for your store.

---

## docs/Shipping-Management

# Shipping Management

## Docs

- [Create App](https://docs.salla.dev/422995m0.md): Salla [Partners Portal](https://salla.partners/login) provides the tools to [create different types of Apps](https://salla.dev/blog/create-your-first-app-on-salla-developer-portal/) including Shipping Apps. These Apps streamline shipping for Salla stores by offering a platform to manage orders shipment. As well as integrate with Salla stores and couriers, providing multi-carrier support. They have become essential for online shopping, providing fast, affordable, and reliable shipping services.
- [App Cycle](https://docs.salla.dev/422994m0.md): There are several steps that occur before processing a shipping order, and these steps are crucial to streamlining the shipping process, from creating a shipment based on the order from the Merchant to handling returned and cancelled shipments. 
- [Setup App](https://docs.salla.dev/422996m0.md): After successfully creating a [Shipping App](?nav=01HNA8MH78MVX1S0DRXDHE3A1Kdoc-422995) it is now ready to have a few tweaks to become a fully functioning Shipping App and is able to be published in the [Salla Apps Store](https://apps.salla.sa).
- [Test App](https://docs.salla.dev/422998m0.md): Testing and shipping are the final steps towards having your App on [Salla App Store](https://apps.salla.sa/). These steps are critical and are simplified in this article.

---

## docs/Shipping-Routes

# Shipping Routes

## Docs

- [  Routes List](https://docs.salla.dev/19665286e0.md): This endpoint allows you to fetch all shipping routes configured for the store.
- [Route Details](https://docs.salla.dev/19665287e0.md): This endpoint allows you to fetch detailed information about a specific shipping route, including
- [Create Route](https://docs.salla.dev/19665288e0.md): This endpoint allows you to create a new shipping route with configurable behavior, type, and conditions.
- [Update Route](https://docs.salla.dev/19665289e0.md): This endpoint allows you to update the details of an existing shipping route by passing its `id` as a path parameter.
- [Default Route](https://docs.salla.dev/19665290e0.md): This endpoint allows you to view or update the default shipping route.
- [Delete Route](https://docs.salla.dev/19665291e0.md): This endpoint allows you to update an existing shipping route by passing its `id` as a path paraneter.

---

## docs/Shipping-and-Fulfilment-API-Change-Log

# Change Log

We are constantly working to improve our Shipping and Orders Fulfilment API. This page will keep you up-to-date on the latest changes, including new endpoints, bug fixes, and performance improvements. All changes, updates are listed in reverse chronological order, with the most recent changes at the top.

:::highlight purple ✅
### Postman Collection
If you are using an API Request Builder, such as [Postman](https://www.postman.com/salla-app), we are regularly updating the [Postman Collection](https://www.postman.com/salla-app) whenever there is an update mentioned in [ChangeLog page](https://docs.salla.dev/422992m0?nav=01HNA8MH78MVX1S0DRXDHE3A1K). 

🧨 **Recent Release is [V2.0.6](https://www.postman.com/salla-app/salla-e-commerce-platform/collection/ba1ul6d/shipments-apis-v2-0-6)**

[![Run in Postman](https://run.pstmn.io/button.svg)](https://www.postman.com/salla-app/)
:::

:::info[Information]
The format of this page is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
:::

## [2.0.11] - 13-10-2025

### Changed

- Added the `shipping_route` in the following endpoints and webhook responses:
    - [Create Shipment](https://docs.salla.dev/5578808e0)
    - [List Shipments](https://docs.salla.dev/5578809e0)
    - [Shipment Details](https://docs.salla.dev/5578811e0)
    - [Update Shipment Details](https://docs.salla.dev/5578810e0)
    - [Cancel Shipment](https://docs.salla.dev/5578812e0)
    - [Return Shipment](https://docs.salla.dev/5578813e0)
    - [Shipments Webhook Events Model](https://docs.salla.dev/433807m0#shipments-webhook-events-model) in the following store events:
        - `shipment.creating`
        - `shipment.created`
        - `shipment.updated`
        - `shipment.cancelled`


## [2.0.10] - 29-07-2025
### Added

- Six new endpoints, [Shipping Routes](https://docs.salla.dev/4399607f0), used to manage the store’s shipping routes.

## [2.0.9] - 17-06-2025
### Changed

- The `status` variable in [List Shipments](https://docs.salla.dev/5578809e0) and [Update Shipment Details](https://docs.salla.dev/5578810e0) endpoints now supports the following new shipment statuses:
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

## [2.0.8] - 05-02-2025

### Changed

- The `billing_account` variable has been added to the following endpoints' responses:
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


## [2.0.7] - 09-01-2025

### Changed

- The variable, `external_company_name`, has been added to the following endpoints' responses and body requests:
    - [Create Shipment](https://docs.salla.dev/5578808e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [List Shipments](https://docs.salla.dev/5578809e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Shipment Details](https://docs.salla.dev/5578811e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Update Shipment Details](https://docs.salla.dev/5578810e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Cancel Shipment](https://docs.salla.dev/5578812e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Return Shipment](https://docs.salla.dev/5578813e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)

## [2.0.6] - 30-12-2024

### Changed

- 🛑 **Starting from January 20th, 2025**, the `status` variable is **required** in the [Update Shipment Details](https://docs.salla.dev/5578810e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K) endpoint's body request. **Recommended** adapting to this change so as not to face any break change in your production environment. 

## [2.0.5] - 29-12-2024

### Changed

- The variable, `options` is added within the `package` object in the following endpoints:
    - [List Shipments](https://docs.salla.dev/5578809e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Shipment Details](https://docs.salla.dev/5578811e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Update Shipment Details](https://docs.salla.dev/5578810e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Create Shipment](https://docs.salla.dev/5578808e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Cancel Shipment](https://docs.salla.dev/5578812e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Return Shipment](https://docs.salla.dev/5578813e0?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
    - [Shipments Webhook Events Model](https://docs.salla.dev/433807m0#shipments-webhook-events-model)

## [2.0.4] - 28-08-2024
### Changed

- The [List Shipments](api-5578809/?nav=01HNA8MH78MVX1S0DRXDHE3A1K) endpoint supports the `per_page` query parameter

## [2.0.3] - 31-03-2024
### Changed

- The [Shipments Webhook Event Model](https://docs.salla.dev/doc-433807/?nav=1#shipments-webhook-events-model) includes the following variables:
    - `ship_to` object includes:
        - `country_id`
        - `city_id`
    - `ship_from` object includes:
        - `country_id`
        - `country_code`
        - `city_id` 
    - `meta` object includes the `diemnsions` object


## [2.0.2] - 16-03-2023

### Changed

- The variables item_id and external_id have been added to the following endpoints' / webhooks' response:
  - [Create Shipment](api-5578808/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [List Shipments](api-5578809/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Update Shipment Details](api-5578810/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Shipment Details](api-5578811/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Shipments Webhook Event Model](https://docs.salla.dev/doc-433807/?nav=1#shipments-webhook-events-model)

## [2.0.1] - 12-07-2023

### Changed

- A new value `delivering` has been added to the variable `status` of the following endpoints:
  - [Create Shipment](api-5435733?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [List Shipments](api-5435734?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Update Shipment Details](api-5435735?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Shipment Details](api-5435736?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Cancel Shipment](api-5435737?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Return Shipment](api-5435738?nav=01HNA8MH78MVX1S0DRXDHE3A1K)

## [1.0.1] - 04-05-2023

### Changed

- The variable `order_reference_id` has been added to the following endpoints:
  - [Create Shipment](api-5578808/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [List Shipments](api-5578809/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Update Shipment Details](api-5578810/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Shipment Details](api-5578811/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
  - [Shipment Tracking](api-5435739?nav=01HNA8MH78MVX1S0DRXDHE3A1K)

---

## docs/Subscriptions

# Subscriptions

## Docs

- [App Subscription Details](https://docs.salla.dev/5401098e0.md): This endpoint allows you to fetch details of App Subscriptions per [Salla Store](http://s.salla.sa/).
- [Update Subscription Balance](https://docs.salla.dev/5401099e0.md): This endpoint allows you to update the balance of an Application's subscription.

---

## docs/Support-Merchant-API-Salla-Docs

# Support

## Developers Community

Our team is available during working hours to assist you with any questions regarding the Salla Partners Portal, app and theme development, or documentation inquiries. You can connect with us by joining:


:::highlight gray 💻 
[Global Developer Community on Telegram](https://t.me/salladev).
:::

## Support Email

For issues affecting your production environment caused by Salla Merchant APIs, you can also reach out via email at: 


:::highlight gray ✉ 

[support@salla.dev](mailto:support@salla.dev)

:::

## Service Status

Stay updated on Salla's system performance with real-time and historical data. You can also subscribe for email notifications on any status changes.

:::highlight gray 🔗 
[Service Status Page](https://status.salla.sa/)
:::

---

## docs/Supported-Events-App-Functions-Documentation-Salla-Docs

# Supported Events

App Functions support a wide range of events triggered by merchant and customer activities. This page provides a comprehensive list of all available events you can listen to in your App Functions.

---

## Event Types

There are two main categories of events:

### Merchant Events

Events triggered by merchant actions in the store dashboard, such as creating products, updating orders, or managing inventory. These can be either:

- ⚡ **Synchronous Actions** — Execute immediately, **block the user**, and must respond in milliseconds (e.g., `shipment.creating`)
- 🔄 **Asynchronous Events** — Process in the background after the operation completes (e.g., `order.created`)

### Customer Events

Events triggered by customer interactions on the storefront, such as viewing products, adding items to cart, or completing checkout. These are always processed asynchronously.

---

## Merchant Actions & Events

### 📦 Orders

Order-related events are triggered when orders are created, updated, or modified in any way.

| Event Name | Type | Description |
|------------|------|-------------|
| **Order Created** | Async | Triggered when a new order is created |
| **Order Completed** | Async | Triggered when an order is marked as completed |
| **Order Updated** | Async | Triggered when any order field is updated |
| **Order Status Updated** | Async | Triggered when the order status changes |
| **Order Cancelled** | Async | Triggered when an order is cancelled |
| **Order Refunded** | Async | Triggered when an order is refunded |
| **Order Deleted** | Async | Triggered when an order is deleted |
| **Order Products Updated** | Async | Triggered when order items are modified |
| **Order Payment Updated** | Async | Triggered when payment information is updated |
| **Order Coupon Updated** | Async | Triggered when a coupon is applied or removed |
| **Order Total Price Updated** | Async | Triggered when the order total changes |

**Common Use Cases**:

- 📧 Send order confirmations
- 🔄 Update external inventory systems
- ⚙️ Trigger fulfillment workflows
- 💰 Sync with accounting software
- 📨 Send custom notifications

**[View Order Event Schemas →](https://docs.salla.dev/1726836m0.md)**

---

### 🛍️ Products

Product events are triggered when products are created, updated, or their inventory changes.

| Event Name | Type | Description |
|------------|------|-------------|
| **Product Added** | Async | Triggered when a product is added to the store |
| **Product Created** | Async | Triggered when a new product is created |
| **Product Updated** | Async | Triggered when product details are modified |
| **Product Deleted** | Async | Triggered when a product is deleted |
| **Product Available** | Async | Triggered when a product becomes available |
| **Product Quantity Low** | Async | Triggered when product inventory is low |

**Common Use Cases**:

- 🔄 Sync products with external catalogs
- 💰 Update pricing across platforms
- 📊 Monitor inventory levels
- 🔔 Trigger restock notifications
- 🔍 Update search indexes

**[View Product Event Schemas →](https://docs.salla.dev/1726830m0.md)**

---

### 🚚 Shipments

Shipment events are triggered during the shipping process. **Note**: `Shipment Creating` is synchronous and blocks the user - it must respond in milliseconds.

| Event Name | Type | Description |
|------------|------|-------------|
| **Shipment Creating** | **Sync** | ⚠️ **Blocks user** - Triggered before shipment creation (must respond in < 500ms) |
| **Shipment Created** | Async | Triggered after a shipment is created |
| **Shipment Cancelled** | Async | Triggered when a shipment is cancelled |
| **Shipment Updated** | Async | Triggered when shipment details are updated |

**Common Use Cases**:

- ⚡ Calculate custom shipping rates (sync - must be fast!)
- ✔️ Validate shipping addresses (sync - must be fast!)
- 🏷️ Create labels with shipping carriers (async)
- 📧 Send tracking notifications (async)
- 🔄 Update order status (async)

<Warning>
**Performance Warning for Sync Event**:

- ⚠️ `Shipment Creating` blocks the merchant - keep logic simple and fast
- ⏱️ Target response time: < 500ms
- ❌ Avoid slow external API calls
- 💾 Use caching when possible
</Warning>

**[View Shipment Event Schemas →](https://docs.salla.dev/1726835m0.md)**

---

### 🌍 Shipping Zones

Shipping zone events are triggered when shipping zones are configured.

| Event Name | Type | Description |
|------------|------|-------------|
| **Shipping Zone Created** | Async | Triggered when a new shipping zone is created |
| **Shipping Zone Updated** | Async | Triggered when a shipping zone is modified |

**Common Use Cases**:

- 🔄 Sync shipping configurations
- 🔌 Update external shipping systems
- ✔️ Validate zone settings

**[View Shipping Zone Event Schemas →](https://docs.salla.dev/1726826m0.md)**

---

### 🚛 Shipping Companies

Shipping company events are triggered when shipping companies are managed.

| Event Name | Type | Description |
|------------|------|-------------|
| **Shipping Company Created** | Async | Triggered when a shipping company is added |
| **Shipping Company Updated** | Async | Triggered when company details are updated |
| **Shipping Company Deleted** | Async | Triggered when a shipping company is removed |

**Common Use Cases**:

- 🔌 Integrate with shipping carriers
- 🔄 Update shipping options
- ⚙️ Sync carrier configurations

**[View Shipping Company Event Schemas →](https://docs.salla.dev/1726832m0.md)**

---

### 👤 Customers

Customer events are triggered when customer accounts are created or modified.

| Event Name | Type | Description |
|------------|------|-------------|
| **Customer Created** | Async | Triggered when a new customer account is created |
| **Customer Updated** | Async | Triggered when customer details are updated |
| **Customer Login** | Async | Triggered when a customer logs in |
| **Customer OTP Request** | Async | Triggered when a customer requests an OTP |

**Common Use Cases**:

- 🔄 Sync customer data with CRM
- 📧 Send welcome emails
- 📊 Track login activity
- 🔐 Implement custom authentication

**[View Customer Event Schemas →](https://docs.salla.dev/1726829m0.md)**

---

### 📂 Categories

Category events are triggered when product categories are managed.

| Event Name | Type | Description |
|------------|------|-------------|
| **Category Created** | Async | Triggered when a new category is created |
| **Category Updated** | Async | Triggered when a category is modified |

**Common Use Cases**:

- 🔄 Sync category structures
- 🗂️ Update navigation menus
- 📋 Organize product catalogs

**[View Category Event Schemas →](https://docs.salla.dev/1726827m0.md)**

---

### 🏷️ Brands

Brand events are triggered when brands are created, updated, or deleted.

| Event Name | Type | Description |
|------------|------|-------------|
| **Brand Created** | Async | Triggered when a new brand is created |
| **Brand Updated** | Async | Triggered when brand details are updated |
| **Brand Deleted** | Async | Triggered when a brand is deleted |

**Common Use Cases**:

- 🔄 Sync brand information
- 📄 Update brand pages
- 🖼️ Manage brand assets

**[View Brand Event Schemas →](https://docs.salla.dev/1726834m0.md)**

---

### 🏪 Store

Store events are triggered when store branches and settings are managed.

| Event Name | Type | Description |
|------------|------|-------------|
| **Store Branch Created** | Async | Triggered when a new branch is created |
| **Store Branch Updated** | Async | Triggered when branch details are updated |
| **Store Branch Set Default** | Async | Triggered when a branch is set as default |
| **Store Branch Activated** | Async | Triggered when a branch is activated |
| **Store Branch Deleted** | Async | Triggered when a branch is deleted |
| **Store Tax Created** | Async | Triggered when a tax rule is created |

**Common Use Cases**:

- 🔄 Sync multi-location inventory
- ⚙️ Update store configurations
- 💰 Manage tax settings

**[View Store Event Schemas →](https://docs.salla.dev/1726831m0.md)**

---

### 🛒 Cart

Cart events are triggered when shopping carts are abandoned.

| Event Name | Type | Description |
|------------|------|-------------|
| **Abandoned Cart** | Async | Triggered when a cart is abandoned |

**Common Use Cases**:

- 📧 Send cart recovery emails
- 📊 Track abandonment rates
- 📢 Trigger remarketing campaigns

**[View Cart Event Schemas →](https://docs.salla.dev/1726838m0.md)**

---

### 🎟️ Coupons

Coupon events are triggered when discount codes are applied.

| Event Name | Type | Description |
|------------|------|-------------|
| **Coupon Applied** | Async | Triggered when a coupon is successfully applied |

**Common Use Cases**:

- 📊 Track coupon usage
- ✔️ Validate coupon rules
- 📈 Update marketing analytics

**[View Coupon Event Schemas →](https://docs.salla.dev/1726837m0.md)**

---

### 🧾 Invoices

Invoice events are triggered when invoices are generated.

| Event Name | Type | Description |
|------------|------|-------------|
| **Invoice Created** | Async | Triggered when an invoice is created |

**Common Use Cases**:

- 📧 Send invoice notifications
- 💰 Sync with accounting systems
- 📄 Generate custom invoices

**[View Invoice Event Schemas →](https://docs.salla.dev/1726824m0.md)**

---

### 🎁 Special Offers

Special offer events are triggered when promotional offers are managed.

| Event Name | Type | Description |
|------------|------|-------------|
| **Special Offer Created** | Async | Triggered when a special offer is created |
| **Special Offer Updated** | Async | Triggered when an offer is modified |

**Common Use Cases**:

- 🔄 Sync promotional campaigns
- 📢 Update marketing materials
- 📊 Track offer performance

**[View Special Offer Event Schemas →](https://docs.salla.dev/1726828m0.md)**

---

### ⭐ Reviews

Review events are triggered when customers submit product reviews.

| Event Name | Type | Description |
|------------|------|-------------|
| **Review Added** | Async | Triggered when a customer adds a review |

**Common Use Cases**:

- 🔍 Moderate reviews
- 📧 Send thank you messages
- ⭐ Update product ratings

**[View Review Event Schemas →](https://docs.salla.dev/1726833m0.md)**

---

## Customer E-commerce Events

Customer events are triggered by storefront interactions and are always processed asynchronously.

---

### 🛍️ Product Interactions

| Event Name | Description |
|------------|-------------|
| **Product Viewed** | Customer views a product page |
| **Product Clicked** | Customer clicks on a product |
| **Product List Viewed** | Customer views a product listing page |
| **Product List Filtered** | Customer applies filters to product list |
| **Product Shared** | Customer shares a product |
| **Product Reviewed** | Customer submits a product review |
| **Products Searched** | Customer performs a product search |

**[View Product Interaction Schemas →](https://docs.salla.dev/1726820m0.md)**

---

### 🛒 Cart & 💳 Checkout

| Event Name | Description |
|------------|-------------|
| **Product Added** | Customer adds product to cart |
| **Product Removed** | Customer removes product from cart |
| **Cart Viewed** | Customer views their cart |
| **Cart Updated** | Cart contents or totals change |
| **Checkout Started** | Customer begins checkout |
| **Checkout Step Viewed** | Customer views a checkout step |
| **Checkout Step Completed** | Customer completes a checkout step |
| **Payment Info Entered** | Customer enters payment information |
| **Order Completed** | Customer completes an order |

**[View Cart & Checkout Schemas →](https://docs.salla.dev/1726822m0.md)**
    
---

### 🎁 Promotions & Coupons

| Event Name | Description |
|------------|-------------|
| **Promotion Viewed** | Customer views a promotion |
| **Promotion Clicked** | Customer clicks on a promotion |
| **Coupon Entered** | Customer enters a coupon code |
| **Coupon Applied** | Coupon is successfully applied |
| **Coupon Denied** | Coupon application is denied |
| **Coupon Removed** | Customer removes a coupon |

**[View Promotion & Coupon Schemas →](https://docs.salla.dev/1726821m0.md)**

---

### ❤️ Wishlist

| Event Name | Description |
|------------|-------------|
| **Wishlist Product Added** | Customer adds product to wishlist |
| **Wishlist Product Removed** | Customer removes product from wishlist |
| **Wishlist Product Added to Cart** | Customer moves wishlist item to cart |

**[View Wishlist Schemas →](https://docs.salla.dev/1726823m0.md)**

---

### 👤 User Account

| Event Name | Description |
|------------|-------------|
| **Signed In** | Customer signs in |
| **Signed Up** | Customer creates an account |
| **Signed Out** | Customer signs out |
| **User Profile Updated** | Customer updates their profile |

**[View User Account Schemas →](https://docs.salla.dev/1726819m0.md)**

---

## Next Steps

- 🚀 **[Quick Start](https://docs.salla.dev/1726817m0.md)** — Create your first App Function
- 🧪 **[Testing App Functions](https://docs.salla.dev/1726816m0.md)** — Learn how to test your functions
- 📚 **[Salla APIs](https://docs.salla.dev/426392m0)** — Explore Salla API documentation

---

## docs/Testing-App-Functions-Documentation-Salla-Docs

# Testing

Testing your App Functions is crucial to ensure they work correctly before deploying to production. This guide covers everything you need to know about testing your functions effectively.

---

## Overview

Salla provides built-in testing tools directly in the Partner Portal, allowing you to:

- 🧪 Test functions with real store data
- 👁️ Preview function responses in real-time
- 🐛 Debug issues before deployment
- ✔️ Validate API integrations
- 🔍 Inspect context data structures

---

## Testing Environment

### Prerequisites

Before testing your App Functions, ensure:

- ✔️ **Demo Store Setup** — Your app is installed on a demo store
- ✔️ **App Scopes Configured** — Required permissions are set
- ✔️ **Test Data Available** — Demo store has relevant data (orders, products, etc.)
- ✔️ **External Services Ready** — Any external APIs or webhooks are accessible

### Accessing the Test Environment

1. 🔐 Log in to [Salla Partner Portal](https://portal.salla.partners)
2. 📱 Navigate to your app
3. 📋 Scroll to the **App Functions** section
4. ✔️ Select the function you want to test
5. 👁️ The test panel appears on the right side of the editor

---

## Testing Your Functions

### Step 1: Select a Demo Store

<Steps>
  <Step title="Choose Your Store">
    
Click **Select Store** in the preview panel and choose your demo store from the dropdown.


![Select Store](https://api.apidog.com/api/v1/projects/451700/resources/366882/image-preview)

<Tip>
**Multiple Stores**: If you have multiple demo stores, you can test against different configurations to ensure your function works in various scenarios.
</Tip>

  </Step>
</Steps>

### Step 2: Prepare Test Data

<Steps>
  <Step title="Get Test Data from Demo Store">
    
Navigate to your demo store dashboard to get the required test data:

- 📦 **For Order Events**: Get an Order ID
- 🛍️ **For Product Events**: Get a Product ID
- 👤 **For Customer Events**: Get a Customer ID
- 📋 **For Other Events**: Get relevant entity IDs


![Demo Store Dashboard](https://api.apidog.com/api/v1/projects/451700/resources/366883/image-preview)

  </Step>
</Steps>

### Step 3: Enter Test Parameters

<Steps>
  <Step title="Input Required Data">
    
Enter the required parameters in the preview panel. For example, if testing an Order Status Updated function, enter the Order ID.

![Enter Order ID](https://api.apidog.com/api/v1/projects/451700/resources/366884/image-preview)

<Note>
**Event-Specific Parameters**: Different events require different parameters. The preview panel will show you what's needed for each event type.
</Note>

  </Step>
</Steps>

### Step 4: Execute and Review

<Steps>
  <Step title="Run the Test">
    
Click **Save and Preview** to execute your function with the test data.
      
![Save and Preview](https://api.apidog.com/api/v1/projects/451700/resources/366885/image-preview)

The preview panel will display:

- ✔️ **Execution Status** — Success or failure
- 📦 **Response Data** — The data returned by your function
- ⏱️ **Execution Time** — How long the function took to run
- 📝 **Console Logs** — Any ```console.log()``` output from your function
- ❌ **Errors** — Any errors that occurred during execution

  </Step>
</Steps>

---

## Inspecting Context Data

Understanding the context object structure is essential for writing effective functions.

### Viewing Context Schema

To view the expected context structure for your function:

<Steps>
  <Step title="Access Context Definition">
    
Right-click on the `context` parameter in your function signature.
      
![Context Menu](https://api.apidog.com/api/v1/projects/451700/resources/366886/image-preview)

  </Step>

  <Step title="Peek Definition">
    
Choose **Peek** > **Peek Definition** from the context menu.


![Peek Definition](https://api.apidog.com/api/v1/projects/451700/resources/366887/image-preview)

  </Step>

  <Step title="Review Structure">
    
View the complete context structure including all available properties and their types.


![Context Structure](https://api.apidog.com/api/v1/projects/451700/resources/366888/image-preview)

Scroll through to see:

- 📦 Payload structure
- 📋 Event-specific data fields
- ⚙️ Settings object
- 🏪 Merchant information
- 💻 Type definitions

  </Step>
</Steps>

---

## Testing API Integrations

When your function calls Salla APIs or external services, follow these best practices:

### Testing Salla API Calls

```typescript
export default async (
  context: OrderCreatedContext
): Promise<Resp> => {
  // Test accessing Salla API with automatic authentication
  // NOTE: Authorization header is automatically injected.
  const response = await fetch("https://api.salla.dev/admin/v2/orders", {
    method: "GET",
  });

  const orders = await response.json();

  // Log for debugging (visible in preview panel)
  console.log("Fetched orders count:", orders.data?.length);

  const data = { 
    total_orders: orders.data?.length,
      first_order: orders.data?.[0],
  };
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

<Success>
**Automatic Authentication**: You can access Salla APIs with automatic token injection. No need to manually handle authentication when coding inside the Partner Portal.
</Success>

### Testing External API Calls

```typescript
export default async (
  context: OrderStatusUpdatedContext
): Promise<Resp> => {
  try {
    const { payload, settings, merchant } = context;

    // Test external webhook
    const webhookResponse = await fetch(settings.webhookUrl, {
      // URL from app settings
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Authorization: `Bearer ${settings.apiKey}`, // API key from app settings
      },
      body: JSON.stringify({
        order_id: payload.data.id,
        status: payload.data.status,
        timestamp: new Date().toISOString(),
      }),
    });

    // Log response for debugging
    console.log("Webhook status:", webhookResp.status);
    console.log("Webhook response:", await webhookResp.text());

    const data = { 
      webhook_status: webhookResp.status
    };
    /*
      * The .setData() should be called mandatorily. (Pass {} as default)
      * The .setStatus() is optionallly called. The default status is 200.
      * The .setMessage() is optional. 
      * Incase there is any error invoke Resp.error().
    */
    const response = Resp.success().setData(data)

    return response;
  } catch (error) {
    console.error('Error sending webhook:', error);
    return Resp.error()
      .setMessage(error.message || 'Unknown error')
      .setStatus(500)
      .setData({ error_type: error.name });
  }
};
```

---

## Best Practices for Testing

### 1. Test Multiple Scenarios

Test your function with different types of data:

- ✔️ **Happy Path**: Normal, expected data
- ⚠️ **Edge Cases**: Empty values, null fields, minimum/maximum values
- ❌ **Error Cases**: Invalid data, API failures, timeouts
- 🔄 **Different States**: Various order statuses, product types, etc.

### 2. Use Meaningful Logs

Add console.log statements to track execution flow:

```typescript
console.log("Function started for order:", context.payload.data.id);
console.log("Calling external API...");
console.log("API response received:", response.status);
console.log("Function completed successfully");
```

<Warning>
**Avoid Logging Sensitive Data**: Never log sensitive information like:

- ❌ API keys or tokens
- ❌ Customer personal data
- ❌ Payment information
- ❌ Passwords or credentials
  </Warning>

### 3. Return Consistent Responses

Always return a structured response object:

```typescript
// Success response
return Resp.success().setData({
    // Relevant data
});


// Error response
return Resp.error()
    .setMessage("Descriptive error message")
    .setStatus(500)
    .setData({
      // Additional error context
});
```

### 4. Handle Errors Gracefully

Use try-catch blocks and provide meaningful error messages:

```typescript
try {
  // Your logic
} catch (error) {
  console.error("Error details:", error);
  return Resp.error()
      .setMessage(error.message || 'Unknown error')
      .setStatus(500)
      .setData({ error_type: error.name });
}
```

### 5. Validate Input Data

Check that required data exists before using it:

```typescript
export default async (
  context: OrderCreatedContext
): Promise<Resp> => {
  const { payload, settings, merchant } = context;

  // Validate required data
  if (!payload.data?.id) {
    return Resp.error()
      .setMessage('Order ID is missing')
      .setStatus(400)
      .setData({});
  }

  if (!settings.webhookUrl) {
    return Resp.error()
      .setMessage('Webhook URL not configured in settings')
      .setStatus(400)
      .setData({});
  }

  // Continue with logic...
};
```

### 6. Test Response Size

Keep response objects small and focused:

```typescript
// ❌ Bad: Returning entire payload
return Resp.success().setData({
    data: context.payload
});

// ✅ Good: Returning only relevant data
return Resp.success().setData({
    order_id: context.payload.data.id,
    status: context.payload.data.status,
    processed_at: new Date().toISOString(),
});
```

<Tip>
**Response Size**: If the response is too large, log only key fields. The preview window works best with concise responses.
</Tip>

---

## Testing External Webhooks

When testing functions that call external webhooks:

### Using Webhook Testing Services

1. 🔗 **Create a test webhook** at [webhook.site](https://webhook.site) or similar service
2. 📋 **Copy the webhook URL** to your app settings
3. ▶️ **Run your function** in the preview panel
4. ✔️ **Check the webhook site** to verify the payload was received

### Example Webhook Test

```typescript
export default async (
  context: OrderCreatedContext
): Promise<Resp> => {
  try {
    const webhookUrl = "https://webhook.site/your-unique-id";

    const response = await fetch(webhookUrl, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        event: context.payload.event,
        order_id: context.payload.data.id,
        merchant_id: context.payload.merchant.id,
        timestamp: new Date().toISOString(),
      }),
    });

    console.log("Webhook called successfully:", response.status);

    return Resp.success().setData({
        webhook_status: response.status,
    });
  } catch (error) {
    return Resp.error()
      .setMessage(error.message)
      .setStatus(400)
      .setData({});
  }
};
```

---

## Debugging Common Issues

### Issue: Function Times Out

**Possible Causes**:

- 🐌 External API is slow or unresponsive
- 🔄 Infinite loops in code
- 📦 Large data processing
- ⚠️ **For Synchronous Actions**: Function is too slow (user is waiting!)

**Solutions**:

- ⏱️ Add timeout to fetch calls
- ⚡ Optimize data processing
- 🔄 Use async operations efficiently
- ⚠️ **For Synchronous Actions**: Keep logic extremely simple and fast (< 500ms)

```typescript
// Add timeout to fetch
const controller = new AbortController();
const timeout = setTimeout(() => controller.abort(), 5000); // 5 second timeout

try {
  const response = await fetch(url, {
    signal: controller.signal, // Links the fetch request to the abort controller
  });
  clearTimeout(timeout);
} catch (error) {
  if (error.name === "AbortError") {
    console.error("Request timed out");
  }
}
```

<Warning>
**Synchronous Actions Performance**: If you're testing a **synchronous action** (e.g., `shipment.creating`), remember that the user is blocked and waiting. Your function must respond in **milliseconds** (< 500ms recommended). Avoid:

- ❌ Slow external API calls
- ❌ Complex calculations
- ❌ Database queries
- ❌ Multiple sequential requests

Keep synchronous actions simple and fast!
</Warning>

### Issue: Context Data is Undefined

**Possible Causes**:

- ❌ Incorrect event type selected
- ❌ Test data doesn't exist in demo store
- ❌ Wrong parameter passed

**Solutions**:

- ✔️ Verify event type matches your function
- ✔️ Check demo store has the required data
- ✔️ Validate test parameters

### Issue: API Calls Fail

**Possible Causes**:

- ❌ Incorrect API endpoint
- ❌ Missing app scopes
- ❌ Invalid request format

**Solutions**:

- ✔️ Verify API endpoint URL
- ✔️ Check app scopes in Partner Portal
- ✔️ Review API documentation
- ✔️ Check request headers and body format

---

## Publishing After Testing

Once you've thoroughly tested your function:

1. ✔️ **Review all test results** to ensure everything works as expected
2. ⚠️ **Test edge cases** and error scenarios
3. 🔌 **Verify external integrations** are working correctly
4. 📝 **Check console logs** for any warnings or errors
5. 🚀 **Return to Partner Portal** and publish your changes

<Warning>
**Sandbox vs Production**: All changes are saved in the sandbox environment until you publish. Always test thoroughly before publishing to production.
</Warning>

---

## Next Steps

- 💻 **[Event Schemas](/docs/events)** — View detailed schemas for all events
- 🚀 **[Quick Start](/docs/quick-start)** — Create your first App Function
- 📋 **[Supported Events](/docs/supported-events)** — Explore all available events
- 📚 **[Salla APIs](https://docs.salla.dev/426392m0)** — API documentation and reference

---

