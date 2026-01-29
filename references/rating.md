# Rating

## Table of Contents

- [rating/Rate-Order-Salla-Developer-Documentation-Twilight-Documentation](#rating-rate-order-salla-developer-documentation-twilight-documentation)
- [rating/Rate-Purchased-Products-Salla-Developer-Documentation-Twilight-Documentation](#rating-rate-purchased-products-salla-developer-documentation-twilight-documentation)
- [rating/Rate-Shipping-Companies-Salla-Developer-Documentation-Twilight-Documentation](#rating-rate-shipping-companies-salla-developer-documentation-twilight-documentation)
- [rating/Rate-Store-Salla-Developer-Documentation-Twilight-Documentation](#rating-rate-store-salla-developer-documentation-twilight-documentation)

---

## rating/Rate-Order-Salla-Developer-Documentation-Twilight-Documentation

# Order

This endpoint is used for the purpose of rating an order. It fetches the order's id, which will be rated.


:::tip
The *order rating* endpoint has been implemented in the [Rating](https://docs.salla.dev/doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, , and It's all setup to save developer's time and effort.
:::
 

## Payload `authenticated`

<DataSchema id="1387268" />


## Response
<Tabs>
    

  <Tab title="Success">

<DataSchema id="1427921" />
      
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
  </Tab>
  
</Tabs>



## Usage
To perform the action of rating an order, the method `order()` may be called as below, with the id of the order to be rated.

```js
salla.rating.order({ order_id: 978 }).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.rating.order(978).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onOrderFetched and onOrderNotFetched events.

### onOrderFetched
This event is triggered when fetching the id of the order to be rated is done without having any errors coming back from the backend.

```js
salla.event.rating.onOrderFetched((response) => {
  console.log(response)
});
```
### onOrderNotFetched
This event is triggered when fetching the id of the order to be rated is not completed and an error has occurred.

```js
salla.event.rating.onOrderNotFetched((errorMessage) => {
  console.log(errorMessage)
});

---

## rating/Rate-Purchased-Products-Salla-Developer-Documentation-Twilight-Documentation

# Products

The customer is able to rate each product purchased in a specific order. This endpoint is used to save the customer's review comments on the purchased products list.



:::tip
The *products rating* endpoint has been implemented in the [Rating](https://docs.salla.dev/doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, , and It's all setup to save developer's time and effort.

:::
## Payload `authenticated`

<DataSchema id="1387271" />


## Response
<Tabs>
  <Tab title="Success">
      
<DataSchema id="1427924" />
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />

      
  </Tab>
  
</Tabs>


## Usage
To perform the process of rating the list of the purchased products, the developer may call the method `products()` along with the products' array and the order id as per the following example. 


```js
salla.rating.products({
  products: [
    {
      product_id: "5871",
      comment: "good quality",
      rating: 5,
    },
    {
      product_id: "2589",
      comment: "i like the colors option",
      rating: 4,
    },
    {
      product_id: "1147",
      comment: "good price",
      rating: 4,
    },
  ],
  order_id: 589,
})
.then((response) => {
  /* add your code here */
});
```

## Events
This endpoint may trigger two events, the onProductsRated and onProductsFailed events.

### onProductsRated
This event is triggered when the process of rating a list of the purchased products is done without having any errors coming back from the backend.

```js
salla.event.rating.onProductsRated((response) => {
  console.log(response)
});
```
### onProductsFailed
This event is triggered when the process of rating a list of the purchased products is not completed and an error has occurred.

```js
salla.event.rating.onProductsFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## rating/Rate-Shipping-Companies-Salla-Developer-Documentation-Twilight-Documentation

# Shipping

This endpoint is used for the purpose of rating the shipping company responsible for delivering orders. The customer will be able to send a review of that shipping company.

:::tip
The *shipping rating* endpoint has been implemented in the [Rating](https://docs.salla.dev/doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, , and It's all setup to save developer's time and effort.
:::

## Payload `authenticated`

<DataSchema id="1427925" />

## Response
<Tabs>
  <Tab title="Success">
 
<DataSchema id="1427926" />
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
  </Tab>
  
</Tabs>



## Usage
The method `shipping` may be called for rating a shipping company responsible for delivering an order as follows.

```js
salla.rating.shipping({
  comment: "Fast delivery",
  order_id: 587,
  rating: 5,
  shipping_company_id: 45
})
.then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onShippingRated and onShippingFailed events.

### onShippingRated
This event is triggered when rating a shipping company responsible for delivering an order is done without having any errors coming back from the backend.

```js
salla.event.rating.onShippingRated((response) => {
  console.log(response)
});
```
### onShippingFailed
This event is triggered when rating a shipping company responsible for delivering an order is not completed and an error has occurred.

```js
salla.event.rating.onShippingFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## rating/Rate-Store-Salla-Developer-Documentation-Twilight-Documentation

# Store

This endpoint is used for the purpose of rating a store. The customer will be able to send a review to a store after placing an order with that store.

:::tip
The *store rating* endpoint has been implemented in the [Rating](https://docs.salla.dev/doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::
## Payload `authenticated`


<DataSchema id="1387273" />


## Response
<Tabs>
  <Tab title="Success">


<DataSchema id="1427922" />
```      
  </Tab>
   <Tab title="Error">
    
<DataSchema id="1427184" />
  </Tab>
  
</Tabs>



## Usage
To perform the action of rating a store after placing an order, the developer may use the method `store()` as follows.


```js
salla.rating.store({
  comment: "Fast delivery",
  order_id: 587,
  rating: 5,
})
.then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onStoreRated and onStoreFailed events.

### onStoreRated
This event is triggered when rating a store by the customer is done without having any errors coming back from the backend.

```js
salla.event.rating.onStoreRated((response) => {
  console.log(response)
});
```
### onStoreFailed
This event is triggered when rating a store by the customer is not completed and an error has occurred.

```js
salla.event.rating.onStoreFailed((errorMessage) => {
  console.log(errorMessage)
});

---

