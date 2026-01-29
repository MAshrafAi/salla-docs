# Theme Architecture Components

## Table of Contents

- [component/Fetch-Header-and-Footer-Menus-Salla-Developer-Documentation-Twilight-Documentation](#component-fetch-header-and-footer-menus-salla-developer-documentation-twilight-documentation)
- [component/Fetch-Store-and-Product-Reviews-Salla-Developer-Documentation-Twilight-Documentation](#component-fetch-store-and-product-reviews-salla-developer-documentation-twilight-documentation)
- [theme-architecture-components/Common-Components](#theme-architecture-components-common-components)
- [theme-architecture-components/Home-Components](#theme-architecture-components-home-components)
- [theme-architecture-components/Product-Components](#theme-architecture-components-product-components)
- [theme-architecture-components/Twilight-Theme-Components-Overview-Twilight-Documentation-Salla-Docs](#theme-architecture-components-twilight-theme-components-overview-twilight-documentation-salla-docs)

---

## component/Fetch-Header-and-Footer-Menus-Salla-Developer-Documentation-Twilight-Documentation

# Menus

This endpoint retrieves menus for a specified component, such as `"header"` or `"footer"`. It is commonly used to fetch menus for a particular component in your theme, typically for dynamically rendering navigation or other UI elements. While `"header"` is the default component, you can specify `"footer"` where needed.

## Payload


<DataSchema id="3663618" />

## Response


<Tabs>
  <Tab title="Success">

<DataSchema id="3663842" />
  </Tab>
</Tabs>

## Usage

<Tabs>
  <Tab title="Header Example">
In the case of using `Header`, the developer can use the example below to receive the data.
    
```js
salla.api.component.getMenus('header')
  .then(data => {
    //...
  })
  .catch(error => {
    //...
  });
```
  </Tab>
  <Tab title="Footer Example">
On the other hand, when using `Footer`, the developer can receive the data using the example below.

```js
salla.api.component.getMenus('footer')
  .then(data => {
    //...
  })
  .catch(error => {
    //...
  });
```
  </Tab>
</Tabs>

## Events

The menu process may trigger two events during the menu process, onMenuFetched and onMenuFetchFailed.



### onMenuFetched

Triggered when the menus are successfully fetched.

```js
salla.event.component.onMenuFetched((response) => {
  console.log(response)
});
```

### onMenuFetchFailed

Triggered if there is an error during the fetching process.

```js
salla.event.component.onMenuFetchFailed((errorMessage) => {
  console.log(errorMessage)
});
```

---

## component/Fetch-Store-and-Product-Reviews-Salla-Developer-Documentation-Twilight-Documentation

# Reviews

This endpoint retrieves reviews from various sources such as store, products and more.

## Payload



<DataSchema id="3663867" />

## Response


<Tabs>
  <Tab title="Success">

<DataSchema id="3663617" />
  </Tab>
</Tabs>

## Usage

The method `getReviews` takes in 3 parameters: The maximum number of items to return per page `per_page`, The review's source, `type`, which could be one of the allowed enum values, as well as `items`, which is the response data.

```js
salla.api.component.getReviews({ per_page :5, type: "product", items:"testimonials"})
```

## Events

The menu process may trigger two events during the menu process, reviewsFetched and reviewsFetchFailed.

### reviewsFetched

This event will be triggered when the reviews are successfully fetched.

```js
salla.event.component.reviewsFetched((response) => {
  console.log(response)
});
```

### reviewsFetchFailed

This event will be triggered if there is an error during the fetching process.

```js
salla.event.component.reviewsFetchFailed((errorMessage) => {
  console.log(errorMessage)
});
```

---

## theme-architecture-components/Common-Components

# Common Components

## Docs

- [Header Components](https://docs.salla.dev/422601m0.md): The default header which comes with **Twilight** includes all of header-related components such as `header`,`breadcrumbs`,`menu` and many more. Developers can easily modify these components, as we see in this article.
- [Footer Components](https://docs.salla.dev/422602m0.md): By default, themes created with **Twilight** include a footer section. The footer section includes  components such as the `contacts`, `payment-methods`, `social media links`, and many more.
- [Comments component](https://docs.salla.dev/422603m0.md): This component is used to display a threaded comments section that also allows adding comments and rating them. It can be displayed as a feedback of products or testimonial which are shown in [Single product page](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [Single page](https://docs.salla.dev/doc-422578?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

---

## theme-architecture-components/Home-Components

# Home Components

## Docs

- [Youtube](https://docs.salla.dev/422582m0.md): This **_pre-defined component_** is responsible for displaying Youtube videos that the developer preselects.
- [Fixed banner](https://docs.salla.dev/422583m0.md): A fixed banner is a **_pre-defined component_** which is in charge of displaying a banner that is fixated on the Home Page.
- [Testimonials](https://docs.salla.dev/422584m0.md): This  **_pre-defined component_** displays testimonials, which are feedback given by customers. The display order is set as per newest.
- [Parallax background](https://docs.salla.dev/422585m0.md): Parallax scrolling background is **_pre-defined component_** that functions as a graphics design method in which the background images move past the camera more slowly than foreground images, giving the impression of depth in a 2D scene from a distance.
- [Photos slider](https://docs.salla.dev/422586m0.md): Photos slider (also known as carousels or slideshows) are a simple way to display a variety of images. It's **_pre-defined component_**. The idea of large, magnificent, dazzling picture shows might be very appealing. Attractive photos can entice new visitors to your site by attracting their attention right away.
- [Store features](https://docs.salla.dev/422587m0.md): This **_pre-defined component_** is responsible for showcasing the store features such as payment methods, shipping methods and so on.
- [Square photos](https://docs.salla.dev/422588m0.md): This **_pre-defined component_** simply displays square shape photos in form of a grid. The first photo will be the __ leading __ photo and will be bigger in size.
- [Fixed products](https://docs.salla.dev/422589m0.md): Use this **_pre-defined component_** to display a group of products that has no scrolling effect. Their location is fixed.
- [Products slider](https://docs.salla.dev/422590m0.md): This **_pre-defined component_** slider helps navigate between a list of products in the form of a scrolling list.
- [Featured products - Style 1](https://docs.salla.dev/422591m0.md): Featured products list, which is a **_pre-defined component_**, is a collection created in a specific design to draw customers' attention to see a certain collection of products primarily.
- [Featured Products - Style 2](https://docs.salla.dev/422592m0.md): Featured products list is a collection created in a specific design to draw customers' attention to see a certain collection of products primarily. This component is a **_pre-defined component_**
- [Featured Products - Style 3](https://docs.salla.dev/422593m0.md): Featured products list is a collection, created in a specific design to draw customers' attention to see a certain collection of products primarily. This component is a **_pre-defined component_**
- [Brands](https://docs.salla.dev/422594m0.md): The store brands' logos are displayed using this component. Developers may use any design to style it because this is a significant section to draw the customers' attention.
- [Enhanced Square Banners](https://docs.salla.dev/422595m0.md): The enhanced square banner component is similar to the [Square Photos](https://docs.salla.dev/doc-422588?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component, however it gives an extra option to add texts for the inner element of the smaller images.
- [Main Links](https://docs.salla.dev/422596m0.md): This component is part of the main view for the home page landing part. It helps to portray the store main categories links.
- [Enhanced Slider](https://docs.salla.dev/422597m0.md): This component is similar to the [Photos slider](https://docs.salla.dev/doc-422586), which displays various images. However, it gives an extra option to add texts for the inner element of the pictures.
- [Slider Products with Headers](https://docs.salla.dev/422598m0.md): This component comes with many attractive elements to display products for the customers. It has Headings to describe the sections and a swiper slider to list as much products as possible.
- [Latest Products](https://docs.salla.dev/422599m0.md): This **_pre-defined component_** is set to display the latest products added to the store automatically. It has a fixed, not scrolled, view. It comes with a pre-defined style, which can easily be modified by the developer.
- [Vertical Menu with Slider](https://docs.salla.dev/422600m0.md): This pre-defined component is used to display a menu for a group of the sub-pages' links in a vertical menu. It has a static view, which can easily be modified by the developer.

---

## theme-architecture-components/Product-Components

# Product Components

## Docs

- [Essentials](https://docs.salla.dev/422604m0.md): The product page template consists of several essential components that give a look at the product details. For example, the product's brands, similar products, and product tags components.
- [Options](https://docs.salla.dev/422605m0.md): In this article, we will list the group components in order to create the options related to the product. For example, the product's colors and size, which we need some special text components to display them.

---

## theme-architecture-components/Twilight-Theme-Components-Overview-Twilight-Documentation-Salla-Docs

# Overview

In general, _components_ are independent and reusable bits of code. **Twilight** theme defines a number of _components_ in [`src/views/components/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components) that have properties with strict typing and default values. A property is only required if you mark it required. You can set default values otherwise.

## 📙 What you'll learn
This article lists _all_ of the components shipped with the Twilight theme engin.

:::tip[Tip]
 The developer has the flexibility of developing and including his own components. This mean that the developer can create new files for any desired new component he may need to add to his theme.
:::

## Components 
Twilight main pages include many components that aim to deliver the best shipping experience for the end user.
In this article we will walk you through the main pages' components, which are:

||||||
|---|--|----|---|---|
|[Home components](#home-components)|[Header components](#header-components)|[Footer components](#footer-components)|[Products components](#products-components)|[Comments component](#comments-component)|



### Home Components 
Home components [`src/views/components/home/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components/home) are found in the home page and it's significant in giving the store front- display. Each component plays a role in exhibiting the store main details such as, Youtube videos of the store, customer testimonials and other components that sets the store tone. More on home components and it's usage in home page [here](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

#### Home Components Location

```shell
└── src
  ├── views 
    ├── components
    |     ...
    |     ├──── home
    |     ...
    ...
```
Home components are: 
- [Youtube](https://docs.salla.dev/doc-422582?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Fixed banner](https://docs.salla.dev/doc-422583?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Testimonials ](https://docs.salla.dev/doc-422584?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- Random testimonials
- [Parallax background](https://docs.salla.dev/doc-422585?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Photos slider](https://docs.salla.dev/doc-422586?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Store features](https://docs.salla.dev/doc-422587?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Fixed products](https://docs.salla.dev/doc-422589?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Products slider](https://docs.salla.dev/doc-422590?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Featured products style 1](https://docs.salla.dev/doc-422591?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Featured products style 2](https://docs.salla.dev/doc-422592?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [Featured products style 3](https://docs.salla.dev/doc-422593?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- [latest products](https://docs.salla.dev/doc-422599?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
- Vertical menue with slider
### [Header Components](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
The header components [`src/views/components/header/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components/header) are found on all pages of the store and considered to be used frequently so for ease of access it's postioned on the top area of the page. More about Header components [here](https://docs.salla.dev/doc-422601).
#### [Header Components Location](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

```sh
└── src 
    ├── components
    |     ...
    |     ├──── header
    |     ...
    ...
```

Header components are :
- Header
- Advertisement
- Breadcrumbs
- Main Menu
- User Menu


### [Footer Components ](https://docs.salla.dev/doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

Footer components [`src/views/components/footer/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components/footer) are also commonly used and usually found in the footer area of the page, such are contacts and payment methods. More about Footer components [here](https://docs.salla.dev/doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

#### Footer Components Location
```sh
└── src 
    ├── components
    |     ...
    |     ├──── footer
    |     ...
    ...
```
Footer components are:
- Footer
- Contacts
- Copyrights
- Mobile Apps
- Pages
- Payment Methods
- Social

### Products Components 

Products components [`src/views/components/product/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components/product) are grouped into 2 groups:

- Essentials
- Options

##### Products Components Location
```sh
└── src 
    ├── components
    |     ...
    |     ├──── products
    |     ...
    ...
```

#### [Essentials](https://docs.salla.dev/doc-422604?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)
Essentials components are the main components related to the product, more about Essentials components [here](https://docs.salla.dev/doc-422604?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

Essentials components are: 
  - Donation progress bar
  - Offer
  - Notify availability
  - Quick access
  - Similar products


<!--#### [Offer](4.2.4-Product-components/4.2.4.02-Offers-Components.md)
Offer components are focused on the offers related tothe products, more about Offer components [here](4.2.4-Product-components/4.2.4.02-Offers-Components.md).
Offers components are:
  - Offer
  - Offer-popup
-->
#### [Options](https://docs.salla.dev/doc-422605?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

These components help to add more options to the product components to make it  versatile by using color options also, adding images using image option can give the used a better view of the product. More about Options components [here](https://docs.salla.dev/doc-422605?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

Options components are:
  - Color
  - Date
  - Datetime
  - Donation
  - Image
  - Multiple Options
  - Number
  - Single Option
  - Splitter
  - Text
  - Textarea
  - Thumbnail
  - Time

### [Comments component](https://docs.salla.dev/doc-422603?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

Comment component is used to display comments made by useres on [Single page](https://docs.salla.dev/doc-422578?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) or [Single product page](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). More about Comments component [here](https://docs.salla.dev/doc-422603?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

##### Comments component location 

``` shell
└── src 
    ├── components
    |   ...
    |   └── Comments      
    |   ...
    ...

```

---

