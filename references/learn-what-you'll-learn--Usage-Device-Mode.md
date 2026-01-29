# Learn What You'Ll Learn  Usage Device Mode

## Table of Contents

- [📙-what-you'll-learn/Usage-Device-Mode](#📙-what-you'll-learn-usage-device-mode)
- [📙-what-you'll-learn/User](#📙-what-you'll-learn-user)
- [📙-what-you'll-learn/Welcome-to-Salla-CLI-Salla-CLI-Salla-Docs](#📙-what-you'll-learn-welcome-to-salla-cli-salla-cli-salla-docs)
- [📙-what-you'll-learn/Wishlist](#📙-what-you'll-learn-wishlist)

---

## 📙-what-you'll-learn/Usage-Device-Mode

# Usage - Device Mode

Device Mode integration allows tracking customer events on mobile or web platforms through embedding a Javascript tracker on the store that listens to the desired events and allows partners to process these events in realtime.

----


## App Snippet Requirement

Using Device Mode integration requires an [**App Snippet**](https://salla.dev/blog/a-guide-to-app-snippet/) to inject the Javascript tracker to listen and process e-commerce events.

---

## Getting Started

### Prerequisites
- Node.js (version 16 or higher)
- pnpm (recommended) or npm

### 1. Cloning the Starter Kit & Installing Dependencies

To prepare the tracker, Salla provides a [starter kit](https://github.com/SallaApp/store-events-tracker-starter-kit) that allows you to quickly implement the events you are interested in listening and process them easily.

```bash
git clone https://github.com/SallaApp/store-events-tracker-starter-kit
```
Once you have cloned the repository, it's time to install the required dependencies.

```bash
cd store-events-tracker-starter-kit
pnpm install
```

### 2. Preview Events

The starter kit ships with an `example.html` in the root of the project, which allows you to easily verify existing events as well as any new events you may add.

To preview the events, run the development server:

```bash
pnpm run dev
```
Then, open the `example.html` file in your browser and interact with the page to trigger the events and verify them in the browser console.

### 3. Customizing Event Logic

The starter kit provides boilerplate code for each event located in the `/src/listeners/` directory.

You can easily customize the logic as required for each event.
In this example, we modify the `Cart Updated` listener to post the event payload to a webhook URL:

```js
// File: src/listeners/cart-updated.ts
import {
  CartUpdatedPayload,
  EcommerceEvents,
} from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.CART_UPDATED;

export default async (payload: CartUpdatedPayload): Promise<void> => {
  // Your custom logic here
  try {
    const response = await fetch("https://acme.com/webhook", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        event: eventName,
        payload,
      }),
    });

    if (!response.ok) {
      console.error(
        `Failed to send webhook: ${response.status} ${response.statusText}`
      );
    }
  } catch (error) {
    console.error("Error sending webhook:", error);
  }
};

```

### 4. Adding New Events

As we continue to add more events, you may update your project anytime by creating your own listeners to observe those events. The build system automatically wires new listeners as long as you follow the existing pattern.

- Create a new TypeScript file in `/src/listeners/`
```js
import { EventPayload, EcommerceEvents } from "@salla.sa/ecommerce-events-base";

export const eventName = EcommerceEvents.YOUR_EVENT_NAME;

export default (payload: EventPayload): void => {
  console.log("YOUR EVENT:", payload);
  // Add your custom logic here
};
```

### 5. Publishing Your Tracker

Once you are happy with your tracker, it's time to publish and start testing it.

Follow these steps to publish your tracker:

#### 5.1. Create an App in Salla Partners Portal
- Visit [https://portal.salla.partners](https://portal.salla.partners)
- Sign in with your Salla Partners account
- Create a new app and configure its basic settings
- Note down your app's details for the next steps

#### 5.2. Build and Upload the Tracker
- Build your tracker for production:
```bash
pnpm run build
```
This creates a `dist/tracker.js` file containing your compiled tracker.
- Upload the `dist/tracker.js` file to your preferred CDN service (e.g., AWS CloudFront, Cloudflare, or any other CDN)
- Make note of the CDN URL where your `tracker.js` file is hosted

#### 5.3. Add Tracker as Snippet
- In the [Salla Partners Portal](https://portal.salla.partners/), navigate to your app
- Go to the ["Snippet"](https://salla.dev/blog/a-guide-to-app-snippet/) section
- Add a new Snippet with the CDN URL of your `tracker.js` file

#### 5.4. Test in Demo Store
- Install your app in the demo store provided by Salla Partners Portal
- Navigate through the demo store and perform various actions (view products, add to cart, checkout, etc.)
- Open browser developer tools and check the console to verify your event listeners are working correctly
- Test all the events you've customized to ensure they're tracking properly

#### 5.5. Publish the App
- Once you've verified everything works correctly in the demo store
- Return to the [Salla Partners Portal](https://portal.salla.partners/)
- Navigate to your app and publish the changes
- Your tracker will now be available for merchants to install and use
---

### Development Commands

- **Start development server**:

```bash
pnpm dev
```

This starts the Vite development server with hot reload

- **Build for production**:

```bash
pnpm build
```

Compiles TypeScript and bundles the project

- **Preview production build**:

```bash
pnpm preview
```

Serves the production build locally for testing

- **Type checking**:

```bash
pnpm type-check
```

Runs TypeScript compiler to check for type errors

---

### Debugging

- Use browser developer tools to inspect console logs
- Check the Network tab for any failed requests
- Verify that the Twilight SDK is properly loaded before the tracker initializes
- Use TypeScript's type checking to catch errors early: `pnpm type-check`

---

### Important Notes

- **Testing**: Always thoroughly test your tracker in the demo store before publishing
- **Performance**: Ensure your tracker doesn't negatively impact store performance
- **Error Handling**: The built-in error handling ensures individual listener failures don't break the entire tracking system
- **Updates**: When you make changes to your tracker, repeat the build and upload process, then update the snapbit URL if necessary

---

### Troubleshooting

- **Events not firing**: Check that the Salla Twilight SDK is properly loaded before your tracker
- **Console errors**: Review your event listener implementations for any JavaScript errors
- **Missing events**: Verify that all your custom event listeners are properly exported and follow the correct pattern

---

## 📙-what-you'll-learn/User

# User

## Docs

- [Cart Summary](https://docs.salla.dev/422695m0.md): The `<salla-cart-summary>` web component is used to show the icon of the shopping cart with a small circle badge indicating the number of items in the cart.
- [Localization](https://docs.salla.dev/422710m0.md): The `<salla-localization-modal>` web component shows the menu for the store's available languages and currencies. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component that shows the menu for the store's available languages and currencies, and that can be customized using the properties' parameters.
- [Login](https://docs.salla.dev/422711m0.md): The `<salla-login-modal>` web component displays the login form, which prompts a user for their credentials in order to authenticate their access. It usually comprises of the standard username or email as well as a phone number. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component, and that can be customized using the properties' parameters available.
- [Loyalty](https://docs.salla.dev/422712m0.md): The `<salla-loyalty>` web component is used to display a popup that represents the Loyalty program. This program enables the store's customers to benefit from collecting the points for vouchers and offers provided by the store. Once they have collected enough points, the customers will be eligible to redeem them for exciting gifts or products.
- [Rating](https://docs.salla.dev/422728m0.md): The `<salla-rating-modal>` web component is used to display the rating scale for a store, product, or shipping company. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component, and that can be customized using the properties' parameters available.
- [User Menu](https://docs.salla.dev/422740m0.md): The `<salla-user-menu>` web component is used to show a navigation menu list with links that route users to accomplish user-related functions including Login, Logout, Profile, Sign Up, and more.
- [User Profile](https://docs.salla.dev/482367m0.md): This `<salla-user-profile>` web component allows the user to display the user information, this can be customised to display information such as Name, Email, Phone Number. 
- [User Settings](https://docs.salla.dev/422741m0.md): The `<salla-user-settings>` web component allows the user to manage their account settings such as enabling notifications and closing accounts, and that can be customized using the properties' parameters available.
- [Verify](https://docs.salla.dev/422742m0.md): The `<salla-verify>` web component used to show fields for verifying email/mobile of users by sending OTP verification code during registration, [login](https://docs.salla.dev/doc-422711?nav=01HNFTE06J4QC24T0D5BPRYKMD), or profile update, and that can be done using the properties' parameters available.

---

## 📙-what-you'll-learn/Welcome-to-Salla-CLI-Salla-CLI-Salla-Docs

# Welcome to Salla CLI 👋 

A Command Line Interface (CLI) is a program that accepts text inputs to execute operating system functions. [Salla CLI](https://github.com/SallaApp/Salla-CLI) is a tool designed for developers to create Salla Apps and Themes, which works with the [Salla APIs](https://docs.salla.dev/). After that, the Apps and Themes can go through [publishing process](https://salla.dev/blog/standards-salla-apps-publications/) to be available in the [Salla App Store](https://apps.salla.sa/) and installed in any of the [Salla Merchant Stores](https://salla.sa/site/).

:::tip[Tip]
Salla CLI tool is developed by Salla team to help in [creating Salla Apps](https://docs.salla.dev/doc-422768) and [Themes](https://docs.salla.dev/doc-422775?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) by using only **1-command**!
:::


### Prerequisites

The basic Salla CLI prerequisites that the developers need are:

- Create a partner account on **[Salla Partners Portal](https://salla.partners/)**.
- For Salla CLI's compatibility: **[Nodejs](https://nodejs.org/en/)** LTS>= 16.13.1 and **[npm](https://www.npmjs.com/)**>= 6.14.0.
- Other optional requirements: **[PHP](https://www.php.net/)** >= 8.2, **[composer](https://getcomposer.org/)** package manager.

### What is Salla CLI usage?

[Salla CLI](https://github.com/SallaApp/Salla-CLI) comes with an easy to use set of straightforward commands that do the complete setup for Salla Apps and Themes. The following table shows the commands grouped by [_Apps commands_](https://docs.salla.dev/doc-422767?nav=01HNA8QHCPJTCY5VSEZ616JCAK) for app-related commands and [_Themes commands_](https://docs.salla.dev/doc-422774?nav=01HNA8QHCPJTCY5VSEZ616JCAK) for theme-related commands.

**Apps commands**
|----|
|[Create App](https://docs.salla.dev/doc-422768?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Create Webhook](https://docs.salla.dev/doc-422769?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Delete](https://docs.salla.dev/doc-422770?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Link](https://docs.salla.dev/doc-422771?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[List and Info](https://docs.salla.dev/doc-422772?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Serve](https://docs.salla.dev/doc-422773?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|

**Themes commands**
|----|
|[Create](https://docs.salla.dev/doc-422775?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Preview](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[List](https://docs.salla.dev/doc-422777?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Delete](https://docs.salla.dev/doc-422778?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|
|[Publish](https://docs.salla.dev/doc-422968?nav=01HNA8QHCPJTCY5VSEZ616JCAK)|

### About Salla CLI documentation

This documentation is carefully designed to provide information about [Salla CLI](https://github.com/SallaApp/Salla-CLI) to create and maintain Apps and Themes. The documentation is regularly updated and enhanced based on our developers' valuable feedback.
:::info[Information]
Join the Salla Developers Community on [Telegram](https://t.me/salladev)

---

## 📙-what-you'll-learn/Wishlist

# Wishlist

## Docs

- [Add](https://docs.salla.dev/422654m0.md): This endpoint adds a product to the customer's wishlist. A customer's wishlist is a collection of desired products saved to the customer's account, indicating interest but not an immediate intent to buy. 
- [Remove](https://docs.salla.dev/422655m0.md): This endpoint removes a product to the customer's wishlist. A customer's wishlist is a collection of desired products saved to the customer's account, indicating interest but not an immediate intent to buy. 
- [Toggle](https://docs.salla.dev/422656m0.md): This endpoint switches a product's addition or removal from the customer's wishlist. It simply calls the other endpoints [Add](https://docs.salla.dev/doc-422654?nav=01HNFTDZPB31Y2E120R84YXKCX) and [Remove](https://docs.salla.dev/doc-422655?nav=01HNFTDZPB31Y2E120R84YXKCX) as needed. A copy of the customer's wishlist is saved in the [broswer local storage](https://docs.salla.dev/doc-422613?nav=01HNFTDZPB31Y2E120R84YXKCX) to speed the process of retrieving its content. Based on the content of the wishlist in the local storage, the items will be added or removed.

---

