# Docs  Conditional Webhooks Merchant Api Salla Docs

## Table of Contents

- [docs/Conditional-Webhooks-Merchant-API-Salla-Docs](#docs-conditional-webhooks-merchant-api-salla-docs)
- [docs/Create-Shipping-App-AWB-Salla-Merchants-APIs-Salla-Docs](#docs-create-shipping-app-awb-salla-merchants-apis-salla-docs)
- [docs/Create-Your-First-App](#docs-create-your-first-app)
- [docs/Create-your-first-App-Partners-Apps-APIs-Salla-Docs](#docs-create-your-first-app-partners-apps-apis-salla-docs)
- [docs/Files-and-Folders-Structure](#docs-files-and-folders-structure)
- [docs/Get-Started](#docs-get-started)

---

## docs/Conditional-Webhooks-Merchant-API-Salla-Docs

# Conditional Webhooks

Webhooks provide a streamlined approach to facilitate communication between applications, offering the advantage of receiving notifications whenever an app receives data from another app. They play a critical role in establishing an event-based communication channel, connecting application owners with Salla. The primary purpose of webhooks is to ensure the synchronization of data between two separate applications.

Webhooks form the foundation of the infrastructure that supports numerous online activities. By [subscribing to a webhook](https://docs.salla.dev/doc-421119#list-of-salla-store-events), developers anticipate receiving a payload that contains relevant information pertaining to the events they are interested in. However, dealing with large volumes of content within these payloads can sometimes be overwhelming and challenging to navigate. This is where Salla Rules comes into play.

Salla Rules offers developers the ability to exercise control and customization over [webhooks](https://docs.salla.dev/doc-421119), utilizing the supported [attributes](https://docs.salla.dev/doc-421120#attributes). Rules enable the breakdown of simple business rules into smaller specification objects, which can later be combined to express more complex rules. This modular approach allows you as a developer to tailor their webhook experiences according to their specific needs and requirements.

## Importance of Rules

### Webhooks Targeting

Narrowing down the received payload is an achievable goal, as rules introduce you to conditional webhooks. Your communication now turns out to be an event-based communication with Salla, and the same is applied in the received payload.

Salla has provided the configurability feature to webhooks. In a sense, Rules contain basic filtering, which allow writing conditions and then afterwards receive particular payload based on the written condition.

As your business grows, you will need to redouble on your service quality served, accuracy delievred, and effort done. With rules, you can easily reduce the amount of the events you listen to, as they usually come loaded in payloads. That said, you only recieve the payloads you are in need in your app.

With rules, you get to head directly to take actions as decisions are easily made, and that means no more time wasted on time-consuming processes. Check for an [overview of webhooks](https://docs.salla.dev/doc-421119) on Salla docs for more details.

<!-- ### Helps Businesses -->

<!-- Business rules can be written as text using a dedicated language, very close to SQL. We refer to them as rules or they can be encapsulated in single classes and referred to as specifications.

Once a rule (or a specification) is written, it can check if a single candidate satisfies it or directly query a data source.

You get to express business rules in a dedicated, simple language. Then, these business rules can be encapsulated in specification classes, reused, and composed to form more complex rules.

Specifications are now reusable and testable. And last but not least, these rules can be used both to check if a candidate satisfies it and to filter any data source. -->

## Use Cases

The following are some use cases that webhooks can be used for:

- You can use rules in webhooks to filter updated carts that contain specific coupon codes.
- You can use rules in webhooks to uniquely identify specific order from a list of orders.
- You can also use rules in webhooks to recognize a specific product using its attributes (SKU, name, etc.).

<!-- Recieve bulk data -->
<!-- Recieve bulk data of Abandoned carts -->
<!-- Create copun codes based on a product with abandanoneded carts -->

<!--

In general, webhooks are crucial for establishing an event-based communication channel between your application and the application architecture of your service provider. They keep critical data synchronized between two distant apps.

As a result, webhooks serve as the foundation for the infrastructure that underpins many of the online activities we take for granted. Consider payment notifications.

If an e-commerce retailer utilizes a third-party payment gateway, the 'payment' event occurs outside of the merchant's website. The payment gateway will use webhooks to call the retailer's registration API and send payment data as soon as it is available. The retailer’s server then accepts this data, enabling it to update its database and user-facing screens.

--- -->

## General Standards in Attributes

Some Binary, Relational, and Logical operators are used when writing rules for a Salla webhook, such as equality, bitwise, and more.

Following the general standards is a must to obtain successful responses, so make sure to follow them. These rules act like conditional webhooks, for you to receive specific data.

Operations, expressions, and conditions to your webhook can be written. For instance, you may use `=,!=,AND,OR` etc in such a manner: `payment_method = YOUR_PAYMENT_METHOD` or in combination `payment_method = mada OR price < 50`. That adds more capability to filter the response based on conditionalities. In the following section, you can look up more into how you can construct your own rules using real-world examples.

## Write Your First Rule

<!-- First, regsiter your webhook using the [Register Webhook](api-5394134) endpoint .

Request

```json
{
  "name": "Salla Update Customer Event",
  "event": "customer.updated",
  "url": "https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814",
  "headers": [
    {
      "key": "Authorization",
      "value": "Your Secret token"
    },
    {
      "key": "Accept-Language",
      "value": "AR"
    }
  ]
}
```

The above `payload` is the normal webhook registration in `Salla`, which will send data from Salla to your server when ever `Customer profile has updated`. Now let's add some rules -->

The following payload registers a new webhook on the [Merchant's dashboard](https://s.salla.sa), not on the [Partners Portal](https://portal.salla.partners), where the developer will be notified whenever the Merchant [created an order](https://docs.salla.dev/doc-421119#order).

```json
{
  "name": "Salla Order Created Event",
  "event": "order.created",
  "url": "https://webhook.site/a61ca376-dd98-4053-b2c4-8ba9cca470fc",
  "version": 2,
  "rule": "total > 100",
  "headers": [
    {
      "key": "Authorization",
      "value": "Your Secret token"
    },
    {
      "key": "Accept-Language",
      "value": "AR"
    }
  ]
}
```
<!-- 
In the above payload you will notice two new field the `version` and `rule` that only exist in [Salla V2's API](https://docs.salla.dev/docs/merchent/openapi.json/paths/~1webhooks~1subscribe/post):

- The **version** tell us what API version you are using; currently it **Salla V2**.

- The **rule** is where you put your custom logic for the webhook by binding to what is supported in the [attributes section](https://docs.salla.dev/docs/merchent/ZG9jOjI0NTE3NDgz-conditional-webhooks#attributes). -->

<!--
!!! note

    Rules only work on Salla V2! -->

<!-- In the rule field we added `branch_id = '827301`, this tells Salla that you want to trigger your webhook whenever a an order is created from a specific `branch` that is of ID `827301`. -->

That said, you have successfully set your first webhook with rules. The next section will be rules to apply in other webhooks' events.

### Examples

The following two examples showcase how conditional webhooks can be implemented practically in your webhook rules queries.

<Tabs>
  <Tab title="Special Offer Webhook Request">

```json
{
  "name": "Salla Special Offer Created Event",
  "event": "specialoffer.created",
  "url": "https://webhook.site/a61ca376-dd98-4053-b2c4-8ba9cca470fc",
  "version": 2,
  "rule": "status = `active` OR applied_to = `first_order`",
  "headers": [
    {
      "key": "Authorization",
      "value": "Your Secret token"
    },
    {
      "key": "Accept-Language",
      "value": "AR"
    }
  ]
}
```

In the above example the webhook was set the event to `specialoffer.created`. In the rule section, we added `OR`
that means, when one of the conditions are `true`, this wil trigger the webhook. In our example, the webhook will be triggered whenever there is a `status` equaling to `active`, or the the special offer created is applied to `order`.

  </Tab>
  <Tab title="Customer Webhook Request">
      
```json
{
  "name": "Salla Update Customer Event",
  "event": "customer.created",
  "url": "https://webhook.site/a61ca376-dd98-4053-b2c4-8ba9cca470fc",
  "version": 2,
  "rule": "city	 = `الرياض` AND location != `حي اليرموك`",
  "headers": [
    {
      "key": "Authorization",
      "value": "Your Secret token"
    },
    {
      "key": "Accept-Language",
      "value": "AR"
    }
  ]
}
```

In the above example, the webhook will be triggered whenever a customer has been created. In the rule section, we added `And`;
that means that both conditions should be `true` to trigger the webhook. In our example, the webhook will be triggered whenever the city is `الرياض` and location is not the whereabouts of `حي اليرموك`.
      
  </Tab>

</Tabs>






<!-- #### Category

Request

```json
{
  "name": "Salla Update Category Event",
  "event": "category.updated",
  "url": "https://webhook.site/a61ca376-dd98-4053-b2c4-8ba9cca470fc",
  "version": 2,
  "rule": "status == active And sort_order >= 2",
  "headers": [
    {
      "key": "Authorization",
      "value": "Your Secret token"
    },
    {
      "key": "Accept-Language",
      "value": "AR"
    }
  ]
}
```

In the above example, the webhook will be triggered whenever a category has been updated. In the rule section, we added `And`;
that means that both conditions should be `true` to trigger the webhook. In our example, the webhook will be triggered whenever a status is `active` and `sort_order` is greater than or equal to `2`. -->
<!--
#### Product

Request

```json
{
  "name": "Salla Update Product Event",
  "event": "product.created",
  "url": "https://webhook.site/a61ca376-dd98-4053-b2c4-8ba9cca470fc",
  "version": 2,
  "rule": "status = hidden AND unlimited_quantity = true OR is_available = true",
  "headers": [
    {
      "key": "Authorization",
      "value": "Your Secret token"
    },
    {
      "key": "Accept-Language",
      "value": "AR"
    }
  ]
}
```

In the above example, the webhook will be triggered whenever a product has been created. In the rule section, we added `And`, `OR`;
that means that whenever both `status` and `unlimited_quantity` are true, then the webhook will be triggered or if `is_available` is `true` then the webhook will triggered.

!!! note
Easily, you can customize your business logic as you want. -->

## Attributes

The following attributes allow you to write conditions only based on them. For example, if you want to write conditions for the `Category` event, use in the `rule` section one or more of the following:

|            |
| ---------- |
| `id`         |
| `name`       |
| `parent_id`  |
| `status`     |
| `sort_order` |


And the same logic goes for all the supported attributes:
- [Order](#order)
- [Product](#product)
- [Customer](#customer)
- [Special Offers](#special-offers)
- [Category](#category)
- [Brand](#brand)
- [Cart](#cart)
- [Miscellaneous](#miscellaneous)
### [Order](https://docs.salla.dev/doc-421119#order)


<Tabs>
  <Tab title="Events">

The supported events are the following:

| Event Name                        |
| --------------------------------- |
| `order.created `                  |
| `order.updated `                  |
| `order.status.updated `           |
| `order.cancelled `                |
| `order.refunded `                 |
| `order.deleted `                  |
| `order.products.updated `         |
| `order.payment.updated `          |
| `order.coupon.updated `           |
| `order.total.price.updated `      |
| `order.shipment.creating `        |
| `order.shipment.created `         |
| `order.shipment.cancelled `       |
| `order.shipment.return.creating ` |
| `order.shipment.return.created `  |
| `order.shipment.return.cancelled` |
| `order.shipping.address.updated ` |

  </Tab>
  <Tab title="Properties">

The rules can contain on or more of the following attributes:

| Name                                        | type          |
| ------------------------------------------- | ------------- |
| `id `                                       | Integer       |
| `reference_id `                             | Integer       |
| `date `                                     | Date and Time |
| `customer_id `                              | Integer       |
| `status_id `                                | Integer       |
| `branch_id `                                | Integer       |
| `coupon_code `                              | String        |
| `feedback_status `                          | String        |
| `total `                                    | Float         |
| `total_discount `                           | Float         |
| `sub_total `                                | Float         |
| `shipping_cost `                            | Float         |
| `cash_on_delivery `                         | Float         |
| `tax_percent `                              | String        |
| `tax_amount `                               | Float         |
| `currency `                                 | String        |
| `payment_method `                           | String        |
| `payment_bank_id `                          | Integer       |
| `shipment_id `                              | Integer       |
| `shipment_pickup_id `                       | Integer       |
| `shipment_tracking_link `                   | String        |
| `shipment_company_id `                      | Integer       |
| `shipment_company_name `                    | String        |
| `shipment_receiver_name `                   | String        |
| `shipment_receiver_email `                  | String        |
| `shipment_receiver_phone `                  | String        |
| `shipment_shipper_name `                    | String        |
| `shipment_shipper_company_name `            | String        |
| `shipment_shipper_email `                   | String        |
| `shipment_shipper_phone `                   | String        |
| `shipment_pickup_address_country `          | String        |
| `shipment_pickup_address_city `             | String        |
| `shipment_pickup_address_shipping_address ` | String        |
| `shipment_pickup_address_street_number `    | String        |
| `shipment_pickup_address_block `            | String        |
| `shipment_pickup_address_postal_code `      | String        |
| `shipment_pickup_address_geo_lat `          | String        |
| `shipment_pickup_address_geo_lng `          | String        |
| `shipment_dropoff_address_country `         | String        |
| `shipment_dropoff_address_city `            | String        |
| `shipment_dropoff_address_shipping_address` | String        |
| `shipment_dropoff_address_street_number `   | String        |
| `shipment_dropoff_address_block `           | String        |
| `shipment_dropoff_address_postal_code `     | String        |
| `shipment_dropoff_address_geo_lat `         | Float         |
| `shipment_dropoff_address_geo_lng `         | Float         |


  </Tab>

</Tabs>


### [Product](https://docs.salla.dev/doc-421119#product)


<Tabs>
  <Tab title="Events">

The supported events are the following:

| Event Name             |
| ---------------------- |
| `product.created `     |
| `product.updated `     |
| `product.deleted `     |
| `product.available `   |
| `product.quantity.low` |

  </Tab>
  <Tab title="Properties">
      
The rules can contain on or more of the following attributes:

| Name                  | type              |
| --------------------- | ----------------- |
| `id `                 | Integer           |
| `currency `           | String            |
| `promotion_title `    | String            |
| `promotion_sub_title` | String            |
| `sku `                | String            |
| `type `               | String            |
| `name `               | String            |
| `short_link_code `    | String            |
| `price `              | Float             |
| `description `        | String            |
| `quantity `           | Integer           |
| `status `             | String            |
| `is_available `       | boolean           |
| `sale_price `         | Float             |
| `sale_end `           | Integer or String |
| `require_shipping `   | boolean           |
| `cost_price `         | Float             |
| `weight `             | Float             |
| `with_tax `           | boolean           |
| `included_tax `       | boolean           |
| `url `                | String            |
| `has_special_price `  | boolean           |
| `regular_price `      | Float             |
| `max_items_per_user ` | Integer           |
| `show_in_app `        | boolean           |
| `notify_quantity `    | Integer or String |
| `unlimited_quantity ` | boolean           |
| `managed_by_branches` | boolean           |
| `brand_id `           | Integer           |

  </Tab>
</Tabs>



### [Customer](https://docs.salla.dev/doc-421119#customer)


<Tabs>
  <Tab title="Events">

The supported events are the following:

| Event Name             |
| ---------------------- |
| `customer.created `    |
| `customer.updated `    |
| `customer.login `      |
| `customer.otp.request` |
      
  </Tab>
  <Tab title="Properties">
    
The rules can contain on or more of the following attributes:

| Name          | type          |
| ------------- | ------------- |
| `id `         | Integer       |
| `first_name ` | String        |
| `last_name `  | String        |
| `mobile `     | String        |
| `mobile_code` | String        |
| `email `      | String        |
| `avatar `     | String        |
| `gender `     | String        |
| `birthday `   | Date and Time |
| `city `       | String        |
| `country `    | String        |
| `currency `   | String        |
| `location `   | String        |


  </Tab>

</Tabs>



### [Special Offers](https://docs.salla.dev/doc-421119#special-offer)


<Tabs>
  <Tab title="Events">
      
The supported events are the following:

| Event Name             |
| ---------------------- |
| `specialoffer.created` |
| `specialoffer.updated` |

      
  </Tab>
  <Tab title="Properties">

The rules can contain on or more of the following attributes:

| Name          | type          |
| ------------- | ------------- |
| `id `         | Integer       |
| `name `       | String        |
| `message `    | String        |
| `offer_type ` | String        |
| `status `     | String        |
| `expiry_date` | Date and Time |


  </Tab>

</Tabs>


### [Category](https://docs.salla.dev/doc-421119#category)



<Tabs>
  <Tab title="Events">
      
The supported events are the following:

| Event Name         |
| ------------------ |
| `category.created` |
| `category.updated` |
  </Tab>
  <Tab title="Properties">

The rules can contain on or more of the following attributes:

| Name         | type    |
| ------------ | ------- |
| `id `        | Integer |
| `name `      | String  |
| `parent_id ` | Integer |
| `status `    | String  |
| `sort_order` | Integer |


  </Tab>

</Tabs>


### [Brand](https://docs.salla.dev/doc-421119#brand)


<Tabs>
  <Tab title="Events">
      
The supported events are the following:

| Event Name      |
| --------------- |
| `brand.created` |
| `brand.updated` |
| `brand.deleted` |

  </Tab>
  <Tab title="Properties">

The rules can contain on or more of the following attributes:

| Name         | type    |
| ------------ | ------- |
| `id `        | Integer |
| `name `      | String  |
| `status `    | boolean |
| `custom_url` | String  |
  </Tab>
 
</Tabs>

### [Cart](https://docs.salla.dev/doc-421119#cart)

<Tabs>
  <Tab title="Events">

The supported event is the following:

| Event Name        |
| ----------------- |
| `abandoned.cart ` |

  </Tab>
  <Tab title="Properties">

The rules can contain on or more of the following attributes:

| Name               | type          |
| ------------------ | ------------- |
| `id `              | Integer       |
| `subtotal `        | Float         |
| `currency `        | String        |
| `total `           | Float         |
| `coupon_code `     | String        |
| `customer_id `     | Integer       |
| `customer_avatar ` | String        |
| `customer_name `   | String        |
| `customer_mobile ` | String        |
| `created_at `      | Date and Time |
| `updated_at `      | Date and Time |



  </Tab>

</Tabs>



### [Miscellaneous](https://docs.salla.dev/doc-421119#miscellaneous)

<Tabs>
  <Tab title="Events">
The supported event is the following:

| Event Name     |
| -------------- |
| `review.added` |
  </Tab>
  <Tab title="Properties">

The rules can contain on or more of the following attributes:

| Name           | type    |
| -------------- | ------- |
| `parent_id `   | Integer |
| `store_id `    | Integer |
| `customer_id ` | Integer |
| `product_id `  | Integer |
| `page_id `     | Integer |
| `order_id `    | Integer |
| `rating `      | Integer |
| `content `     | String  |
| `status `      | String  |
| `ip_address `  | String  |
| `ip_city `     | String  |
| `ip_country `  | String  |
| `type `        | String  |

  </Tab>
 
</Tabs>

---

## docs/Create-Shipping-App-AWB-Salla-Merchants-APIs-Salla-Docs

# Create Shipping App 

Salla [Partners Portal](https://salla.partners/login) provides the tools to [create different types of Apps](https://salla.dev/blog/create-your-first-app-on-salla-developer-portal/) including Shipping Apps. These Apps streamline shipping for Salla stores by offering a platform to manage orders shipment. As well as integrate with Salla stores and couriers, providing multi-carrier support. They have become essential for online shopping, providing fast, affordable, and reliable shipping services.

:::danger[Important]
To enable your shipping application to appear in Salla’s AWB options, contact the partners team at [partners@salla.sa](mailto:partners@salla.sa). 
:::

## What you'll learn:
In this article we will walk you through the steps of creating a Shipping App using the [Partners Portal](https://salla.partners) as well as setting up the App for shipping service providers.

- [How to Create a Shipping App](#how-to-create-a-shipping-app)

## How to Create a Shipping App 

Creating Shipping Apps using the [Partners Portal](https://salla.partners) is a straightforward process.

First, log in to [Salla Partners](https://portal.salla.partners) account Then, click on the *My Apps* menu item on the left of the page. 
<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-01.png?hi)

This will redirect the page to the *My Apps* page. Click on *Create your first App* to begin creating an App.


<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-02.png?how)


:::tip[Note]
With [Salla App Store](https://apps.salla.sa), you can have two types of Apps:

**Public App:** your App can go into public usage and display for those users who browse the Salla App Store. The Merchants can view your App's details and may download/purchase your App.

**Private App:** privately built and developed apps for integration to either larger scaled or individual Merchants. The Apps won't be displayed or accessed from the Salla App Store homepage search results and more.
:::

In this step, you will need to choose your App's type  **Public**.

:::caution[Note]
**Private Apps** don’t have the option of Shipping App category
:::


<!-- focus: false -->
<!--![](https://cdn.salla.network/docs/MerchantAPI/create-app-03.png?w)-->


![App Type](https://api.apidog.com/api/v1/projects/451700/resources/366889/image-preview)


Afterward, start entering the basic information of your App:
|Item|Description|
|--|--|
|Icon|The App icon image, it should have Minimum width : 250 pixels, height : 250 pixels. And the Width to high ratio is : 1 : 1 . |
|Name| The App name should be provided in English and Arabic|
|Category| **Shipping Apps** for Shipping services Apps, **General App** for other than Shipping App|
|Description|Describe your App in 50 characters, in English and Arabic|
|App Website|The App website URL link|
|Support Email|The App support email address|

Make sure to choose App Category as Shipping. As shown below:
![](https://cdn.salla.network/docs/MerchantAPI/create-app-17.png?vr)

Following is a complete example for Shipping App Basic information:
![](https://cdn.salla.network/docs/MerchantAPI/create-app-18.png?vr)


The developer will receive a notification for creating the App successfully in the [Partners Portal](https://salla.partners/) and on the email linked to the partner's account.

<TipInfo>Read more about publishing Salla App [here](https://salla.dev/blog/standards-salla-apps-publications/).</TipInfo>
<br>

---

## docs/Create-Your-First-App

# Create Your First App

Salla has made it easier for developers worldwide to reach its audience of over 60,000 active retailers. Achieve more and make money by offering your services to many Merchants or by engaging them in high-touch customer interactions. You can do more, as we explained in a [previous article](https://salla.dev/blog/welcome-to-sallas-developer-portal/).

:::tip[Note]
Developers can access a rich list of Salla's Partners resources using the [dedicated API documentation](https://docs.salla.dev/doc-421117), which provides in-depth access methods to Salla customers, stores, and more.
:::

With the [Partners Portal](https://portal.salla.partners/), you can create Apps, test on demo stores, release them on the [Salla Apps Marketplace](https://apps.salla.sa/en) and get paid.

:::info[Information]
The[ Salla Partner Portal](https://portal.salla.partners/) gives more capabilities for developers to design, develop, build, ship, and connect their apps with the Salla E-commerce portal.
:::
 As we will be unraveling in this article, the [portal](https://salla.partners/) will be much more effortless to workaround.
### Create Salla App

To start, make sure to have a [verified](https://salla.dev/blog/id-verification-by-salla-is-here/) [Salla Partners account](https://salla.dev/blog/create-salla-partners-account/) on [https://salla.partners](https://salla.partners/).

Login to your account on [https://salla.partners](https://portal.salla.partners/) using your credentials. Once logged in you will be redirected to the main page.

<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-02.png?how)


From the left menu, can click on "My Apps". This will land on the Apps page where you can create your first app.

<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-02.png)

:::tip[Note]
With Salla App Store, you can have two types of Apps:

**Public App:** your App can go into public usage and display for those users who browse the Salla App Store. The Merchants can view your App's details and may download/purchase your App.

**Private App:** privately built and developed apps for integration to either larger scaled or individual Merchants. The Apps won't be displayed or accessed from the Salla App Store homepage search results and more.
:::

In this step, you will need to choose your App's type either Public or Private.

<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-03.png?w)
:::tip[Note]
**Shipping App** can be a **Public** or **Private** App, you will be able to choose the App category in the next section.
:::

Afterward, start entering the basic information of your App:
|Item|Description|
|--|--|
|Icon|The App icon image, should have Minimum width : 250 pixels, height : 250 pixels. And the Width to high ratio : 1 : 1 . |
|Name| The App name should be provided in English and Arabic|
|Category| **Shipping Apps** for Shipping services Apps., **General App** for other than Shipping App|
|Description|Describe your App in 50 characters|
|App Website|The App website URL link|
|Support Email|The App support email address|



<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-04.png)

Following is a complete example for App Basic information:

<!-- focus: false -->
![image](https://cdn.salla.network/docs/MerchantAPI/create-app-05.png)

Now you can click on "Create App". 

🥳You have successfully created your first App on Salla Partners Portal.

:::tip[Note]
Getting here, means the App was **created**. In order to **publish** you will need to continue reading.
:::

#### **App Details**
After creating the App, you will be redirected to the App details page. App Details page is where you will find the App deatils inlcuding App Keys, App Scope, Webhooks Notifications App Trusted IP's, App Settings, App Snippet, Custom Plans, DNS Management, App Testing, App Testing, App Publishing. Each section will be explained in the following parts.
 
##### **1- App Keys**
The App keys details are required to authorize your App via Merchants. Such credentials include:

- Client ID
- Client Secret Key with an option to generate a new Client secret key
- OAuth Modes, either Easy Mode as in-house authorization or Custom Mode.

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-07.png?v)

##### **2- App Scope**
After that, you will come to the "App Scope" section. This section specifies your app's scope to protect your app by identifying and restricting access to certain features and services.

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-08.png?v)

##### **3- Webhooks and Notifications**
Next, you will have the "Webhooks/Notifications". [Webhooks](https://salla.dev/blog/webhooks-101/) are one way that Apps can send automated messages or information to other apps. You can use that to be notified whenever events occur in stores, such as "create an order", "register a new customer", and others. Scrolling down, you will outlook more options:

- Adding your Webhook URL to where you will be receiving the events you choose to listen to
- Get your Webhook Secret key with the option to generate a new one
- Stream App Events
- Add Store Events

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-09.png?v)
###### **a. App Events**
For [App Events](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ), your webhook will automatically receive the events when a merchant triggers an action on your app, such as:

- App Installed
- App Updated
- App Trial Started
- App Trial Ended
- App Subscription Started
- App Subscription Ended
- App Subscription Renewed
- App Rated

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-10.png?v)

###### **b. Store Events**
For adding [Store Events](https://docs.salla.dev/doc-421119#list-of-events), Salla has listed out events you can listen to with each having its own attributes, such as:

- Orders
- Products
- Customers
- Categories
- Brands
- Stores
- Miscellaneous

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-11.png?v)

##### **4- App Trusted IP**
In this section, you can [add a trusted IPs](https://salla.dev/blog/secure-your-apps-with-the-trusted-ip-address-now/) for your App for more secure communication between the App and Salla API
![](https://cdn.salla.network/docs/MerchantAPI/create-app-08.png)

##### **5- App Snippets**
The App snippets can be added in this section. Click on "View Snippets" to start adding.

![](https://cdn.salla.network/docs/MerchantAPI/create-app-09.png)

<TipInfo> Read more about App Snippets [here](https://salla.dev/blog/a-guide-to-app-snippet/).</TipInfo>
<br>
##### **6- App Settings**
In this section you can edit the App settings, including buliding the App Settings and Settings Validation URL
![](https://cdn.salla.network/docs/MerchantAPI/create-app-10.png)

<TipInfo>you can follow the steps in this [article](https://salla.dev/blog/how-to-build-app-settings-form/) for detailed guidance.</TipInfo>

<br>
##### **7- Custom Plans**
This feature enables you to create unique plans and features tailored to your specific needs. 
![](https://cdn.salla.network/docs/MerchantAPI/create-app-11.png)

<TipInfo>Read more about Custom Plans [here](https://salla.dev/blog/comprehensive-guide-to-custom-plans-on-salla-partners/).</TipInfo>

<br>
##### **8- DNS Management**
Managing DNS (Domain Name System) records for a Salla Store involves configuring the settings that enable the store’s domain name to be associated with its corresponding IP address, which helps to ensure that visitors can access the store using the desired domain name.
![](https://cdn.salla.network/docs/MerchantAPI/create-app-12.png)

<TipInfo>More about DNS Management [here](https://salla.dev/blog/easily-manage-dns-records-on-salla-partners/)</TipInfo>
<br>

##### **9- App Testing**
In this section you can test your App using a demo store, the demo store will provide a real life experience of an actual store where you can test your App features.
![](https://cdn.salla.network/docs/MerchantAPI/create-app-13.png)

<TipInfo>Follow the steps of creating a demo store [here](https://salla.dev/blog/how-to-test-your-app-using-salla-demo-stores/)</TipInfo>

<br>


#### App Publishing

App publishing allows your App to be displayed in [Salla Apps Store](https://apps.salla.sa/en) for all Salla Merchants. 
To publish your App, scroll down on the App Details page and click on the "Start Publishing your App" button, to begin the process.

![](https://cdn.salla.network/docs/MerchantAPI/create-app-14.png)

The publishing process consists of six sections, Basic Information, App Configurations, App Features, Pricing, Contact Information and Service Trial. 

<TipInfo>Read more about publishing Salla App [here](https://salla.dev/blog/standards-salla-apps-publications/).</TipInfo>
<br>
With that said, we covered the [Salla Partner Portal](https://salla.partners/) fully, with all its procedures to create your first App on the portal. Follow up with your email and [portal](https://salla.partners/) notifications for further understanding of the portal.


## Your Gateway to Success

With the steps mentioned above, you will create your first App on Salla with ease and a smooth process.

Time for you to elevate your work, experience, and ability and have a solid reputation with passive income that could be higher than expected, as we have [discussed](https://salla.dev/blog/welcome-to-sallas-developer-portal/).

If you are facing any issues or have any further questions, be part of the Global Developer Community on [Telegram](https://t.me/salladev)

---

## docs/Create-your-first-App-Partners-Apps-APIs-Salla-Docs

# Create Your First App

Salla has made it easier for developers worldwide to reach its audience of over 60,000 active retailers. Achieve more and make money by offering your services to many Merchants or by engaging them in high-touch customer interactions. You can do more, as we explained in a [previous article](https://salla.dev/blog/welcome-to-sallas-developer-portal/).

:::tip[Note]
Developers can access a rich list of Salla's Partners resources using the [dedicated API documentation](https://docs.salla.dev/doc-421117), which provides in-depth access methods to Salla customers, stores, and more.
:::

With the [Partners Portal](https://portal.salla.partners/), you can create Apps, test on demo stores, release them on the [Salla Apps Marketplace](https://apps.salla.sa/en) and get paid.

:::info[Information]
The[ Salla Partner Portal](https://portal.salla.partners/) gives more capabilities for developers to design, develop, build, ship, and connect their apps with the Salla E-commerce portal.
:::

As we will be unraveling in this article, the [Portal](https://portal.salla.partners/) will be much more effortless to workaround.

### Create Salla App
To start, make sure to have a [verified](https://salla.dev/blog/id-verification-by-salla-is-here/) [Salla Partners account](https://salla.dev/blog/create-salla-partners-account/) on [Salla Partners](https://portal.salla.partners/).

Login to your account on [Salla Partners](https://portal.salla.partners/) using your credentials. Once logged in you will be redirected to the main page.

<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-01.png)

From the left menu, can click on "My Apps". This will land on the Apps page where you can create your first app.

<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-02.png?how)

:::tip[Note]
With Salla App Store, you can have two types of Apps:

**Public App:** your App can go into public usage and display for those users who browse the Salla App Store. The Merchants can view your App's details and may download/purchase your App.

**Private App:** privately built and developed apps for integration to either larger scaled or individual Merchants. The Apps won't be displayed or accessed from the Salla App Store homepage search results and more.
:::

In this step, you will need to choose your App's type either Public or Private.

<!-- focus: false -->
<!--//![](https://cdn.salla.network/docs/MerchantAPI/create-app-03.png)-->

![](https://i.imgur.com/GV22JFJ.png)

:::tip[Note]
**Shipping App** can **only** be a **Public** App, you will be able to choose the App category in the next section.
:::

Afterward, start entering the basic information of your App:
|Item|Description|
|--|--|
|Icon|The App icon image, should have Minimum width : 250 pixels, height : 250 pixels. And the Width to high ratio : 1 : 1  |
|Name| The App name should be provided in English and Arabic|
|Category| **Shipping Apps** for Shipping services Apps, **General App** for other than Shipping App, **Communication App** for communication providers.|
|Description|Describe your App in 50 characters|
|App Website|The App website URL link|
|Support Email|The App support email address|



<!-- focus: false -->
![](https://cdn.salla.network/docs/MerchantAPI/create-app-04.png)

Following is a complete example for App Basic information:

<!-- focus: false -->
![image](https://cdn.salla.network/docs/MerchantAPI/create-app-05.png)

Now you can click on "Create App". 

🥳You have successfully created your first App on Salla Partners Portal.

:::tip[Note]
Getting here, means the App was **created**. In order to **publish** you will need to continue reading.
:::

#### **App Details**
After creating the App, you will be redirected to the App details page. App Details page is where you will find the App deatils inlcuding App Keys, App Scope, Webhooks Notifications App Trusted IP's, App Settings, App Snippet, Custom Plans, DNS Management, App Testing, App Testing, App Publishing. Each section will be explained in the following parts.
 
##### **1- App Keys**
The App keys details are required to authorize your App via Merchants. Such credentials include:

- Client ID
- Client Secret Key with an option to generate a new Client secret key
- OAuth Modes, either Easy Mode as in-house authorization or Custom Mode.

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-07.png?v)

##### **2- App Scope**
After that, you will come to the "App Scope" section. This section specifies your app's scope to protect your app by identifying and restricting access to certain features and services.

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-08.png?v)

##### **3- Webhooks and Notifications**
Next, you will have the "Webhooks/Notifications". [Webhooks](https://salla.dev/blog/webhooks-101/) are one way that Apps can send automated messages or information to other apps. You can use that to be notified whenever events occur in stores, such as "create an order", "register a new customer", and others. Scrolling down, you will outlook more options:

- Adding your Webhook URL to where you will be receiving the events you choose to listen to
- Get your Webhook Secret key with the option to generate a new one
- Stream App Events
- Add Store Events

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-09.png?v)
###### **a. App Events**
For [App Events](https://docs.salla.dev/doc-421413?nav=01HNA8M216X4HFNGWM9TWSTCKQ), your webhook will automatically receive the events when a merchant triggers an action on your app, such as:

- App Installed
- App Updated
- App Trial Started
- App Trial Ended
- App Subscription Started
- App Subscription Ended
- App Subscription Renewed
- App Rated

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-10.png?v)

###### **b. Store Events**
For adding [Store Events](https://docs.salla.dev/doc-421119#list-of-events), Salla has listed out events you can listen to with each having its own attributes, such as:

- Orders
- Products
- Customers
- Categories
- Brands
- Stores
- Miscellaneous

<!-- focus: false -->
![](https://cdn.salla.network/docs/PartnerAPI/how-to-11.png?v)

##### **4- App Trusted IP**
In this section, you can [add a trusted IPs](https://salla.dev/blog/secure-your-apps-with-the-trusted-ip-address-now/) for your App for more secure communication between the App and Salla API
![](https://cdn.salla.network/docs/MerchantAPI/create-app-08.png)

##### **5- App Snippets**
The App snippets can be added in this section. Click on "View Snippets" to start adding.

![](https://cdn.salla.network/docs/MerchantAPI/create-app-09.png)

<TipInfo> Read more about App Snippets [here](https://salla.dev/blog/a-guide-to-app-snippet/).</TipInfo>
<br>
##### **6- App Settings**
In this section you can edit the App settings, including buliding the App Settings and Settings Validation URL
![](https://cdn.salla.network/docs/MerchantAPI/create-app-10.png)

<TipInfo>You can follow the steps in this [article](https://salla.dev/blog/how-to-build-app-settings-form/) for detailed guidance.</TipInfo>

<br>
##### **7- Custom Plans**
This feature enables you to create unique plans and features tailored to your specific needs. 
![](https://cdn.salla.network/docs/MerchantAPI/create-app-11.png)

<TipInfo>Read more about Custom Plans [here](https://salla.dev/blog/comprehensive-guide-to-custom-plans-on-salla-partners/).</TipInfo>

<br>
##### **8- DNS Management**
Managing DNS (Domain Name System) records for a Salla Store involves configuring the settings that enable the store’s domain name to be associated with its corresponding IP address, which helps to ensure that visitors can access the store using the desired domain name.
![](https://cdn.salla.network/docs/MerchantAPI/create-app-12.png)

<TipInfo>More about DNS Management [here](https://salla.dev/blog/easily-manage-dns-records-on-salla-partners/).</TipInfo>
<br>

##### **9- App Testing**
In this section you can test your App using a demo store, the demo store will provide a real life experience of an actual store where you can test your App features.
![](https://cdn.salla.network/docs/MerchantAPI/create-app-13.png)

<TipInfo>Follow the steps of creating a demo store [here](https://salla.dev/blog/how-to-test-your-app-using-salla-demo-stores/)</TipInfo>

<br>


#### App Publishing

App publishing allows your App to be displayed in [Salla Apps Store](https://apps.salla.sa/en) for all Salla Merchants. 
To publish your App, scroll down on the App Details page and click on the "Start Publishing your App" button, to begin the process.

![](https://cdn.salla.network/docs/MerchantAPI/create-app-14.png)

The publishing process consists of six sections, Basic Information, App Configurations, App Features, Pricing, Contact Information and Service Trial. 

<TipInfo>Read more about publishing Salla App [here](https://salla.dev/blog/standards-salla-apps-publications/).</TipInfo>
<br>
With that said, we covered the [Salla Partner Portal](https://salla.partners/) fully, with all its procedures to create your first App on the portal. Follow up with your email and [portal](https://salla.partners/) notifications for further understanding of the portal.


## Your Gateway to Success

With the steps mentioned above, you will create your first App on Salla with ease and a smooth process.

Time for you to elevate your work, experience, and ability and have a solid reputation with passive income that could be higher than expected, as we have [discussed](https://salla.dev/blog/welcome-to-sallas-developer-portal/).

If you are facing any issues or have any further questions, be part of the Global Developer Community on [Telegram.](https://t.me/salladev)

---

## docs/Files-and-Folders-Structure

# Files and Folders Structure

## Docs

- [Directory structure](https://docs.salla.dev/421918m0.md): Salla theme is a collection of files and folders that define the theme's presentation layer. 
- [Twilight.json](https://docs.salla.dev/421921m0.md): The [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) file is included within the Twilight theme, and it is placed in the root directory. This setup file contains the main theme's information, features and components for the rendering purpose that occurs on the Theme. Use [Salla Partners Portal](https://salla.partners) to conduct visual modifications that includes [Theme settings](https://docs.salla.dev/apis/doc-421879), [Theme features](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and [Theme components](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

---

## docs/Get-Started

# Get Started

**Salla Merchant APIs** are a suite of RESTful endpoints, purpose-built for secure, fast, and easy access to Merchant data. Developers can build their [Apps](https://salla.partners) by consuming Salla’s standard APIs, scale their Apps to encompass a mass base of over 60,000 [online stores](https://salla.sa), and publish their innovations to one central hub, the [Salla App Store](https://apps.salla.sa). **Learn more about creating your first Salla App by following this [article](https://salla.dev/blog/create-your-first-app-on-salla-developer-portal/).**



:::tip[Base URI] 

All API URLs referenced in the documentation have the following base: `https://api.salla.dev/admin/v2`
:::

### <img src="https://api.apidog.com/api/v1/projects/451700/resources/344159/image-preview" width ="7%" /> List of Salla's Merchant APIs

These endpoints include a suite range of APIs for:

<AccordionGroup>
  <Accordion title="Order Management" defaultOpen>
    <CardGroup cols={3}>
      <Card title="Abandoned Carts" href="https://docs.salla.dev/api-5394138" Icon icon="material-outline-shopping_cart">
        Track and manage abandoned shopping carts.
      </Card>
      <Card title="Order Assignments" href="https://docs.salla.dev/api-5576999" Icon icon="material-outline-assignment">
        Assign orders to specific employees or branches.
      </Card>
      <Card title="Order Histories" href="https://docs.salla.dev/api-5394162" Icon icon="material-outline-history">
        Track and manage the history of orders.
      </Card>
      <Card title="Order Invoices" href="https://docs.salla.dev/api-5394157" Icon icon="material-outline-receipt">
        Generate and manage order invoices.
      </Card>
      <Card title="Order Items" href="https://docs.salla.dev/api-5565737" Icon icon="material-outline-list_alt">
        Manage individual items within an order.
      </Card>
      <Card title="Order Reservations" href="https://docs.salla.dev/api-5579097" Icon icon="material-outline-event">
        Handle order reservations and related actions.
      </Card>
      <Card title="Order Statuses" href="https://docs.salla.dev/api-5394148" Icon icon="material-outline-flag">
        Manage different statuses for orders.
      </Card>
      <Card title="Order Tags" href="https://docs.salla.dev/api-5394154" Icon icon="material-outline-label">
        Assign and manage tags for orders.
      </Card>
      <Card title="Orders" href="https://docs.salla.dev/api-5394146" Icon icon="material-outline-shopping_bag">
        Handle order management and details.
      </Card>
      
    </CardGroup>
      <Card title="Exports" href="https://docs.salla.dev/api-5607986" Icon icon="material-outline-file_download">
        Export data related to products, orders, and other entities.
      </Card>
  </Accordion>
  <Accordion title="Product Management">
    <CardGroup cols={2}>
      <Card title="Brands" href="https://docs.salla.dev/api-5394213" Icon icon="material-outline-emoji_objects">
        Manage product brands in the store.
      </Card>
      <Card title="Categories" href="https://docs.salla.dev/api-5394207" Icon icon="material-outline-category">
        Organize products into categories.
      </Card>
      <Card title="Digital Products" href="https://docs.salla.dev/api-5394181" Icon icon="material-outline-cloud_upload">
        Handle the management of digital products.
      </Card>
      <Card title="Product Images" href="https://docs.salla.dev/api-5394184" Icon icon="material-outline-image">
        Manage images associated with products.
      </Card>
      <Card title="Product Option Values" href="https://docs.salla.dev/api-5394199" Icon icon="material-outline-tune">
        Manage specific values for product options.
      </Card>
      <Card title="Product Options" href="https://docs.salla.dev/api-5394195" Icon icon="material-outline-settings">
        Define and manage options available for products.
      </Card>
      <Card title="Product Quantities" href="https://docs.salla.dev/api-5394192" Icon icon="material-outline-storage">
        Track and manage product quantities in stock.
      </Card>
      <Card title="Product Tags" href="https://docs.salla.dev/api-5394180" Icon icon="material-outline-label_important">
        Manage tags associated with products.
      </Card>
      <Card title="Products" href="https://docs.salla.dev/api-5394168" Icon icon="material-outline-store">
        Handle product management including creation and updates.
      </Card>
      <Card title="Product Variants" href="https://docs.salla.dev/api-5394202" Icon icon="material-outline-merge_type">
        Manage different variants of products.
      </Card>
    </CardGroup>
  </Accordion>
  <Accordion title="Customer Management">
    <CardGroup cols={2}>
      <Card title="Customers" href="https://docs.salla.dev/api-5394121" Icon icon="material-outline-people">
        Manage customer information and profiles.
      </Card>
      <Card title="Customer Groups" href="https://docs.salla.dev/api-5394129" Icon icon="material-outline-group_work">
        Organize customers into groups for targeted actions.
      </Card>
        
              <Card title="Loyalty Points" href="https://docs.salla.dev/api-12250577" Icon icon="material-outline-timeline">
        Organize customers into groups for targeted actions.
      </Card>
        
    </CardGroup>
  </Accordion>
  <Accordion title="Marketing and Sales">
    <CardGroup cols={2}>
      <Card title="Advertisements" href="https://docs.salla.dev/api-5394265" Icon icon="material-outline-campaign">
        Handle advertisement settings and campaigns.
      </Card>
      <Card title="Affiliates" href="https://docs.salla.dev/api-5394270" Icon icon="material-outline-handshake">
        Manage affiliate programs and partnerships.
      </Card>
      <Card title="Coupons" href="https://docs.salla.dev/api-5394275" Icon icon="material-outline-local_offer">
        Handle the creation and management of discount coupons.
      </Card>
      <Card title="Special Offers" href="https://docs.salla.dev/api-5394217" Icon icon="material-outline-whatshot">
        Create and manage special offers for products.
      </Card>
      
    </CardGroup>
      <Card title="Reviews" href="https://docs.salla.dev/api-5394279" Icon icon="material-outline-star">
        Manage product and service reviews.
      </Card>
  </Accordion>
  <Accordion title="Store Configuration">
    <CardGroup cols={2}>
      <Card title="Branches" href="https://docs.salla.dev/api-5394224" Icon icon="material-outline-business_center">
        Handle different store branches.
      </Card>
      <Card title="DNS Records" href="https://docs.salla.dev/api-5394251" Icon icon="material-outline-dns">
        Manage DNS records for custom domains.
      </Card>
      <Card title="Employees" href="https://docs.salla.dev/api-5394259" Icon icon="material-outline-engineering">
        Manage employee roles and permissions in the store.
      </Card>
      <Card title="Store" href="https://docs.salla.dev/api-5394261" Icon icon="material-outline-settings_applications">
        Configure store settings and information.
      </Card>
      
              <Card title="Webhooks" href="https://docs.salla.dev/api-5394135" Icon icon="material-outline-notifications_active">
        Configure webhooks for event notifications.
      </Card>
        
              <Card title="Custom URLs" href="https://docs.salla.dev/api-10393771" Icon icon="material-outline-dashboard_customize">
        Configure webhooks for event notifications.
      </Card>
    </CardGroup>

  </Accordion>
  <Accordion title="Shipment Integration">
    <CardGroup cols={2}>
      <Card title="Shipments" href="https://docs.salla.dev/api-5394232" Icon icon="material-outline-local_shipping">
        Track and manage shipments for orders.
      </Card>
      <Card title="Shipping Companies" href="https://docs.salla.dev/api-5394239" Icon icon="material-outline-domain">
        Manage shipping company integrations.
      </Card>
      <Card title="Shipping Rules" href="https://docs.salla.dev/api-5394243" Icon icon="material-outline-gavel">
        Define rules for shipping based on various conditions.
      </Card>
      <Card title="Shipping Zones" href="https://docs.salla.dev/api-5394247" Icon icon="material-outline-map">
        Define and manage different shipping zones.
      </Card>
    </CardGroup>
  </Accordion>
  <Accordion title="Financial Management">
    <CardGroup cols={3}>
      <Card title="Payments" href="https://docs.salla.dev/api-5394164" Icon icon="material-outline-payment">
        Handle payment methods and transactions.
      </Card>
      <Card title="Taxes" href="https://docs.salla.dev/api-5394141" Icon icon="material-outline-attach_money">
        Manage tax settings and rules for transactions.
      </Card>
      <Card title="Transactions" href="https://docs.salla.dev/api-8382471" Icon icon="material-outline-account_balance">
        Manage financial transactions associated with orders.
      </Card>
    </CardGroup>
  </Accordion>
  <Accordion title="Localization">
    <CardGroup cols={2}>
      <Card title="Cities" href="https://docs.salla.dev/api-5394230" Icon icon="material-outline-location_city">
        Manage cities for shipping and localization.
      </Card>
      <Card title="Countries" href="https://docs.salla.dev/api-5394228" Icon icon="material-outline-public">
        Manage countries for localization and shipping.
      </Card>
      <Card title="Currencies" href="https://docs.salla.dev/api-5394257" Icon icon="material-outline-euro_symbol">
        Configure currencies available for transactions.
      </Card>
      <Card title="Languages" href="https://docs.salla.dev/api-5738815" Icon icon="material-outline-language">
        Manage the languages available in the store.
      </Card>
    </CardGroup>
  </Accordion>
</AccordionGroup>


### ✅ Requirements

In order to make developers' interactions with Salla APIs easier, and for a more seamless, professional experience, the bare minimum requirements are as follows:

| |
| -- |
| Basic understanding of programming, API consumption, webhooks calling, and JSON  schema. |    
| Authentication & Authorization using the [OAuth2.0 security protocol](https://docs.salla.dev/doc-421118). |
| Verified [Salla Partners](https://salla.partners) account. |
    
### 💻 APIs Powered By OAuth2.0 With Salla Partners

[Salla Partners](https://salla.partners), backed by the [OAuth2.0 security protocol](https://docs.salla.dev/doc-421118), allows for scoped access to the Merchants' store. Developers use their account on the Partners Portal to mark the scopes they want to obtain, which is based on their own App’s logic. Those marked app scopes will appear for the Merchant when requesting access, and if access is authorized, the developer can use the access token for a period of 14 days with the ability to refresh it using the refresh token within a 1-month timeline. Read more about the OAuth implementation via these articles [here](https://salla.dev/blog/oauth-2-0-in-action-with-salla/) and [here](https://salla.dev/blog/oauth-2-using-postman/).

### 🔗 Webhooks

[Webhooks](https://docs.salla.dev/doc-421119) are an automated way for a server to talk to another server, allowing application developers to perform actions based on certain events. They provide an efficient and secure means of receiving near-real-time notifications from other services like payment processors, shipping providers and more. Salla provides two sets of events:

- [App Events](https://docs.salla.dev/doc-421413): Automatic events sent to your webhook server that are related to your Salla App, which include Store Authorization, App Installed, App Subscription Started, App Settings Updated, and more!

- [Store Events](https://docs.salla.dev/doc-421119#list-of-salla-store-events): Events you can subscribe to from the Partners Portal where only the events you want will be sent to the Webhook Server URL set on the Portal. Such events are explained further below:

<CardGroup cols={4}>
  <Card title="Orders" href="https://docs.salla.dev/doc-433804">
    Receive updates on order activities.
  </Card>
  <Card title="Products" href="https://docs.salla.dev/doc-433805">
    Get notifications about product-related events.
  </Card>
  <Card title="Shippings" href="https://docs.salla.dev/doc-433806">
    Be informed of shipping-related changes.
  </Card>
  <Card title="Shipments" href="https://docs.salla.dev/doc-433807">
    Receive alerts for shipment status updates.
  </Card>
  <Card title="Customers" href="https://docs.salla.dev/doc-433808">
    Stay notified about customer activities.
  </Card>
  <Card title="Categories" href="https://docs.salla.dev/doc-433809">
    Get updates for category changes.
  </Card>
  <Card title="Brand" href="https://docs.salla.dev/doc-433810">
    Receive information on brand-related events.
  </Card>
  <Card title="Store" href="https://docs.salla.dev/doc-433811">
    Be notified of store-related occurrences.
  </Card>
  <Card title="Cart" href="https://docs.salla.dev/doc-433812">
    Get alerts on cart activities.
  </Card>
  <Card title="Invoice" href="https://docs.salla.dev/doc-433813">
    Receive updates concerning invoices.
  </Card>
  <Card title="Special Offer" href="https://docs.salla.dev/doc-433814">
    Be informed of special offer events.
  </Card>
  <Card title="Miscellaneous" href="https://docs.salla.dev/doc-433815">
    Get notified about other general updates, such Reviews.
  </Card>
</CardGroup>
 
 
<Container>
Salla also supports conditional webhooks, where you can write rules specific for a webhook you subscribed to. Read more on how to use such a feature [here](https://docs.salla.dev/doc-421120).
</Container>

 


### 🚫 Rate Limit

[Rate Limit](https://docs.salla.dev/doc-421125) regulates the number of API requests a client/developer can send per second. This helps protect API resources from abuse and overuse, and ensures that the API service is available to all customers who need it. When consuming Salla APIs, and to ensure fairness and stability for all the developers, Rate Limit are set to all the API endpoints.

### 🌐 Language Support

Some specific API endpoints have support for multiple languages, which can be achieved via Accept Language and Content Language Header values. Read more on how to utilize the Multi-Language Support feature in Salla APIs in this [article](https://docs.salla.dev/doc-421122).

:::check[🕹 Test it out]

To get going quickly, we recommend using an API collaboration tool called [Postman](https://www.postman.com/). You can use the link below to import our collection of endpoints.
<br> [![Run in Postman](https://run.pstmn.io/button.svg)](https://www.postman.com/salla-app/workspace/salla-e-commerce-platform/overview)
:::

### 📝 ChangeLog

Introducing a new endpoint? Updating an existing one? Deprecating or even announcing a [breakchange](https://docs.salla.dev/doc-421127)? All is found in the [ChangeLog page](https://docs.salla.dev/doc-421127) as well as the [API ChangeLog](https://t.me/SallaAPI) Telegram Channel. The Salla APIs ChangeLog allows users to view new releases, updates, and critical changes to all Salla's APIs. This provides an excellent way for Salla Developers to stay up-to-date with the latest changes that are occurring on Salla.

### 👥 Community

[Salla Developer Community](https://t.me/salladev) is a vibrant and active community of developers who discuss topics around Salla Products such as Salla Partners, Salla APIs, Salla Open Source Projects, Twilight, and more. This space is found to connect with developers who are enthusiastic about creating amazing apps and themes as well as providing ultimate, end to end solutions to Salla Merchants. The [knowledgbase portal](https://salla.dev) is made for blogs and tutorials that target developers in using Salla Products. Be part of the community and join the Telegram group from [here](https://t.me/salladev).

---

