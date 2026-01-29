# Learn What You'Ll Learn  Additional Resources

## Table of Contents

- [📙-what-you'll-learn/Additional-Resources](#📙-what-you'll-learn-additional-resources)
- [📙-what-you'll-learn/Apps-Command](#📙-what-you'll-learn-apps-command)
- [📙-what-you'll-learn/Auth](#📙-what-you'll-learn-auth)
- [📙-what-you'll-learn/Booking](#📙-what-you'll-learn-booking)
- [📙-what-you'll-learn/Cart](#📙-what-you'll-learn-cart)
- [📙-what-you'll-learn/Change-Log](#📙-what-you'll-learn-change-log)
- [📙-what-you'll-learn/Comment](#📙-what-you'll-learn-comment)
- [📙-what-you'll-learn/Component](#📙-what-you'll-learn-component)
- [📙-what-you'll-learn/Currency](#📙-what-you'll-learn-currency)
- [📙-what-you'll-learn/Customize-Twilight-Web-Components-–-Theme-Components-Customization-Tailwind-Theming-Guide-Salla-Stor](#📙-what-you'll-learn-customize-twilight-web-components-–-theme-components-customization-tailwind-theming-guide-salla-stor)

---

## 📙-what-you'll-learn/Additional-Resources

# Additional Resources

## Docs

- [Upgrade and Version](https://docs.salla.dev/422763m0.md): As a part of maintaining a good performance for the Apps and Themes in Salla, the developers continuously enhance their products with new features that require updating. This article shows the commands that the developer can use to perform the upgrade and check the current version of Salla CLI.
- [Troubleshooting](https://docs.salla.dev/422765m0.md): In the course of using the Salla CLI, you may encounter various issues or error messages. These can stem from a variety of causes, from minor misconfigurations to deeper problems requiring more thorough investigation. This section presents a range of common errors and their corresponding troubleshooting steps to guide you in resolving these issues efficiently. Remember, each problem is an opportunity to better understand the workings of the Salla CLI.

---

## 📙-what-you'll-learn/Apps-Command

# Apps Command

## Docs

- [Overview](https://docs.salla.dev/422767m0.md): This section is about Salla Apps commands. In this overview, developers can find a brief guide to the commands [Salla CLI](https://github.com/SallaApp/Salla-CLI#:~:text=version%20with%20this-,command,-%3A) made for the Apps.
- [Create  App](https://docs.salla.dev/422768m0.md): Developers create [Salla Apps](https://salla.partners/), which are primarily used in [Salla stores](https://salla.sa) to provide functionality and other services. This article demonstrates how to use the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `salla app create` to create Salla Apps.
- [Create Webhook](https://docs.salla.dev/422769m0.md): Webhook simplifies the way Apps communicate with each other, as it is triggered by an event in a source system. For instance, a Salla Merchant Store and / or Salla Apps Store sends the data payload to a destination system, for example the Developer's App.
- [Delete](https://docs.salla.dev/422770m0.md): Using [Salla CLI](https://github.com/SallaApp/Salla-CLI) commands, developers can quickly delete the apps they created. This article explains how to delete an app using the command `salla app delete`.
- [Link](https://docs.salla.dev/422771m0.md): Developers can link an App with their Salla Partners account to manage the Apps that they created. The developer can use the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command to link a local app to the Partners account.
- [List and Info](https://docs.salla.dev/422772m0.md): Salla's skilled developers are continuously creating amazing Apps for Salla. To keep track and check the Apps created by the developers, they can easily use the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `salla app list` to display the Apps associated with their [Salla Parnters](https://salla.partners/) account, as explained later in this article.
- [Serve](https://docs.salla.dev/422773m0.md): Developers can test the App and get the Apps information such as Remote URL, Local URL, Webhook URL, and OAuth Callback URL. `Salla app serve` command can be accessed via the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command. Read this article to learn more about the `serve`.

---

## 📙-what-you'll-learn/Auth

# Auth

## Docs

- [Login](https://docs.salla.dev/422618m0.md): In general, the authentication API allows a developer to control all aspects of a user's identity. It has endpoints for logging in, logging out, and using APIs, among other things. This *login* endpoint is used to authenticate a user. Either the email or the phone number can be used as a login identifier, which means that the user has two *types* of login process, `email` and `phone`. 
- [Logout](https://docs.salla.dev/422619m0.md): This logout endpoint terminates the current session. As a result, the customer's authentication will be terminated, and it will be required to obtain a new access token in order to make further API calls.
- [Verify](https://docs.salla.dev/422620m0.md): This endpoint handles the customer's access code verification. It sends the entered access code to the backend and waits for the response. In the case of receiving a positive response, it helps by directing the customer to the store's home page. Otherwise, if the verification process fails, it informs the customer to re-send the correct access code.
- [Resend](https://docs.salla.dev/422621m0.md): This `resend` endpoint is simply to re-send the access code to the customer if it was not received correctly. The customer is given 30 seconds to enter the received access code, so if there was an issue with receiving the access code, another new code may be re-sent.
- [Register](https://docs.salla.dev/422623m0.md): The customer registration endpoint creates a customer account in the merchant's store. A registration request must provide the customer main information such as *first name, email, phone*, and more. Additionally, the login verification type should be stored in *verfied_by* field, so that later the verification *code* will be sent to that verification type.
- [Refresh](https://docs.salla.dev/422624m0.md): To make the customer's login process easier, the store may use an access token to keep the client logged in for a period of time. Access tokens, on the other hand, may only be valid for a short amount of time for security reasons. A refresh token is used to "refresh" the access token once it has expired. This endpoint refresh token allows a client to receive new access tokens without requiring them to log in again.

---

## 📙-what-you'll-learn/Booking

# Booking

## Docs

- [Add](https://docs.salla.dev/422687m0.md): This endpoint is a feature provided by an online Salla Store that allows customers to book a product as a service. This endpoint handles requests to add a new booking for a specific product/service, and creates a booking record in the store's database that includes relevant details. The endpoint streamlines the booking process for customers and store administrators, and provides a convenient way to book products as services.

---

## 📙-what-you'll-learn/Cart

# Cart

## Docs

- [Latest](https://docs.salla.dev/422625m0.md): This endpoint fetches the last cart created by the customer. In other words, the cart will be fetched based on the latest products.
- [Details](https://docs.salla.dev/422626m0.md): This endpoint displays an Cart's details for the customer, The cart's items will be listed here along with their details.
- [Quick Add](https://docs.salla.dev/422628m0.md): The `quickAdd` endpoint enables the customer to add a product directly from the products list to the cart without the need to open that product page. Under the hood, this endpoint calls the [`addItem`](https://docs.salla.dev/doc-422629?nav=01HNFTDZPB31Y2E120R84YXKCX) endpoint by passing the id of the product which will be added to the cart.
- [Add Item](https://docs.salla.dev/422629m0.md): This `addItem` endpoint adds an item from the merchant's store to the customer's shopping cart. The customer may select the item, type in the quantity he wants to order, and click on the "add to cart" button. This sends the product to the shopping cart, and then the customer may continue to shop for other items.
- [Delete Item](https://docs.salla.dev/422630m0.md): This endpoint removes an item from the customer's shopping cart. The customer may remove an item by clicking on the "remove from to cart" button. 
- [Delete Image](https://docs.salla.dev/422632m0.md): This endpoint removes an image file attached to an item already added to the cart by the customer.
- [Add Coupon](https://docs.salla.dev/422633m0.md): A coupon is a code that consists of a special series of characters, or string, used by customers to get a discounted price or limited offer on the cart's items. This *add* endpoint is used for this purpose.
- [Remove Coupon](https://docs.salla.dev/422634m0.md): A coupon is a code can be removed by customers, this  will revert any added discounted price or limited offer on the cart's items. This *remove* endpoint is used for this purpose.
- [Get Upload Image](https://docs.salla.dev/422635m0.md): This endpoint allows the user to add an image file to the cart in the case that the user needs to attach an image to the order it is placing through the shopping cart.
- [Get Quick Order Settings](https://docs.salla.dev/422636m0.md): The Get Quick Order Settings endpoint retrieves the configuration settings for a merchant's quick order feature, including the title, sub-title, thanks message, order button text, email requirement, agreement requirement, allowed countries, custom styling options, confirmation button text, and the agreement text. These settings determine the behavior and appearance of the quick order feature on the merchant's store.
- [Create Quick Order](https://docs.salla.dev/422637m0.md): This endpoint enables the user to select particular items, complete the purchase of that item, and then proceed directly to the checkout page to complete the purchase without having to complete any intermediary stages.
- [Order Status](https://docs.salla.dev/422638m0.md): This endpoint returns the current status of a cart, including whether it is active or not, and the next step to take. The next step can be either to refresh the cart, prompt the user to login, or proceed to checkout, and may include an optional URL. This endpoint is used for monitoring and managing the status of a cart during the checkout process.
- [Get Current Cart Id](https://docs.salla.dev/422639m0.md): This endpoint returns the unique identifier (ID) of the current cart associated with a particular user or session. It is used to retrieve the current cart ID, which is typically required for other cart-related operations such as adding or removing items from the cart, checking out, or retrieving cart details.
- [Price Quote](https://docs.salla.dev/422640m0.md): The priceQuote endpoint calculates and returns a price quote for the items in a cart. This endpoint takes into account any discounts, taxes, shipping costs, and other factors that may affect the final price, and returns the calculated price along with a breakdown of the individual costs. The price quote can be used to inform the user of the total cost of their purchase and to facilitate the checkout process.

---

## 📙-what-you'll-learn/Change-Log

# Change Log


In this page, you will find all about Salla Twilight Theme Engine frequent updates, bug fixes, and more. We will be displaying both the unreleased and released updates on [Salla's Documentation](https://docs.salla.dev/) 

:::check[Telegram Community]
Join the Global Salla Developers community on [Telegram](https://t.me/salladev) for any inquiries about the Twilight engine.
:::


<Accordion title="🛠️ Developer Action Items" defaultOpen>
Each Twilight release includes different action items for developers, which vary by update. These items guide developers on what they should do to stay compatible and improve functionality with the latest release:

| Action Item             | Description                                                         |
|-------------------------|-------------------------------------------------------------------|
| No Action Required      | Developers do not need to make any changes.                        |
| Rebuild Assets          | Developers should rebuild assets with the latest package version.  |
| Modify Existing Code    | Developers are required to update their current implementations.    |
| Leverage New Feature    | Developers can utilize or benefit from new functionalities.         |
| Check Documentation     | Developers are advised to check the documentation for new feature details. |
| Apply Configuration Changes | Developers must modify configuration settings accordingly.    |
| Refactor Code           | Developers may need to revise existing code to align with updates.  |
| Update API Calls        | Developers should update any affected API calls.                   |
</Accordion>

:::note[]
The format of this page is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
:::

## [2.14.317] - 17-12-2025
### Added
New Twilight Version `2.14.317` is released, which includes:
- Handling special characters to unify campaign with special chars, with proper error handling for decode failures
    - **🛠️ Developer Actions:**
        - No Action Required.

## [2.14.316] - 17-12-2025
### Added
New Twilight Version `2.14.316` is released, which includes:
- Changes on Themes Components Bundles:
    - Hide individual sub-product prices in the bundle order details view.
    - Added a `cart_item_id` field to the products array in the Cart Viewed analytics event, enabling tracking of individual cart items.
    - Sub-product titles now support clickable actions for improved interactivity. 
        - **🛠️ Developer Actions:**
            - No Action Required.

## [2.14.314] - 14-12-2025
### Added
New Twilight Version `2.14.314` is released, which includes:
- Realtime context is added to analytics by introducing a new `attachRealtimeContext()` method that consolidates realtime data attachment logic.
     - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.313] - 09-12-2025
### Added
New Twilight Version `2.14.313` is released, which includes:
- Moved profile URL construction to a reusable buildProfileUrl(token) method.
     - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.312] - 07-12-2025
### Added
New Twilight Version `2.14.312` is released, which includes:
- Support Salla hooks allowing partners to inject content into specific theme slots.
     - **🛠️ Developer Actions:**
       - No Action Required.


## [2.14.306] - 29-11-2025
### Added
New Twilight Version `2.14.306` is released, which includes:
- Fixed Issues when visiting store from campaigns with Arabic names
     - **🛠️ Developer Actions:**
        - No Action Required.


## [2.14.304] - 27-11-2025
### Added
New Twilight Version `2.14.304` is released, which includes:
- Updated the fallback analytics host URL from https://www.salla.cloud/_app/e to https://salla.cloud/_app/e, removing the www subdomain.
     - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.301] - 26-11-2025
### Added
New Twilight Version `2.14.301` is released, which includes:
- Fixed pagination flicker in the bundle product slider by adding explicit CSS display and sizing rules to prevent layout shifts during Swiper initialization
     - **🛠️ Developer Actions:**
         - No Action Required.

## [2.14.302] - 26-11-2025
### Added
New Twilight Version `2.14.302` is released, which includes:
- Update WhatsApp contact links to open chats directly with each store number via wa.me, so customers jump straight into a conversation.
     - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.299] - 25-11-2025
### Added
New Twilight Version `2.14.299` is released, which includes:
- Simplified profile link logic in salla-user-menu JS Web Component
  to return the external profile URL only when Salla Account is enabled

    - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.295] - 23-11-2025
### Added
New Twilight Version `2.14.295` is released, which includes:
- Fixed ad display logic: removed reliance on localStorage so ads now appear in the theme editor, and updated banner handling to show all ads (using filter instead of find).

    - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.300] - 25-11-2025
### Added
New Twilight Version `2.14.300` is released, which includes:
- Fixed user menu icon in [salla-user-menu](https://docs.salla.dev/422740m0) JS Web Component .

    - **🛠️ Developer Actions:**
       - No Action Required.


## [2.14.295] - 23-11-2025
### Added
New Twilight Version `2.14.295` is released, which includes:
- In `Salla-product-options` Apple Pay API check (hasApplePay()) is replaced with a new user agent-based detection method (isAppleDevice()) for handling paste events in RTL inputs.

    - **🛠️ Developer Actions:**
       - No Action Required.



## [2.14.294] - 20-11-2025
### Added
New Twilight Version `2.14.294` is released, which includes:
- Set Cart for status request to fix a bug and restore essential e-commerce functionality with a more efficient implementation.
    - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.293] - 20-11-2025
### Added
New Twilight Version `2.14.293` is released, which includes:
-  Cart assignment deduplication after user login to prevent multiple concurrent assignment requests. The changes introduce a `guestCartAssigned` flag and refactor the cart assignment flow in  [`salla-login`](https://docs.salla.dev/422711m0) modal.
    - **🛠️ Developer Actions:**
       - No Action Required.


## [2.14.292] - 19-11-2025
### Added
New Twilight Version `2.14.292` is released, which includes:
- Fix bundle accordion expand.
    - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.291] - 17-11-2025
### Added
New Twilight Version `2.14.291` is released, which includes:
- Fixed [`salla-login`](https://docs.salla.dev/422711m0) modal API path, added safeguards for cart assignment (`guestCartAssigned`, `pendingAssignRequest`, `withAssign`), and enhanced error logging.
- Added the route to apple pay shipping method
- Enhanced order details refund status
    - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.290] - 13-11-2025
### Added
New Twilight Version `2.14.290` is released, which includes:
- UI adjustments for the Arabian Oud theme by modifying Tailwind CSS utility 
    - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.289] - 13-11-2025
### Added
New Twilight Version `2.14.289` is released, which includes:
- Push change event on paste in [`salla-product-options`](https://docs.salla.dev/422720m0) JS Web Component.
   - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.288] - 12-11-2025
### Added
New Twilight Version `2.14.288` is released, which includes:
- Resolved an issue with Text options not triggering the onChange event in [`salla-product-options`](https://docs.salla.dev/422720m0) JS Web Component during paste actions on iOS Safari and Chrome browsers.
   - **🛠️ Developer Actions:**
       - No Action Required.

<!--
 
## [2.14.278] - 11-11-2025
### Added
New Twilight Version `2.14.278` is released, which includes:
- Added requirement for theme developers to include the `salla-trust-badges` component in the footer section to ensure trust elements are displayed consistently.

    - **🛠️ Developer Actions:**
    - No Action Required.
-->

## [2.14.282] - 30-10-2025
### Added 
New Twilight Version `2.14.277` is released, which includes:
- Prevent app install alert from showing when running inside the mobile app.
- Added createFormDataWrapper to cart API for unified handling of cart payloads (objects and FormData) in `salla-cart` JS Web Components.
   - **🛠️ Developer Actions:**
       - No Action Required.


## [2.14.279] - 27-10-2025
### Added 
New Twilight Version `2.14.277` is released, which includes:
- Fixing copy/paste protection to allow normal input in form fields while keeping store content protected.
   - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.277] - 27-10-2025
### Added 
New Twilight Version `2.14.277` is released, which includes:
- Loading is added to to [`salla-bottom-alert`](https://docs.salla.dev/422693m0).
   - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.277] - 27-10-2025
### Added 
New Twilight Version `2.14.277` is released, which includes:
- Update salla bottom alert component for Ready stores for an enhanced view in desktop and mobile view.
   - **🛠️ Developer Actions:**
       - No Action Required.


## [2.14.276] - 26-10-2025
### Added 
New Twilight Version `2.14.276` is released, which includes:
- Fixing cart product option in [`salla-conditional-fields`](https://docs.salla.dev/422699m0) and [`salla-product-options`](https://docs.salla.dev/422720m0) JS Web Components.
   - **🛠️ Developer Actions:**
       - No Action Required.

## [2.14.275] - 22-10-2025
### Added 
New Twilight Version `2.14.275` is released, which includes:
- Enahnced cookies capturing
- Mobile paste support for text input is added in [`salla-conditional-fields`](https://docs.salla.dev/422699m0) and [`salla-product-options`](https://docs.salla.dev/422720m0) JS Web Components.

   - **🛠️ Developer Actions:**
       - No Action Required.


## [2.14.273] - 21-10-2025
### Added 
New Twilight Version `2.14.273` is released, which includes:

- Supporting multiple bundle product types in the following JS Web Components:
    - `salla-accordion` 
    - [`salla-add-product-button`](https://docs.salla.dev/doc-422692)
    - [`salla-button`](https://docs.salla.dev/422694m0)
    - [`salla-modal`](https://docs.salla.dev/422714m0)
    - `salla-multiple-bundle-product`
    - [`salla-product-option`](https://docs.salla.dev/422720m0)
    - [`salla-skeleton`](https://docs.salla.dev/422734m0)
    - [`salla-slider`](https://docs.salla.dev/422735m0)
- Comments sorting on the product page issues resolved in [`salla-comments`](https://docs.salla.dev/482455m0) JS Web Component.
- Mobile paste for text inputs is now supported in [`salla-conditional-fields`](https://docs.salla.dev/422699m0) JS Web Component.

## [2.14.253] - 06-10-2025
### Added 
New Twilight Version `2.14.253` is released, which includes:
- Supporting new order details in the following JS Web Components:
    - salla-accordion
    - [`salla-button`](https://docs.salla.dev/422694m0)
    - [`salla-map`](https://docs.salla.dev/422713m0)
    - salla-order-details
        - **🛠️ Developer Actions:**
            - No Action Required.

## [2.14.252] - 05-10-2025
### Added 
New Twilight Version `2.14.252` is released, which includes:
- Enhanced Cart and simplify sync flow in [`cart api`](https://docs.salla.dev/433812m0).
    - **🛠️ Developer Actions:**
        - No Action Required.

## [2.14.251] - 05-10-2025
### Added 
New Twilight Version `2.14.251` is released, which includes:
- Enhancement on automating price initialization in [`salla-product-option`](https://docs.salla.dev/422720m0) JS Web Component. 
        - **🛠️ Developer Actions:**
            - No Action Required.

## [2.14.250] - 02-10-2025
### Added 
New Twilight Version `2.14.250` is released, which includes:
- Enhancement on reliability and consistency of custom tracker events to send partners events in parallel.
    - **🛠️ Developer Actions:**
        - No Action Required.

## [2.14.248] - 02-10-2025
### Added 
New Twilight Version `2.14.248` is released, which includes:
- Fixed infinite history scroll option in [`salla-comments`](https://docs.salla.dev/482455m0) JS Web Component.
    - **🛠️ Developer Actions:**
        - No Action Required

## [2.14.242] - 27-09-2025
### Added 
New Twilight Version `2.14.242` is released, which includes:
- Loyalty program is hidden when disabled in [`salla-user-menu`](https://docs.salla.dev/422740m0) JS Web Component.
    - **🛠️ Developer Actions:**
        - No Action Required.

## [2.14.141] - 27-09-2025
### Added
New Twilight Version `2.14.141` is released, which includes:
- Enhance cart update to fetch and apply dynamic offer data in `salla-tiered-offer` JS Web Component.
- Fix adding extra content when pasting on iOS 26 in [`salla-product-option`](https://docs.salla.dev/422720m0) JS Web Component. 
    - Must enable protect content option on themes settings
        - **🛠️ Developer Actions:**
            - No Action Required.

## [2.14.196] - 20-08-2025
### Added
- New Twilight Version `2.14.196` is released, which includes:
    - Avoid directly identifying the user by attaching the user information as context (traits) without performing an explicit user identification, which occurs using `setContextProperty('traits', config.user)`.
    - Enhance the [`salla-metadata`](https://docs.salla.dev/464599m0) JS Web Component with a cleaner async/await version that uses built-in `salla.api.metadata.fetchValues` and logs errors instead of throwing them.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.194] - 19-08-2025
### Added
- New Twilight Version `2.14.194` is released, which includes:
    - Fix metadata to show new URLs in the [`salla-metadata`](https://docs.salla.dev/464599m0) JS Web Component.
    - Added checkout promotion when clicked or viewed as tracking events in the [`salla-offer-modal`](https://docs.salla.dev/422715m0) JS Web Component
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.192] - 18-08-2025
### Added
- New Twilight Version `2.14.192` is released, which includes:
    - Support store details side sheet in the [`salla-bottom-alert`](https://docs.salla.dev/422693m0), [`salla-loading`](https://docs.salla.dev/422709m0), [`salla-modal`](https://docs.salla.dev/422714m0), and [`salla-slider`](https://docs.salla.dev/422735m0) JS Web Components
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.189] - 12-08-2025
### Added
- New Twilight Version `2.14.189` is released, which includes:
    - Apple pay issues fixed in the [`salla-quick-buy`](https://docs.salla.dev/422725m0) JS Web Component
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.188] - 11-08-2025
### Added
- New Twilight Version `2.14.188` is released, which includes:
    - Support browsing multi market in the [`salla-scopes`](https://docs.salla.dev/422729m0) JS Web Component
    - Apple Pay amount and currency issues fixed in the [`salla-quick-buy`](https://docs.salla.dev/422725m0) JS Web Component
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.187] - 10-08-2025
### Added
- New Twilight Version `2.14.187` is released, which includes:
  - Make the [`salla-offer-modal`](https://docs.salla.dev/422715m0) body scrollable in mobile screens
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.186] - 09-08-2025
### Added
- New Twilight Version `2.14.186` is released, which includes:
  - Handle invalid offers data passed to `salla-cart-item-offers` JS web component
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.185] - 08-08-2025
### Added
- New Twilight Version `2.14.185` is released, which includes:
  - Fix Cart gifting in the [`salla-gifting`](https://docs.salla.dev/422705m0) JS Web Component, where it checks that both `productId` and `formSelector` exist before running the gift button logic, instead of just checking for `formSelector`.
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.184] - 07-08-2025
### Added
- New Twilight Version `2.14.184` is released, which includes:
  - Fix the error appearing on cart item offers if not updated in the `salla-cart-item-offers` JS Web component.
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.183] - 06-08-2025
### Added
- New Twilight Version `2.14.183` is released, which includes:
  - Reverted `2.14.181` change of Apply pay currency being based on the user's confgiguration currency code
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.182] - 05-08-2025
### Added
- New Twilight Version `2.14.182` is released, which includes:
  - Fix free shipping on Apple Pay
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.181] - 04-08-2025
### Added
- New Twilight Version `2.14.181` is released, which includes:
  - Fixed Apple pay currency appearance to be based on the user's configuration currency code
    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.180] - 03-08-2025
### Added
- New Twilight Version `2.14.180` is released, which includes:
  - *Cart Script Fix*
    - Avoids casting the cart item ID to integer to preserve product option behavior
    - **Code Change:**
      - **File**: `src/assets/js/cart.js`
        - From:
          ```js
          if (!arrayTwoId.includes(parseInt(form.id.value))) { ... }
          ```
        - To:
          ```js
          if (!arrayTwoId.includes(form.id.value)) { ... }
          ```
    - 🛠️ **Developer Actions:**
      - **Modify Existing Code:** Update cart script logic to avoid casting `form.id.value` to `integer`. **More details in [this PR](https://github.com/SallaApp/theme-raed/pull/638)**

## [2.14.179] - 29-07-2025
### Added
- New Twilight Version `2.14.179` is released, which includes:
    - Remove price check from Mispay visibility logic in the [`salla-installment`](https://docs.salla.dev/422707m0) JS Web Component,
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.178] - 28-07-2025
### Added
- New Twilight Version `2.14.178` is released, which includes:
    - Send product options with gift in the [`salla-gifting`](https://docs.salla.dev/422705m0) JS Web Component
        - 🛠️ **Developer Actions:**  
            - No Action Required
            
## [2.14.177] - 27-07-2025
### Added
- New Twilight Version `2.14.177` is released, which includes:
    - Disable options availability feature in the cart page in the [`salla-product-options`](https://docs.salla.dev/422720m0) JS Web Component.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.176] - 24-07-2025
### Added
- New Twilight Version `2.14.176` is released, which includes:
    - Use Normal Login To Open Fast-checkout
    - Display History of Loyalty Points to Customers
        - 🛠️ **Developer Actions:**  
            - **Modify Existing Code:** Requires updating Twilight in your theme and rebuilding assets to enable loyalty point history display.

## [2.14.175] - 22-07-2025
### Added
- New Twilight Version `2.14.175` is released, which includes:
    - Fixed a syntax error in the [`salla-offer`](https://docs.salla.dev/440408m0) JS Web Component by removing an invalid semicolon in a Promise callback.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.173] - 21-07-2025

### Added

- New Twilight Version `2.14.173` is released, which includes:
    - Improved SSO login and logout for `fast-checkout` by enhancing redirect handling, adding iframe-based logout, supporting unauthenticated mini-checkout users, and removing redundant login modals.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.172] - 20-07-2025

### Added

- New Twilight Version `2.14.172` is released, which includes:
    - Fix booking price with the SAR symbol in the `salla-booking-field` JS Web Component.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.171] - 17-07-2025

### Added

- New Twilight Version `2.14.171` is released, which includes:
    - Fixed the cart offers request issue in the [`salla-offers`](https://docs.salla.dev/440408m0) JS Web Component.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.170] - 16-07-2025

### Added

- New Twilight Version `2.14.170` is released, which includes:
    - Activate the new SAR symbol in the cart page.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.169] - 15-07-2025

### Added

- New Twilight Version `2.14.169` is released, which includes:
    - SAR currency symbol is now shown in API responses by default.
        - 🛠️ **Developer Actions:**  
            - No Action Required

## [2.14.168] - 15-07-2025

### Added

- New Twilight Version `2.14.168` is released, which includes:
    - Validation for missing `itemId` before loading the [`salla-reviews-summary`](https://docs.salla.dev/602149m0) JS Web Component.  
    - Store Address is added in the reviews schema.

    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.162] - 15-07-2025

### Added

- New Twilight Version `2.14.162` is released, which includes:
    - Cart scope updates and resets now occur only when the user is not on the cart page.

    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.161] - 15-07-2025

### Added

- New Twilight Version `2.14.161` is released, which includes:
    - Restricted `injectMaintenanceAlert` and `injectThemePreviewAlert` to display only when the store is not embedded in an iframe, improving the embedded view experience.

    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.160] - 15-07-2025

### Added

- New Twilight Version `2.14.160` is released, which includes:
    - Update scope retrieval to prioritize the store’s default configuration over stored values.

    - 🛠️ **Developer Actions:**  
        - No Action Required

## [2.14.159] - 15-07-2025

### Added

- New Twilight Version `2.14.159` is released, which includes:
    - Fixed bugs in the [`salla-installment`](https://docs.salla.dev/422707m0) JS Web Component. The component now reliably handles delayed loading by using a retry mechanism.

    - 🛠️ **Developer Actions:**  
        - No Action Required


## [2.14.158] - 30-06-2025
### Added
- New Twilight Version `2.14.158` is released, which includes:
    - Fix resetting the cart after changing the scope
    - Fix updating scope from the URL
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.155] - 25-06-2025
### Added
- New Twilight Version `2.14.155` is released, which includes:
    - Fix the offers products in the [`salla-offers-modal`](https://docs.salla.dev/422715m0)
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.154] - 24-06-2025
### Added
- New Twilight Version `2.14.154` is released, which includes:
    - Fix [`salla-tel-input`](https://docs.salla.dev/doc-422739?nav=01HNFTE06J4QC24T0D5BPRYKMD) issues after upgrade
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.153] - 23-06-2025
### Added
- New Twilight Version `2.14.153` is released, which includes:
    - Get the scope parameter from the URL and update the API headers in the Scope API
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.152] - 22-06-2025
### Added
- New Twilight Version `2.14.152` is released, which includes:
    - Prevent listen to login messages if the login modal is closed in the [`salla-login-modal`](https://docs.salla.dev/422711m0) JS Web Component
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.143] - 10-06-2025
### Added
- New Twilight Version `2.14.143` is released, which includes:
    - Show Apple Pay on Snapchat browser
        - 🛠️ Developer Actions:
                - No Action Required
    
    - Make sure the `User` object is Passed on both `Signed In` and `Signed Up` events for analytics purposes.
    - Use the [`salla-products-slider`](https://docs.salla.dev/422722m0) JS Web component within the [`salla-offer-modal`](https://docs.salla.dev/422715m0) JS Web component
        - 🛠️ Developer Actions:
                - **Modify Existing Code:** If you are using the [`salla-offer-modal`](https://docs.salla.dev/422715m0) JS Web component, you can add the [`salla-products-slider`](https://docs.salla.dev/422722m0) inside it. Just make sure it does not break your theme or layout.

## [2.14.140] - 03-06-2025
### Added
- New Twilight Version `2.14.140` is released, which includes:
    - Prevent render the [`salla-reviews-summary`](https://docs.salla.dev/602149m0) JS Web component if the `itemId`variable is not passed
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.137] - 27-05-2025
### Added
- New Twilight Version `2.14.137` is released, which includes:
    - Enhancements to catch the `intended_to` parameter after login.
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.135] - 21-05-2025
### Added
- New Twilight Version `2.14.135` is released, which includes:
    - Display the [`salla-contacts`](https://docs.salla.dev/478494m0) JS Web Component only if the store has contacts.
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.134] - 20-05-2025
### Added
- New Twilight Version `2.14.134` is released, which includes:
    - Add swiper events and methods to use it in theme files in the [`salla-slider`](https://docs.salla.dev/422735m0) JS Web Component.
    - Emit events on closing the [`salla-login-modal`](https://docs.salla.dev/422711m0) JS Web Component
    - Fix scroll restoration in the single product when using the [`salla-products-list`](https://docs.salla.dev/422719m0) JS Web Component
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.133] - 17-05-2025
### Added
- New Twilight Version `2.14.133` is released, which includes:
    - Visual asset utilized in event-based analytics
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.126] - 08-05-2025
### Added
- New Twilight Version `2.14.126` is released, which includes:
    - Using the Analytics class to track events and page views, store them, and forward them to custom trackers, ensuring new trackers receive past events for consistent analytics.
        - 🛠️ Developer Actions:
                - No Action Required

## [2.14.122] - 29-04-2025

### Added

- New Twilight Version `2.14.122` is released, which includes:
    - Removed the temporary patch that used the old SAR symbol when updating prices.
      - 🛠️ Developer Actions:
        - **Refactor Code**: Use `innerHTML` instead of `innerText` for displaying Cart/Product prices.

## [2.14.116] - 27-04-2025

### Added

- New Twilight Version `2.14.116` is released, which includes:
    - Disable the edit profile option when the SSO login is active.
    - Call the `logUTMVisit` function only when needed.
      - 🛠️ Developer Actions:
        - No Action Required

## [2.14.113] - 26-04-2025

### Added

- New Twilight Version `2.14.113` is released, which includes:
    - Pass `s-utm-referrer` to Track Events.
    - Fixed an issue where product page snapshots were not being removed properly in the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
      - 🛠️ Developer Actions:
        - No Action Required

## [2.14.104] - 20-04-2025

### Added

- New Twilight Version `2.14.104` is released, which includes:
    - Support physical gifting on the [&lt;salla-gifting>](https://docs.salla.dev/422705m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component.
        - 🛠️ Developer Actions:
            - No Action Required

## [2.14.103] - 17-04-2025

### Added

- New Twilight Version `2.14.103` is released, which includes:
    - Support SSO-Login
        - 🛠️ Developer Actions:
            - No Action Required

## [2.14.102] - 16-04-2025

### Added

- New Twilight Version `2.14.102` is released, which includes:

    - Updated styles for Tamara and tabby in the [&lt;salla-installment>](https://docs.salla.dev/422707m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component 
        - 🛠️ Developer Actions:
            - No Action Required


## [2.14.101] - 08-04-2025

### Added

- New Twilight Version `2.14.101` is released, which includes:
    - Standardize the visual design of BNPL options in the [`salla-installment`](https://docs.salla.dev/422707m0?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## [2.14.98] - 08-04-2025

### Added

- New Twilight Version `2.14.98` is released, which includes:
    - Support tracking new events in the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.95] - 08-04-2025

### Added

- New Twilight Version `2.14.95` is released, which includes:
    - Disable snapshot loading in the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.91] - 07-04-2025

### Added

- New Twilight Version `2.14.91` is released, which includes:
    - Handle more navigation history scenarios in the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.88] - 16-03-2025

### Added

- New Twilight Version `2.14.88` is released, which includes:
    - Custom fields format date to align with the dashboard in the [`salla-metadata`](https://docs.salla.dev/464599m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.86] - 13-03-2025

### Added

- New Twilight Version `2.14.86` is released, which includes:
    - Fix currency bugs in the wallet.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.80] - 09-03-2025

### Added

- New Twilight Version `2.14.80` is released, which includes:
    - Increase the default delay of the [`salla-slider`](https://docs.salla.dev/422735m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component to **10** seconds.
        - 🛠️ **Developer Actions**:
            - No Action Required


## [2.14.78] - 02-03-2025

### Added

- New Twilight Version `2.14.78` is released, which includes:
    - Replace the HTML currency symbol on the options names in the [`salla-product-options`](https://docs.salla.dev/422720m0) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.77] - 26-02-2025

### Added

- New Twilight Version `2.14.77` is released, which includes:
    - Disabling the use of SAR in the [Salla Cart page](https://docs.salla.dev/doc-429431/?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.76] - 22-02-2025

### Added
- New Twilight Version `2.14.76` is released, which includes:
    - Avoid cases to replace currencies not set to `SAR`.
        - 🛠️ **Developer Actions**:
            - No Action Required

### Added
- New Twilight Version `2.14.75` is released, which includes:
    - Fix the new SAR symbol on the "My Orders" page.
    - Fix the new SAR symbol on the default `product-card`.
        - 🛠️ **Developer Actions**:
            - No Action Required
### Added
- New Twilight Version `2.14.74` is released, which includes:
    - Fix the new SAR currency symbol on price range filters in both the `salla-price-range` and the [`salla-progress-bar`](https://docs.salla.dev/422723m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components.
    - Fix the new SAR currency symbol on donations in the [`salla-progress-bar`](https://docs.salla.dev/422723m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.73] - 21-02-2025

### Added

- New Twilight Version `2.14.73` is released, which includes:
    - Disable SAR currency symbol on update prices in the [`salla-conditional-offer`](https://docs.salla.dev/537931m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - **Modify Existing Code**: Use `innerHTML` instead of `innerText` to update money using `salla.money()`.

## [2.14.72] - 20-02-2025

### Added

- New Twilight Version `2.14.72` is released, which includes:
    - Support the new SAR currency symbol.
        - 🛠️ **Developer Actions**:
            - No Action Required
            - Just Double check that it's not affecting any areas where the symbol is used. **💡 Tip:** use `salla.money(number, false)` to avoid rendering the new symbol.

- New Twilight Version `2.14.70` is released, which includes:
    - Change alignment for store custom fields in the [`salla-metadata`](https://docs.salla.dev/464599m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required


## [2.14.64] - 05-02-2025

### Added

- New Twilight Version `2.14.64` is released, which includes:
    - Support new event helper, `salla.event.onlyWhen(eventName, callback)`
    - Retrieve the correct donation amount in the gifting modal in the [`salla-gifting`](https://docs.salla.dev/422705m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.62] - 03-02-2025

### Added

- New Twilight Version `2.14.62` is released, which includes:
    - Fix gifting modal selectors by using unique IDs in the [`salla-gifting`](https://docs.salla.dev/422705m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.61] - 02-02-2025

### Added


- New Twilight Version `2.14.61` is released, which includes:
    - Avoid show [Emkan](https://www.emkanfinance.com.sa/) by default in the [`salla-installment`](https://docs.salla.dev/422707m0) JS Web Component
        - 🛠️ **Developer Actions**:
            - No Action Required

- New Twilight Version `2.14.60` is released, which includes:
    - New integration added with [Emkan](https://www.emkanfinance.com.sa/) in the [`salla-installment`](https://docs.salla.dev/422707m0) JS Web Component
        - 🛠️ **Developer Actions**:
            - No Action Required

<!--

## [2.14.58] - 30-01-2025

### Added

- New Twilight Version `2.14.58` is released, which includes:
    - [Display Cart Calculation](https://github.com/SallaApp/theme-raed/pull/511/files) Enhancement
        - 🛠️ **Developer Actions**:
            - Modify Existing Code
-->

## [2.14.57] - 29-01-2025

### Added

- New Twilight Version `2.14.57` is released, which includes:
    - Fix issue of currency in Tamara in the [`salla-installment`](https://docs.salla.dev/422707m0) JS Web Component
    - Prevent duplicate filters in category URLs in the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.54] - 23-01-2025

### Added

- New Twilight Version `2.14.54` is released, which includes:
    - Replace the `input` event with `change` event within text inputs in the [`salla-product-options`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    - Use (Day/Month/Year) date format in the [`salla-comments`](https://docs.salla.dev/482455m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.51] - 15-01-2025

### Added

- New Twilight Version `2.14.51` is released, which includes:
    - Enhance `selectedOptions` synchronization for accurate change event reflection in the [`salla-product-options`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
        - 🛠️ **Developer Actions**:
            - Rebuild Assets

- New Twilight Version `2.14.50` is released, which includes:
    - Update Partner visits' tracking endpoint 
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.49] - 14-01-2025

### Added

- New Twilight Version `2.14.49` is released, which includes:
    - Enhance product options' validation for the Cart page the [`salla-product-options`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD), [`salla-products-slider`](https://docs.salla.dev/422722m0?nav=01HNFTE06J4QC24T0D5BPRYKMD), and [`salla-quantity-input`](https://docs.salla.dev/422724m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components
    - Enhance snapshot For products navigation history in the [`salla-product-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component 
    - Fix issues related to Madfu and Mispay widget installments
        - 🛠️ **Developer Actions**:
            - Rebuild Assets

## [2.14.48] - 13-01-2025

### Added

- New Twilight Version `2.14.48` is released, which includes:
    - Add support for Madfu installment in the [`salla-installment`](https://docs.salla.dev/422707m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
        - 🛠️ **Developer Actions**:
            - Rebuild Assets

## [2.14.47] - 12-01-2025

### Added

- New Twilight Version `2.14.47` is released, which includes:
    - Support new event in the Cart API SDK, `cart::submitting`
    - Support the Rajehi Installment in the [`salla-installment`](https://docs.salla.dev/422707m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Enhance product options' validation for the Cart page in the [`salla-product-options`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD), [`salla-products-slider`](https://docs.salla.dev/422722m0?nav=01HNFTE06J4QC24T0D5BPRYKMD), and [`salla-quantity-input`](https://docs.salla.dev/422724m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components
        - 🛠️ **Developer Actions**:
            - Leverage New Feature (validation in cart page)
            - Rebuild Assets (Rajehi installment Feature)

## [2.14.44] - 10-01-2025

### Added

- New Twilight Version `2.14.44` is released, which includes:
    - Disable snapshot in homepage in the [`salla-product-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.43] - 08-01-2025

### Added

- New Twilight Version `2.14.43` is released, which includes:
    - Handle scroll restoration in the default homepage in the [`salla-product-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.40] - 01-01-2025

### Added

- New Twilight Version `2.14.40` is released, which includes:
    - Fix alignment of [SBC (Saudi Business Center)](https://eauthenticate.saudibusiness.gov.sa/) icon in the [`salla-payments`](https://docs.salla.dev/478374m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.39] - 29-12-2024

### Added

- New Twilight Version `2.14.39` is released, which includes:
    - Add support for radio inputs in the [`salla-conditional-fields`](https://docs.salla.dev/422699m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.35] - 15-12-2024

### Added

- New Twilight Version `2.14.35` is released, which includes:
    - Enable Merchants to customize product options layout for multiple options.
    - Enhances and fixes in UI for the new single / multiple options in the [`<salla-product-options>`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component.
    - Added `config` prop to allow layout customization (grid or list) for multiple options.
        - Implemented dynamic rendering based on layout type for multiple options.
        - Added CSS styles for grid and list layouts for multiple options.
        - Included fallback behavior for invalid or missing configuration.
            - 🛠️ **Developer Actions**:
                - **Leverage New Feature**: The developer should add a configuration property in the [`<salla-product-options>`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component with the type of single / multiple option layout in this manner:
            ```html
            <salla-product-options 
              options="{{ product.options }}" 
              product-id="{{ product.id }}" 
              config='{
                "single-option": { "type": "button" },
                "multiple-option": { "type": "button" }
              }'>
            </salla-product-options>
            ```
                - **Rebuild Assets**: rebuild assets to apply the recent UI enhancements.

## [2.14.32] - 11-12-2024

### Added

- New Twilight Version `2.14.32` is released, which includes:
    - Refine `invalidHandler` to prevent unwanted scrolling on validation errors
    - Fix scrolling issue on the product page when there are many options
    - Prevents redundant `scrollIntoView` calls by ensuring scrolling is limited to the first invalid field.
    - Avoids scrolling on the cart page (`salla.url.is_page('cart')` check)
    - Adds modular `scrollToElement` for cleaner, reusable scrolling logic
    - Ensures `s-product-options-option-error` class is not re-added unnecessarily
    - Improves user experience by mitigating disorienting scroll behavior during validation
        - 🛠️ **Developer Actions**:
            - **Rebuild Assets**: reflect changes on Tailwind  classes

## [2.14.30] - 11-12-2024

### Added

- New Twilight Version `2.14.30` is released, which includes:
    - Handle returns to a different category when there is a snapshot in the [`salla-product-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.29] - 10-12-2024

### Added

- New Twilight Version `2.14.29` is released, which includes:
    - Optimize event handling and enhance safety for the product card functionality in the [`salla-product-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.27] - 08-12-2024

### Added

- New Twilight Version `2.14.27` is released, which includes:
    - Preserve scroll position on the [`salla-product-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component after navigating back
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.26] - 04-12-2024

### Added

- New Twilight Version `2.14.26` is released, which includes:
    - Fix the add to cart opertion from special offers popup in the [`salla-offer-modal`](https://docs.salla.dev/422715m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Support a new property, `unique-key`, on the [`salla-product-options`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
        - 🛠️ **Developer Actions**:
            - **Leverage New Feature:** use the `unique-key` property on the [`salla-product-options`](https://docs.salla.dev/422720m0?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component in case the developer have duplicated items in same page

## [2.14.24] - 27-11-2024

### Added

- New Twilight Version `2.14.24` is released, which includes:
    - Fix bug for includeing properties on both the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) and [`salla-slider`](https://docs.salla.dev/doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web components
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.22] - 20-11-2024

### Added

- New Twilight Version `2.14.22` is released, which includes:
    - Reduce authentication requests
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.21] - 10-11-2024

### Added

- New Twilight Version `2.14.21` is released, which includes:
    - Allow developers to update and / or verify the customer's profile mobile number
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.20] - 02-11-2024

### Added

- New Twilight Version `2.14.20` is released, which includes:
    - Wait for Salla to be ready to render the [salla-scopes](https://docs.salla.dev/doc-422729?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component

## [2.14.19] - 30-10-2024

### Added

- New Twilight Version `2.14.19` is released, which includes:
    - Ensure the [`salla-scopes`](https://docs.salla.dev/doc-422729?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component's modal displays correctly for single branch availability without requiring additional selection.
    - Resolve filters and social links not working in category and brand pages on both the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) and [`salla-social`](https://docs.salla.dev/doc-499802?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web components

## [2.14.17] - 22-10-2024

### Added

- New Twilight Version `2.14.17` is released, which includes:
    - New key added to the customer data, `salla.config.get('user.can_comment')`, where whether or not the customer can add a comment.

## [2.14.14] - 06-10-2024

### Added

- New Twilight Version `2.14.14` is released, which includes:
    - Add lang to the menus requests
        - 🛠️ **Developer Actions**:
            - Modify Existing Code by discontinue using `{% component 'header.menu' %}` and `{% component 'footer.menu' %}`. Instead, use the [`salla-menu`](https://docs.salla.dev/doc-478492?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS web component to render the menus via ajax, using `salla.api.component.getMenus(headerOrFooter)` More details [here](https://docs.salla.dev/doc-705835?nav=01HNFTDZPB31Y2E120R84YXKCX)

## [2.14.13] - 06-10-2024

### Added

- New Twilight Version `2.14.13` is released, which includes:
    - Support store Urchin Tracking Modules *(a.k.a **UTMs**)*

## [2.14.12] - 06-10-2024
### Added
- New Twilight Version `2.14.12` is released, which includes:
    - Fix issues on the [`salla-breadcrumb`](https://docs.salla.dev/doc-482370?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component
        - 🛠️ **Developer Actions**:
            - Check Documentation for the [`salla-breadcrumb`](https://docs.salla.dev/doc-482370?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component where further details are mentioned

## [2.14.10] - 06-10-2024
### Added
- New Twilight Version `2.14.10` is released, which includes:
    - Add the store_id variable to the requests in the [`salla-menu`](https://docs.salla.dev/doc-478492?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component to avoid browser cache issues
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.9] - 03-10-2024
### Added
- New Twilight Version `2.14.9` is released, which includes:
    - Optimize the [`salla-breadcrumb`](https://docs.salla.dev/doc-482370?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component by auto-generating the breadcrumbs instead of using the API
        - 🛠️ **Developer Actions**:
            - No Action Required

## [2.14.8] - 30-09-2024
### Added
- New Twilight Version `2.14.7` is released, which includes:
    - Add an inline HTML `type="button"` to load more in the [`salla-comments`](https://docs.salla.dev/doc-482455?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component  
    - Enhance loading in the [`salla-orders`](https://docs.salla.dev/doc-508225?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Twilight Version `2.14.8` is released, which includes:
    - Fix setting the Order ID in the [`salla-rating-modal`](https://docs.salla.dev/doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component  
    - Ability to upload images in `.webp` format

## [2.14.5] - 29-09-2024
### Added
- New Twilight Version `2.14.5` is released, which includes:
    - Fix reset storage Cart On the `CartPage` when the session cart is different in the [`salla-conditional-offer`](https://docs.salla.dev/doc-537931?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Add new action, `salla.document.reload()`, to reload any store page if needed

## [2.14.4] - 25-09-2024
### Added
- New Twilight Version `2.14.4` is released, which includes:
    - Support Blog Interaction with Comments and Likes:
        - Support for liking and unliking on the blog single page.
        - Display likes count and comments count on blog cards using the [`salla-comments`](https://docs.salla.dev/doc-482455?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
        - Enable comments and replies using the [`salla-comments`](https://docs.salla.dev/doc-482455?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component on the blog post page. 

## [2.14.3] - 24-09-2024
### Added
- New Twilight Version `2.14.3` is released, which includes:
    - Support Masked Reviewer Name in the [`salla-user-settings`](https://docs.salla.dev/doc-422741?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.2] - 18-09-2024
### Added
- New Twilight Version `2.14.2` is released, which includes:
    - Logout from iframe after deactivation

## [2.14.1] - 08-09-2024
### Added
- New Twilight Version `2.14.1` is released, which includes:
    - Using one login for all salla stores using a unified domain, `"accounts.salla.com"`

## [2.13.122] - 03-09-2024
### Added
- New Twilight Version `2.13.122` is released, which includes:
    - Add validation for price property and handle zero values in the [`salla-installment`](https://docs.salla.dev/doc-422707?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Disable local storage logic on the [`salla-menu`](https://docs.salla.dev/doc-478492?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Product options not updating due to product ID type mismatch in the [`salla-products-list`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.120] - 25-08-2024
### Added
- New Twilight Version `2.13.120` is released, which includes:
    - Disable the UTM feature

## [2.13.119] - 22-08-2024
### Added
- New Twilight Version `2.13.119` is released, which includes:
    - Fix authentication issue on web browsers in the [`salla-login`](https://docs.salla.dev/doc-422711/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component 

## [2.13.114] - 20-08-2024
### Added
- New Twilight Version `2.13.114` is released, which includes:
    - Get the UTM Sources by extracting the URL parameters, filtering by `utmKeys`, and storing them in `utmParams`

## [2.13.112] - 19-08-2024
### Added
- New Twilight Version `2.13.112` is released, which includes:
    - Update Mis Pay BNPL platform to calculate amount on 4 different installments
    - Support for UTM sources by mapping the `CLICKID` parameters to their respective sources for the following:
        - Facebook
        - Google
        - Tiktok
        - Twitter
        - Snapchat

## [2.13.111] - 14-08-2024
### Added
- New Twilight Version `2.13.111` is released, which includes:
    - Fix Appointment field issues in the `salla-booking-field` JS Web Component
    - Fixed the issue with clearing Salla-related cookies after logout. The `salla.cookie.clearAll(force)` function now correctly clears browser cookies and accepts an optional `force` boolean parameter, defaulting to `false`.
        - When `force` is `true`: All cookies, regardless of origin, will be cleared.
        - When `force` is `false` or omitted: Only Salla-related cookies will be cleared, leaving other cookies intact.

    - Add two new methods for single and bulk translation in the [`salla.lang`](https://docs.salla.dev/doc-422614?nav=01HNFTDZPB31Y2E120R84YXKCX#Un1adding-new-translations) method

## [2.14.102] - 23-07-2024
### Added
- New Twilight Version `2.14.102` is released, which includes:
    - Update user's address when Apple Pay is authorized in the [`salla-quick-buy`](https://docs.salla.dev/doc-422725/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Support multiple uploads on the [`salla-file-upload`](https://docs.salla.dev/doc-422703/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Enhancing the Merchant reviews system by:
        - Allow up to 3 images attached to the comment
        - Enable Customers to flag comments as `"Helpful"`
        - Contact store support straight from the comment form via the specified channels *(Email - content is pre-filled with store name, client name, and order number - and WhatsApp)*
        - Introducing new [`salla-reviews-summary`](https://docs.salla.dev/doc-602149/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component to display the general rating on the product page

## [2.14.100] - 18-07-2024
### Added
- New Twilight Version `2.14.100` is released, which includes:
    - Allow Apple Pay on gift order request in the [`salla-gifting`](https://docs.salla.dev/doc-422705/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Enhance country flags quality in the [`salla-product-options`](https://docs.salla.dev/doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.99] - 13-07-2024
### Added
- New Twilight Version `2.14.99` is released, which includes:
    - Show Fast Checkout button in the [`salla-add-product-button`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.98] - 11-07-2024
### Added
- New Twilight Version `2.14.98` is released, which includes:
    - Disable fast-checkout in financial support products in the [`salla-add-product-button`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Disable country option with no card available in the [`salla-product-options`](https://docs.salla.dev/doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.96] - 10-07-2024
### Added
- New Twilight Version `2.14.96` is released, which includes:
    - Support Digital Product Options on the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.94] - 09-07-2024
### Added
- New Twilight Version `2.14.94` is released, which includes:
    - Update Metadata API URL with new backend schema in the [`salla-metadata`](https://docs.salla.dev/doc-464599/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.93] - 08-07-2024
### Added
- New Twilight Version `2.14.93` is released, which includes:
    - Make reviews text optional in the [`salla-rating-modal`](https://docs.salla.dev/doc-422728/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Prevent disposable emails in the [`salla-login-modal`](https://docs.salla.dev/doc-422711/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Update amount in Apple Pay after selecting the payment method

## [2.14.91] - 03-07-2024
### Added
- New Twilight Version `2.14.91` is released, which includes:
    - Fix icon spacing in the [`salla-advertisement`](https://docs.salla.dev/doc-478502/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Handle multiple booking fields in one page in the `salla-booking-field` JS Web Component
    - Avoid lost Apple Pay Transaction for network errors

## [2.14.89] - 02-07-2024
### Added
- New Twilight Version `2.14.89` is released, which includes:
    - Enhancements on the book appointment option in the `salla-booking-field` JS Web Component

## [2.14.88] - 01-07-2024
### Added
- New Twilight Version `2.14.88` is released, which includes:
    - Fix wrong selected option in the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    - Support order option book appointment field in the `salla-booking-field` JS Web Component

## [2.14.83] - 27-06-2024
### Added
- New Twilight Version `2.14.83` is released, which includes:
    - Support skeleton for the [`salla-user-profile`](https://docs.salla.dev/doc-482367/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Support new API, [`salla.product.api.fetchOptions([1,2,3])`](https://docs.salla.dev/doc-569578/?nav=01HNFTDZPB31Y2E120R84YXKCX), to fetch bulk products options
    - Support new property, `includes='["options"]'`, on both the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) and the [`salla-products-slider`](https://docs.salla.dev/doc-422722/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components to display product options

- New Twilight Version `2.14.85` is released, which includes:
    - Fix duplicate number when pasting OTP in the [`salla-verify`](https://docs.salla.dev/doc-422742/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.82] - 24-06-2024
### Added
- New Twilight Version `2.14.82` is released, which includes:
    - Minimum age restriction added to the customer form for birthdate validation on the [`salla-user-profile`](https://docs.salla.dev/doc-482367/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.14.81] - 23-06-2024
### Added
- New Twilight Version `2.14.81` is released, which includes:
    - Reset cart after changes occurring on scopes on the [`salla-scopes`](https://docs.salla.dev/doc-422729/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.80] - 10-06-2024
### Added

- New Twilight Version `2.13.80` is released, which includes:
  - Avoid redundant API calls when cache is available on the [footer menu](https://docs.salla.dev/doc-422602/?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- New Twilight Version `2.13.79` is released, which includes:
  - Support testimonials on the [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.78] - 06-06-2024
### Added

- New Twilight Version `2.13.78` is released, which includes:
  - Switching currency causes issues on the [`conditional offers`](https://docs.salla.dev/doc-537931/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix Store ID not found errors on the [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Enhance too many API hits on `getLatestCart` on the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.76] - 03-06-2024
### Added

- New Twilight Version `2.13.76` is released, which includes:
  - Avoid missing Store ID error on the [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Fast Checkout Version `1.0.16` is released, which includes:
  - Early pass the User's email to Tamara's payload
  - Load `iFrame` only when the user needs to interact

## [2.13.75] - 29-05-2024
### Added

- New Twilight Version `2.13.75` is released, which includes:
  - Fix issues on the [`conditional offers`](https://docs.salla.dev/doc-537931/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix the [`fast checkout`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD#Un0fast-checkout-feature) widget when appearing on extra small screens

- New Fast Checkout Version `1.0.15` is released, which includes:
  - Fix issues appearing on `Pay By Tamara`
  - Fix orders without checkboxes options
  - Enhancements on the validation logic

## [2.13.74] - 28-05-2024
### Added

- New Twilight Version `2.13.74` is released, which includes:
  - Add new required fields’ configurations to Tabby promotion

## [2.13.73] - 26-05-2024
### Added

- New Twilight Version `2.13.73` is released, which includes:
  - Auto login `fast-checkout` in the [`salla-add-product-button`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Twilight Version `2.13.72` is released, which includes:
  - Incorrect progress when an item is removed from the [`salla-conditional offer`](https://docs.salla.dev/doc-537931/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Loading translation in fast checkout widget in the [`salla-add-product-button`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Twilight Version `2.13.71` is released, which includes:
  - Add loading skeleton to the [`salla-conditional-offer`](https://docs.salla.dev/doc-537931/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Support `fast-checkout` in the [`salla-add-product-button`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.67] - 22-05-2024
### Added

- New Twilight Version `2.13.67` is released, which includes:
  - Fix showing HTML tags on the [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Twilight Version `2.13.66` is released, which includes:
  - Enhancement to utilize the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component on the Wishlist Page
  - Support new component, [`salla-conditional-offer`](https://docs.salla.dev/doc-537931/?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## [2.13.64] - 19-05-2024
### Added

- New Twilight Version `2.13.64` is released, which includes:
  - Fix unsupported Tailwind padding utility class, `pe`
  - Fix comments date on old Safari browser versions and show form avatar, `showAvatar`, property on the [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.62] - 14-05-2024
### Added
- New Twilight Version `2.13.62` is released, which includes:
    - Enhancements in  [`salla-payments`](doc-478374) 
        - New property added
              - `exclude`
         - Properties removed 
               - `withMadeInKsa`
               - `withSbc`
               - `sbcId`
    - Added new Twitter icon for [`salla-social`](doc-499802) Web Component
    - Added caching feature to [`salla-menu`](doc-478492) API
    


## [2.13.61] - 12-05-2024
### Added
- New Twilight Version `2.13.61` is released, which includes:
    - In [`salla-reviews`](doc-508226) JS Web Component, the reviews now supports rendering as HTML.
    - [`Helpers methods`](doc-422617) now support `isPreview()` and `isIframe()` functions.
    - [`salla-metadata`](doc-464599) JS Web Component now supports `salla.design`.


## [2.13.59] - 06-05-2024
### Added
- New Twilight Version `2.13.59` is released, which includes:
    - Handling no offers message as warning instead of an error in the [salla-offers](doc-440408) JS Web Component.


## [2.13.54] - 05-05-2024
### Added

- New Twilight Version `2.13.54` is released, which includes:
    - Add `type` and `sort` properties to [`salla-reviews`](doc-508226) JS Web Component and [Salla Helpers](doc-422617).
    - Return `salla.lang.onLoaded()` as Promise in [Language](doc-422614) JS Web Component. 

## [2.13.51] - 02-05-2024
### Added

- New Twilight Version 2.13.51 is released, which includes:
    - Enhancements on `salla.onReady()` to be a Promise.
    - Allow using `salla.onReady().then(config => console.log(config))` without callback.

## [2.13.49] - 01-05-2024
### Added

- New Twilight Version 2.13.49 is released, which includes:
    - Enhancements on the [`intl-tel-input`](doc-422739/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component to support a new range of numbers.
    - Fix `salla-price-range` rendering in the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    - Add prop for toggling comment avatar visibility [`salla-comments`](doc-482455?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    - Enhancements for [`salla-breadcrumb`](https://docs.salla.dev/doc-482370/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.


## [2.13.44] - 25-04-2024
### Added

- New Twilight Version `2.13.44` is released, which includes:
    - Added new `method` `salla.helpers.hasApplePay()` supported in [salla-quick-buy](https://docs.salla.dev/doc-422725/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    - Hide `ApplePay` on Snapchat Browser Temporary.



## [2.13.43] - 25-04-2024
### Added
- New Twilight Version `2.13.43` is released, which includes:
    - Resolve API response handling for [`salla-reviews`](doc-508226?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## [2.13.42] - 24-04-2024
### Added

- New Twilight Version `2.13.42` is released, which includes:
    - Hide title on the [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component when there are no comments

## [2.13.41] - 23-04-2024
### Added

- New Twilight Version `2.13.41` is released, which includes:
    - Fix the `showOffer` method in the [`salla-offer-modal`](doc-422715?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    - Support new storage method with TTL, which is `salla.storage.setWithTTL()`
    - Add the `"apply"` button on the minimum and maximum prices on the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.

## [2.13.40] - 21-04-2024
### Added

- New Twilight Version `2.13.40` is released, which includes:
    - 2 New JS Web Components:
        - [`salla-orders`](doc-508225?nav=01HNFTE06J4QC24T0D5BPRYKMD)
        - [`salla-reviews`](doc-508226?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - Support the variable `product_show_special_offers` in both the [`salla-advertisment`](https://docs.salla.dev/doc-478502?nav=01HNFTE06J4QC24T0D5BPRYKMD) and [`salla-offer`](doc-440408?nav=01HNFTE06J4QC24T0D5BPRYKMD) 
    - Support length to text fields on the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.13.38] - 15-04-2024
### Added
- New Twilight Version `2.13.38` is released, which includes:
    - Fix rending errors in the following JS Web Components:
        - [`salla-advertisment`](https://docs.salla.dev/doc-478502?nav=01HNFTE06J4QC24T0D5BPRYKMD)
        - [`salla-apps-icons`](https://docs.salla.dev/doc-478518?nav=01HNFTE06J4QC24T0D5BPRYKMD)
        - [`salla-contacts`](https://docs.salla.dev/doc-478494?nav=01HNFTE06J4QC24T0D5BPRYKMD)
        - [`salla-payments`](https://docs.salla.dev/doc-478374?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - Fix issues related to Apple Pay on the [`salla-quick-buy`](https://docs.salla.dev/doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component.

## [2.13.37] - 14-04-2024
### Added
- New Twilight Version `2.13.37` is released, which includes:
    - Fix missing store ID in menu request in both [`salla-advertisment`](https://docs.salla.dev/doc-478502/?nav=01HNFTE06J4QC24T0D5BPRYKMD) and [`salla-menu`](https://docs.salla.dev/doc-478492/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components.

## [2.13.36] - 02-04-2024
### Added
- New Twilight Version `2.13.36` is released, which includes:
    - Fix Using the default donation option after a failed payment on the [`salla-add-product-button`](https://docs.salla.dev/doc-422692/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.

## [2.0.44] - 31-03-2024
### Added

- New Twilight Version `2.13.35` is released, which includes:
    - Increase Payments Logos Sizes on the [`salla-payments`](https://docs.salla.dev/doc-478374/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Twilight Version `2.13.34` is released, which includes:
    - Add the `limit` property on the [`salla-menu`](https://docs.salla.dev/doc-478492/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - Show Cash On Delivery (COD) on the [`salla-payments`](https://docs.salla.dev/doc-478374/?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component only when it is active

## [2.0.43] - 27-03-2024
### Added
- New Twilight Version `2.13.33` is released, which includes:
    - Disable FrontEnd Offers Cache
    - 8 New JS Web Components are released:
      - [`salla-apps-icons`](https://docs.salla.dev/doc-478518/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-breadcrumb`](https://docs.salla.dev/doc-482370/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-contacts`](https://docs.salla.dev/doc-478494/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-advertisment`](https://docs.salla.dev/doc-478502/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-comments`](https://docs.salla.dev/doc-482455/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-payments`](https://docs.salla.dev/doc-478374/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-menu`](https://docs.salla.dev/doc-478492/?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-user-profile`](https://docs.salla.dev/doc-482367/?nav=01HNFTE06J4QC24T0D5BPRYKMD)


## [2.0.42] - 19-03-2024
### Added
- New Twilight Version `2.13.31` is released, which includes:
    - Support add rate for CDN `salla.url.cdn(path, width, height)` in the [salla-user-menu](doc-422740?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
    - A new JS Web component is released, [`salla-metadata`](doc-464599?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## [2.0.41] - 27-02-2024
### Added
- New Twilight Version `2.13.28` is released, which includes:
    - Delay Requesting to fetch the current cart ID in the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.40] - 22-02-2024
### Added
- New Twilight Version `2.13.27` is released, which includes:
    - Fix `lazyload` images in the [`salla-products-slider`](doc-422722) JS Web Component
    - Enhance the [`salla-offer`](doc-440408?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component for optimized api interaction

## [2.0.39] - 14-02-2024
### Added

- New Twilight Version `2.13.25` is released, which includes:
    - Fixed submit button bug on Snapchat Browser where users need to first login
- New Twilight Version `2.13.24` is released, which includes:
    - Fixed a security vulnerability enabling HTML injection through URL manipulation within the [`notify`](doc-422615) library.
    
## [2.0.38] - 05-02-2024
### Added

- New Twilight Version 2.13.20 has been released which includes:
  - Enhancing the not found usecase in the [Carts API](doc-422626)
  - A new JS Web component is released, [`salla-order-summary`](doc-422695?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## [2.0.37] - 28-01-2024
### Added

- New Twilight Version `2.13.17` is released, which includes:
  - Fix Notify Out Of Stock Options in the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.36] - 21-01-2024
### Added
- New Twilight Version `2.13.2` is released, which includes:
  - Support SEO Schema and datalayer in the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.

## [2.0.35] - 17-01-2024
### Added
- New Twilight Version `2.13.0` is released, which includes:
  - Enhance SEO for the following JS Web Components:
    - [`salla-bottom-alert`](doc-422693?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - [`salla-login-modal`](doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - [`salla-product-card`](doc-422718?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD)
    - [`salla-verify`](doc-422742?nav=01HNFTE06J4QC24T0D5BPRYKMD)
  - Support new installment, MIS Pay, in the [salla-installment](doc-422707?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.
    
## [2.0.34] - 31-12-2023
### Added

- New Twilight Version `2.12.79-alpha.0` is released, which includes:
  - Logic enhancements for the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Reloading enhancements on the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.33] - 21-12-2023
### Added

- New Twilight Version `2.12.77` is released, which includes:
  - Reload products list without `infScroll` on the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Resolve comments for auto selecting filters on refresh on the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component 

## [2.0.32] - 18-12-2023
### Added
- New Twilight Version `2.12.75` is released, which includes:
  - Resolve issue with variants filter option value on the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component 

## [2.0.29] - 14-12-2023
### Added

- New Twilight Version `2.12.74` is released, which includes:
  - Fixing query duplication bugs in the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component 

- New Twilight Version `2.12.73` is released, which includes:
  - Enhancing the [`salla-bottom-alert`](doc-422693?nav=01HNFTE06J4QC24T0D5BPRYKMD) by adding more spacing for the mobile responsiveness 

- New Twilight Version `2.12.72` is released, which includes:
  - Enhancing the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component & the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component 
  - Enhancing Query param addition to URL in the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fixing bugs in Developer name in the [`salla-bottom-alert`](doc-422693?nav=01HNFTE06J4QC24T0D5BPRYKMD)
  - Fixing bugs in Applying filters from URL after refresh in the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component 

## [2.0.28] - 11-12-2023
### Added
- New Twilight Version `2.12.69` is released, which includes:
  - Support the Store Price and the Developer Name in the [salla-bottom-alert](doc-422693?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component.

## [2.0.27] - 05-12-2023
### Added
- New Twilight Version `2.12.68` is released, which includes:
  - Enhance the [salla-search](doc-422730?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component allowed words in the input field.

## [2.0.27] - 20-11-2023
### Added

- New Twilight Version `2.12.64` is released, which includes:
  - Fix reset OTP validation in the [`salla-verify`](doc-422742?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.26] - 05-11-2023
### Added
- New Twilight Version `2.12.61` is released, which includes:
  - Enhance login validation for the [`salla-login-modal`](doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component and [`salla-verify`](doc-422742?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.25] - 30-10-2023
### Added

- New Twilight Version `2.12.60` is released, which includes:
  - Fix the [`salla-bottom-alert`](doc-422693?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component in the Safari browser

## [2.0.24] - 26-10-2023
### Added

## [2.0.23] - 18-10-2023
### Added
- New Twilight Version `2.12.54` is released, which includes:
  - Remove URL from products for source landing-page on the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component and the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Support `apple-pay-only` in the [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Support new property, `inline`, in the [`salla-login-modal`](doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
- New Twilight Version `2.12.56` is released, which includes:
  - Support Passing `CartId` To the [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.23] - 18-10-2023
### Added

- New Twilight Version `2.12.50` is released, which includes:
  - Fix many currencies display on the [`salla-localization-modal`](doc-422710?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

- New Twilight Version `2.12.52` is released, which includes:
  - Support passing the Custom Products Cards on the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component and the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix show price as a dash in the store settings of the product on the [`salla-product-card`](doc-422718?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Enhancing reloading in the [`salla-login-modal`](doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.22] - 05-10-2023
### Added

- New Twilight Version `2.12.49` is released, which includes:
  - Fix donation with Apple Pay in the [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix related renderings to the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix cached data on the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.21] - 28-09-2023
### Added

- New Twilight Version `2.12.48` is released, which includes:
  - Fix the products count issue on the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Allow [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) Using ApplePay on iframes
  - Remove the Choices Login Method Tab on the [`salla-login`](doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component. By default, it will show login by SMS

## [2.0.20] - 21-08-2023
### Added

- New Twilight Version `2.12.42` is released, which includes:
  - Support the Slider configurations in the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Enhancement for the [`salla-count-down`](doc-422701?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components default translations

## [2.0.19] - 17-08-2023
### Added

- New Twilight Version `2.12.41` is released, which includes:
  - Support new KSA numbers by fixing the [`salla-tel-input`](doc-422739?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component validation issue

## [2.0.18] - 17-08-2023
### Added

- New Twilight Version `2.12.38` is released, which includes:
  - Append the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component's items after a set amount of time in milliseconds

## [2.0.17] - 17-08-2023
### Added

- New Twilight Version `2.12.36` is released, which includes:
  - Fix an early loading bug on both the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) and the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components

## [2.0.16] - 16-08-2023
### Added

- New Twilight Version `2.12.34` is released, which includes:
  - Fix the issue of `Store Identifier not found` when bad connections occur on both the [`salla-products-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) and the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components

## [2.0.15] - 16-08-2023
### Added

- New Twilight Version `2.12.33` is released, which includes:
  - Update the donation `manual amount` in the [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.14] - 2023-08-16
### Added

- New Twilight Version `2.12.32` is released, which includes:
  - Support the `salla.logger.history()` when the `debug` variable is set to `active`
  - Update the donation `amount` variable in the [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.13] - 14-08-2023
### Added

- New Twilight Version `2.12.30` is released, which includes:
  - Four countries have been excluded from the [`salla-tel-input`](doc-422739?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Reference error fixed in the [Get Current Cart ID JS SDK API](doc-422639)

## [2.0.12] - 19-08-2023
### Added

- New Twilight Version `2.12.29` is released, which includes:
  - The login cycle has undergone a number of improvements.
  - Use `GET` requests for [offers](doc-422643) & [price](doc-422641) endpoints instead of `POST` in the [Product JS SDK API](doc-422610)

## [2.0.11] - 26-08-2023
### Added

- New Twilight Version `2.12.19` is released, which includes:
  - Support the `load-more-text` property in the [`salla-infinite-scroll`](doc-422706?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web component

## [2.0.10] - 23-07-2023
### Added

- New Twilight Version `2.12.18` is released, which includes:
  - Fix the hashtag encoding in the [salla-filters](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component URL
  - Inject cache headers in salla requests

## [2.0.9] - 20-07-2023
### Added

- New Twilight Version `2.12.17` is released, which includes:
  - Fix conditional fields validation in the [salla-product-options](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.8] - 16-07-2023
### Added
- New Twilight Version `2.12.16` is released, which includes:
  - Update Installments Blocks Price in the [salla-installment](doc-422707?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.7] - 13-07-2023
### Added

- New Twilight Version `2.12.14` is released, which includes:
  - New JS Web Component is released, [`salla-bottom-alert`](doc-422693?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## [2.0.6] - 06-07-2023
### Added

- New Twilight version `2.12.13` is released, which includes:
  - Enhance fetching the user's profile request in the [`salla-user-menu`](doc-422740?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Support donation options in the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix the filter widgets' height after submission in the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
  - Fix `source-value` validation by handling expired donations on both [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) and [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Components

## [2.0.5] - 14-06-2023
### Added

- New Twilight version `2.12.9` is released, which includes:
  - Fix multiple validation options in cart on the [`salla-product-options`](doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.5] - 13-06-2023
### Added

- New Twilight version `2.12.8` is released, which includes:
  - Handle expired donation in the [Single Product](doc-422561) page
  - Fix the [`salla-social-share`](doc-422736?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component animation as well as multiple instance issues
  - Hide the [`salla-quick-buy`](doc-422725?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component in the booking products 

## [2.0.4] - 11-06-2023
### Added

- New Twilight version `2.12.6` is released, which includes:
  - Fix access to [`salla-sliders`](doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD) on some countries, where developers should be using Salla CDN, `https://cdn.salla.network`, instead of Swiper jsdelivr, `https://cdn.isdelive.net`

## [2.0.3] - 07-06-2023
### Added

- New Twilight patch version `2.12.5` is released, which includes:
  - Fix donation message in the [Single Product](doc-422561) page
  - Support URL property in the [`salla-social-share`](doc-422736?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.2] - 01-06-2023
### Added

- New Twilight patch version `2.12.4` is released, which includes:
   - Support thumbs config prop in the [`salla-slider`](doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component
   - Enhancements for the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component

## [2.0.1] - 23-05-2023
### Added

- New Twilight minor version `2.12.0` is released, which includes:
  - Disable `add-to-cart` button while loading in the following JS Web Components:
      - [`salla-add-product-button`](doc-422692?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-cart-summary`](doc-422695?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-gifting`](doc-422705?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-rating-modal`](doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-social-share`](doc-422736?nav=01HNFTE06J4QC24T0D5BPRYKMD)
      - [`salla-user-settings`](doc-422741?nav=01HNFTE06J4QC24T0D5BPRYKMD)
  - Show current phone/email on the [`salla-verify`](doc-422742?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component


## [1.0.3] - 21-05-2023
### Added

- JS Web Components - Auto Play property added to the [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) component.

## [1.0.2] - 16-05-2023

### Added

- Added the [`salla-filters`](doc-422704?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component to the Elements JS Web Components

### Added

- The [`salla-product-list`](doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component has support for the property `Sort By`
- The [`salla-products-slider`](doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component has support for the property `Limit`

## [1.0.1] - 01-03-2023

### Added

- Added the endpoints [Fetch](doc-422682), [Get Page Comemnts](doc-422683), and [Get Product Comemnt](doc-422684) to the Comment API.

---

## 📙-what-you'll-learn/Comment

# Comment

## Docs

- [Add Comment](https://docs.salla.dev/422681m0.md): The customer can add their review to the merchant's store using the *add* endpoint. The comment can be about a specific product or a specific page.
- [Fetch](https://docs.salla.dev/422682m0.md): The *fetch* endpoint allows you to retrieve comments related to a particular object or resource within the platform. By making a request to this endpoint, you can retrieve comments made by users or customers, providing valuable insights, feedback, and discussions related to the specific object.
- [Get Page Comments](https://docs.salla.dev/422683m0.md): The *get page comments* endpoint enables you to retrieve comments associated with a specific page identified by its pageId. By making a request to this endpoint, you can retrieve comments made by users or customers on the specified page.
- [Get Product Comments](https://docs.salla.dev/422684m0.md): The *get product comments* endpoint enables you to retrieve comments associated with a specific product identified by its productId. By making a request to this endpoint, you can retrieve comments made by users or customers on the specified product.

---

## 📙-what-you'll-learn/Component

# Component

## Docs

- [Reviews](https://docs.salla.dev/705836m0.md): This endpoint retrieves reviews from various sources such as store, products and more.
- [Menus](https://docs.salla.dev/705835m0.md): This endpoint retrieves menus for a specified component, such as `"header"` or `"footer"`. It is commonly used to fetch menus for a particular component in your theme, typically for dynamically rendering navigation or other UI elements. While `"header"` is the default component, you can specify `"footer"` where needed.

---

## 📙-what-you'll-learn/Currency

# Currency

## Docs

- [Change](https://docs.salla.dev/422679m0.md): This endpoint is used to *change* the currency of a merchant's store and to represent prices for the products. Although the store payouts can be in a different currency, the customer can choose any of the currencies mentioned in the currency selection to display the prices.
- [List](https://docs.salla.dev/422680m0.md): This endpoint is used to list the currencies of a merchant's store. Although the store payouts can be in a different currency, the store's owners can list the different available currencies in the store.

---

## 📙-what-you'll-learn/Customize-Twilight-Web-Components-–-Theme-Components-Customization-Tailwind-Theming-Guide-Salla-Stor

# Components Customization

Using **Twilight**, it's easy to change how the **user interfaces (UI)** of the JS Web Components look. This is to enable better user interface consistency throughout the theme and to prevent data from being hard-coded. The user interface can be customized in a variety of ways, including changing the colors, fonts, layouts, and sizes of its components.

In this article, we'll explore how the components' UI customization works, Tailwind installation and configuration, as well as the different ways to modify the look-and-feel of the JS Web Components.

## 📙 What you'll learn
- How it works
- Tailwind Installation and Confiuragtion
- Components UI customization

## How it works

**Twilight Web Components** are based on the basis and configuration of the [Tailwind CSS Framework](https://tailwindcss.com/). This ensures that all web components are easily customizable and that all output CSS styles comply with [Tailwind's configuration](https://tailwindcss.com/docs/configuration).

In order to make a general customization of the theme's overall look-and-feel, the file `tailwind.config.js` can be modified. The following is the default source code for this file, from which we can see how to change the values related to the theme's `colors`, `font`, and more.

:::tip[Note]
More information about this configuration file can be found [here](https://tailwindcss.com/docs/configuration).
:::

```js title="tailwind.config.js"
module.exports = {
...
  theme: {
    screens: {
      sm: '480px',
      md: '768px',
      lg: '976px',
      xl: '1440px',
    },
    colors: {
      'blue': '#1fb6ff',
      'purple': '#7e5bef',
      'pink': '#ff49db',
      'orange': '#ff7849',
      'green': '#13ce66',
      'yellow': '#ffc82c',
      'gray-dark': '#273444',
      'gray': '#8492a6',
      'gray-light': '#d3dce6',
    },
    fontFamily: {
      sans: ['Graphik', 'sans-serif'],
      serif: ['Merriweather', 'serif'],
    },
    extend: {
      spacing: {
        '128': '32rem',
        '144': '36rem',
      },
      borderRadius: {
        '4xl': '2rem',
      }
    }
  }
...
}
```


## Custom CSS framework

Twilight Web Components use the same [CSS Variables](https://docs.salla.dev/doc-421945?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) that have already been introduced. That means the developer also has the flexibility to use self-developed CSS styles away from the [Tailwind CSS Styles](https://tailwindcss.com/docs/utility-first).

The core idea here is that each component has its own CSS class, which allows the developer to implement the style as he wishes. For example, the JS Web Component [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) comes with the following CSS class:

```css
.s-button{
  &-wrap{
    
  }
  &-element{
    
  }
  &-link{
    
  }
  &-icon{
    
  }
....
}
```
In the above example, developers can add customizable styles to change, for example, the button's `link` and `icon`. In the coming articles of this documentation, we will explore how the UI for each JS Web Component can be modified using its `.scss` file.

---

