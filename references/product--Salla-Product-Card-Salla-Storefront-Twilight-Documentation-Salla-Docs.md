# Product  Salla Product Card Salla Storefront Twilight Documentation Salla Docs

## Table of Contents

- [product/Salla-Product-Card-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-product-card-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Product-List-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-product-list-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Product-Options-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-product-options-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Product-Size-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-product-size-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Product-Slider-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-product-slider-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Products-Availability-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-products-availability-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Quick-Buy-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-quick-buy-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Quick-Order-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-quick-order-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Scopes-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-scopes-salla-storefront-twilight-documentation-salla-docs)
- [product/Salla-Search-Salla-Storefront-Twilight-Documentation-Salla-Docs](#product-salla-search-salla-storefront-twilight-documentation-salla-docs)
- [product/Search-Products-by-Keyword-Twilight-Documentation](#product-search-products-by-keyword-twilight-documentation)
- [product/Upload-Gift-Image-Twilight-Documentation](#product-upload-gift-image-twilight-documentation)

---

## product/Salla-Product-Card-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Product Card

The `<salla-product-card>` web component is used to contain content and actions about a single product in a card display mode. The component incorporates options for displaying images, hovering over buttons, product information, and more.

## Example

<!--
focus: false
-->

![Product Card](https://cdn.salla.network/docs/twilight/6/js-web-product-card-01.png?v=1-10-2022)

## Usage

<Tabs>
  <Tab title="HTML">
 
 ```html
<!-- Basic Product Card component usage -->
<salla-product-card
  minimal="false"
  special="true">
</salla-product-card>
```
      
  </Tab>

<Tab title="SASS">

This JS web component can be targeted for styling by its `.s-product-card` class. Following is a complete source code for customizing this component:

```js

.s-product-card {
  &-entry {}

  &-image {
    &::before {
      font-family: "sallaicons";
      content: "\ec1f" !important;
    }
  }

  &-vertical {}

  &-horizontal {}

  &-fit-height {}

  &-special {}

  &-full-image {}

  &-minimal {}

  &-donation {}

  &-shadow {}

  &-out-of-stock {}

  &-wishlist-btn {}

  &-content {
    &-main {}

    &-sub {}

    &-footer {}

    &-title {}

    &-subtitle {}

    &-pie {
      &-svg {
        circle {
          transition: stroke-dashoffset 1s linear;
          -webkit-transition: stroke-dashoffset 1s linear;
          -moz-transition: stroke-dashoffset 1s linear;
          -ms-transition: stroke-dashoffset 1s linear;
          -o-transition: stroke-dashoffset 1s linear;
          stroke: #E8EDF2;
          stroke-width: 2px;
          stroke-linecap: round;
          fill: none
        }

        &-base {}

        &-bar {
          stroke: var(--color-primary) !important;
          stroke-dasharray: 100 100;
          stroke-dashoffset: 100
        }
      }
    }

    // for special card
    &-extra-padding {}
  }

  &-donation-input {}
}
```
      
  </Tab>    
</Tabs>


## Properties

| Property        | Attribute         | Description              | Type      | Default     |
| --------------- | ----------------- | ------------------------ | --------- | ----------- |
| Full Image     | `full-image`      | Whether or not to show the full image on the card.         | `boolean` | `undefined` |
| Hide Add Button    | `hide-add-btn`    | Whether or not to hide the "add to cart" button. | `boolean` | `undefined` |
| Horizontal    | `horizontal`      | Whether or not to show the product card as Horizontal card.         | `boolean` | `undefined` |
| Special     | `special`      | Whether or not to show the product card as Special card.            | `boolean` | `undefined` |
| Minimal       | `minimal`         | Whether or not to show the product card as Minimal card.            | `boolean` | `undefined` |
| Product       | `product`         | The product's data.     | `string`  | `undefined` |
| Shadow On Hover | `shadow-on-hover` | Whether or not to support the effect of shadow on hover. | `boolean` | `undefined` |
| Show Quantity  | `show-quantity`   | Whether or not to show quantity.           | `boolean` | `undefined` |

## Slots
The`slots` makes it customizable to modify certain labels, such as `add-to-cart-label`.

| Slot                  | Description        |
| --------------------- | ------------------ |
| `"add-to-cart-label"` | The add to cart text label |



 ### Custom Salla Product Card Component
 
 
:::tip[Note]
The above mentioned content represents the **default** `salla-product-card` component. If you want to further customize the component and build your own product card component, please read further in this section
:::

 The developer can fully customize cards which comes within the Product Lists when calling the component, by utilizing the `custom-salla-product-card` phrase. That allows developers to create their own custom product cards that is returned when the `salla-products-list` is called.

 The following code is about defining a custom HTML element called `custom-salla-product-card` that extends the functionality of a standard HTML element.

The custom element is defined using the `customElements` object provided by the browser, and is given the name `custom-salla-product-card` that Salla has pre-deifned. This element is then assigned to the class variable, say `ProductCard`, which extends the `HTMLElement` class.

The `ProductCard` class has two methods: `connectedCallback` and `render`. The `connectedCallback` method is called automatically by the browser when the element is added to the DOM, and the `render` method is used to generate the content for the custom element.

:::info[Information]
📚 Learn more about Custom Components [Mozilla](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_custom_elements) and [Salla Developer Portal](https://salla.dev/blog/twilight-theme-customization-designing-a-unique-salla-product-card-from-scratch/), as well as [Theme Raed](https://github.com/SallaApp/theme-raed/blob/63bab893bc24d0208103d2450e9b717384e2f50f/src/assets/js/partials/product-card.js).


<Tabs>
  <Tab title="Structure">
```js
class ProductCard extends HTMLElement {
  connectedCallback() {
    try {
      this.product = this.product || JSON.parse(this.getAttribute("product"));
    } catch (e) {
      console.error("could not parse product data");
      return;
    }

    //... your initiate using this.product


    // this.render() is called in salla.onReady to ensure 
    // rendering occurs after the theme finishes loading.
    salla.onReady(() => this.render());
  }

  render() {
    //another logic if you want...
    this.innerHTML = `<div class="product-card">${this.product.name} - ${salla.money(this.product.price)}</div>`;
  }
}

customElements.define("custom-salla-product-card", ProductCard);
```

  </Tab>
  <Tab title="Example">
```js
class ProductCard extends HTMLElement {
  constructor(){
    super()
  }
  
  connectedCallback(){
    // Parse product data
    this.product = this.product || JSON.parse(this.getAttribute('product')); 

    if (window.app?.status === 'ready') {
      this.onReady();
    } else {
      document.addEventListener('theme::ready', () => this.onReady() )
    }
  }

  onReady(){
      
      this.fitImageHeight = salla.config.get('store.settings.product.fit_type');
      salla.wishlist.event.onAdded((event, id) => this.toggleFavoriteIcon(id));
      salla.wishlist.event.onRemoved((event,id) => this.toggleFavoriteIcon(id, false));
      this.placeholder = salla.url.asset(salla.config.get('theme.settings.placeholder'));
      this.getProps()

      // Get page slug
      this.source = salla.config.get("page.slug");

      
      // If the card is in the landing page, hide the add button and show the quantity
      if (this.source == "landing-page") {
        this.hideAddBtn = true;
        this.showQuantity = true;
      }

      salla.lang.onLoaded(() => {
        // Language
        this.remained = salla.lang.get('pages.products.remained');
        this.donationAmount = salla.lang.get('pages.products.donation_amount');
        this.startingPrice = salla.lang.get('pages.products.starting_price');
        this.addToCart = salla.lang.get('pages.cart.add_to_cart');
        this.outOfStock = salla.lang.get('pages.products.out_of_stock');

        // re-render to update translations
        this.render();
      })
      
      this.render()
  }

  initCircleBar() {
    let qty = this.product.quantity,
      total = this.product.quantity > 100 ? this.product.quantity * 2 : 100,
      roundPercent = (qty / total) * 100,
      bar = this.querySelector('.s-product-card-content-pie-svg-bar'),
      strokeDashOffsetValue = 100 - roundPercent;
    bar.style.strokeDashoffset = strokeDashOffsetValue;
  }


  toggleFavoriteIcon(id, isAdded = true) {
    document.querySelectorAll('.s-product-card-wishlist-btn[data-id="' + id + '"]').forEach(btn => {
      app.toggleElementClassIf(btn, 's-product-card-wishlist-added', 'not-added', () => isAdded);
      app.toggleElementClassIf(btn, 'pulse-anime', 'un-favorited', () => isAdded);
    });
  }

  formatDate(date) {
    let d = new Date(date);
    return `${d.getFullYear()}-${d.getMonth() + 1}-${d.getDate()}`;
  } 

  getProductBadge() {
    if (this.product.promotion_title) {
      return `<div class="s-product-card-promotion-title">${this.product.promotion_title}</div>`
    }
    if (this.showQuantity && this.product?.quantity) {
      return `<div
        class="s-product-card-quantity">${this.remained} ${salla.helpers.number(this.product?.quantity)}</div>`
    }
    if (this.showQuantity && this.product?.is_out_of_stock) {
      return `<div class="s-product-card-out-badge">${this.outOfStock}</div>`
    }
    return '';
  }

  getPriceFormat(price) {
    if (!price || price == 0) {
      return salla.config.get('store.settings.product.show_price_as_dash')?'-':'';
    }

    return salla.money(price);
  }

  getProductPrice() {
    let price = '';
    if (this.product.is_on_sale) {
      price = `<div class="s-product-card-sale-price">
                <h4>${this.getPriceFormat(this.product.sale_price)}</h4>
                <span>${this.getPriceFormat(this.product?.regular_price)}</span>
              </div>`;
    }
    else if (this.product.starting_price) {
      price = `<div class="s-product-card-starting-price">
                  <p>${this.startingPrice}</p>
                  <h4> ${this.getPriceFormat(this.product?.starting_price)} </h4>
              </div>`
    }
    else{
      price = `<h4 class="s-product-card-price">${this.getPriceFormat(this.product?.price)}</h4>`
    }

    return price;
  }

  getAddButtonLabel() {
    if (this.product.status === 'sale' && this.product.type === 'booking') {
      return salla.lang.get('pages.cart.book_now'); 
    }

    if (this.product.status === 'sale') {
      return salla.lang.get('pages.cart.add_to_cart');
    }

    if (this.product.type !== 'donating') {
      return salla.lang.get('pages.products.out_of_stock');
    }

    // donating
    return salla.lang.get('pages.products.donation_exceed');
  }

  getProps(){

    /**
     *  Horizontal card.
     */
    this.horizontal = this.hasAttribute('horizontal');
  
    /**
     *  Support shadow on hover.
     */
    this.shadowOnHover = this.hasAttribute('shadowOnHover');
  
    /**
     *  Hide add to cart button.
     */
    this.hideAddBtn = this.hasAttribute('hideAddBtn');
  
    /**
     *  Full image card.
     */
    this.fullImage = this.hasAttribute('fullImage');
  
    /**
     *  Minimal card.
     */
    this.minimal = this.hasAttribute('minimal');
  
    /**
     *  Special card.
     */
    this.isSpecial = this.hasAttribute('isSpecial');
  
    /**
     *  Show quantity.
     */
    this.showQuantity = this.hasAttribute('showQuantity');
  }

  render(){
    this.classList.add('s-product-card-entry'); 
    this.setAttribute('id', this.product.id);
    !this.horizontal && !this.fullImage && !this.minimal? this.classList.add('s-product-card-vertical') : '';
    this.horizontal && !this.fullImage && !this.minimal? this.classList.add('s-product-card-horizontal') : '';
    this.fitImageHeight && !this.isSpecial && !this.fullImage && !this.minimal? this.classList.add('s-product-card-fit-height') : '';
    this.isSpecial? this.classList.add('s-product-card-special') : '';
    this.fullImage? this.classList.add('s-product-card-full-image') : '';
    this.minimal? this.classList.add('s-product-card-minimal') : '';
    this.product?.donation?  this.classList.add('s-product-card-donation') : '';
    this.shadowOnHover?  this.classList.add('s-product-card-shadow') : '';
    this.product?.is_out_of_stock?  this.classList.add('s-product-card-out-of-stock') : '';

    this.innerHTML = `
        <div class="${!this.fullImage ? 's-product-card-image' : 's-product-card-image-full'}">
          <a href="${this.product?.url}">
            <img class="s-product-card-image-${salla.url.is_placeholder(this.product?.image?.url)
              ? 'contain'
              : this.fitImageHeight
                ? this.fitImageHeight
                : 'cover'} lazy"
              src=${this.placeholder}
              alt=${this.product?.image?.alt}
              data-src=${this.product?.image?.url || this.product?.thumbnail}
            />
            ${!this.fullImage && !this.minimal ? this.getProductBadge() : ''}
          </a>
          ${this.fullImage ? `<a href="${this.product?.url}" class="s-product-card-overlay"></a>`:''}
          ${!this.horizontal && !this.fullImage ?
            `<salla-button
              shape="icon"
              fill="outline"
              color="light"
              name="product-name-${this.product.id}"
              aria-label="Add or remove to wishlist"
              class="s-product-card-wishlist-btn animated "
              onclick="salla.wishlist.toggle(${this.product.id})"
              data-id="${this.product.id}">
              <i class="sicon-heart"></i>
            </salla-button>` : ``
          }
        </div>
        <div class="s-product-card-content">
          ${this.isSpecial && this.product?.quantity ?
            `<div class="s-product-card-content-pie">
              <span>
                <b>${salla.helpers.number(this.product?.quantity)}</b>
                ${this.remained}
              </span>
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="-2 -1 36 34" class="s-product-card-content-pie-svg">
                <circle cx="16" cy="16" r="15.9155" class="s-product-card-content-pie-svg-base" />
                <circle cx="16" cy="16" r="15.9155" class="s-product-card-content-pie-svg-bar" />
              </svg>
            </div>`
            : ``}

          <div class="s-product-card-content-main ${this.isSpecial ? 's-product-card-content-extra-padding' : ''}">
            <h3 class="s-product-card-content-title">
              <a href="${this.product?.url}">${this.product?.name}</a>
            </h3>

            ${this.product?.subtitle && !this.minimal ?
              `<p class="s-product-card-content-subtitle">${this.product?.subtitle}</p>`
              : ``}
          </div>
          ${this.product?.donation && !this.minimal && !this.fullImage ?
          `[<salla-progress-bar donation=${this.product?.donation} />
          <div class="s-product-card-donation-input">
            ${this.product?.donation?.can_donate ?
              `[<label htmlFor="donation-amount">${this.donationAmount} <span>*</span></label>,
              <input
                type="text"
                onInput="${e => {
                  salla.helpers.inputDigitsOnly(e.target);
                  this.addBtn.donatingAmount = (e.target).value;
                }}"
                id="donation-amount"
                name="donating_amount"
                class="s-form-control"
                placeholder="${this.donationAmount}" />]`
              : ``}
          </div>]`
            : ''}
          <div class="s-product-card-content-sub ${this.isSpecial ? 's-product-card-content-extra-padding' : ''}">
            ${this.getProductPrice()}
            ${this.product?.rating?.stars && !this.minimal ?
              `<div class="s-product-card-rating">
                <i class="sicon-star2"></i>
                <span>${this.product.rating.stars}</span>
              </div>`
               : ``}
          </div>

          ${this.isSpecial && this.product.discount_ends
            ? `<salla-count-down date="${this.formatDate(this.product.discount_ends)}" end-of-day=${true} boxed=${true}
              labeled=${true} />`
            : ``}


          ${!this.hideAddBtn ?
            `<div class="s-product-card-content-footer gap-2">
              <salla-add-product-button fill="outline" width="wide"
                product-id="${this.product.id}"
                product-status="${this.product.status}"
                product-type="${this.product.type}">
                ${this.product.status == 'sale' ? 
                    `<i class="text-[16px] sicon-${ this.product.type == 'booking' ? 'calendar-time' : 'shopping-bag'}"></i>` : ``
                  }
                ${this.product.add_to_cart_label ? this.product.add_to_cart_label : this.getAddButtonLabel() }
              </salla-add-product-button>

              ${this.horizontal || this.fullImage ?
                `<salla-button 
                  shape="icon" 
                  fill="outline" 
                  color="light" 
                  id="card-wishlist-btn-${this.product.id}-horizontal"
                  aria-label="Add or remove to wishlist"
                  class="s-product-card-wishlist-btn animated"
                  onclick="salla.wishlist.toggle(${this.product.id})"
                  data-id="${this.product.id}">
                  <i class="sicon-heart"></i> 
                </salla-button>`
                : ``}
            </div>`
            : ``}
        </div>
      `

      // re-init favorite icon
      if (!salla.config.isGuest()){
        salla.storage.get('salla::wishlist', []).forEach(id => this.toggleFavoriteIcon(id));
      }

      document.lazyLoadInstance?.update(this.querySelectorAll('.lazy'));

      if (this.product?.quantity && this.isSpecial) {
        this.initCircleBar();
      }
    }
}

customElements.define('custom-salla-product-card', ProductCard);
```

  </Tab>
</Tabs>

---

## product/Salla-Product-List-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Products List

The `<salla-products-list>` web component is used to display a group of related products with some information, such as products' names, prices, and other relevant information in an organized way. Users can interact with the component by clicking on a product to view its details.


## Example

<!--
focus: false
-->

![Products List](https://cdn.salla.network/docs/twilight/6/js-web-product-list-01.jpg?v=1-10-2022)


## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Product List component usage -->
<salla-products-list
  source="offers"
  limit="5"
  horizontal-cards="true">
</salla-products-list>
```
      
  </Tab>
  
</Tabs>


:::tip[Note]
This component, `salla-product-list`, uses inherently the **default** [`salla-product-card`](https://docs.salla.dev/doc-422718?nav=01HNFTE06J4QC24T0D5BPRYKMD) component. If you want to further customize the component, feel free to read more details from [here](https://docs.salla.dev/doc-422718#custom-salla-product-card-component).
:::


## Properties

| Property               | Attribute                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                   | Type                                                                                                          | Default                       |
| ---------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| Autoload               | `autoload`               | Whether or not to autoload the next page's content when scrolling to its view                                                                                                                                                                                                                                                                                                                                                                 | `boolean`                                                                                                     | `'false'`                     |
| Filters Results        | `filters-results`        | Display the filteration results. The events `salla-filters::changed` and `salla-filters::re-render` should be listened to in order for this property to function properly                                                                                                                                                                                                                                                                     | `boolean`                                                                                                     | `undefined`                   |
| Horizontal Cards       | `horizontal-cards`       | Shows the product lists in a horizontal cards' way                                                                                                                                                                                                                                                                                                                                                                                            | `boolean`                                                                                                     | `undefined`                   |
| Includes             | `includes`               | Specifies additional data to be included in the product fetch response. The value can be an array of strings or a JSON string. <br>Example:<br> - As an array:<br> &nbsp; - `includes=["options", "images"]`<br> - As a JSON string:<br> &nbsp; - `includes='["options", "images"]'` <br> The array or JSON string can include product options, `"options"`, in the response.<br>| `string \| string[]`                                                                                          | `undefined`                   |
| Limit                  | `limit`                  | Limit the number of products in the list.                                                                                                                                                                                                                                                                                                                                                                                                     | `number`                                                                                                      | `undefined`                   |
| Product Card Component | `product-card-component` | Custom Card Component for the Salla Products List.  This property  allows you to [customize](doc-422718#custom-salla-product-card-component) the appearance of individual product cards within a Salla Products List.                                                                                                                                                                                                                         | `string`                                                                                                      | `'custom-salla-product-card'` |
| Row Cards             | `row-cards`              | Display product cards in a vertical list, with each row containing only one product card                                                                                                                                                                                                                                                                                                                                                                                                                | `boolean`                                                                                                     | `undefined`                   |
| Sort By                | `sort-by`                | Sorting the list of products.                                                                                                                                                                                                                                                                                                                                                                                                                 | `string`                                                                                                      | `undefined`                   |
| Source                 | `source`                 | The Products List's source                                                                                                                                                                                                                                                                                                                                                                                                                    | `"brands" \| "categories" \| "json" \| "latest" \| "offers" \| "related" \| "search" \| "selected" \| "tags"` | `undefined`                   |
| Source Value           | `source-value`           | The source value, which could be consisting of different values such as the following: • array of IDs when `source` in `['categories', 'brands', 'tags', 'selected']` \| • keyword when `source` = `'search'` \| • products payload when `source` = `'json'` \| • product_id when `source` = `'related'`                                                                                                                                      | `string`                                                                                                      | `undefined`                   |



## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `reload` which reloads the product list view.


| Method                   | Description                                           | Return Type            |
| ------------------------ | ----------------------------------------------------- | ---------------------- |
| `reload()`                 | Reloads the product list view                                   | `Promise<any>`         |
| `setFilters(filters: any)`                 | Sets the filters value                                   | `Promise<any>`         |

---

## product/Salla-Product-Options-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Product Options

The `<salla-product-options>` web component is used to show to the Merchant all the fields that are customizable to curate the experience of personalizing a product prior to ordering it. Read more details on the proper use of each element of the component from [here](https://docs.salla.dev/doc-422605?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

:::tip[Note]
Available API Endpoints for the Product Options component are:

- [Product Details](https://docs.salla.dev/doc-422649?nav=01HNFTDZPB31Y2E120R84YXKCX)
- [Upload Gift Image](https://docs.salla.dev/doc-422648?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::


## Example

<!--
focus: false
-->

![Product Options](https://cdn.salla.network/docs/twilight/6/js-web-product-options-01.jpg?v=1-10-2022)

## Usage

<Tabs>
  <Tab title="HTML">
 
      
   ```html
<!-- Basic Product Options component usage in the Product Page - The product object will be given by default -->
{% if product.options|length %}
  <salla-product-options
    options="{{ product.options }}"
    product-id="{{ product.id }}">
  </salla-product-options>
{% endif %}
```
    
  </Tab>
    
  <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-product-options` class. Following is a complete source code for customizing this component:

```css
.s-product-options{
  &-wrapper{

  }
  &-option-container{

  }
  &-option{

  }
  &-option-label{

  }
  &-option-content{

  }
  &-colors-wrapper{

  }
  &-date-element{

  }
  &-time-element{
    
  }
  &-datetime-element{

  }
  &-image-input{

  }
  &-multiple-options-wrapper{

  }
  &-splitter{

  }
  &-text{

  }
  &-textarea{

  }
  &-thumbnails-wrapper{

  }
}
```      
  </Tab>  
  
</Tabs>



## Properties

| Property   | Attribute    | Description                                                  | Type     | Default                       |
| ---------- | ------------ | ------------------------------------------------------------ | -------- | ----------------------------- |
| Options    | `options`    | Product detail information.                                  | `string` | `undefined`                   |
| Product ID | `product-id` | The Product ID to which the all options will be fetched for. | `number` | `salla.config.get('page.id')` |

## Events

| Event                        | Description                                                             | Type                    |
| ---------------------------- | ----------------------------------------------------------------------- | ----------------------- |
`changed`              | This event will be fired when the product options is changed.             | `CustomEvent<any>`      |

:::info[Information]
The `changed` event in the `salla-product-options` component, contains some data about the changed options, which is explained in the following structure and example.
:::

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `getOption` which gets a specific option by its ID.

| Method   | Description             | Return Type            |
| -------- | ----------------------- | ---------------------- |
| `getOption(option_id: any)` | Gets a specific option by its ID.  | `Promise<Option>` |
| `getSelectedOptions()` | Gets all selected options. | `Promise<any[]>` |
| `getSelectedOptionsData()` | Gets the IDs of the selected options. | `Promise<{}>` |
| `hasOutOfStockOption()` | Returns a `true` value if there is any out of stock options that are selected and vise versa. | `Promise<boolean>` |
| `reportValidty()` | Reports the options' form validty. | `Promise<boolean>` |


## JSON Code Structure

#### Structure


| Name     | Description                                            |
| -------- | ------------------------------------------------------ |
| `event`  | The native change event for each option               . |
| `option` | The entire changed option data                        . |
| `detail` | The specific item that has been selected in the option. |


#### Example

<details>

  <summary> <tt>detail</tt> </summary>
  <code>{id: 123456789, name: 'XL', additional price: 0, option_value: null, image: null, ...}</code> 

  </details>

  <details>
  <summary><tt>event</tt> </summary>
  <code>{isTrusted: true, type: 'change', target: select.s-form-control, currentTarget: null, eventPhase: 0 ...}</code> 

  </details>

  <details>
  <summary><tt>option</tt> </summary>
  <code>{id: 1234567899, name: "المقاس", required: true, type: 'single-option', placeholder: 'اختر' ...}</code> 

</details>

---

## product/Salla-Product-Size-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Product Size Guide

The `<salla-product-size-guide>` web component is used to enable the merchant to add product measurements of height, weight, depth and other metrics for the customer to visualize the actual product size in real life. The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `open` and `close` the Product Size Guide component.

:::tip[Note]
Available API Endpoints for the Product Size Guide component are:

- [Get Size Guides](https://docs.salla.dev/doc-422651?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::


## Example

<!--focus: false -->

![Product Size Guide Image](https://cdn.salla.network/docs/twilight/6/js-web-product-size-01.png)

## Usage

<Tabs>
  <Tab title="HTML">

      
```html
<!-- Basic Product Size Guide for a specific product -->
<salla-button
  shape="link"
  color="primary"
  onclick="salla.event.dispatch('size-guide::open', '1153090815')"
>
  Show Size Guide
</salla-button>

<!-- product size guide modal -->
<salla-product-size-guide></salla-product-size-guide>
```
      
  </Tab>
  
</Tabs>



## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `close` which hides the size-guide pop-up modal window. 


| Method                     | Description                              | Return Type            |
| -------------------------- | ---------------------------------------- | ---------------------- |
| `close()`                  | Hides the size-guide pop-up modal window | `Promise<HTMLElement>` |
| `open(product_id: number)` | Show the size-guide pop-up modal window  | `Promise<any>`         |

## Slots
The`slots` makes it customizable to modify certain labels, such as `footer`.
| Slot       | Description                                                      |
| ---------- | ---------------------------------------------------------------- |
| `footer` | The bottom section of the component. Value is "empty" by default |
| `header` | The upper section of the component. Value is "empty" by default  |

---

## product/Salla-Product-Slider-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Products Slider

The `<salla-products-slider>` web component is used to navigate horizontally through a group of related products. Product sliders can be easily arranged in a highly customizable layout, allowing for various product views or collections to be presented in a visually appealing way.

## Example

<!--
focus: false
-->

![Products Slider](https://cdn.salla.network/docs/twilight/6/js-web-product-slider-01.jpg?v=1-10-2022)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Products Slider component usage -->
<salla-products-slider
  source="latest"
  block-title="Brands"
  slider-id="096176">
</salla-product-slider>
```      
  </Tab>
<Tab title="SASS">

    
```css
.s-products-slider{
  &-wrapper{

  }
  &-slider{

  }
  &-card{

  }
}
```

  </Tab>    
</Tabs>


:::tip[Note]
This component, `salla-products-slider`, uses inherently the **default** [`salla-product-card`](https://docs.salla.dev/doc-422718?nav=01HNFTE06J4QC24T0D5BPRYKMD) component. If you want to further customize the component, feel free to read more details from [here](https://docs.salla.dev/doc-422718#custom-salla-product-card-component).
:::

## Properties

| Property        | Attribute         | Description                                                                                                                                                                                                             | Type                                                                                                                | Default     |
| --------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------- |
| Auto Play    | `autoplay`     | Allow a products slider to automatically advance to the next slide.                                                                                                                                                                       | `boolean`                                                                                                            | `undefined` |
| Block Title    | `block-title`     | Title of the block, which works only if the slider is set to `true`                                                                                                                                                                       | `string`                                                                                                            | `undefined` |
| Display All URL | `display-all-url` | Lists down all URLs                                                                                                                                                                                                        | `string`                                                                                                            | `undefined` |
| Includes             | `includes`               | Specifies additional data to be included in the product fetch response. The value can be an array of strings or a JSON string. <br>Example:<br> - As an array:<br> &nbsp; - `includes=["options"]`<br> - As a JSON string:<br> &nbsp; - `includes='["options"]'` <br> The array or JSON string can include product options, `"options"`, in the response.<br>| `string \| string[]`                              | `undefined`                   |
| Limit         | `limit`           | Limits the number of products in the list                                                                                                                                                                               | `number`                                                                                                            | `undefined` |
| Product Card Component | `product-card-component` | Custom Card Component for the Salla Products Slider.  This property allows you to [customize](https://docs.salla.dev/doc-422718?nav=01HNFTE06J4QC24T0D5BPRYKMD) the appearance of individual product cards within a Salla Products Slider.                                                 | `string`                                                                                                            | `'custom-salla-product-card'` |
| Slider ID      | `slider-id`       | Slider ID's value. If it is not provided, it will be generated automatically.                                                                                                                                                              | `string`                                                                                                            | `undefined` |
| Source        | `source`          | The Products List's source                                                                                                 | `"brands" \| "categories" \| "json" \| "landing-page" \| "latest" \| "offers" \| "related" \| "selected" \| "tags"` | `undefined` |
| Source Value   | `source-value`    | The source value, which could be consisting of different values such as the following: • array of IDs when `source` in `['categories', 'brands', 'tags', 'selected']` \| • keyword when `source` = `'search'` \| • products payload when `source` = `'json'` \| • product_id when `source` = `'related'` | `string`                                                                                                      | `undefined` |
| Sub Title      | `sub-title`       | The sub title of the block, which works only if the slider is set to `true`                                                                                                                                                                   | `string`                                                                                                            | `undefined` |

---

## product/Salla-Products-Availability-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Product Availability

The `<salla-product-availability>` web component is to show the "Notify availability" option as a button for the registered customer, while prompting unregistered merchants to input their phone number/email to be added to the notification list. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component and that can be customized using the properties' parameters available.

:::tip[Note]
Available API Endpoints for the Product Availability component is:

- [Product Availability](https://docs.salla.dev/doc-422642?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::

## Example

<!--
focus: false
-->

![Product Availability Example](https://cdn.salla.network/docs/twilight/6/js-web-product-availability-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">
   
```html
<!-- Product Availability Modal with SMS & Mobile for unsubscribed users -->
<salla-product-availability
  product-id="12345"
  channels="sms,email"
  is-subscribed="false">
</salla-product-availability>

<!-- Product Availability for subscribed users -->
<salla-product-availability product-id="12345" is-subscribed="true"></salla-product-availability>
```
   
  </Tab>
  <Tab title="SASS">

      
This JS web component can be targeted for styling by its `.s-product-availability` class. Following is a complete source code for customizing this component:

```css

.s-product-availability {
  &-wrap {

  }
  &-subscribed {

  }

  &-subs-icon {

  }

  &-body {

  }

  &-label {

  }

  &-input {

  }

  &-footer {

  }

  &-footer-btn {

  }

  &-error-msg {

  }
}
```
  </Tab>  
</Tabs>

:::tip[Tip]
`is-subscribed` boolean variable manipulates the status of the Product Availability Component.
:::


## Properties

| Property      | Attribute       | Description                                                               | Type                                | Default                       |
| ------------- | --------------- | ------------------------------------------------------------------------- | ----------------------------------- | ----------------------------- |
| Channels      | `channels`      | Available notification channels                                           | `"email" \| "sms" \| "sms,email"` | `undefined`                   |
| Is Subscribed | `is-subscribed` | Whether or not the current user subscribed to the notification channel                       | `boolean`                           | `'false'`                       |
| Product ID    | `product-id`    | Product ID under which the merchant can sign up for an availability notice | `number`                            | `salla.config.get('page.id')` |

---

## product/Salla-Quick-Buy-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Quick Buy

The `<salla-quick-buy>` web component is used for quick purchase. It redirects the customer immediately to the checkout page. By streamlining the shopping experience, customer can cut out extra steps and reduce abandonments, giving customers a secure and frictionless way to buy goods online. 

:::tip[Note]
This component redirects customers directly to the checkout page if *Apple Pay* is not active for their current store. However, if *Apple Pay* is active, it will start a new Apple Pay session to prompt the customer to pay.
:::

## Example

<!--focus: false -->
![Quick Buy](https://cdn.salla.network/docs/twilight/6/js-web-quick-buy-01.jpeg) 

## Usage

<Tabs>
  <Tab title="HTML">
      
   ```html
<!-- Basic Quick Buy component usage -->
<salla-quick-buy
  product-id="950497"
  type="donate">
</salla-quick-buy>
```   
  </Tab>
  <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-quick-buy` class. Following is a complete source code for customizing this component:

```css
.s-quick-buy {
  &-button {
    .s-button-text {
      display: flex;
    }
  }

  &-apple-pay {

  }
}

apple-pay-button {
  --apple-pay-button-width: 100%;
  --apple-pay-button-height: 40px;
  --apple-pay-button-border-radius: 7px;
  --apple-pay-button-padding: 0px 5px;
  --apple-pay-button-box-sizing: content-box;
}
```

      
  </Tab>  
  
</Tabs>


## Properties

| Property | Attribute  | Description                                                                                                | Type                             | Default     |
| -------- | ---------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------- | ----------- |
| Amount            | `amount`              | Product's amount value.                                                                                                         | `number`                                                     | `0`         |
| Currency          | `currency`            | Product's amount currency.                                                                                                 | `string`                                                     | `undefined` |
| Is Require Shipping | `is-require-shipping` | To be passed to the `purchaseNow` request.                                                                                     | `boolean`                                                    | `undefined` |
| Options           | --                    | Product options, if is empty will get the data from the `document.querySelector('salla-product-options[product-id="X"]')` | `{}`                                                         | `{}`        |
| Product ID         | `product-id`          | Product's ID.                                                                                                             | `string`                                                     | `undefined` |
| Type              | `type`                | Button's type.                                                                                                            | `"book" \| "buy" \| "donate" \| "order" \| "pay" \| "plain"` | `'buy'`     |

---

## product/Salla-Quick-Order-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Quick Order

The `<salla-quick-order>` web component allows customers to request a call from the store owner for assistance with making their order. Customers provide their contact information through this component and the store owner is notified of the request. The store owner can then contact the customer directly to provide assistance with their order. This web component is an easy and convenient way for customers to receive help and support from the store owner, improving the overall customer experience. 
It may consist of one or more components, such as [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD), [`<salla-modal>`](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD), [`<salla-tel-input>`](https://docs.salla.dev/doc-422739?nav=01HNFTE06J4QC24T0D5BPRYKMD) and more.

<!-- Available API Endpoint for the Quick Buy component is:

- [Get Quick Checkout Setting]() -->

## Example

<!--focus: false -->
![Quick Order Order](https://cdn.salla.network/docs/twilight/6/js-web-quick-order-01.png?v=1-10-2022)


## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Quick Order component usage -->
<salla-quick-order
  is-email-required="true"
  product-id="207865447"
  quick-order-style="white">
</salla-quick-order>
```      
  </Tab>
<Tab title="SASS">
 

This JS web component can be targeted for styling by its `.s-quick-order` class. Following is a complete source code for customizing this component:

```css
.s-quick-order {
    .s-quick-order-container {
        padding: 15px;
        border: 1px solid #d0d0d0;
        border-radius: 6px;
        background: #f3f3f3;

        &.gray {
            background: #f3f3f3;
            border: 1px solid #d0d0d0;
        }

        &.white {
            background: #fff;
            border: 1px solid #dfdfdf;
        }

        .s-quick-order-button-cont {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
        }

        .s-quick-order-checkbox-container {
            display: flex;
            margin: 10px 0;

            input {
                padding: 10px;
                width: 20px;
                border: 1px solid #eee;
                border-radius: 5px;
                margin: 6px;
            }
        }

        .s-quick-order-expandable {
            visibility: hidden;
            height: 0;
            transition: height 1s ease;

            &.show {
                visibility: visible;
                height: auto;
            }
        }

        input {
            padding: 10px;
            width: 100%;
            border: 1px solid #eee;
            border-radius: 5px;
        }
    }
}
```

    
  </Tab>    
</Tabs>



## Properties

| Property                 | Attribute                  | Description                                                                | Type      | Default                                                        |
| ------------------------ | -------------------------- | -------------------------------------------------------------------------- | --------- | -------------------------------------------------------------- |
| Agreement Text           | `agreement-text`           | Shows an agreement text from server or from props                          | `string`  | `salla.lang.get(     'pages.checkout.show_full_agreement'   )` |
| Confirm Pay Button Title | `confirm-pay-button-title` | Displays a confirmation button text of the "quick order confirm pay" label | `string`  | `'اشتر الآن'`                                                        |
| Is Email Required        | `is-email-required`        | Whether or not the email is required                                       | `boolean` | `false`                                                        |
| Pay Button Title         | `pay-button-title`         | Customizes the "pay title" button context                                  | `string`  | `'اطلب المنتج'`                                                        |
| Product ID               | `product-id`               | Fetches the Product ID from either local or from a specific page           | `string`  | `undefined`                                                    |
Quick Order Style        | `quick-order-style`        | Styles the Quick Order component                                           |`\| "default" \| "grey" \| "white" \|` | `'default'`    
| Quick Order Title        | `quick-order-title`        | Customizes the Quick Order title text                                      | `string`  | `'ليش تنتظر؟'`                                                      |
| Sub Title                | `sub-title`                | Customizes the Quick Order sub title text                                  | `string`  | `'احصل على المنتج مباشرة الآن'`                                                  |
| Thanks Message           | `thanks-message`           | Displays a Thank You message after the purchase is completed               | `string`  | `undefined`                                                    |


## Events

| Event                | Description                                                       | Type               |
| -------------------- | ----------------------------------------------------------------- | ------------------ |
| `quickOrderSubmited` | This event will be fired when the order gets submitted successfully. | `CustomEvent<any>` |

---

## product/Salla-Scopes-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Scopes

The `<salla-Scopes>` web component shows a list of scopes (Branches) owned by the store. It consists of [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component that enables the addition of a header component, and that can be customized using the properties' parameters.


## Example

<!--
focus: false
-->

![Branch Example](https://cdn.salla.network/docs/twilight/6/js-web-branches-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Button to activate Show Branch -->
<salla-button data-target="branches-header"
    onclick="salla.event.dispatch('scopes::open'{mode: 'availability', product_id: 1234})">
    Show Branch
</salla-button>

<!-- Scopes Component props -->
<salla-scopes search-display-limit="6" selection="optional"></salla-scopes>
```
      
  </Tab>
<Tab title="JS">
 
```js
// Save reference to the Button Component below
var branches = document.querySelector("salla-branches");
```
  </Tab>   
    
  <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-branches` class. Following is a complete source code for customizing this component:

```css

.s-branches {
  &-title {

  }
  &-input-wrap {

  }
  &-input {

  }
  &-label {

  }
  &-select {

  }
  &-space-v {

  }
  &-sr-only {

  }
  &-is-closed {

  }
  &-closed-badge {

  }
  &-clickable {

  }
  &-submit {

  }
  &-color-red {

  }
  &-color-green {

  }
  &-color-gray {

  }
}
```
      
  </Tab>  
</Tabs>

## Properties

| Property             | Attribute              | Description                                                          | Type                          | Default    |
| -------------------- | ---------------------- | -------------------------------------------------------------------- | ----------------------------- | ---------- |
| Search Display Limit | `search-display-limit` | Determines when to show the search field                             | `number`                      | `6`        |
| Selection            | `selection`            | Either optionally open the modal or enforce the pop-up to the viewer | `"mandatory" \| "optional" \| | `optional`|

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `show` and/or `hide` the component.


| Method                                  | Description                                        | Return Type            |
| --------------------------------------- | -------------------------------------------------- | ---------------------- |
| `close()`                               | Closes the scope modal dialog.                     | `Promise<HTMLElement>` |
| `open(mode?: any, product_id?: number)` | Opens the scope modal dialog.                      | `Promise<any>`         |
| `handleSubmit()`                        | Submits a form which modifies the existing scopes. | `Promise<any>`         |

## Slots
The `slots` makes it customizable to modify certain labels, such as `footer`
| Slot     | Description                                                                                                                            |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `footer` | This slot utilizes the "`handleSubmit`" method to submit the form. The bottom section of the component, which is used for form action. |

<!-- theme: success

> 💡 **Tip**
>
> To use a method, you can for instance `show` the component via the event:
>
> ```html
> onclick="salla.event.dispatch(`branches::show`)"
> ```
>
> and `hide` the component via the event:
>
> ```html
> onclick="salla.event.dispatch(`branches::hide`)"
> ``` -->

---

## product/Salla-Search-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Search

The `<salla-search>` website element shows a search box, field, or bar. Its specific purpose is to accept user input for database searching. It consists of a [Modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) activated by the [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component, and that can be customized using the slots' parameters available.

:::tip[Note]
Available API Endpoints for the Search component is:

- [Search Products](https://docs.salla.dev/doc-422644?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::

## Example

<!--
focus: false
-->

![Search Example](https://cdn.salla.network/docs/twilight/6/js-web-search-01.gif)

## Usage
<Tabs>
  <Tab title="HTML">

```html
<!-- Button to open search component-->
<salla-button onclick="search.open()">Search</salla-button>

<!-- Basic Salla Search component-->
<salla-search></salla-search>

<!-- Inline Search Bar Input Field-->
<salla-search inline="true" height="50"></salla-search>

<!-- Custom Slots within Inline Search Bar-->
<salla-search inline>
    <div slot="product">{name} | {price} | {regular_price} | {image}</div>
</salla-search>
```
    
  </Tab>
<Tab title="JS">
    
```js
// Save reference to the Search Component below
var search = document.querySelector("salla-search");
```        
  </Tab>
    
  <Tab title="SASS">
  
This JS web component can be targeted for styling by its `.s-search` class. Following is a complete source code for customizing this component:

```js

.s-search {
  &-inline{
    
  }
  &-container {
    &-open {

    }
  }
  &-input {

  }
  &-icon {

  }
  &-spinner {

  }
  &-spinner-loader {

  }
  &-results {

  }
  &-no-results{

  }
  &-container-open{
    
  }
  &-product {
    &-image-container {

    }
    &-image {
      
    }
    &-details {

    }
    &-title {

    }
    &-price {

    }
  }
}
```
    
  </Tab>  
</Tabs>



## Properties

| Property | Attribute | Description                                                                    | Type      | Default   |
| -------- | --------- | ------------------------------------------------------------------------------ | --------- | --------- |
| Height   | `height`  | Adjusts the height of the search input Bar                                     | `number`  | `'60'`    |
| Inline   | `inline`  | Sets the component display without the pop-up modal window                     | `boolean` | `'false'` |
| Oval     | `oval`    | Creates the Search Bar in an oval shape by adding a border radius to the input | `boolean` | `'false'` |

## Slots
The`slots` makes it customizable to modify certain labels, such as `product` where developers can self-modify labels of `name`, `price`, `regular_price`, and `image`.

| Slot      | Description                                                                                                                                  |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `product` | In the results, the products card outcome is replaced by the following replaceable props: `{name}`, `{price}`, `{regular_price}`, `{image}`. |

---

## product/Search-Products-by-Keyword-Twilight-Documentation

# Search products

A search query is group of keywords that a customer enters to satisfy their information needs. This endpoint enables the customer to enter a phrase or a keyword combination to find a product list of interest.

:::tip
The *search products* endpoint has been implemented in the [Search](https://docs.salla.dev/doc-422730?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::


## Payload


<DataSchema id="1387275" />


## Response
<Tabs>
  <Tab title="Success">
  
<DataSchema id="1387277" />
  </Tab>
    
   <Tab title="Error">

<DataSchema id="1427314" />
      
  </Tab>
  
</Tabs>



## Usage
To perform the action of searching for products using a query string, the developer may call the method `products()` as follows;


```js
salla.product.search({ query: "green iphone" }).then((response) => {
  /* add your code here */
});

// TIP: short version
salla.product.search("green iphone").then((response) => {
  /* add your code here */
});
```

## Events
This endpoint may trigger two events, the onSearchResults and onSearchFailed events.
### onSearchResults
This event is triggered when searching for products using a query string is done without having any errors coming back from the backend.

```js
salla.product.event.onSearchResults((response) => {
  console.log(response)
});
```
### onSearchFailed
This event is triggered when searching for products using a query string is not completed and an error has occurred.

```js
salla.product.event.onSearchFailed((errorMessage) => {
  console.log(errorMessage)
});

---

## product/Upload-Gift-Image-Twilight-Documentation

# Upload Gift Image

This endpoint is used to upload a product image associated with the gifted product.

:::tip
The *upload gift image* endpoint has been implemented in the [Gifting](https://docs.salla.dev/doc-422705?nav=01HNFTE06J4QC24T0D5BPRYKMD) Web Component, and It's all setup to save developer's time and effort.
:::

## Payload


<DataSchema id="1387242" />


## Response
<Tabs>
  <Tab title="Success">
      
<DataSchema id="1427796" />
  </Tab>
   <Tab title="Error">

<DataSchema id="1427184" />
      
  </Tab>
  
</Tabs>


## Usage
To perform the action of uploading a product image associated with a gifted product, the developer may call the method `uploadGiftImage()` as follows.


```js
salla.product.uploadGiftImage({ multipartPayload: my_form }).then((response) => {
  /* add your code here */
});
```


## Events
This endpoint may trigger two events, the onGiftImageUploadSucceeded and onGiftImageUploadFailed events.

### onGiftImageUploadSucceeded
This event is triggered when uploading a product image associated with a gifted product is done without having any errors coming back from the backend.

```js
salla.product.event.onGiftImageUploadSucceeded((response) => {
  console.log(response)
});
```
### onGiftImageUploadFailed
This event is triggered when uploading a product image associated with a gifted product is not completed and an error has occurred.

```js
salla.product.event.onGiftImageUploadFailed((errorMessage) => {
  console.log(errorMessage)
});

---

