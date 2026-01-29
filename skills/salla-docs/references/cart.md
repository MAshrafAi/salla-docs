# Cart

## Table of Contents

- [cart/Add-Product-to-Cart-Twilight-JS-SDK-Twilight-Documentation](#cart-add-product-to-cart-twilight-js-sdk-twilight-documentation)
- [cart/Apply-Discount-Coupon-to-Cart-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation](#cart-apply-discount-coupon-to-cart-twilight-js-sdk-salla-developer-docs-twilight-documentation)
- [cart/Cart-Details-Twilight-JS-SDK-Twilight-Documentation](#cart-cart-details-twilight-js-sdk-twilight-documentation)
- [cart/Create-Quick-Order-Twilight-JS-SDK-Twilight-Documentation](#cart-create-quick-order-twilight-js-sdk-twilight-documentation)
- [cart/Delete-Cart-Item-Image-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation](#cart-delete-cart-item-image-twilight-js-sdk-salla-developer-docs-twilight-documentation)
- [cart/Delete-Product-from-Cart-Twilight-JS-SDK-Twilight-Documentation](#cart-delete-product-from-cart-twilight-js-sdk-twilight-documentation)
- [cart/Get-Current-Cart-ID-Twilight-JS-SDK-Twilight-Documentation](#cart-get-current-cart-id-twilight-js-sdk-twilight-documentation)
- [cart/Get-Quick-Order-Settings-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation](#cart-get-quick-order-settings-twilight-js-sdk-salla-developer-docs-twilight-documentation)
- [cart/Order-Status-Twilight-JS-SDK-Twilight-Documentation](#cart-order-status-twilight-js-sdk-twilight-documentation)
- [cart/Price-Quote-Calculate-Final-Cart-Cost-Twilight-Documentation](#cart-price-quote-calculate-final-cart-cost-twilight-documentation)
- [cart/Quick-Add-to-Cart-Twilight-JS-SDK-Twilight-Documentation](#cart-quick-add-to-cart-twilight-js-sdk-twilight-documentation)
- [cart/Remove-Discount-Coupon-from-Cart-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation](#cart-remove-discount-coupon-from-cart-twilight-js-sdk-salla-developer-docs-twilight-documentation)
- [cart/Twilight-JS-SDK-Cart-Latest-Retrieve-Customer’s-Last-Cart-Twilight-Documentation](#cart-twilight-js-sdk-cart-latest-retrieve-customer’s-last-cart-twilight-documentation)
- [cart/Upload-Image-to-Cart-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation](#cart-upload-image-to-cart-twilight-js-sdk-salla-developer-docs-twilight-documentation)

---

## cart/Add-Product-to-Cart-Twilight-JS-SDK-Twilight-Documentation

# Add Item

This `addItem` endpoint adds an item from the merchant's store to the customer's shopping cart. The customer may select the item, type in the quantity he wants to order, and click on the "add to cart" button. This sends the product to the shopping cart, and then the customer may continue to shop for other items.

:::tip
The *add item* endpoint has been implemented in the [Add Product](https://docs.salla.dev/doc-422692?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and it's ready for use.

:::


## Payload


<DataSchema id="1387197" />


## Response

<Tabs>
  <Tab title="Success">

<DataSchema id="1427397" />
      
     
  </Tab>
   <Tab title="Error">


<DataSchema id="1427184" />
  </Tab>
  
</Tabs>

## Usage
The method `addItem` adds an item into the cart, the developer may call the method `addItem` as follows:


#### Simple Product

```js
salla.cart.addItem({
    id: 1234,
    quantity: 1,
    notes: "please i need to get the red color"
}).then((response) => {
    /* add your code here */
});
```
#### Variable product

```js
salla.cart.addItem({
    id: 1234,
    quantity: 1,
    options: {
      // option id: option value or option value id (select choice)
      117414452: 11232214, // option value id (select choice)
      117416632: "http://option-value-as-url-of-image.com", // for upload field
      117411132: "option value as string" // for string field
    },
    notes: "please i need to get the red color"
}).then((response) => {
    /* add your code here */
});
```

## Events
This endpoint may trigger two events, the onItemAdded and onItemAddedFailed events.

### onItemAdded
This event is triggered when adding an item to the cart is done without having any errors coming back from the backend.
```js
salla.cart.event.onItemAdded((response, product_id) => {
  console.log(response)
});
```
### onItemAddedFailed
This event is triggered when adding an item to the cart is not completed and an error has occurred. For example, the id of the product to be added to the cart was not found.
```js
salla.cart.event.onItemAddedFailed((errorMessage, product_id) => {
  console.log(errorMessage)
});
```

---

## cart/Apply-Discount-Coupon-to-Cart-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation

# Add Coupon

A coupon is a code that consists of a special series of characters, or string, used by customers to get a discounted price or limited offer on the cart's items. This *add* endpoint is used for this purpose.

## Payload


<DataSchema id="1427417" />

## Response
<Tabs>
  <Tab title="Success">
      
<DataSchema id="1427410" />
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>


## Usage
To perform the action of applying a coupon to the cart's items, the developer may call the `add()` as shown below.


```js
salla.cart.addCoupon({ coupon: "Free_Shipping") }).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.cart.addCoupon('Free_Shipping').then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onCouponAdded and onCouponAdditionFailed events.

### onCouponAdded
This event is triggered when applying a new coupon by the customer is done without having any errors coming back from the backend.

```js
cart.event.cart.onCouponAdded((response) => {
  console.log(response)
});
```
### onCouponAdditionFailed
This event is triggered when applying a new coupon by the customer is not completed and an error has occurred.

```js
salla.event.cart.onCouponAdditionFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## cart/Cart-Details-Twilight-JS-SDK-Twilight-Documentation

# Details

This endpoint displays an Cart's details for the customer, The cart's items will be listed here along with their details.

## Response
<Tabs>
  <Tab title="Success">
 
<DataSchema id="1427374" />
    
     
  </Tab>
   <Tab title="Error">

     
<DataSchema id="1427314" />
  </Tab>
  
</Tabs>


## Usage
The `details()` method does not receive any parameters. Simply, the developer may call this method and be able to get the customer's order details according to the cart's items.

```js
Salla.cart.details().then((response) => {
  /* add your code here */
});
```
### Advance Usage
Pass `options` or `attachments` or both for more `cartItems` related data such as **options** in this example `cart.items.options.type`.


```js
Salla.cart.details(null, ['options','attachments']).then((response) => {
  /* add your code here */
});
```

:::tip[]
Use the simpler call unless you explicitly need `options` or `attachments`, as extra fields increase response size and processing time.
:::


## Events
This endpoint may trigger two events, the onDetailsFetched and onDetailsNotFetched events.

### onDetailsFetched
This event is triggered when fetching the cart's items list is done without having any errors coming back from the backend.

```js
salla.cart.event.onDetailsFetched((response) => {
  console.log(response)
});
```
### onDetailsNotFetched
This event is triggered when fetching the cart's items list is not completed and an error has occurred.

```js
salla.cart.event.onDetailsNotFetched((errorMessage) => {
  console.log(errorMessage)
});
```

---

## cart/Create-Quick-Order-Twilight-JS-SDK-Twilight-Documentation

# Create Quick Order

This endpoint enables the user to select particular items, complete the purchase of that item, and then proceed directly to the checkout page to complete the purchase without having to complete any intermediary stages.

## Payload

<DataSchema id="1387201" />

## Response

<Tabs>
  <Tab title="Success">

<DataSchema id="1427430" />

  </Tab>
   <Tab title="Error">

<DataSchema id="1427314" />
  </Tab>
  
</Tabs>


## Usage
To perform the action completing the purchase of items and proceeding directly to the checkout, the developer may call the `createQuickOrder()` as shown below.

```js
salla.cart.createQuickOrder({
    email: "ali_22@gmail.com",
    phone: "056342682",
    country_code: "966",
    name: "Ali",
    product_ids: [22,65,3],
    agreement: true,
  })
  .then((response) => {
    /* add your code here */
  });

```


## Events
This endpoint may trigger two events, the onQuickOrderSucceeded and onQuickOrderFailed events.

### onQuickOrderSucceeded
This event is triggered when the action completing the purchase of items and proceeding directly to the checkout is done without having any errors coming back from the backend.

```js
ssalla.cart.event.onQuickOrderSucceeded((response) => {
  console.log(response)
});
```
### onQuickOrderFailed
This event is triggered when the action completing the purchase of items and proceeding directly to the checkout is not completed and an error has occurred.

```js
salla.cart.event.onQuickOrderFailed((errorMessage) => {
  console.log(errorMessage)
});
```

---

## cart/Delete-Cart-Item-Image-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation

# Delete Image

This endpoint removes an image file attached to an item already added to the cart by the customer.

## Payload

<DataSchema id="1387202" />


## Response

<Tabs>
  <Tab title="Success">

<DataSchema id="1427405" />

  </Tab>
   <Tab title="Error">


<DataSchema id="1427314" />
      
  </Tab>
  
</Tabs>

## Usage

To delete an image file attached to an item already added to the cart, the developer may call the method `deleteItem` as follows:

```js
salla.cart.deleteItem({ file_id: 12345} ).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.cart.deleteItem(12345).then((response) => {
  /* add your code here */
});
```



## Events
This endpoint may trigger two events, the onImageDeleted and onImageNotDeleted events.

### onImageDeleted
This event is triggered when removing an image file attached to an item already added to the cart is done without having any errors coming back from the backend.

```js
salla.cart.event.onImageDeleted((response) => {
  console.log(response)
});
```

### onImageNotDeleted
This event is triggered when removing an image file attached to an item already added to the cart is not completed and an error has occurred. For example, the id of the image file was not found.

```js
salla.cart.event.onImageNotDeleted((errorMessage) => {
  console.log(errorMessage)
});
```

---

## cart/Delete-Product-from-Cart-Twilight-JS-SDK-Twilight-Documentation

# Delete Item

This endpoint removes an item from the customer's shopping cart. The customer may remove an item by clicking on the "remove from to cart" button. 

## Payload

<DataSchema id="1387204" />



## Response

<Tabs>
  <Tab title="Success">

<DataSchema id="1427401" />
  
  </Tab>
   <Tab title="Error">

<DataSchema id="1427314" />
  </Tab>
  
</Tabs>


## Usage
To perform the action of removing an item from the cart, the developer may call the method `deleteItem` along with the id of the item that will be removed from the cart.
```js
salla.cart.deleteItem({ id: 12345 }).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.cart.deleteItem(12345).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onItemDeleted and onItemDeletedFailed events.

### onItemDeleted
This event is triggered when removing an item from the cart is done without having any errors coming back from the backend.

```js
salla.cart.event.onItemDeleted((response) => {
  console.log(response)
});
```
### onItemDeletedFailed
This event is triggered when removing an item from the cart is not completed and an error has occurred. For example, the id of the product to be added to the cart was not found, or there is no product with such an id currently in the cart.

```js
salla.cart.event.onItemDeletedFailed((errorMessage) => {
  console.log(errorMessage)
});
```

---

## cart/Get-Current-Cart-ID-Twilight-JS-SDK-Twilight-Documentation

# Get Current Cart Id

This endpoint returns the unique identifier (ID) of the current cart associated with a particular user or session. It is used to retrieve the current cart ID, which is typically required for other cart-related operations such as adding or removing items from the cart, checking out, or retrieving cart details.

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427443" />

  
  </Tab>
   <Tab title="Error">

       
<DataSchema id="1427184" />
  </Tab>
  
</Tabs>


## Usage
To perform the action of returning the ID of the current cart, the developer may call the `getCurrentCartId()` as shown below.

```js
salla.cart.getCurrentCartId()
  .then((response) => {
    /* add your code here */
  });

```

---

## cart/Get-Quick-Order-Settings-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation

# Get Quick Order Settings

The Get Quick Order Settings endpoint retrieves the configuration settings for a merchant's quick order feature, including the title, sub-title, thanks message, order button text, email requirement, agreement requirement, allowed countries, custom styling options, confirmation button text, and the agreement text. These settings determine the behavior and appearance of the quick order feature on the merchant's store.

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427422" />

      
  </Tab>
   <Tab title="Error">


<DataSchema id="1427184" />
  </Tab>
  
</Tabs>


## Usage
To perform the action of getting the setting of a quick order, the developer may call the `getQuickOrderSettings()` as shown below.

```js
salla.cart.getQuickOrderSettings().then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onQuickOrderSettingFetched and onQuickOrderSettingFailed events.

### onQuickOrderSettingFetched
This event is triggered when getting the setting of a quick order is done without having any errors coming back from the backend.

```js
ssalla.cart.event.onQuickOrderSettingFetched((response) => {
  console.log(response)
});
```
### onQuickOrderSettingFailed
This event is triggered when getting the setting of a quick order is not completed and an error has occurred.

```js
salla.cart.event.onQuickOrderSettingFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## cart/Order-Status-Twilight-JS-SDK-Twilight-Documentation

# Order Status

This endpoint returns the current status of a cart, including whether it is active or not, and the next step to take. The next step can be either to refresh the cart, prompt the user to login, or proceed to checkout, and may include an optional URL. This endpoint is used for monitoring and managing the status of a cart during the checkout process.

## Payload


<DataSchema id="1427312" />


## Response
<Tabs>
  <Tab title="Success">

     
<DataSchema id="1427313" />
  </Tab>
   <Tab title="Error">

    
<DataSchema id="1427184" />
  </Tab>
  
</Tabs>


## Usage
To perform the action of returning the current status of a cart, the developer may call the `status()` as shown below.

```js
salla.cart.status({cart_id: 5432}).then((response) => {
  /* add your code here */
});
```

---

## cart/Price-Quote-Calculate-Final-Cart-Cost-Twilight-Documentation

# Price Quote

The priceQuote endpoint calculates and returns a price quote for the items in a cart. This endpoint takes into account any discounts, taxes, shipping costs, and other factors that may affect the final price, and returns the calculated price along with a breakdown of the individual costs. The price quote can be used to inform the user of the total cost of their purchase and to facilitate the checkout process.

## Payload

<DataSchema id="1427456" />


## Response
<Tabs>
  <Tab title="Success">
    
<DataSchema id="1427457" />
      
  </Tab>
   <Tab title="Error">
 
<DataSchema id="1427184" />
  </Tab>
  
</Tabs>


## Usage
To perform the action of calculating and returning a price quote for the items in a cart, the developer may call the `priceQuote()` as shown below.

```js
salla.cart.priceQuote({cart_id: 5432}).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onPriceQuoteSucceeded and onPriceQuoteFailed events.

### onPriceQuoteSucceeded
This event is triggered when of calculating and returning a price quote for the items in a cart is done without having any errors coming back from the backend.

```js
ssalla.cart.event.onPriceQuoteSucceeded((response) => {
  console.log(response)
});
```
### onPriceQuoteFailed
This event is triggered when of calculating and returning a price quote for the items in a cart is not completed and an error has occurred.

```js
salla.cart.event.onPriceQuoteFailed((errorMessage) => {
  console.log(errorMessage)
});
```

---

## cart/Quick-Add-to-Cart-Twilight-JS-SDK-Twilight-Documentation

# Quick Add

The `quickAdd` endpoint enables the customer to add a product directly from the products list to the cart without the need to open that product page. Under the hood, this endpoint calls the [`addItem`](https://docs.salla.dev/doc-422629?nav=01HNFTDZPB31Y2E120R84YXKCX) endpoint by passing the id of the product which will be added to the cart.

:::tip
The *quick add* endpoint has been implemented in the [Add Product](https://docs.salla.dev/doc-422692?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and it's ready for use.
:::


## Payload


<DataSchema id="1387213" />

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427381" />

  </Tab>
   <Tab title="Error">
      
<DataSchema id="1427314" />
  </Tab>
  
</Tabs>



## Usage
To perform the action of adding a product into the cart, the developer may call the method `quickAdd` as follows:
```js
salla.cart.quickAdd({ id: 12345 }).then((response) => {
  /* add your code here */
});


// TIP: short version
salla.cart.quickAdd(12345).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint calls the [`addItem`](https://docs.salla.dev/doc-422629?nav=01HNFTDZPB31Y2E120R84YXKCX) endpoint by passing the id of the product which will be added to the cart. Accordingly, all of the addItem's [events](https://docs.salla.dev/doc-422611?nav=01HNFTDZPB31Y2E120R84YXKCX) are applicable.

---

## cart/Remove-Discount-Coupon-from-Cart-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation

# Remove Coupon

A coupon is a code can be removed by customers, this  will revert any added discounted price or limited offer on the cart's items. This *remove* endpoint is used for this purpose.

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427419" />
    
  </Tab>
   <Tab title="Error">
       
<DataSchema id="1427184" />   
       
  </Tab>
  

</Tabs>

## Usage
To perform the action of removing a coupon to the cart's items, the developer may call the `remove()` as shown below.

```js
salla.cart.deleteCoupon().then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onCouponDeleted and onCouponDeletionFailed events.

### onCouponDeleted
This event is triggered when removing coupon from the cart's items is done without having any errors coming back from the backend.

```js
ssalla.cart.event.onCouponDeleted((response) => {
  console.log(response)
});
```
### onCouponDeletionFailed
This event is triggered when removing coupon from the cart's items is not completed and an error has occurred.

```js
salla.cart.event.onCouponDeletionFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## cart/Twilight-JS-SDK-Cart-Latest-Retrieve-Customer’s-Last-Cart-Twilight-Documentation

# Latest

This endpoint fetches the last cart created by the customer. In other words, the cart will be fetched based on the latest products.

## Response
<Tabs>
  <Tab title="Success">


<DataSchema id="1427234" />
      
  </Tab>
   <Tab title="Error">


       
<DataSchema id="1427314" />
  </Tab>
  
</Tabs>


## Usage
The `latest()` method does not receive any parameters. Simply, the developer may call this method and be able to get the last cart created by the customer.

```js
salla.cart.latest().then((response) => {
  /* add your code here */
});

```


## Events
This endpoint may trigger two events, the onLatestFetched and onLatestFailed events.

### onLatestFetched
This event is triggered when fetching the last cart created by the customer is done without having any errors coming back from the backend.

```js
salla.event.cart.onLatestFetched((response) => {
  console.log(response);
});
```

### onLatestFailed
This event is triggered when fetching the last cart created by the customer is not completed and an error has occurred.

```js
salla.event.cart.onLatestFailed((errorMessage) => {
  console.log(errorMessage);
});
```

---

## cart/Upload-Image-to-Cart-Twilight-JS-SDK-Salla-Developer-Docs-Twilight-Documentation

# Get Upload Image

This endpoint allows the user to add an image file to the cart in the case that the user needs to attach an image to the order it is placing through the shopping cart.

## Payload

<DataSchema id="1427420" />

## Response
<Tabs>
  <Tab title="Success">

<DataSchema id="1427421" />

  </Tab>
   <Tab title="Error">


<DataSchema id="1427184" />
  </Tab>
  
</Tabs>

## Usage
To perform the action of uploading an image to the cart, the developer may call the `getUploadImageEndpoint()` as shown below.

```js
salla.cart.getUploadImageEndpoint({cart_id: 5432}).then((response) => {
  /* add your code here */
});
```

---

