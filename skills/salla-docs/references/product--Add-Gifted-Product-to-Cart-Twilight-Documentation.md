# Product  Add Gifted Product To Cart Twilight Documentation

## Table of Contents

- [product/Add-Gifted-Product-to-Cart-Twilight-Documentation](#product-add-gifted-product-to-cart-twilight-documentation)
- [product/Fetch-Product-List-Twilight-Documentation](#product-fetch-product-list-twilight-documentation)
- [product/Fetch-Product-Options-Twilight-Documentation](#product-fetch-product-options-twilight-documentation)
- [product/Fetch-Product-Size-Guides-Salla-Developer-Documentation-Twilight-Documentation](#product-fetch-product-size-guides-salla-developer-documentation-twilight-documentation)
- [product/Get-Product-Details-Twilight-Documentation](#product-get-product-details-twilight-documentation)
- [product/Get-Product-Offer-Details-Twilight-Documentation](#product-get-product-offer-details-twilight-documentation)
- [product/Get-Product-Price-Twilight-Documentation](#product-get-product-price-twilight-documentation)
- [product/Product-Availability-Subscription-Twilight-Documentation](#product-product-availability-subscription-twilight-documentation)
- [product/Retrieve-Gift-Product-Details-Twilight-Documentation](#product-retrieve-gift-product-details-twilight-documentation)
- [product/Retrieve-Product-Categories-Twilight-Documentation](#product-retrieve-product-categories-twilight-documentation)
- [product/Salla-Add-Product-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-add-product-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Advertisement-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-advertisement-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Comments-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-comments-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Conditional-Offer-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-conditional-offer-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Gifting-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-gifting-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Installment-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-installment-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Meta-Data-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-meta-data-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Offer-Modal-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-offer-modal-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Offer-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#product-salla-offer-salla-storefront-web-components-twilight-documentation-salla-docs)
- [product/Salla-Orders-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-orders-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Payments-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-payments-salla-storefront-twilight-documentation-salla-docs)

---

## product/Add-Gifted-Product-to-Cart-Twilight-Documentation

# Add Gift To Cart

This endpoint is used to add a product that has been gifted to the shopping cart, after which the customer can be redirected to the shopping cart page in order to complete the purchase of that product as a solo.

:::tip
The *add gift to cart* endpoint has been implemented in the [Gifting](https://docs.salla.dev/doc-422705?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::

## Payload `authenticated`

<DataSchema id="1427536" />


## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427537" />
      
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
  </Tab>
  
</Tabs>



## Usage
To perform the action of adding a product that has been gifted to the shopping cart, the developer may call the method `addGiftToCart` as follows.


```js
salla.product.addGiftToCart({
  product_id: 258741,
  payload: Object,
  withRedirect: false
}).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onAddGiftToCartSucceeded and onAddGiftToCartFailed events.

### onAddGiftToCartSucceeded
This event is triggered when the action of adding a product that has been gifted to the shopping cart is done without having any errors coming back from the backend.

```js
salla.product.event.onAddGiftToCartSucceeded((response) => {
  console.log(response)
});
```
### onAddGiftToCartFailed
This event is triggered when the action of adding a product that has been gifted to the shopping cart is not completed and an error has occurred.

```js
salla.product.event.onAddGiftToCartFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Fetch-Product-List-Twilight-Documentation

# Fetch

This endpoint is used for fetching product lists from a Merchant Store. The endpoint accepts query parameters that are validated to ensure they are of the correct data type. If the validation succeeds, a GET request is made to the API endpoint and the response is returned. If the validation fails, an error message is returned via a Promise. 

:::tip
The *fetch* endpoint has been implemented in the [Product List](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::

## Payload


<DataSchema id="1387254" />



## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427819" />
   
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
  </Tab>
  
</Tabs>


## Usage
To perform the action of retrieving a list of products, the developer may call the method fetch() as follows. For this method we define the query parameters as an object with a source property of `categories` and a source_value property of an array `[1, 2, 3]`. We then call the `fetch()` method of the salla.product object and pass in the query parameters as an argument.


```js
// Define the query parameters
const queryParams = {
  source: 'categories',
  source_value: [1, 2, 3]
};

// Call the fetch method
salla.product.fetch(queryParams)
  .then((response) => {
    // Do something with the response data
    console.log(response);
  })
  .catch((error) => {
    // Handle any errors that occur
    console.error(error);
  });
```


## Events
This endpoint may trigger two events, the onProductListFetchSucceeded and onProductListFetchFailed events.

### onProductListFetchSucceeded
This event is triggered when the action of retrieving a list of products is done without having any errors coming back from the backend.

```js
salla.product.event.onProductListFetchSucceeded((response) => {
  console.log(response)
});
```
### onProductListFetchFailed
This event is triggered when the action of retrieving a list of products is not completed and an error has occurred.

```js
salla.product.event.onDetailFetchFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Fetch-Product-Options-Twilight-Documentation

# Fetch Options

This endpoint is used for fetching related data that is useful to include in the product, such as reviews, ratings, categories, or any other related entities.

The `includes` parameter is an optional part of the `FetchProductsQueryParams` interface. It allows you to list related data that should be included in the response when fetching products. This way, you can get more detailed information in one request, without making multiple API calls.

:::tip
The *fetchOptions* endpoint has been implemented in the [fetch product](https://docs.salla.dev/doc-422650/?nav=01HNFTDZPB31Y2E120R84YXKCX) endpoint, and It's all set up to save developer's time and effort.
:::

## Payload


<DataSchema id="2534851" />

## Response
<Tabs>
  <Tab title="Success">

      
<DataSchema id="2524739" />
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
  </Tab>
  
</Tabs>


## Usage

Define an array, `productIds`, and pass the product IDs. Then, call the `salla.product.api.fetchOptions` method from and pass in the `productIds` array. The method returns a promise, and the result, stored in `productOptions`, contains the options for the specified products.

> 📝 You can use the [`"fetch()"`](https://docs.salla.dev/doc-422650/?nav=01HNFTDZPB31Y2E120R84YXKCX) API with the `"includes"` query parameter to fetch a list of product options

```js
const productIds = [34253234, 123353455, 67567567]
const productOptions = await salla.product.api.fetchOptions(productIds)
```


## Events
This endpoint may trigger two events, the onProductOptionsFetched and onProductOptionsNotFetched events.

### onProductOptionsFetched
This event is triggered when the action of fetching product options is done without having any errors coming back from the backend.

```js
salla.product.event.onProductOptionsFetched((response) => {
 console.log(response);
});
```
### onProductOptionsNotFetched
This event is triggered when the action of fetching product options is not completed and an error has occurred.

```js
salla.product.event.onProductOptionsNotFetched((error) => {
 console.log(error);
});
```

---

## product/Fetch-Product-Size-Guides-Salla-Developer-Documentation-Twilight-Documentation

# Size Guides

This endpoint is used to fetch the size guide for a specific product in an online store. The endpoint takes a `product_id` parameter, which is the ID of the product for which the size guide is being fetched.

:::tip
The *Size Guides* endpoint has been implemented in the [Product Size Guide](https://docs.salla.dev/doc-422721?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::
## Payload


<DataSchema id="1387260" />

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1387261" />
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>



## Usage
To perform the action of retrieving the size guide for any product, the developer may call the method `getSizeGuides()` and pass in the product ID as an argument as follows:

```js
// Call the getSizeGuides method with a product ID
salla.product.getSizeGuides(12345)
  .then(response => {
    // Do something with the size guide data
    console.log(response);
  })
  .catch(error => {
    // Handle any errors that occur
    console.error(error);
  });
```


## Events
This endpoint may trigger two events, the `onSizeGuideFetched` and `onSizeGuideFetchFailed` events.

### onSizeGuideFetched
This event is triggered when the action of retrieving the size guide for any product is done without having any errors coming back from the backend.

```js
salla.product.event.onSizeGuideFetched((response) => {
  console.log(response)
});
```
### onSizeGuideFetchFailed
This event is triggered when the action of retrieving retrieving the size guide for any product is not completed and an error has occurred.

```js
salla.product.event.onSizeGuideFetchFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Get-Product-Details-Twilight-Documentation

# Get Product Details

This endpoint is used to return information about a particular product to the user.

:::tip
The *get details* endpoint has been implemented in the [Product Options](https://docs.salla.dev/doc-422720?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::


## Payload


<DataSchema id="1387256" />


## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427797" />
   
      
  </Tab>
   <Tab title="Error">
  
<DataSchema id="1427184" />
  </Tab>
  
</Tabs>



## Usage
To perform the action of retrieving product details, the developer may call the method getDetails() as follows:


```js
salla.product.getDetails(23345, ["images", "sold_quantity", "category"])
  .then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onDetailFetched and onDetailFetchFailed events.

### onDetailFetched
This event is triggered when the action of retrieving product details is done without having any errors coming back from the backend.

```js
salla.product.event.onDetailFetched((response) => {
  console.log(response)
});
```
### onDetailFetchFailed
This event is triggered when the action of retrieving product details is not completed and an error has occurred.

```js
salla.product.event.onDetailFetchFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Get-Product-Offer-Details-Twilight-Documentation

# Offer details

This endpoint is used to fetch any offered items related to the product. Other products may be offered along with the product as an offer from the merchant. This endpoint displays all of the items as an offer.

:::tip
The *product offers* endpoint has been implemented in the [Offer](https://docs.salla.dev/doc-422715?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::

## Payload


<DataSchema id="1427499" />

## Response
<Tabs>
  <Tab title="Success">
      
      
<DataSchema id="1387248" />
      
       
  </Tab>
   <Tab title="Error">
       

<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>


## Usage
To perform the action of fetching any offered items related to the product, the developer may run the `details()` method as below.


```js
salla.product.offers({ id: 12345 }).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.product.offers(12345).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onOfferExisted, onOffersFetched and onFetchOffersFailed events.

### onOfferExisted
This event is triggered when fetching any existed offer related to the product is done without having any errors coming back from the backend.

```js
salla.event.product.onDetailsFetched((response) => {
  console.log(response)
});
```

### onOffersFetched
This event is triggered when fetching any offered items related to the product is done without having any errors coming back from the backend.

```js
salla.event.product.onOffersFetched((response) => {
  console.log(response)
});
```
### onFetchOffersFailed
This event is triggered when fetching any offered items related to the product is not completed and an error has occurred.

```js
salla.event.product.onFetchOffersFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Get-Product-Price-Twilight-Documentation

# Get price

This endpoint returns the price of a product. It only needs the id of the product whose price is on need.

## Payload

<DataSchema id="1427476" />

## Response
<Tabs>
  <Tab title="Success">
      
<DataSchema id="1427477" />
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>

## Usage
To perform the action of getting a product's price, the developer may call the method `getPrice()` along with the product's id.

#### Simple Product

```js
salla.product.getPrice({
    id: 1234,
    quantity: 1,
    notes: "please i need to get the red color"
}).then((response) => {
    /* add your code here */
});
```


#### Variable product

```js
salla.product.getPrice({
    id: 1234,
    quantity: 1,
    options: {
      117414452: 11232214, // option value id (select choice)
      117414412: 11232514, // option value id (select choice)
    },
    notes: "please i need to get the red color"
}).then((response) => {
    /* add your code here */
});
```

## Events
This endpoint may trigger two events, the onPriceUpdated and onPriceUpdateFailed events.

### onPriceUpdated
This event is triggered when getting a product's price is done without having any errors coming back from the backend.

```js
salla.event.product.onPriceUpdated((response) => {
  console.log(response)
});
```
### onPriceUpdateFailed
This event is triggered when getting a product's price is not completed and an error has occurred.

```js
salla.event.product.onPriceUpdateFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Product-Availability-Subscription-Twilight-Documentation

# Product availability

This endpoint helps the customer in the absence of a product's stock. A customer may need to subscribe to that product availability subscription list in order to be notified once the stock is available for purchase again. 

:::tip
The *product availability* endpoint has been implemented in the [Product Availability](https://docs.salla.dev/doc-422717?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and it's ready for use.

:::
## Payload

<DataSchema id="1427481" />

## Response
<Tabs>
  <Tab title="Success">
 
<DataSchema id="1427486" />
  </Tab>
   <Tab title="Error">
       
<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>



## Usage
To enable the customer to subscribe to a product and get notification once its stock is available, the developer can use the method `availabilitySubscribe()` to receive the customer's contact information and add them to the product availability subscription list.

#### Logged User


```js
// product id: 12345
salla.product.availabilitySubscribe({
  id: 12345
}).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.product.availabilitySubscribe(12345).then((response) => {
  /* add your code here */
});
```
#### Guest (Mobile)

```js
salla.product.availabilitySubscribe({
  id: 12345,
  country_code: "+966",
  mobile: "55558887",
}).then((response) => {
      /* add your code here */
});
```

#### Guest (Email)


```js
salla.product.availabilitySubscribe({
  id: 12345,
  email: "user@email.com",
}).then((response) => {
      /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onAvailabilitySubscribed and onAvailabilitySubscribedFailed events.

### onAvailabilitySubscribed
This event is triggered when subscribing a customer to a product availability subscription list is done without having any errors coming back from the backend.

```js
salla.event.product.onAvailabilitySubscribed((response) => {
  console.log(response)
});
```
### onAvailabilitySubscribedFailed
This event is triggered when subscribing a customer to a product availability subscription list is not completed and an error has occurred.

```js
salla.event.product.onAvailabilitySubscribedFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Retrieve-Gift-Product-Details-Twilight-Documentation

# Get Gift Details

This endpoint provides the details of the gifted product, along with any related entities, such as images and texts associated with the gift.

 
:::tip
The *get gift details* endpoint has been implemented in the [Gifting](https://docs.salla.dev/doc-422705?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component , and It's all setup to save developer's time and effort.
:::

## Payload


<DataSchema id="1387239" />

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427523" />
  
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>


## Usage
To perform the action of providing the details of the gifted product, the developer may call the method `getGiftDetails()` as follows.


```js
salla.product.getGiftDetails({ product_id: 852369 }).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onGiftFetched and onGiftFetchFailed events.

### onGiftFetched
This event is triggered when the action of providing the details of the gifted product is done without having any errors coming back from the backend.

```js
salla.product.event.onGiftFetched((response) => {
  console.log(response)
});
```
### onGiftFetchFailed
This event is triggered when the action of providing the details of the gifted product is not completed and an error has occurred.

```js
salla.product.event.onGiftFetchFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Retrieve-Product-Categories-Twilight-Documentation

# Categories

This endpoint lists all of the products within a given category. Categories aid in the organisation of products so that visitors may quickly find what they're looking for in the store.

## Payload

<DataSchema id="1427521" />

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427522" />
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
  </Tab>
  
</Tabs>



## Usage
To perform the action of retriving the categories for a product, the developer may call the method `categories()` as follows.


```js
salla.product.categories({ id: 17 }).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.product.categories(17).then((response) => {
  /* add your code here */
});
```

More about adding Categories as a component in this clip.


<Video src="https://youtu.be/WgItYTCSISI?si=GGjP7A5durx_A1To
"></Video>


## Events
This endpoint may trigger two events, the onCategoriesFetched and onCategoriesFailed events.

### onCategoriesFetched
This event is triggered when retriving the categories for a product is done without having any errors coming back from the backend.

```js
salla.event.search.onCategoriesFetched((response) => {
  console.log(response)
});
```
### onCategoriesFailed
This event is triggered when retriving the categories for a product is not completed and an error has occurred.

```js
salla.event.search.onCategoriesFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Salla-Add-Product-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Add Product

The `<salla-add-product-button>` web component allows controllability over button text labels and behaviours based on the `product-status` and `product-type` properties. It consists of [Product Availability](https://docs.salla.dev/doc-422717?nav=01HNFTE06J4QC24T0D5BPRYKMD) component and [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component.

:::tip[Note]
Available API Endpoints for the Add Product component are:

- [Product Availability](https://docs.salla.dev/doc-422642?nav=01HNFTE06J4QC24T0D5BPRYKMD)
:::

## Example

<!--
focus: false
-->

![Add Product Example](https://cdn.salla.network/docs/twilight/6/js-web-add-to-cart-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Add Product Button component usage -->
<salla-add-product-button width="wide" product-id="2233214522">
  Add to Cart
</salla-add-product-button>
```      
  </Tab>
    
<Tab title="JS">
        
```js
const AddProductButton = document.querySelector('salla-add-product-button');

AddProductButton.addEventListener('failed', event => {
  salla.logger.warn('Add to cart api request failed', event);
})

AddProductButton.addEventListener('success', event => {
  salla.logger.warn('Add to cart api request done', event);
})
```      
  </Tab>  
    <Tab title="SASS">

```css
:host {
  display: block;
}

salla-add-product-button[width=wide] {
  width: 100%;
}
```      
  </Tab>  
  
</Tabs>

## Properties

| Property        | Attribute         | Description                                                                                                                                                                                                                              | Type                                                                                         | Default     |
| --------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------- |
| Channels        | `channels`        | Available notification channels                                                                                                                                                                                                          | `string`                                                                                     | `null` |
| Donating Amount | `donating-amount` | Donation amount value                                                                                                                                                                                                                    | `number`                                                                                     | `'0'`       |
| Notify Options Availability | `notify-options-availability` | Listen to Product Options availability.                 | `boolean`                         
| Product ID      | `product-id`      | Product ID under which the merchant can sign up for an availability notice                                                                                                                                                               | `any`                                                                                        | `undefined` |
| Product Status  | `product-status`  | Product status based on the allowed type values.                                                                                                                                                                                         | `"out" \| "out-and-notify" \| "sale"`                                                        | `'sale'`    |
| Product Type    | `product-type`    | Product type based on the allowed type values.                                                                                                                                                                                           | `"codes" \| "digital" \| "donating" \| "food" \| "group_products" \| "product" \| "service"` | `'product'` |
| Quantity        | `quantity`        | Passing custom quantity number to be injected within the component, which affects `sale` product statuses as the [Quantity Input](doc-422724?nav=01HNFTE06J4QC24T0D5BPRYKMD) component will be customized with the number passed. | `number`                                                                                     | `'0'`       |
| Quick Buy                  | `quick-buy`                   | Support for the Quick Pay Button                                | `boolean`                                                                                                 | `undefined` |
| Subscribed Options         | `subscribed-options`          | Shows the Subscribed Options ex: "[[139487,2394739],[1212,1544]]" | `string`                                                                                                  | `undefined` |
| Support Sticky Bar          | `support-sticky-bar`          | Support for themes that have a sticky bar                   | `boolean`                                                                                                 | `undefined` |

:::tip[Note]
- The Product Status `out` refers to the product being out of sale where a disabled button is labeled as "Sold Out". The `out-and-notify` type is where the [Product Availbility component](https://docs.salla.dev/doc-422717?nav=01HNFTE06J4QC24T0D5BPRYKMD) takes place as Merchants are allowed to subscribe when the specific product becomes available.
- The Product Status `sale` is where the specified product is currently under sale which will allow for a [Button component](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) to appear and be labeled as "Add to Cart".
- Each Product Type customizes how certain button labels appearance. For instance, if `product-type` is set to `donating`, then the label `Donate` will appear when `product-status` is set to `sale`.
:::


## Events

| Event     | Description                                                                      | Type               |
| --------- | -------------------------------------------------------------------------------- | ------------------ |
| `failed`  | This event will be fired when the Add Product to the cart fails    | `CustomEvent<any>` |
| `success` | This event will be fired when the Add Product to the cart succeeds | `CustomEvent<any>` |


:::tip[Fast Checkout Feature]

Salla has made buying easier by adding several payment options directly to the product details page. 
Now, customers can complete their transactions using most common payment methods without needing to go to a different page. This approach aims to provide a seamless and convenient shopping experience in Salla Merchants’ stores for their customers.

The payment interface is displayed in a pop-up modal, enabling customers to:
- View cart summary,  price details, including discounts, shipping costs, and more.
-  Apply / remove discount coupons.
- Select an existing delivery address or add a new one.
- Choose a preferred shipping company.
- Pay using one of four different payment methods, which are:
    • Apple Pay
    • Credit cards (Visa, MasterCard, or Mada)
    • Installment plans (Tabby and Tamara)
    • Cash on delivery
:::

:::caution[Alert]
This component is not allowed to be customized by the developer and can only be called to the Theme. Only three properties can be customized using their CSS variables, height, width, border-radius:

```
salla-mini-checkout-widget {  
--salla-fast-checkout-button-height: 2.5rem;
  --salla-fast-checkout-button-width: 100%;
  --salla-fast-checkout-button-border-radius: 0.375rem;
}
```
:::

---

## product/Salla-Advertisement-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Advertisement



The `<salla-advertisement>` web component allows you to displays Advertisement items such as icons, URLs, target, description, with the ability to edit the Advertisement background and text color.
## Example

<!--
focus: false
-->

![Alt text](https://cdn.salla.network/docs/twilight/6/js-web-advertisement-01.png)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<salla-advertisement slot="icon"></salla-advertisement>
```
</Tab>
  <Tab title="SASS">

This JS web component can be targeted for styling by its `:host` class. Following is a complete source code for customizing this component:

```css
:host {
  display: block;
}
```
  </Tab>
</Tabs>


## Slots
The`slots` makes it customizable to modify certain labels, such as `adv`.

| Slot   | Description |
| ------ | ----------- |
| `adv` | Replaces the advertisment component with any of the following slots: `{icon}`, `{url}`, `{target}`, `{description}`, `{bg_color}`, and `{text_color}`.    	|

---

## product/Salla-Comments-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Comments


The `<salla-comments>` web component allows the user to enter textual contents as a comment for a Product or Page.

## Example


![Comments image](https://cdn.salla.network/docs/twilight/6/js-web-comments-01.png)

## Usage


<Tabs>
  <Tab title="HTML">
```html
<salla-comments
  type="product"
  item-id="154684624"
  hide-form = false>
</salla-comments>
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

## Properties

| Property | Attribute | Description | Type	| Default |
| -------- | --------- | ----------- | ------- | ------- |
| Block Title          | `block-title`      | Comment Block's Title         | `string`                                  | `undefined`        |
| Hide Form | `hide-form` |This allows to make the comment section non visible| `boolean` | `undefined`|
| Item Id _(required)_ | `item-id`	| A unique identifier for Page or product | `number` | `undefined`|
| Load More Text | `load-more-text` | This item allows loading additional text. | `string` | `undefined`|
| Show Form Avatar      | `show-form-avatar` | Whether to show or hide the commenter’s avatar | `boolean`                                 | `false`            |
| Type | `type`| This item is used to identify the Comment type | `CommentType.BLOG` \| `CommentType.PAGE` \| `CommentType.PRODUCT`  |

---

## product/Salla-Conditional-Offer-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Conditional Offer

The `<salla-conditional-offer>` web component enables dynamic presentation of offers and discounts based on the customer's cart status.
:::info[Information]
Developers can use this component to enhance the user experience by automatically applying relevant offers, encouraging higher cart turnover and improved customer satisfaction. It can be enabled from the [Merchant Dashboard > Marketing Tools > Conditional Offers tab](https://s.salla.sa/marketing/marketing_tools).
:::

### Example
![image](https://cdn.salla.network/docs/twilight/6/js-web-conditional-offer.png)

## Usage

:::caution[Alert]
Conditional offers are activated when the total value of the cart meets or exceeds a defined limit set by the Merchant from the Dashboard. Potential promotions include fixed / percentage discounts on the cart total or the addition of a free product. This applies on:
- Number of products added in the cart.
- Cart total value.
:::

<Tabs>
  <Tab title="HTML">
 	 
```html
<!-- Conditional Offer component usage -->

<salla-conditional-offer> </salla-conditional-offer> 
``` 	 
  	</Tab>
    <Tab title="SASS">
     This JS web component can be targeted for styling by using the prefix `s-conditional-offer`, for example developers can customize the styling of the variable `checkpoint` in this way `s-conditional-offer-checkpoint: {background-color: #000000}` . Following is a complete list of variables for customizing this component:
        
| Variable Name |
| -- |
| `active-checkpoint` |
| `checkpoint` |
| `checkpoint-border` |
| `checkpoint-border-colored` |
| `checkpoint-container` |
| `checkpoint-image-content` |
| `checkpoint-label` |
| `checkpoint-label.active` |
| `checkpoint-label.first-checkpoint` |
| `container` |
| `item-avatar-content` |
| `item-avatar-content.active` |
| `product-link` |
| `progress-container` |
| `progress-line` |
| `progress-line-active` |
| `progress-line-container` |
| `progress-line-inactive` |
| `skeleton-checkpoint` |
| `skeleton-checkpoints-wrapper` |
| `skeleton-subtitle` |
| `skeleton-title` |
| `skeleton-wrapper` |
| `subtitle` |
| `subtitle-i` |
| `title` |
| `title-wrapper` |
    </Tab>   
</Tabs>

    


:::tip[Note]
No configurations are needed to use this component, as it is enabled/disabled from the [Merchant’s dashboard](https://s.salla.sa/marketing/marketing_tools) which can be queried using: `salla.config.get('store.features')`
:::

---

## product/Salla-Gifting-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Gifting

The `<salla-gifting>` web component is used to display items as gifts, which can be used after the customer has completed a purchase. It can be customized using the properties' parameters available.

:::tip[Note]
Available API Endpoints for the Gifting component is:

- [Gift Details](https://docs.salla.dev/doc-422646?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Add Gift To Cart](https://docs.salla.dev/doc-422647?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Upload Gift Image](https://docs.salla.dev/doc-422648?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::



## Example

<!--focus: false -->
![Gifting](https://cdn.salla.network/docs/twilight/6/js-web-gifting-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Gifting component usage -->
<salla-gifting
  product-id="1153090815"
  onclick="gift.open()">
</salla-gifting>
```
  </Tab>
    
  <Tab title="JS">
        
```js
// Save reference to the Gifting Component as below
const gift = document.querySelector("salla-gifting");
```      
  </Tab>  
    <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-gifting-steps-wrapper` class. Following is a complete source code for customizing this component:

```css
.s-gifting-steps-wrapper {
  transition: .2s cubic-bezier(.55, 0, .1, 1) 0s;
}

.s-gifting-select{
  background-image: url("data:image/svg+xml;utf8,<svg version='1.1' fill='gray' xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'><title>keyboard_arrow_down</title><path d='M9.875 11.104l6.125 6.125 6.125-6.125 1.875 1.875-8 8-8-8z'></path></svg>");
  background-size: 24px;
  background-repeat: no-repeat;
  background-position: 99%;
  appearance: none;
}
// dir rtl
[dir=rtl] .s-gifting-select{
  background-position: 5px;
}
```
      
  </Tab>  
  
</Tabs>


## Properties

| Property | Attribute | Description | Type  | Default |
| -------- | --------- | ----------- | ----- | ------- |
| Product ID      | `product-id`     | The product id for which the gifting system is required.         | `number` | `undefined`   |
| Widget Title|	`widget-title` |	The Widget's title value |	`string` |	`undefined`   |
| Widget Subtitle|	`widget-subtitle` |	The Widget's subtitle value |	`string` |	`undefined`   |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `currencywidget-btn-content` which is used to customize the widget's button content.

| Method  | Description | Return Type |
| ------- | ----------- | ----------- |
| `close()` | Hides / closes the gifting modal window.         | `Promise<HTMLElement>`       |
| `goToStep2()` | Go to the step 2 in the gifting system.          | `Promise<void>`       |
| `open()` | Shows / opens the gifting modal window.         | `Promise<any>`       |

## Slots
The`slots` makes it customizable to modify certain labels, such as `currencywidget-btn-content`.

| Slot       | Description                                                                                    |
| ---------- | ---------------------------------------------------------------------------------------------- |
| `currencywidget-btn-content` | It is used to customize the widget's button content. |

---

## product/Salla-Installment-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Installment

The `<salla-installment>` web component is used to show a block area for the available installment payment options provided for a specific product. It consists of the supported payment in installments' options in an inline manner, and that can be customized using the properties' parameters available.

## Example

<!--
focus: false
-->

![Installment Example](https://cdn.salla.network/docs/twilight/6/js-web-instalment-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">
    
  ```js
<salla-installment price="1200">
</salla-installment>
```

      
  </Tab>
  <Tab title="SASS">

```css
#tabbyPromoWrapper {
  background: white;
  border-radius: 0.375rem;
  transition: box-shadow 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  margin-bottom: 20px;

  .salla-y &{
    border: 1px solid var(--color-grey-dark);
    border-radius: 12px
  }

  &:hover{
    box-shadow: 0 0 #0000, 0 0 #0000, 5px 10px 30px #2B2D340D;
  }

  #tabbyPromo {
    * {
      font-family: var(--font-main);
    }

    > div > div {
      max-width: none;
      //padding: 15px;
      box-shadow: none;
      border: none;
    }

    .tabby-promo-snippet {
      max-width: 100%;
      min-height: 100px;
      padding: 18px 20px;
      // border-color: var(--color-grey-dark);
      border: none !important;


      &__text, &__link {
        font-size: var(--font-sm);
        color: var(--color-text) !important;
      }

      &__link {
        font-weight: bold;
      }
    }
  }
}

.tabby-promo-wrapper {
  #tabby-promo {
    font-family: var(--font-main) !important;

    .tabby-promo {
      &__feature-title {
        font-size: var(--font-md);
      }

      &__feature-desc {
        font-size: var(--font-sm);
        line-height: 20px;
      }
    }
  }
}

/*
* Installment::Tamara & Spotii
*/
.tamara-product-widget{
  margin-bottom: 20px;
}

.tamara-product-widget,
.spotii-wrapper {
  min-height: 100px;
  position: relative;
  color: var(--color-text);
  font-size: var(--font-sm);
  line-height: 1.25;
  padding: 18px 20px 18px 100px !important;
  background: white;
  border-radius: 0.375rem;
  transition: box-shadow 0.5s cubic-bezier(0.4, 0, 0.2, 1);

  .salla-y &{
    border-radius: 12px;
    border: 1px solid var(--color-grey-dark);
  }

  &:hover{
    box-shadow: 0 0 #0000, 0 0 #0000, 5px 10px 30px #2B2D340D;
  }
  .spotii-logo {
    float: left;
    margin: 0 0 0 -75px;
  }
}
.ltr .tamara-product-widget,
.ltr .spotii-wrapper{
  text-align: left;
  padding: 18px 100px 18px 20px !important;
  .spotii-logo {
    float: right;
    margin: 0 -75px 0 0;
  }
  .spotii-product-widget {
    text-align: left !important;
  }
}

.spotii-wrapper {
  margin-bottom: 20px;
  .spotii-promo {
    font-size: var(--font-md);
  }

  .spotii-product-widget {
    font-size: var(--font-sm) !important;
    margin-top: 10px;
  }
}

.tamara-product-widget{
  .tamara-logo {
    position: absolute;
    left: 20px;
    top: 18px;
    margin: 0 !important;

    .ltr &{
      right: 20px;
      left: auto;
    }
  }

  span {
    font-family: var(--font-main);
    font-size: var(--font-sm);
    color: var(--color-text);

    &:last-child {
      display: block;
      position: relative;
      margin-top: 8px;
    }
  }
}

.tamara-popup {
  &__wrap {
    overflow: auto !important;
  }
}
```
      
  </Tab>  
</Tabs>


## Properties

| Property   | Attribute  | Description           | Type     | Default                                  |
| ---------- | ---------- | --------------------- | -------- | ---------------------------------------- |
| Country  | `country`  | Country code identifier          | `string` | `salla.config.get('user.country_code')`  |
| Currency | `currency` | Installment price currency         | `string` | `'salla.config.get('user.currency_code')'` |
| Language | `language` | Current installment language         | `string` | `'salla.config.get('user.language_code')'` |
| Price    | `price`    | Current product price | `string` | `undefined`                              |

## Settings

This component relay on the store settings in twilight config, if you are using thie comonent outside store pages, you can set the available installment payment options via `salla.config` 

```js
salla.config.set('store.settings.installments', {
  tamara_installment: true,
  tabby_installment: true,
  spotii_pay: true
})
```

:::info[Information]
Because the installment method is based on third-party components, there are **no custom classes** - _like there are for other components_ - to style such classes.
:::

---

## product/Salla-Meta-Data-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Meta Data

The `<salla-metadata>` web component helps to show detailed specifications for a product. It can display one or multiple sections of information, like links, text, files, and other details about the product.

## Example

<!--
focus: false
-->

![Meta Data Example](https://cdn.salla.network/docs/twilight/6/js-web-metadata-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
    
  ```js
<salla-metadata entity-id="691043">
</salla-metadata>
```

      
  </Tab>  
</Tabs>


## Properties

| Property   | Attribute   | Description                                                                      | Type     | Default     |
| ---------- | ----------- | -------------------------------------------------------------------------------- | -------- | ----------- |
| Entity   | `entity`    | The entity type which its default value is `product`.                                                                 | `string` | `'product'` |
| Entity ID | `entity-id` | Either Product or Entity ID to which the specifications are going to be fetched for. | `number` | `undefined` |

---

## product/Salla-Offer-Modal-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Offer Modal

The `<salla-offer-modal>` web component shows a list of products with an offer given by the store admin. These offered products are related to a specific product. It consists of [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component to which Merchants can select offers related to product(s) they added to the cart, and that can be customized using the slots' parameters available.

:::tip[note]
Available API Endpoints for the Offer component is:

- [Product Offer Details](https://docs.salla.dev/doc-422643?nav=01HNFTDZPB31Y2E120R84YXKCX)

:::

## Example

<!--
focus: false
-->

![Offer Example](https://cdn.salla.network/docs/twilight/6/js-web-offer-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">

   ```html
<!-- Button to activate Show Offer -->
<salla-button onclick="salla.event.dispatch(`offer::open`, 12345)">
  Offer Modal
</salla-button>

<!-- Offer Modal Component -->
<salla-offer-modal>
  <div slot="header">
      <p>%{{store.username}}%</p>
      <p>%{{store.logo%}}</p>
  </div>
</salla-offer-modal>
```      
  </Tab>
  <Tab title="SASS">

      
This JS web component can be targeted for styling by its `.s-offer-modal` class. Following is a complete source code for customizing this component:

```js

.s-offer-modal {
  &-body {
    
  }
  &-badge {
    &-icon {

    }
    &-text {

    }
  }
  &-product {
    &-image-wrap {

    }
    &-image {

    }
    &-info {

    }
    &-name {

    }
    &-price {

    }
    &-old-price {

    }
  }
  &-btn-wrap {

  }
  &-footer {

  }
  &-expiry {

  }
  &-remember-label {

  }
  &-remember-input {

  }
  &-scrolled-slider-wrap {

  }
  &-slider-nav {

  }
  &-nav-btn {

  }
  &-nav-btn-icon {

  }
  &-next-btn {
    
  }
  &-prev-btn {
    
  }
  &-btn-is-active {

  }
}
```

  </Tab>  
</Tabs>


## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `show` a specific `product` or `offer`.


| Method                     | Description                                       | Return Type     |
| -------------------------- | ------------------------------------------------- | --------------- |
| `open(product_id: number)` | Opens the available offers for a specific product | `Promise<any>`  |
| `showOffer(offer: any)`    | Shows offer details for a specific product        | `Promise<void>` |


:::tip[Tip]
To use a method, you can for instance `open` the component via the event:
```html
onclick="salla.event.dispatch(`offer::open`, 12345)"
```
:::


## Slots
The`slots` makes it customizable to modify certain labels, such as `header`.

| Slot       | Description                                                                                |
| ---------- | ------------------------------------------------------------------------------------------ |
| `header`   | The top of the popup, which has replaceable properties `{name}`, `{message}`.                    |
| `category` | Replaces Category badge, which has replaceable properties `{name}`, `{url}`.                     |
| `product`  | Replaces product card, which has replaceable properties `{name}`, `{url}`, `{image}`, `{price}`. |

---

## product/Salla-Offer-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Offer


The `<salla-offer>` web component displays offers, categories, products, banks, and discount information. It uses the [`salla-slider`](https://docs.salla.dev/doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD) component for carousel functionality.

## Example

<Frame caption="Product Offer">
  ![](https://cdn.salla.network/docs/twilight/6/js-web-offer-01.png)
</Frame>

<Frame caption="Discount Table Offer">
  ![](https://cdn.salla.network/docs/twilight/6/js-web-offer-02.png)
</Frame>

<Frame caption="Category Offer">
  ![](https://cdn.salla.network/docs/twilight/6/js-web-offer-03.png)
</Frame>

<Frame caption="Banks Offer">
  ![](https://cdn.salla.network/docs/twilight/6/js-web-offer-04.png)
</Frame>

## Usage


<Tabs>
  <Tab title="HTML">

```html
<salla-offer product-id="673490471"></salla-offer>
```
  </Tab>
  <Tab title="SASS">
This JS web component can be targeted for styling by its `.s-offer-wrapper .s-slider-block__title` class. Following is a complete source code for customizing this component:

```js

.s-offer-wrapper .s-slider-block__title {
  h2 {
    font-size: 1.125rem;
    line-height: 1.75rem;
    color: #f87171;

    &::before {
      font-family: "sallaicons";
      content: "\ee30" !important;
      position: absolute;
      top: 1rem;
      font-size: 3rem;
      font-weight: 400;
      line-height: 1;
      color: #fef2f2;
    }
  }
}

.s-offer-bank-wrapper-sinlge-item{
    display: flex;
    align-items: center !important;
    gap: 14px;
}

.s-offer-bank-wrapper {
  display: flex !important;
  width: 100% !important;
}
```
      
  </Tab>
</Tabs>



## Properties

| Property    | Attribute    | Description                                     | Type     | Default     |
| ----------- | ------------ | ----------------------------------------------- | -------- | ----------- |
| Product Card Component` | `product-card-component` | [Custom Card Component](doc-422718) for the [`salla-products-list`](doc-422719).  This component allows you to customize the appearance of individual [product cards](doc-422718) within a [`salla-products-list`](doc-422719). | `string` | `'custom-salla-product-card'` |



## Slots
The`slots` makes it customizable to modify certain labels, such as `category`.

| Slot         | Description                                         |
| ------------ | --------------------------------------------------- |
| `category` | This slot is for customizing the category entry layout. |

---

## product/Salla-Orders-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Orders

The `<salla-orders>` web component shows a table with order details, such as order ID, product total, order status, and more.


## Example

<!--
focus: false
-->

![Orders Component](https://cdn.salla.network/docs/twilight/6/js-web-orders.png)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<salla-orders></salla-orders>
```
  </Tab>      

  
</Tabs>

## Properties

| Property       | Attribute        | Description                                          | Type                   | Default     |
| -------------- | ---------------- | ---------------------------------------------------- | ---------------------- | ----------- |
| Load More Text | `load-more-text` | Load more text                                       | `string`               | `undefined` |
| Params       | `params`               | A query Parameter to send along with the fetch request | `OrderQueryParameters` | `undefined` |

---

## product/Salla-Payments-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Payments


The `<salla-payments>` web component allows users to display Payments items including `sbc-id`, `withMadeInKsa`, and `withSbc`.

## Example 

![Payments Component](https://cdn.salla.network/docs/twilight/6/js-web-payment-01.png)

## Usage

<Tabs>

  <Tab title="HTML">

```
<salla-payments></salla-payments>
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



## Properties

| Property    	| Attribute      	| Description                                                                     	| Type  	| Default 	|
| --------------- | ------------------ | ----------------------------------------------------------------------------------- | --------- | ----------- |
| SBC ID     	| `sbc-id`       	| The SBC (Saudi Business Council) certificate ID.                                	| `string`  | `undefined` |
| With Made In KSA | `with-made-in-ksa` | Whether or not to include the ["Made in KSA"](https://saudimade.sa/en) certification.          	| `boolean` | `undefined` |
| With SBC   	| `with-sbc`     	| Whether or not to include the SBC (Saudi Business Council) certificate. | `boolean` | `undefined` |


## Slots
The`slots` makes it customizable to modify certain labels, such as `cod`.

| Slot    	| Description                                                   	|
| ----------- | ----------------------------------------------------------------- |
| `cod` 	| Replaces the Cash On Delivery (cod) item with the slot `image`.           	|
| `payment` | Replaces the payment item with the slots `image`, `name`. |
| `sbc` 	| Replaces the SBC certificate item with the slot `image`.   |

---

