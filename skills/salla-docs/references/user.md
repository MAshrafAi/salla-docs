# User

## Table of Contents

- [user/Salla-Cart-Summary-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-cart-summary-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-Localization-Modal-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-localization-modal-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-Login-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-login-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-Loyalty-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-loyalty-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-Rating-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-rating-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-User-Menu-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-user-menu-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-User-Profile-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-user-profile-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-User-Settings-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-user-settings-salla-storefront-twilight-documentation-salla-docs)
- [user/Salla-Verify-Salla-Storefront-Twilight-Documentation-Salla-Docs](#user-salla-verify-salla-storefront-twilight-documentation-salla-docs)

---

## user/Salla-Cart-Summary-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Cart Summary

The `<salla-cart-summary>` web component is used to show the icon of the shopping cart with a small circle badge indicating the number of items in the cart.


## Example

<!--focus: false -->
![Cart Summary](https://cdn.salla.network/docs/twilight/6/js-web-cart-summary-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
  <!-- <!-- in case you want to use custom icon -->
 <!-- < i slot="icon" class="sicon-shopping-bag"></i> -->

```html
<!-- Basic Cart Summary component usage -->
<salla-cart-summary show-cart-label ="true"></salla-cart-summary>
```
    
  </Tab>
    
<Tab title="SASS">

This JS web component can be targeted for styling by its `.s-cart-summary` class. Following is a complete source code for customizing this component:

```css

.s-cart-summary{
  &-wrapper{

  }
  &-icon{

  }
  &-count{

  }
  &-total{
    
  }
}
```
      
  </Tab>    
</Tabs>


## Properties

| Property        | Attribute         | Description                             | Type                                                                             | Default     |
| --------------- | ----------------- | --------------------------------------- | -------------------------------------------------------------------------------- | ----------- |
| Show Cart Label |	`show-cart-label` |	Shows the cart label |	`boolean` |	`undefined` |


## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `animateToCart(image:any)` which animates the product images in the cart summary.


| Method                      | Description                                    | Return Type     |
| --------------------------- | ---------------------------------------------- | --------------- |
| `animateToCart(image: any)` | Animates the product Image in the cart summary | `Promise<void>` |

---

## user/Salla-Localization-Modal-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Localization

The `<salla-localization-modal>` web component shows the menu for the store's available languages and currencies. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component that shows the menu for the store's available languages and currencies, and that can be customized using the properties' parameters.




:::caution[Alert]
The `<salla-localization-modal>` **must not** be called more than once at the same page.
:::
 

:::tip[Note]
Available API Endpoints for the Localization component are:

- [Get Language](https://docs.salla.dev/doc-422614?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Currencies](https://docs.salla.dev/doc-422612#get-sdks-configurations)
- [List Currencies](https://docs.salla.dev/doc-422680?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Change Currency](https://docs.salla.dev/doc-422679?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::
## Example

<!--focus: false -->
![Localization](https://cdn.salla.network/docs/twilight/6/js-web-localization-01.gif)

<!-- <img src="https://cdn.salla.network/docs/twilight/6/js-web-localization-01.gif" width="100%"> -->

<!--
focus: false
-->

<!-- ![Localization Example](https://cdn.salla.network/docs/twilight/6/js-web-localization-01.gif) -->

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Button to open localization modal -->
<salla-button onclick="salla.event.emit(`localization::open`)">
  Currencies & languages
</salla-button>

<salla-localization-modal language="ar" currency="sa">
  <!-- you can customize the currency dom item -->
  <!-- <div slot="currency">{name} {currency} {country_code}</div>-->

  <!-- you can customize the language dom item -->
  <!-- <div slot="language">{name} {currency} {country_code}</div>-->
</salla-localization-modal>
```      
  </Tab>

   <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-localization-modal` class. Following is a complete source code for customizing this component:

```js

.s-localization-modal {
  &-title {

  }
  &-section {

  }
  &-section-inner {

  }
  &-item {

  }
  &-input {

  }
  &-label-slot {

  }
  &-label {

  }
  &-flag {

  }
  &-currency {

  }
  // dropdwon select, displys if the itmes length is more thant 5 items.
  &-select {

  }
}
```
      
  </Tab>  
    
</Tabs>



## Properties

| Property | Attribute  | Description                                                                    | Type     | Default                                    |
| -------- | ---------- | ------------------------------------------------------------------------------ | -------- | ------------------------------------------ |
| Language | `language` | Enabling the current localization attribute, either existing or newly selected | `string` | `'salla.config.get('user.language_code')'` |
| Currency | `currency` | Enabling the current currency attribute, either existing or newly selected     | `string` | `'salla.config.get('user.currency_code')'` |

## Methods
The pre-defined `methods` allow for calling to call functions built by Salla to carry out certain actvities, such as `close` / `open` the modal component or activating the action `submit`.


| Method     | Description                         | Return Type            |
| ---------- | ----------------------------------- | ---------------------- |
| `close()`  | Closes the localization's component | `Promise<HTMLElement>` |
| `open()`   | Opens the localization's component  | `Promise<boolean>` |
| `submit()` | Submits the language/currency data  | `Promise<void>`        |


## Slots
The `slots` makes it customizable to modify certain labels, such as `currency` & `language`, as well as adding `header` & `footer` extended features.


| Slot       | Description                                                                                    |
| ---------- | ---------------------------------------------------------------------------------------------- |
| `currency` | Replaces currency label with replaceable props which are `{name}`, `{code}`, `{country_code}`. |
| `language` | Replaces language label with replaceable props which are `{name}`, `{code}`, `{country_code}`. |
| `header`   | Replaces the top of the modal.                                                                 |
| `footer`   | Replaces the bottom of the modal.                                                              |

---

## user/Salla-Login-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Login

The `<salla-login-modal>` web component displays the login form, which prompts a user for their credentials in order to authenticate their access. It usually comprises of the standard username or email as well as a phone number. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component, and that can be customized using the properties' parameters available.

:::tip[Note]
Available API Endpoints for the Login component is:

- [Auth Login](https://docs.salla.dev/doc-422618?nav=01HNFTDZPB31Y2E120R84YXKCX)

:::

## Example

<!--
focus: false
-->

![Login Example](https://cdn.salla.network/docs/twilight/6/js-web-login-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Button to open the Login Component-->
<salla-button width="wide" onClick="salla.event.emit('login::open')">
  Login
</salla-button>

<salla-login-modal is-email-allowed is-email-required is-mobile-allowed>
  <!-- a slot show before login DOM via email .-->
  <!-- <div slot="before-login-email">-->
  <!-- </div>-->

  <!-- a slot show after login DOM via mobile .-->
  <!-- <div slot="after-login-mobile">-->
  <!-- </div>-->
</salla-login-modal>
```      
  </Tab>
<Tab title="SASS">

This JS web component can be targeted for styling by its `.s-login-modal` class. Following is a complete source code for customizing this component:

```js

.s-login-modal {
  &-sub-title {

  }
  &-main-btn {
    
  }
  &-main-btn-icon {

  }
  &-main-btn-text {

  }
  &-main-btn-arrow {

  }
  &-label {

  }
  &-input {

  }
  &-otp-input {

  }
  &-link {

  }
  &-error-message {

  }
  &-wrapper {

  }
  &-tab {

  }
  &-active {

  }
  &-unactive {

  }
}
```
      
  </Tab>    
</Tabs>



## Properties

| Property          | Attribute           | Description                           | Type      | Default     |
| ----------------- | ------------------- | ------------------------------------- | --------- | ----------- |
| Inline          | `inline`            | Display the login modal in an inline manner                                                                                      | `boolean` | `undefined` |
| Is Email Allowed  | `is-email-allowed`  | Granting email input by the merchant  | `boolean` | `undefined` |
| Is Email Required | `is-email-required` | Requiring email input by the merchant | `boolean` | `false` |
| Is Mobile Allowed | `is-mobile-allowed` | Granting mobile input by the merchant. Outside KSA is set to `false` by default | `boolean` | `true` |
| Support Web Authentication | `support-web-auth` | Once the API verifyies the success of the process, it will login the customer in web pages. | `boolean` | `true` |
| Without Reload   | `without-reload`    | Render reloading of the page after a successful login                                                                               | `boolean` | `false`     |

## Methods
The pre-defined `methods` allow for calling the function built by Salla which is `open` to display the Login Component.


| Method   | Description                 | Return Type            |
| -------- | --------------------------- | ---------------------- |
| `open(event?: any)` | Opens the login's component | `Promise<HTMLElement>` |


## Slots

The`slots` makes it customizable to modify certain labels, such as `before-login-email` & `after-registeration`, as well as adding `footer` extended feature.

| Slot                  | Description                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| `before-login-email`  | Shows content before the login with email screen has appeared            |
| `before-login-mobile` | Shows content before the mobile with mobile screen has appeared          |
| `before-login-type`   | Shows content before the login types has been listed in the login screen |
| `before-registration` | Shows content before user registers                                      |
| `after-login-email`   | Shows content after the login with email screen has appeared             |
| `after-login-mobile`  | Shows content after the login with mobile screen has appeared            |
| `after-login-type`    | Shows content after the login types has been listed in the login screen  |
| `after-registration ` | Shows content after user registers                                       |
| `footer`              | Shows content at the modal's footer                                      |

---

## user/Salla-Loyalty-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Loyalty

The `<salla-loyalty>` web component is used to display a popup that represents the Loyalty program. This program enables the store's customers to benefit from collecting the points for vouchers and offers provided by the store. Once they have collected enough points, the customers will be eligible to redeem them for exciting gifts or products.

It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component, and that can be customized using the properties' parameters available.

:::tip[Note]
Available API Endpoints for the Loyalty component are:

- [Get Program](https://docs.salla.dev/doc-422667?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Reset](https://docs.salla.dev/doc-422669?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Exchange](https://docs.salla.dev/doc-422668?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::

## Example

<!--focus: false -->
![Loyalty Image](https://cdn.salla.network/docs/twilight/6/js-web-loyalty-01.png)

## Usage

<Tabs>
  <Tab title="HTML">

 ```html
<!-- Show button as widget to activate the modal -->
<salla-loyalty customer-points="1000">
  <salla-button slot="widget" onclick="salla.event.dispatch('loyalty::open')">
    Exchange
  </salla-button>
</salla-loyalty>

<!-- Show default widget to exchange the points -->
<salla-loyalty
 customer-points="1000"
 prize-points="10"
 prize-title="Discount Coupon (percentage amount): 10%">
</salla-loyalty>
```      
  </Tab>
  
</Tabs>

## Properties


| Property        | Attribute         | Description                                             | Type               | Default     |
| --------------- | ----------------- | ------------------------------------------------------- | ------------------ | ----------- |
| Customer Points | `customer-points` | Available customer points with which they can exchange. | `number`           | `undefined` |
| Guest Message   | `guest-message`   | Message to show for guest users.                        | `string`           | `undefined` |
| Prize Points    | `prize-points`    | The exchanged prize point.                              | `number \| string` | `undefined` |
| Prize Title     | `prize-title`     | The exchangable prize title.                            | `string`           | `undefined` |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `open` and `close` the Loyalty modal.


| Method                   | Description                                           | Return Type            |
| ------------------------ | ----------------------------------------------------- | ---------------------- |
| `open()`                 | Shows loyalty modal                                   | `Promise<any>`         |
| `close()`                | Hides loyalty modal                                   | `Promise<HTMLElement>` |
| `exchangeLoyaltyPoint()` | Exchanges loyalty points with the selected prize item | `Promise<any>`         |
| `resetExchange()`        | Cancels exchanged prizes                              | `Promise<any>`         |

---

## user/Salla-Rating-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Rating

The `<salla-rating-modal>` web component is used to display the rating scale for a store, product, or shipping company. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component, and that can be customized using the properties' parameters available.


## Example

<!--
focus: false
-->

![Rating Example](https://cdn.salla.network/docs/twilight/6/js-web-rating-01.gif)


## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Button to activate-->
<salla-button onclick="salla.event.dispatch(`rating::open`)">Open Rating</salla-button>

<!-- Show Rating Modal-->
<salla-rating-modal order-id="14643439"></salla-rating-modal>
```      
  </Tab>

   <Tab title="SASS">
  
This JS web component can be targeted for styling by its `.s-rating-modal` class. Following is a complete source code for customizing this component:

```css

.s-rating-modal {
  &-wrapper {

  }
  &-footer {

  }
  &-btn {

  }
  &-dots {

  }
  &-step-dot {

  }
  &-step {

  }
  &-active {

  }
  &-unactive {

  }
  &-hidden {

  }
  &-unvisiable {

  }
  &-step-wrap {

  }
  &-product-details {

  }
  &-rounded-icon {

  }
  &-title {

  }
  &-store-logo {

  }
  &-shipping-logo {

  }
  &-shipping-icon {

  }
  &-comment {

  }
  &-validation-msg {

  }
  &-product {

  }
  &-product-img {
    
  }
  &-product-title {

  }
  &-thanks {

  }
  &-icon {

  }
  &-thanks-msg {

  }
  &-thanks-btn {

  }
  &-thanks-time {

  }
  &-btn-star {

  }
  &-btn-star-large {

  }
  &-btn-star-small {

  }
  &-hovered {

  }
  &-selected {

  }
  &-stars-company {

  }
  &-stars-product {

  }
  &-bg-gray {

  }
  &-bg-primary {

  }
} 
```

    
  </Tab>  
</Tabs>



## Properties

| Property | Attribute  | Description                         | Type     | Default                       |
| -------- | ---------- | ----------------------------------- | -------- | ----------------------------- |
| Order ID | `order-id` | The Order ID as an input for rating | `number` | `'salla.config.get('page.id')'` |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `open` and/or `close` the Rating Component.

| Method   | Description                | Return Type             |
| -------- | -------------------------- | ----------------------- |
| `close()` | Closes the rating component | `Promise<HTMLElement>`  |
| `open()` | Opens the rating component | `Promise<NodeJS.Timeout>` |


:::tip[Tip]
 To use a method, you can for instance `open` the component via the event:

 ```html
 onclick="salla.event.dispatch(`rating::open`)"
 ```
 and `close` the component via the event:
 ```html
 onclick="salla.event.dispatch(`rating::close`)"
 ```
:::

---

## user/Salla-User-Menu-Salla-Storefront-Twilight-Documentation-Salla-Docs

# User Menu

The `<salla-user-menu>` web component is used to show a navigation menu list with links that route users to accomplish user-related functions including Login, Logout, Profile, Sign Up, and more.

## Example

<!--focus: false -->

![User Menu](https://cdn.salla.network/docs/twilight/6/js-web-user-menu-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
      
 ```html
<!-- Basic User Menu component usage -->
<salla-user-menu
  inline="true"
  show-header="true">
</salla-user-menu>
```     
  </Tab>

   <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-user-menu` class. Following is a complete source code for customizing this component:

```css
.s-user-menu{
  &-wrapper{

  }
  &-toggler{

  }
  // Default trigger
  &-trigger{
    &-avatar{

    }
    &-content{

    }
    &-hello{

    }
    &-name{

    }
    &-icon{

    }
  }
  // Your custom trigger
  &-trigger-slot{

  }
  &-dropdown{
    &-header{
      img{

      }
      &-content{

      }
      &-close{

      }
    }
    &-list{

    }
    &-item{
      &-title{

      }
      &-badge{

      }
    }

  }
  &-inline{
    
  }
}
```
      
  </Tab>  
</Tabs>


## Properties

| Property          | Attribute           | Description                                                             | Type      | Default |
| ----------------- | ------------------- | ----------------------------------------------------------------------- | --------- | ------- |
| Avatar Only       | `avatar-only`       | Whether or not to display the trigger as only an avatar                 | `boolean` | `false` |
| Inline            | `inline`            | Whether or not to show only the list without the dropdown functionality | `boolean` | `false` |
| Relative Dropdown | `relative-dropdown` | Whether or not to make the dropdown menu relative to parent element     | `boolean` | `false` |
| Show Header       | `show-header`       | Whether or not to present the dropdown header in mobile sheet           | `boolean` | `false` |

## Slots
The `slots` makes it customizable to modify certain labels, such as `trigger`.

| Slot        | Description                                                                                                    |
| ----------- | -------------------------------------------------------------------------------------------------------------- |
| `trigger` | Replaces the trigger widget label with replaceable props which are `{avatar}`, `{hello}`, `{first_name}`, `{last_name}`, `{icon}`. |

---

## user/Salla-User-Profile-Salla-Storefront-Twilight-Documentation-Salla-Docs

# User Profile

This `<salla-user-profile>` web component allows the user to display the user information, this can be customised to display information such as Name, Email, Phone Number. 


## Example

<!--
focus: false
-->

![User Profile Component](https://cdn.salla.network/docs/twilight/6/js-web-user-profile-01.png)

## Usage


<Tabs>
  <Tab title="HTML">
  ```html
<salla-user-profile
    custom-fields='[
        {
            "id": 743827961,
            "label": "Experience",
            "description": "",
            "type": "text",
            "required": 0,
            "value": null
        }, {
            "id": 2117208314,
            "label": "Age",
            "description": "",
            "type": "number",
            "required": 1,
            "value": null
        }, {
            "id": 1209997307,
            "label": "Friends Picture",
            "description": "",
            "type": "photo",
            "required": 0,
            "value": null
        }, {
            "id": 635713220,
            "label": "Multi Uploader",
            "description": "Please select multiple file",
            "type": "photo",
            "required": 1,
            "value": null
        }        
    ]'>
</salla-user-profile>
```
  </Tab>
  <Tab title="SASS">
 This JS web component can be targeted for styling by its `:host` class. Following is a complete source code for customizing this component:

```js
:host {
  display: block;
}
```
  </Tab>
  
</Tabs>


<!--
type: tab
title: TWIG
-->




<!--
type: tab
title: SASS
-->



<!-- type: tab-end -->


## Properties

| Property | Attribute | Description | Type    | Default |
| -------- | --------- | ----------- | ------- | ------- |
| Custom Fields    | `custom-fields`    | Custome fields that can be rendered in addition to the default ones.        | `string` | `undefined` |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `setCustomFields(fields:CustomField[])`which sets custom fields for the component.

| Method | Description | Return Type |
| ------ | ----------- | ----------- |
| `setCustomFields(fields: CustomField[])`    | Sets custom fields for the component. Can be useful for non HTML usage.        | `Promise<void>`          |

---

## user/Salla-User-Settings-Salla-Storefront-Twilight-Documentation-Salla-Docs

# User Settings

The `<salla-user-settings>` web component allows the user to manage their account settings such as enabling notifications and closing accounts, and that can be customized using the properties' parameters available.

:::tip[Note]
Available API Endpoints for the User Settings component is:

- [Update Settings](https://docs.salla.dev/doc-422685?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::

## Example

<!--focus: false -->
![User Settings](https://cdn.salla.network/docs/twilight/6/js-web-user-settings-01.png)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Basic User Settings component usage -->
<salla-user-settings
  is-notifiable="true">
</salla-user-settings>
```      
  </Tab>

<Tab title="SASS">

This JS web component can be targeted for styling by its `.s-user-settings` class. Following is a complete source code for customizing this component:

```css
.s-user-settings{
  &-wrapper{

  }
  &-section{

  }
  &-title{

  }
  &-subtitle{

  }
  &-action{
    
  }
}
```
      
  </Tab>  
    
</Tabs>



## Properties

| Property       | Attribute       | Description                                            | Type      | Default |
| -------------- | --------------- | ------------------------------------------------------ | --------- | ------- |
| Is Notifiable | `is-notifiable` | Value used for handling notification toggle check box. | `boolean` | `false` |

---

## user/Salla-Verify-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Verify

The `<salla-verify>` web component used to show fields for verifying email/mobile of users by sending OTP verification code during registration, [login](https://docs.salla.dev/doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD), or profile update, and that can be done using the properties' parameters available.

:::tip[Note]
Available API Endpoints for the Verify component are:

- [Auth Verification](https://docs.salla.dev/doc-422620?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Contact Verification](https://docs.salla.dev/doc-422686?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::


## Example

<!--
focus: false
-->

![Verify Example](https://cdn.salla.network/docs/twilight/6/js-web-verify-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- render it as modal and will show via open method or event -->
<salla-verify></salla-verify>

<!-- render it as inline dom to show otp collect form -->
<salla-verify display="inline"></salla-verify>
```      
  </Tab>

   <Tab title="JS">
      
```js
var verifyComponent = document.querySelector("salla-verify");

verifyComponent.addEventListener("verified", function (response) {
    console.log('otp verified');
});
```
  </Tab>  
    
   <Tab title="SASS">
  
This JS web component can be targeted for styling by its `.s-verify` class. Following is a complete source code for customizing this component:

```css

.s-verify {
  &-host{
    
  }
  &-message {

  }
  &-label {

  }
  &-codes {

  }
  &-input {

  }
  &-footer {

  }
  &-submit {

  }
  &-resend-message {

  }
  &-timer {

  }
  &-resend {

  }
  &-back {
    
  }
}
```  
  </Tab>  
</Tabs>



## Properties

| Property    | Attribute     | Description                                               | Type                 | Default   |
| ----------- | ------------- | --------------------------------------------------------- | -------------------- | --------- |
| Auto Reload | `auto-reload` | Should auto reloading the page after success verification. | `boolean`            | `'true'`  |
| Display     | `display`     | Should render component without modal                     | `"inline" \| "modal"` | `'modal'` |
| Support Web Authentication     | `support-web-auth`     | Once the API verifies the success. It will login the customer in web pages                     | `boolean` | `true` |
| Type          | `type`          | Verifying method                                          | `"email" \| "mobile"`   | `'mobile'`   |

## Events

| Event      | Description                     | Type               |
| ---------- | ------------------------------- | ------------------ |
| `verified` | This is triggered when success verification event is fired. | `CustomEvent<any>` |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `getCode` which gets the current code and `open(data:any)` which shows the verifying as modal.

| Method   | Description                                  | Return Type            |
| -------- | -------------------------------------------- | ---------------------- |
| `getCode()`   | Gets the current code. | `Promise<string>` |
| `open(data: any)`   | Shows the verifying as modal. | `Promise<void>` |

## Slots
The `slots` makes it customizable to modify certain labels, such as `after-footer`.

| Slot             | Description                                                                   |
| ---------------- | ----------------------------------------------------------------------------- |
| `after-footer` |Placeholder position that appears after the footer.                                                          |
| `footer`       | Replaces the footer. By default, it contains: `verify button`, `resend`, and `timer`. |

---

