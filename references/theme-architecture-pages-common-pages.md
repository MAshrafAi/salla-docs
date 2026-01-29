# Theme Architecture Pages Common Pages

## Table of Contents

- [theme-architecture-pages-common-pages/Cart-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-common-pages-cart-page-template-twilight-documentation-salla-docs)
- [theme-architecture-pages-common-pages/Landing-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-common-pages-landing-page-template-twilight-documentation-salla-docs)
- [theme-architecture-pages-common-pages/Loyalty-Program-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-common-pages-loyalty-program-page-template-twilight-documentation-salla-docs)
- [theme-architecture-pages-common-pages/Static-Single-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-common-pages-static-single-page-template-twilight-documentation-salla-docs)
- [theme-architecture-pages-common-pages/Thank-You-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-common-pages-thank-you-page-template-twilight-documentation-salla-docs)
- [theme-architecture-pages/Blog-Pages](#theme-architecture-pages-blog-pages)
- [theme-architecture-pages/Brand-Pages](#theme-architecture-pages-brand-pages)
- [theme-architecture-pages/Common-Pages](#theme-architecture-pages-common-pages)
- [theme-architecture-pages/Customer-Pages](#theme-architecture-pages-customer-pages)
- [theme-architecture-pages/Product-Pages](#theme-architecture-pages-product-pages)
- [theme-architecture-pages/Themes-Home-Page-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-themes-home-page-twilight-documentation-salla-docs)
- [theme-architecture-pages/Themes-Pages-Overview-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-themes-pages-overview-twilight-documentation-salla-docs)

---

## theme-architecture-pages-common-pages/Cart-Page-Template-Twilight-Documentation-Salla-Docs

# Cart

The [`cart page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/cart.twig) renders the shopping cart page where customers can check what they have added to their shopping cart, and then simply proceed for checkout. The general view of this page displays the list of the items added to the cart, so then the customer can modify any quantity or remove any item.
In addtion,  can upload any files or attach any note along with the cart's items.

**Following is the page location and url:**

```shell title = "🌐 Page URL: http://www.store-domain.com/cart"
└── src
  ├── views
    ├── pages
    |   ...
    |   ├── cart.twig
    |   ...
    ...
```
<br/>

### Example
<!--
focus: false
-->
![Cart page](https://cdn.salla.network/docs/twilight/4/pages-cart-01.png)

### Variables


<DataSchema id="1383859" />


### Components
This page starts by displaying the `breadcrumbs` component. The `{% component breadcrumbs %}` line returns the current navigation  for the user.

```js
{% component 'header.breadcrumbs'%}
```
### JS Web Components
Cart page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Quantity Input [`<salla-quantity-input>`](https://docs.salla.dev/doc-422724?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Loyalty [`<salla-loyalty>`](https://docs.salla.dev/doc-422712?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The [`cart page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/cart.twig) calls for the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject extra information.

```js
{% hook 'cart:items.start' %}
{% hook 'cart:items.end' %}
{% hook 'cart:summary.start' %}
{% hook 'cart:summary.end' %}
```


#### Usage

The [`cart page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/cart.twig) consists of several parts, which are a form to display all of the cart's items/product, free shipping option, and any added discount.

#### Cart items form
Using an HTML `<form>`, the developer can display all of the `items` added to the cart. All of the items can be displayed along with their options by using a *for-loop* statement as follows:

```php lineNumbers
{% for item in cart.items %}
    <form onchange="salla.cart.updateItem(new FormData(event.currentTarget))" id="item-{{ item.id }}">
        <input name="id" type="hidden" value="{{ item.id }}"/>

        <salla-conditional-fields>

            <a href="{{ item.url }}">
                <img src="{{ item.product_image }}" alt="{{ item.product_name }}"/>
            </a>

            <a href="{{ item.url }}">{{ item.product_name }} </a>
            <span class="{{ item.offer?'':'hidden' }}">{{ item.product_price|money }}</span>
            <span class="{{ item.offer?'case1-style':'case2-srtyle' }}">{{ item.price|money }}</span>
            <span class="{{ item.offer?'':'hidden' }}">{{ item.offer.names }} </span>

            {% if item.is_hidden_quantity %}
                <input name="quantity" type="hidden" value="{{ item.quantity }}"/>
                <span>{{ item.quantity }}</span>
            {% else %}
                <salla-quantity-input max="{{ product.max_quantity }}" value="{{ item.quantity }}" name="quantity">
                </salla-quantity-input>
            {% endif %}

            <span>{{ trans('pages.cart.total') }}:</span>
            <span>{{ item.is_available?item.total|money: trans('pages.cart.out_of_stock') }}</span>

            {% for option_index, option in item.options %}
                {# if there is no need for a label, or it needs special handling in the element file #}
                {% if option.type in ["splitter"] %}
                    {{ option.element|raw }}
                {% else %}
                    {% if option.type != "donation" %}
                        <label for="options[{{ option.id }}]">
                            <strong>
                                {{ option.name }} {% if option.required %}<span>*</span>{% endif %}
                            </strong>
                            <small>{{ option.placeholder }}</small>
                        </label>
                    {% endif %}
                    {{ option.element(product.id)|raw }}
                {% endif %}
            {% endfor %}
        </salla-conditional-fields>  
        .....
    </form>
{% else %}
    {{ trans('pages.cart.empty_cart') }}
{% endfor %}
```

#### Free shipping
Using the variable `cart.free_shipping_bar.has_free_shipping`, the developer may check if there is free shipping selected, and then build the logic to handle this part.

```php lineNumbers
<h4>{{ trans('pages.cart.free_shipping') }}</h4>
<p>
    <span>{{ (cart.free_shipping_bar.has_free_shipping ? trans('pages.cart.has_free_shipping') :trans('pages.cart.free_shipping_alert', {'amount': cart.free_shipping_bar.remaining|money})) | raw }}</span>
    <span>🎉</span>
</p>

<h4>{{ trans('pages.cart.summary') }}</h4>
<div>
    <span>{{ trans("pages.cart.items_total") }}</span>
    <strong>{{ cart.sub_total|money }}</strong>
</div>
<div>
    <span>{{ trans('pages.cart.shipping_cost') }}</span>
    <strong>{{ cart.real_shipping_cost|money }}</strong>
</div>
```

#### Apply Copoun and discount
Customer can also apply any given copoun in this page; however this is subject to the store settings which can be checked by the `store.settings.cart.apply_coupon_enabled` variable. Accordingly, any given discount can be shown using the `cart.real_discount` varible.

```php lineNumbers
{% if store.settings.cart.apply_coupon_enabled %}
    <form onsubmit="return salla.form.submit('coupon.add');" class="border-t border-border-color border-b py-5 mb-5">
        <input type="hidden" name="id" value="{{  cart.id }}">
        <label class="block text-sm">{{ trans('pages.cart.have_coupon') }}</label>
        <div class="mt-2.5 relative">
            <input placeholder="{{ trans('pages.cart.coupon_placeholder') }}"
                   class="pe-24 form-input" value="{{ cart.coupon }}"
                   name="coupon"
                   type="text">

            {% if cart.coupon %}
                <salla-button type="button" onclick="salla.coupon.remove({{ cart.id }})" class="btn--coupon has-coupon" oader-position="center">
                    <span class="coupon-text">{{ trans('pages.cart.remove_coupon') }}</span>
                    <i class="sicon-cancel icon text-xl w-8"></i>
                </salla-button>
            {% else %}
                <salla-button type="submit" class="btn--coupon" oader-position="center">
                    <span class="coupon-text">{{ trans('pages.cart.save_coupon') }}</span>
                    <i class="sicon-cancel icon text-xl w-8"></i>
                </salla-button>
            {% endif %}
        </div>
    </form>
{% endif %}
```


Finally, the complete order within the cart page can sent using the following Salla component button:

```php lineNumbers
<salla-button onclick="salla.cart.submit()" loader-position="end" width="wide">
  {{ trans('pages.cart.complete_order') }}
</salla-button>
```


:::tip[Educational Clip]
<Video src="https://youtu.be/B09v5wejnQM?si=rm4TzBSPmlGkiw8G"></Video>
:::

---

## theme-architecture-pages-common-pages/Landing-Page-Template-Twilight-Documentation-Salla-Docs

# Landing Page

A `landing page template` for a Twilight theme is a pre-suggested web page that serves as the entry point for the online store. It provides a foundation for developers to build upon  and typically includes an offer with a countdown timer to encourage conversions. It should be visually appealing, user-friendly, and align with your goals and target audience.

**Following is the page location and url:**

```shell title = "🌐 Page URL: http://www.store-domain.com/"
└── src
    ├── views
      ├── pages
      |   ...
      |   ├── landing-page.twig
      |   ...
      ...
```

## Example 
<!--
focus: false
-->
![Landing Page](https://cdn.salla.network/docs/twilight/4/landing-page-01.png?v=1-10-2022)


## Variables 


<DataSchema id="1383864" />


## Components 
Besides extending the master layout to show the common header and footer, this page may display different sort of Product components such us [`home.store-features`](https://docs.salla.dev/doc-422587?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), [`home.testimonials`](https://docs.salla.dev/doc-422584?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), [`components.home.fixed-products`](https://docs.salla.dev/doc-422583?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and [`components.home.products-slider`](https://docs.salla.dev/doc-422590?nav=01HNFTD5Y5ESFQS3P9MJ0721VM):

```php
{% component 'home.store-features' %}
{% component 'home.testimonials' with{type:landing.testimonials_type} %}
{% include 'components.home.fixed-products' %}
{% include 'components.home.products-slider' %}
```


## JS Web Component

The Landing Page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores:

- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Count Down [`<salla-count-down>`](https://docs.salla.dev/doc-422701?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Products Slider [`<salla-products-slider>`](https://docs.salla.dev/doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Products List [`<salla-products-list>`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD)

## Usage 
This page template receives the `landing` object, which contains all of the information related to the landing page. If this object was not received, the developer may show the 404 not found error page:

```php lineNumbers
{% if not landing %}
<div>
  <header>
    <div><a href="{{ store.url }}"><img src="{{ store.logo }}" alt="logo" /></a>
      <h1>{{trans('common.errors.404')}}</h1>
      <div>{{trans('common.elements.back_home')}}</div>
    </div>
  </header>
</div>
```

If the `landing` object has been received, the developer may check different thing such as if the Landing Page offer `is_expired` or not:

```php lineNumbers
{% if landing.is_expired %}
<div>
  <header>
    <div><a href="{{ store.url }}"><img src="{{ store.logo }}" alt="logo" /></a>
      <h1>{{trans('pages.offer.offer_finished')}}</h1>
      <p>{{ trans('pages.offer.offer_expired_message') }}</p>
      <div>{{trans('common.elements.back_home')}}</div>
    </div>
  </header>
```

On the other hand, if the `landing` object has been received and there is ongoing offer, the developer would need to set the values of the following in order to start showing the related products:

```php
{% set products=landing.products %}
{% set hide_add_btn=true %}
{% set show_quantity=landing.show_quantity %}
{% set title=trans('pages.offer.included_products') %}
```

Besed on the above, the developer may show the products as follows:

```php lineNumbers
{% if landing.is_slider %}
  {% include 'components.home.products-slider' %}
{% else %}
  {% include 'components.home.fixed-products' %}
{% endif %}
```

---

## theme-architecture-pages-common-pages/Loyalty-Program-Page-Template-Twilight-Documentation-Salla-Docs

# Loyalty

The [`loyalty page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/loyalty.twig) shows the content of the  loyalty program, which is meant to enable the store's customers to benefit from collecting the points for vouchers and offers provided by the store. Once they have collected enough points, the customers will be eligible to redeem them for exciting gifts or products.

**Following is the page location and url:**

```shell title = "🌐 Page URL: http://www.store-domain.com/loyalty/oKgyXG"
└── src
    ├── views
      ├── pages
      |   ...
      |   ├── loyalty.twig
      |   ...
      ...
```
<br/>

### Example
<!--
focus: false
-->
![Thank you](https://cdn.salla.network/docs/twilight/4/loyalty-page-01.png?v=1-10-2022)


### Variables


<DataSchema id="1383865" />


### Components
Besides extending the master layout to show the common header and footer, this page starts by displaying the `breadcrumbs` component. The `{% component breadcrumbs %}` line returns the current navigation for the user:

```php
{% component 'header.breadcrumbs'%}
```

### JS Web Components
The Loyalty page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores:

- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Loyalty [`<salla-loyalty>`](https://docs.salla.dev/doc-422712?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Slider [`<salla-slider>`](https://docs.salla.dev/doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD)


### Usage
This page template receives the [`loyalty`](https://docs.salla.dev/doc-422712?nav=01HNFTE06J4QC24T0D5BPRYKMD) object, which contains all of the information related to the loyalty program, such as its name and description. The developer may show the collected points of a logged in user by using the variable `user.loyalty_points`.

```php lineNumbers
<div>
  <span>{{ loyalty.name }}</span>
</div>
<div>
  <h1>{{loyalty.name}}</h1>
  <p>
    {{loyalty.description}}
  </p>
  
  {% if user.loyalty_points %}
    <p>{{user.loyalty_points}}</p>
  {% endif %}
</div>

```

A _for-loop_ statement can be used to display a list of the possible methods for collecting points as follows:

```php lineNumbers
{% for point in loyalty.points %}
<div>
    <i class="{{ point.icon ? point.icon : 'sicon-star' }}" style="color: {{point.color}}"></i>
    <div style="background-color: {{point.color}}"></div>
</div>
<div>
    <h4 style="color: {{point.color}}">
        {{point.points}}
        <p>{{point.description}}</p>
</div>
{% endfor %}
```

In case of the method for collecting points is to here a link, the developer may show the sharing link as follows:

```php lineNumbers
{% if point.type == 'share' %}
<h3>{{ point.url }}</h3>
```

After all, the developer can display the list of prizes using the following _for_ loop statement, noting that another nested loop can be used to display any awarded products:

```php lineNumbers
{% for prizeGroup in loyalty.prizes %}
<div>
  <h2>{{ prizeGroup.title }}</h2>
</div>
{% for prize in prizeGroup.items %}
  <div>
    <div>
      {% if prize.url %}
      <a href="{{ prize.url }}"> {{ prize.image }} </a>
      {% endif %}
      <div>
        {% if prize.url %}
        <a href="{{ prize.url }}">{{ prize.name }}</a> 
        {% else %} 
          {{ prize.name}} 
        {% endif %}
      </div>
      <p>{{ prize.description }}</p>
      {% if user.type == 'user' %}
        <div>{{ prize.cost_points }}</div>
      {% endif %}
    </div>
  </div>
{% endfor %} 
{% endfor %}
```

:::tip[Educational Clip]
<Video src="https://youtu.be/uJrmfvLnl38?si=NfOdAxIWPbTwQ1TU"></Video>
:::

---

## theme-architecture-pages-common-pages/Static-Single-Page-Template-Twilight-Documentation-Salla-Docs

# Single page

Twlight provides the ability to create [`single pages`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/page-single.twig) that show static content. Examples of that are the copy right page, terms and conditions, delivery information, shipping methods, and payment methods information pages. All of these topics are essential for the store owner, as he needs them to deliver specific information to the customers. This kind of information is rarely changed. For this reason, these pages are considered static. 

**Following is the page location and url:**

```shell title = "🌐 Page URL: http://www.store-domain.com/page-slug/page-1651849934"
└── src
    ├── views
      ├── pages
      |   ...
      |   ├── page-single.twig
          ...
    ...
```


### Example
<!--
focus: false
-->
![Single page](https://cdn.salla.network/docs/twilight/4/pages-single-page-01.png)

### Variables


<DataSchema id="1383882" />


### Components
This page starts by displaying the [`breadcrumbs`](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component. The `{% component breadcrumbs %}` line returns the current naviation for the user.

```php
{% component 'header.breadcrumbs'%}
```

The users' `comments` on a specific page may be displayed using the component `{% component 'comments' %}`.

```php 
{% component 'comments' %}
```

### Usage
This page template receives the object `page` which contains the details of the static content to be displayed. For example, the developer can use the variables `page.title` and `page.cotent` which are the core of this page template.

```php
{{ page.title }}
{{ page.content|raw }}
```

The users' `comments` on a specific page may be displayed using the component `{% component 'comments' %}`.

```php
{% component 'comments' %}
```

---

## theme-architecture-pages-common-pages/Thank-You-Page-Template-Twilight-Documentation-Salla-Docs

# Thank you

The [`thank you page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/thank-you.twig) is the page the customer is taken to after completing an order transaction. Naturally, the page includes a brief thank you message that signals the store's appreciation for completing the order - just like any consumer would expect. In addition, this page template lists the [order details](https://docs.salla.dev/doc-422564?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) for the customer's reference.

**Following is the page location and url:**

```shell title = "🌐 Page URL: http://www.store-domain.com/thankyou/oKgyXG"
└── src
    ├── views
      ├── pages
      |   ...
      |   ├── thank-you.twig
      |   ...
      ...
```
<br/>

### Example
<!--
focus: false
-->
![Thank you](https://cdn.salla.network/docs/twilight/4/pages-thank-you-01.png)


### Variables


<DataSchema id="1383884" />


### Hooks
The `thank you page template` may call the following [hooks](doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject extra information.

```php
{% hook 'thank-you:items.start' %}
{% hook 'thank-you:items.end' %}
```

### JS Web Components
The Thank You page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores:

- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Usage
This page template receives the `order` object, which contains all of the information related to the purchased order. 

The developer may start by displaying the order id using the variable `order.order_id`.
After that, a _for-loop_ statement is used in order to list the purchased items with their details. For example, `item.codes` and `item.name`. Other details can also be displayed, such as attached files, with these items, using the array `item.files`. 

Below is a full example of that:

```php lineNumbers
<p>Thank you</p>
<p>Order Id #{{ order.id }}</p>

<p>Order details</p>

{% for item in order.items %}
    {% if item.codes|length %}
        ({{ item.name }})
        {% for code in item.codes %}
            {{ code }}
        {% endfor %}
    {% endif %}

    {% if item.files|length %}
        {{ thank_you.files }} ({{ item.name }})
        {% for file in item.files %}
            <a href="{{ file.url }}">{{ file.name }}</a>
        {% endfor %}
    {% endif %}
{% endfor %}
```

Another thing that can be done on this page is to show that the order details have been sent to the customer's email using the variable `order.customer.email` along with the order invoice.

```php lineNumbers
{% if order.email_sent %}
  {{ thank_you.email_sent }}
  {{ order.customer.email }}
{% else %}
  {{ thank_you.resend_email }}
  {{ thank_you.sent_invoice }}
{% endif %}
```

After that, it would also be good to show store support contact information in case the customer needs to contact the store owner.

```php lineNumbers
<p>Support</p>

{% if store.contacts.mobile %}
  {{ store.contacts.mobile }}
{% endif %} 

{% if store.social.whatsapp %}
  {{ store.social.whatsapp }}
{% endif %}
```
:::tip[Educational Clip]
<Video src="https://youtu.be/w9kPR4I3yUw?si=0xSBzyFpgG3UKz6z"></Video>
:::

---

## theme-architecture-pages/Blog-Pages

# Blog Pages

## Docs

- [Blog listing](https://docs.salla.dev/422567m0.md): The [`blog listing page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/blog/index.twig) is used for rendering the list of all of the available blogs' articles. This template will show an excerpt for each blog article along with the article title, summary, image, and author name. The developer has complete control over the appearance of this page.
- [Single blog](https://docs.salla.dev/422568m0.md): This [`single  blog page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/blog/single.twig) is to display the content of a single article from the store's blog. The content can be a mix of text and images. This is part of the internal marketing tool for the store owner to draw the customer's attention to specific products or ideas. Each article is displayed along with its tags, in the event of having tags. This template may also show any related articles to the current single article.

---

## theme-architecture-pages/Brand-Pages

# Brand Pages

## Docs

- [Brands listing](https://docs.salla.dev/422570m0.md): The [`brand listing page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/index.twig) is used to render the list of all of the available brands in the store. This template shows the list of the alphabet characters, which represent the first characters of each available brand. Then comes the list of the brands' logos for the chosen letter. The developer has complete control over the appearance of this page.
- [Single brand](https://docs.salla.dev/422572m0.md): This [`single brand page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/single.twig) is to display the details of a single brand within the store's list of brands. These details can be a short blurb about that brand and a marketing banner for it. It also shows the list of that brand's products as well. The goal here is to group the products of that brand along with information about them on one page for the customer's reference.

---

## theme-architecture-pages/Common-Pages

# Common Pages

## Docs

- [Cart](https://docs.salla.dev/422575m0.md): The [`cart page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/cart.twig) renders the shopping cart page where customers can check what they have added to their shopping cart, and then simply proceed for checkout. The general view of this page displays the list of the items added to the cart, so then the customer can modify any quantity or remove any item.
- [Loyalty](https://docs.salla.dev/422576m0.md): The [`loyalty page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/loyalty.twig) shows the content of the  loyalty program, which is meant to enable the store's customers to benefit from collecting the points for vouchers and offers provided by the store. Once they have collected enough points, the customers will be eligible to redeem them for exciting gifts or products.
- [Thank you](https://docs.salla.dev/422577m0.md): The [`thank you page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/thank-you.twig) is the page the customer is taken to after completing an order transaction. Naturally, the page includes a brief thank you message that signals the store's appreciation for completing the order - just like any consumer would expect. In addition, this page template lists the [order details](https://docs.salla.dev/doc-422564?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) for the customer's reference.
- [Single page](https://docs.salla.dev/422578m0.md): Twlight provides the ability to create [`single pages`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/page-single.twig) that show static content. Examples of that are the copy right page, terms and conditions, delivery information, shipping methods, and payment methods information pages. All of these topics are essential for the store owner, as he needs them to deliver specific information to the customers. This kind of information is rarely changed. For this reason, these pages are considered static. 
- [Landing Page](https://docs.salla.dev/422579m0.md): A `landing page template` for a Twilight theme is a pre-suggested web page that serves as the entry point for the online store. It provides a foundation for developers to build upon  and typically includes an offer with a countdown timer to encourage conversions. It should be visually appealing, user-friendly, and align with your goals and target audience.

---

## theme-architecture-pages/Customer-Pages

# Customer Pages

## Docs

- [Profile](https://docs.salla.dev/422562m0.md): This [`profile template page`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/profile.twig) is for the customer's profile, which is utilised to show customer-related information including, name, email and phone number. The customer can also modify and update their information on this page. 
- [Orders list](https://docs.salla.dev/422563m0.md): This [`orders list page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/index.twig) is designated for listing customers orders where customers can check their existing orders to view the status, price, order number and make changes where applicable. 
- [Order details](https://docs.salla.dev/422564m0.md): This [`single order page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/single.twig) can aid customers in viweing an order details such as items, prices, quantities and order status. 
- [Wishlist](https://docs.salla.dev/422565m0.md): This [`wishlist page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/wishlist.twig) can help customers save items that they wish to buy, this can greatly help to check the offers that apply to the items the customers are interested in as well as keeping track of the stock.
- [Notifications](https://docs.salla.dev/422566m0.md): The [`notifications page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/notifications.twig) can help display short texts/messages to notify customers with the latest updates regarding their orders.

---

## theme-architecture-pages/Product-Pages

# Product Pages

## Docs

- [Products listing](https://docs.salla.dev/422559m0.md): Twilight Theme includes a [`products listing template page`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/index.twig). This page template is based on a category or search query. It is created to produce better products listings based on a specific need or purpose set by the developer. 
- [Single product](https://docs.salla.dev/422561m0.md): The [`single product page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/single.twig) is designated to view product details such as the title, description, type, color, size, price, and quantity. Each product will have its own details displayed on this page.

---

## theme-architecture-pages/Themes-Home-Page-Twilight-Documentation-Salla-Docs

# Home Page

The [`home page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/index.twig) renders the first page which the customer encounters. This page is essential to give the first impact of the store's look-and-feel. The main store attractions are located on this page to showcase the ease of accessibility to go around the store. 

Following is the page location and url :

``` shell title = "🌐 Page URL: http://www.store-domain.com/"
└── src
  ├── views
    ├── pages
    |   ...
    |   ├── index.twig
    |   ...
    ...
```

### Example
<!--
focus: false
-->
![Single page](https://cdn.salla.network/docs/twilight/4/pages-home-01.png)

### Variables


<DataSchema id="1383863" />

### Components
By default, the home page displays a collection of Theme Features listed in the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) under the `features` section. Which are located in the [`src/views/components/home/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components/home) folder and were developed specially for the Home Page. 

More about [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) file in this [article](https://docs.salla.dev/doc-421921?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).


:::info[A thing to know!]
- The Theme Features names have the prefix `component-` inside [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json).
- Developer must remove the Theme Features that will not be used in the theme.
- It's advised to use the Theme Features as a best practise to ensure a smooth experience for all Salla partners.
:::

The content of `{% component home %}` renders the following Theme Features as per the [store's](https://salla.sa) settings. 


| <div style="width:220px">Theme Feature</div> | Discription |
|---|---|
| [Youtube](https://docs.salla.dev/doc-422582?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | This feature is responsible for displaying Youtube videos that the developer preselects. |
| [Fixed Banner](https://docs.salla.dev/doc-422583?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Fixed banner is the area in charge of displaying a banner that is fixated on the home page. |
| [Featured prodcuts style 1](https://docs.salla.dev/doc-422591?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Using this feature, showcases the featured products in a pre-defined style.|
| [Featured prodcuts style 2](https://docs.salla.dev/doc-422592?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Using this feature, showcases the featured products in a pre-defined style. |
| [Featured prodcuts style 3](https://docs.salla.dev/doc-422593?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Using this feature, showcases the featured products in a pre-defined style. |
| [Testimonials](https://docs.salla.dev/doc-422584?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | This feature displays testimonials that the developer preselects. 
|[Parallax backgorund](https://docs.salla.dev/doc-422585?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)|This feature displays products with a backgournd that zooms out slowly giving a 2D effect. |
| [Photos slider](https://docs.salla.dev/doc-422586?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Photos are displayed in a slider by using this feature. |
| [Store Features](https://docs.salla.dev/doc-422587?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | This feature oversees the display of store's overall features, such as detailed product description or customer review of the product. |
| [Square photos](https://docs.salla.dev/doc-422588?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Use this feature to display photos in a square shape. |
| [Fixed products](https://docs.salla.dev/doc-422589?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | Use this feature to pin the products that you wish to have displayed always. |
| [Products slider](https://docs.salla.dev/doc-422589?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | This slider feature helps navigate between products vertically/horizontally. |
| [Latest Products](https://docs.salla.dev/doc-422599?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) | This feature displays the latest products added to the store automatically. |
|[Vertical Menu with Slider](https://docs.salla.dev/doc-422600?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)|This feature display a vertical menue with slider to display links and images|

<!-- |[Vertical menu with slider](../4.2-Components/4.2.1-Home-components/4.2.20-Home-vertical-menu-with-slider.md)| Used to display a menu for a group of the sub-pages' links in a vertical menu. | -->

### Theme Preview 
The components can be added using the theme preview in the [Theme menu item](https://salla.partners/themes) of Salla Partners Portal. The developer can add the component and enable it in the theme preview dashboard.
![Theme Preview Dashboard](https://cdn.salla.network/docs/twilight/4/theme-preview-dashboard-01.png)


### Usage
Twilight provides two different methods to handle the Home Page via the file [`src/views/pages/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/index.twig). The goal here is to enable the developer to perform any design or appearance he may need for this page.

The methods are:
-	[Theme Features and Theme Components](#theme-features-and-theme-components)
-	[Developer Static Content](#static-content)

### Theme Features and Theme Components
This is the default method, in which the Home Page simply displays the [Theme Features](#components) explained in the previous section of this article.

In addition to the Theme Features, the developer has the option to build their own/new Theme Component(s) as per the store’s requirements. 


:::info[The new Theme Component should be:]
- Created inside the path [`src/views/components/*.twig`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components)
- The schema is declared inside the file [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) under the `components` section.
:::

Following is an example of the [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) where we delcare a new Theme Component named "custom-slider". 



```js title="./twilight.json" lineNumbers
...
  "components": [
    {
      "name": "custom-slider",
      "title": "صور متحركة (مخصص)",
      "icon": "sicon-image-carousel",
      "path": "home.custom-slider",
      "fields": [
        {
          "id": "images",
          "type": "collection",
          "format": "collection",
          "required": true,
          "minLength": 1,
          "maxLength": 10,
          "fields": [
            {
              "id": "image",
              "type": "string",
              "format": "image"
            },
            {
              "id": "title",
              "type": "string",
              "label": "عنوان رئيسي (إختياري)"
            },
            {
              "id": "sub_title",
              "type": "string",
              "format": "textarea",
              "label": "نص توضيحي (إختياري)"
            }
          ]
        }
      ]
    },

...
```

In the previous example, the `path` of the new component is mentioned in `"path": "home.custom-slider"`. This means that the new component is located inside `src/views/components/home/custom-slider.twig`. 

:::tip[Note]
The developer has the option to create their component anywhere within the [`src/views/components/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components) folder.
:::

Twilight is shipped with some ready Theme components, which can be easily modified by the developer. Below is the list of these Theme Components.

| Components                                        | Description                                                      |
|----------------------------------------------------------------|-----------------------------------------------------|
| [Brands](https://docs.salla.dev/doc-422594?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)| Brands' logos of the store are displayed in this component section. |
| [Main links](https://docs.salla.dev/doc-422596?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)                          | This component helps to portray the store main links.                             |
| [Enhanced Slider](https://docs.salla.dev/doc-422597?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)                 | The slider component helps navigate vertically/horizontally.                      |
| [Slider products with header](https://docs.salla.dev/doc-422598?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)           | Slider products with header displays the products in a slide and give the sldier a header title.                                                                              |
|[Enhanced Square Banners](https://docs.salla.dev/doc-422595?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)|Enhanced banners in a square shape are displayed with this component's help|


Below is the [`src/views/pages/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/index.twig) file for the Home Page, where, in line #3, the `{% component home %}` renders both of the Theme Features and Theme Components. 

```js title="src/views/pages/index.twig [Line #3]" lineNumbers
{% extends "layouts.master" %}
{% block content %}
    {% component home %}
{% endblock %}
{% block scripts %}
    <script type="text/javascript" defer src="{{ asset('dist/home.js') }}"></script>
{% endblock %}
```

The visibility of each of the Theme Features and Theme Components in the Home Page is managed from the [Partners Portal](https://salla.partners/). This means that the partner has the ability to show/hide any of the Theme Features and Theme Components.

<!--
focus: false
-->

![Theme Features](https://cdn.salla.network/docs/twilight/1/setup-theme-05.png?hi)

#### Static Content
In this method, the developer has the option of building their own static content without using the Theme Features nor Theme Component(s). However it's highly advised to utalize the previous methods to ensure a smooth expereince for the end users.

The added static content does not depend on any of the Store settings. It will be displayed as per the given design by the developer. Below is an example for this method.
 

```php title="src/views/pages/index.twig" lineNumbers
{% extends "layouts.master" %}
{% block content %}

    <-- just add your static content here -->  
    <div id="container">
        <h2> My Home Page </h2>
        <img src="{{ asset('images/my_img.png') }}" alt="" />
    </div>
    
{% endblock %}
{% block scripts %}
    <script type="text/javascript" defer src="{{ asset('dist/home.js') }}"></script>
{% endblock %}
```

---

## theme-architecture-pages/Themes-Pages-Overview-Twilight-Documentation-Salla-Docs

# Overview

Twilight theme engine comes with pre-defined list of pages that form together the Salla theme pages.

Following is the pages location:

```sh

└── src
  ├── views
    ├── pages
    ...
```
<br/>

:::caution[Alert]
The pre-defined pages' names and paths are **not changeable**. Meaning, the developer may modify page contents, however, the page's filename and path should not be changed.
:::



## 📙 What you'll learn
This article lists all of the predefined pages that come with the Twilight theme. These pages together make a complete store from displaying items and categorizing them all the way to cart. There are nine pages in total which are:
- [Home](#home-page)
- [Product pages](#products-pages)
  - [Products listings](#products-pages)
  - [Single product ](#products-pages)
- [Customer pages](#customer-pages)
  - [Profile](#customer-pages)
  - [Order list](#customer-pages)
  - [Orders details](#customer-pages)
  - [Wishlist](#customer-pages)
  - [Notification](#customer-pages)
- [Blog pages](#blog-pages)
  - [Single blog page](#blog-pages)
  - [Blog listing page](#blog-pages)
- [Brands pages](#brands-pages)
  - [Signle brand page](#brands-pages)
  - [Brands listing page](#brands-pages)
- [Cart](#cart-page)
- [Loyalty](#loyalty-page)
- [Thank you](#thank-you-page)
- [Single page](#single-page)
<hr>

### [Home page](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

[Home page](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is the most significant page in the store, it collects all the main functions that the customer needs once they land on the store website. [Home page](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is located at [`src/views/pages/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/index.twig). More about Home page [here](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). 

### [Products pages](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

Products pages are where the products details are listed. There are two kinds of products pages which are [Single product](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [Products listings](https://docs.salla.dev/doc-422559?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). 

The single product page displayes informations of a particular product such as price, variety, dimensions, size, availability and so on. Single product page is located at [`src/views/pages/product/single.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/single.twig). More about Single product page [here](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). 

The products listings page gives an organized view of products such as:
|Product listing|Description|
|---|---|
|Category listing| is where the store owner show cases the store items as they wish, and accordingly the developler should customize the page|
|Offers listing| The best about shopping is hunting for offers! Well, this page is in charge of that. Store owners can manage the items they have on offer and make them stand out to attract customers.|
|Search results listing|Having a store with many items can be overwhelming and finding what you want can be tricky, this page helps to display the items searched by the customer in a neat way.|
|Tags listing| Tags page allowes you to mark or categorize a page or groups of pages on your store. It also helps to identify, with greater ease and in more business-relevant terms, what your website visitors are accessing. You can then use the information as a more intuitive way to segment, build lead score models, and report on store performance.|

Products listings are located at [`src/views/pages/product/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/index.twig), you can also find more info about Product listings [here](https://docs.salla.dev/doc-422559?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### [Customer pages](https://docs.salla.dev/849314f0?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

Customer's related pages are significant in managing their related data. 
Customer pages are:

- [Profile](https://docs.salla.dev/doc-422562?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) page,
  this page displays the customer's demographic details such as name, email, address and phone number. Customer profile page is located at [`src/views/pages/customer/profile.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/profile.twig). More about Profile page [here](https://docs.salla.dev/doc-422562?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
- [Order list ](https://docs.salla.dev/doc-422563?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) page,
  this page helps listing the orders made by the customer. Customer order list page is located at [`src/views/pages/customer/orders/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/index.twig). More about Order list [here](https://docs.salla.dev/doc-422563?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
- [Orders details](https://docs.salla.dev/doc-422564?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) page, this page displays further details of customer orders. Customer order details page is located at [`src/views/pages/customer/orders/single.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/single.twig). More about Orders details page [here](doc-422564?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
- [Wishlist](https://docs.salla.dev/doc-422565?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) page, this page displays items which are in the customer's wishlist. Customer wishlist is located at [`src/views/pages/customer/wishlist.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/wishlist.twig). More about Wishlist page [here](https://docs.salla.dev/doc-422565?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
- [Notifications](https://docs.salla.dev/doc-422566?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) page, shows the notifications sent to the customer. Customer notifications page is located at [`src/views/pages/customer/notifications.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/notifications.twig). More about Notifications page [here](https://docs.salla.dev/doc-422566?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### Blog pages

- [Single blog page](https://docs.salla.dev/doc-422568?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) template, displays a single article content from the store bolg. The content includes words and images.Single blog page is located at [`src/views/pages/blog/single.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/blog/single.twig). More about single blog page [here](https://docs.salla.dev/doc-422568?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
- [Blog listing page](https://docs.salla.dev/doc-422567?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) template, renders a list of the available blogs articles. It will show snippits for each blog article including the article title, summary, image, and author name. Blog listing page is located at [`src/views/pages/blog/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/blog/index.twig). More about blog listing page [here](https://docs.salla.dev/doc-422567?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

### Brands pages

- [Single brand page](https://docs.salla.dev/doc-422572?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), shows the details of a particular brand that belongs to a list of brands the store offers. The page is located at [`src/views/pages/brands/single.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/single.twig). More about single brand page [here](https://docs.salla.dev/doc-422572?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
- [Brands listing page](https://docs.salla.dev/doc-422570?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), shows the list of brands associated with the store. The page is located at [`src/views/pages/brands/index.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/index.twig). More about brands listing page [here](https://docs.salla.dev/doc-422570?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### [Cart page](https://docs.salla.dev/doc-422575?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

The [Cart page](https://docs.salla.dev/doc-422575?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is where the customer can manage the items they are going to buy, so it's critical for the store to provide a seamingly experience for its customer. The page is located at [`src/views/pages/cart.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/cart.twig). More about Cart page [here](https://docs.salla.dev/doc-422575?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### [Loyalty Page](https://docs.salla.dev/doc-422576?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

The [Loyalty page](https://docs.salla.dev/doc-422576?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is where the developer can introduce a loyalty program to enable the merchant offer points to the store cutomers and trade in the points for rewards. The page is located at [`src/views/pages/loyalty.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/loyalty.twig). Explore more about Loyalty page [here](https://docs.salla.dev/doc-422576?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### [Thank you page](https://docs.salla.dev/doc-422577?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

A [Thank you page](https://docs.salla.dev/doc-422577?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is the page visitors, leads, and customers see after joining your email list, submitting a form, or making a purchase. Think of a thank you page as a way to turn new visitors into warm leads and returning customers into repeat buyers. [Thank you page](https://docs.salla.dev/doc-422577?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is located at [`src/views/pages/thank-you.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/thank-you.twig). 
More about Thank you page [here](https://docs.salla.dev/doc-422577?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### [Single Page](https://docs.salla.dev/doc-422578?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

The aim of using this page is for those pages that are fixed or don't need frequent changes, such as policy page, terms and conditions page and so on. Single Page is located at [`src/views/pages/page-single.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/page-single.twig). More about Single Page [here](https://docs.salla.dev/doc-422578?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

### [Landing Page](https://docs.salla.dev/doc-422579?nav=01HNFTD5Y5ESFQS3P9MJ0721VM)

This page provides a strong starting point that's easy to customize. It includes an attractive offer and a countdown timer to help increase sales. With eye-catching visuals and user-friendly features, this template is a perfect fit for goals and target audience. Create an impressive online presence with this optimized landing page template.

Landing Page is located at [`src/views/pages/landing-page.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/landing-page.twig). More about Landing Page [here](doc-422579?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

---

