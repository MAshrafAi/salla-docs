# Theme Architecture Pages Customer Pages

## Table of Contents

- [theme-architecture-pages-customer-pages/Notifications-Page-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-customer-pages-notifications-page-twilight-documentation-salla-docs)
- [theme-architecture-pages-customer-pages/Orders-List-Page-Guide-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-customer-pages-orders-list-page-guide-twilight-documentation-salla-docs)
- [theme-architecture-pages-customer-pages/Single-Order-Page-Guide-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-customer-pages-single-order-page-guide-twilight-documentation-salla-docs)
- [theme-architecture-pages-customer-pages/Themes-Customer-Profile-Page-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-customer-pages-themes-customer-profile-page-twilight-documentation-salla-docs)
- [theme-architecture-pages-customer-pages/Wishlist-Page-Guide-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-customer-pages-wishlist-page-guide-twilight-documentation-salla-docs)

---

## theme-architecture-pages-customer-pages/Notifications-Page-Twilight-Documentation-Salla-Docs

# Notifications

The [`notifications page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/notifications.twig) can help display short texts/messages to notify customers with the latest updates regarding their orders.

``` shell title = "🌐 Page URL: http://www.store-domain.com/notifications"
└── src 
  ├── views
  |   ├── pages
  |   |   ├── customer
  |   |   |   ...
  |   |   |   ├── notifications.twig
              ...
```

### Example
<!--
focus: false
-->
![Customer Notifications](https://cdn.salla.network/docs/twilight/4/customer-notification-01.png)

### Variables

<DataSchema id="1383866" />

### Components
This page extends the default layout [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and accordingly, it takes the unified look-and-feel. For example, all of the [`header's`](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [`footer's`](https://docs.salla.dev/doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) components will be  added automatically to this page.

In addition, the [`User`](models/user.json) model is accessible automatically on this page because it's included in the [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) layout file.

### JS Web Components
Customer's Notification page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Infinite Scroll [`<salla-infinite-scroll>`](https://docs.salla.dev/doc-422706?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The [`notifications page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/notifications.twig) may call the following [hooks](https://docs.salla.dev/doc-422552) in order to inject extra information.

```js
{% hook 'customer:notifications.items.start' %}
{% hook 'customer:notifications.items.end' %}
```

### Usage
This page receives an array of `notifications` as an object. This array contains all of the notification's data for the currently logged-in user. Each notification can be displayed using a `for-loop` statement. 

A common implementation for this page, is to display each notification as a link, which the user can click to open and view the details of the notification he wants to see.


:::tip[Note]
The Salla component [`salla-infinite-scroll`](https://docs.salla.dev/doc-422706?nav=01HNFTE06J4QC24T0D5BPRYKMD) has been used to ease the pagination process.
:::

```php lineNumbers=true
<salla-infinite-scroll next-page="{{ notifications.next_page }}" item=".notifications-row">
    {% for notification in notifications %}
        <div class="notifications-row">
            <h4>{{ notification.title }}</h4>
            <p>{{ notification.sub_title }}</p>
            <span> {{ notification.date }} </span>
        </div>
    {% else %}
        <div>
            <p>{{ trans('blocks.header.no_notifications') }}</p>
        </div>
    {% endfor %}
</salla-infinite-scroll>
```

---

## theme-architecture-pages-customer-pages/Orders-List-Page-Guide-Twilight-Documentation-Salla-Docs

# Orders list

This [`orders list page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/index.twig) is designated for listing customers orders where customers can check their existing orders to view the status, price, order number and make changes where applicable. 

``` shell title = "🌐    Page URL: http://www.store-domain.com/orders"
└── src 
  ├── views
  |   ├── pages
  |   |   ├── customer
  |   |   |   ├── orders
  |   |   |   |     ...
  |   |   |   |   ├── index.twig
                    ...
```

### Example
<!--
focus: false
-->
![Orders list](https://cdn.salla.network/docs/twilight/4/customer-order-list-01.png)


### Variables

<DataSchema id="1383860" />

### Components
This page extends the default layout [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and accordingly, it takes the unified look-and-feel. For example, all of the [`header's`](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [`footer's`](https://docs.salla.dev/doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) components will be  added automatically to this page.

In addition, the `User` model is accessible automatically on this page because it's included in the [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) layout file.

### JS Web Components
Customer Orders List page may include the following [JS Web Components](https://docs.salla.dev/doc-422556?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Infinite Scroll [`<salla-infinite-scroll>`](https://docs.salla.dev/doc-422706?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The [`orders list page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/index.twig) calls for the following [hooks](https://docs.salla.dev/doc-422552) in order to inject extra information.

```php
{% hook 'customer:orders.index.items.start' %}
{% hook 'customer:orders.index.items.end' %}
```

### Usage
Mainly, in this page's template, the list of the customer's `orders` are displyed using a `for-loop` statement. This can be done easily by using the `orders` object as we see in the following example. Note that the Salla component salla [infinite scroll](https://docs.salla.dev/doc-422706?nav=01HNFTE06J4QC24T0D5BPRYKMD) has been used to ease the pagination process.

```php lineNumbers=true
{% if orders|length %}
    <salla-infinite-scroll next-page="{{ orders.next_page }}" item=".customer-row">
        <table>
            <thead>
            <tr>
                <th scope="col">{{ trans('pages.thank_you.order_id') }}</th>
                <th scope="col">{{ trans('pages.orders.total') }}</th>
                <th scope="col">{{ trans('pages.orders.date') }}</th>
                <th scope="col">{{ trans('pages.orders.status') }}</th>
            </tr>
            </thead>
            <tbody>
            {% for order in orders %}
                <tr class="customer-row">
                    <td><span>{{ trans('pages.thank_you.order_id') }}:</span> #{{ order.reference_id }}</td>
                    <td><span>{{ trans('pages.orders.total') }}:</span> {{ order.total|money }}</td>
                    <td><span>{{ trans('pages.orders.date') }}:</span> {{ order.created_at|date("l j F Y") }}</td>
                    <td>
                        <span>{{ trans('pages.orders.status') }}:</span>
                        <span> {{ order.status.name }} </span>
                    </td>
                </tr>
            {% endfor %}
            </tbody>
        </table>
    </salla-infinite-scroll>

{% else %}
    <div>
        <span>{{ trans('pages.orders.non_orders') }}</span>
    </div>
{% endif %}
```

---

## theme-architecture-pages-customer-pages/Single-Order-Page-Guide-Twilight-Documentation-Salla-Docs

# Order details

This [`single order page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/single.twig) can aid customers in viweing an order details such as items, prices, quantities and order status. 


``` shell title = "🌐 Page URL: http://www.store-domain.com/order/jrXpVm"

└── src 
  ├── views
  |   ├── pages
  |   |   ├── customer
  |   |   |   ├── orders
  |   |   |   |     ...
  |   |   |   |   ├── single.twig
                    ...
```

### Example
<!--
focus: false
-->
![Order details](https://cdn.salla.network/docs/twilight/4/customer-order-details-01.png)


### Variables

<DataSchema id="1383868" />

### Components
This page extends the default layout [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and accordingly, it takes the unified look-and-feel. For example, all of the [`header's`](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [`footer's`](doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) components will be  added automatically to this page.

In addition, the `User` model is accessible automatically on this page because it's included in the [`master.twig`](https://docs.salla.dev/doc-421944) layout file.

### JS Web Components
Customer's Order Details page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Rating Modal [`<salla-rating-modal>`](https://docs.salla.dev/doc-422728?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Map [`<salla-map>`](https://docs.salla.dev/doc-422713?nav=01HNFTE06J4QC24T0D5BPRYKMD) (Read Only)
- Modal [`<salla-modal>`](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Rating Stars [`<salla-rating-stars>`](https://docs.salla.dev/doc-422727?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
This [`single order page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/orders/single.twig) allows calling the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject more information:
 
```js
{% hook 'customer:orders.single.details.start' %}
{% hook 'customer:orders.single.details.end' %}
```

### Usage

In the order's detailes page template, we need to show several element related to the `order` that is currently being handeled. For example below we have a table that shows the order's `order.created_at`, `order.shipping.logo`, `order.shipping.name`, `order.shipping.number`, `order.status.name`. This is to disaply the shipping information of the order.

```php lineNumbers=true
<table>
    <tbody>
    <tr>
        <td>
            <div>{{ trans('pages.orders.date') }}</div>
            <strong>{{ order.created_at|date }}</strong>
        </td>

        {% if order.shipping %}
            <td>
                <div>{{ trans('pages.orders.shipment_details') }}</div>
                <div>
                    {% if order.shipping.logo %}
                        <div><img src="{{ order.shipping.logo }}" alt=""/></div>
                    {% endif %}
                    <strong>{{ order.shipping.name }}</strong>
                </div>
            </td>
        {% endif %}

        {% if order.shipping.number %}
            <td>
                <div>{{ trans('pages.orders.shipment_no') }}</div>
                <strong>{{ order.shipping.number|raw }}</strong>
            </td>
        {% endif %}

        <td>
            <span> {{ order.status.name }} </span>
        </td>
    </tr>
    </tbody>
</table>
```

After that, it's essential to display the list of the order's `items/products`. For this, we use a for-loop statement to show the details of each item/product:
```php lineNumbers=true
{% for item in order.items %}
    {% if item.product %}
        <a href="{{ item.product.url }}" style="display: block">
            <img src="{{ item.image ?: asset('images/placeholder.png') }}" alt="{{ item.name }}"/>
            <p> {{ item.name }}</p>
            <strong>{{ item.price|money }}</strong>
        </a>
    {% else %}
        <div><span>{{ item.name }}</span> <strong>{{ item.price|money }}</strong></div>
    {% endif %}
    <div>
        <span>{{ trans('pages.products.quantity') }}</span>
        <strong>{{ item.quantity }}</strong>
    </div>
    <div>
        <span>{{ trans('pages.products.price') }}</span>
        <strong>{{ item.price|money }}</strong>
    </div>
    <div>
        <span>{{ trans('pages.orders.total') }}</span>
        <strong>{{ item.total|money }}</strong>
    </div>
    <hr>
{% endfor %}
```

An item/product within an order may contain several `options` as per the customer selection. These options can be displayed as follows:

```php lineNumbers=true
{% if item.options %}
    <h2>{{ trans('pages.cart.item_options') }}</h2>
    {% for option in item.options %}
        <p> {{ option.name }}: </p>
        {% if option.is_image %}
            <a href="{{ option.value }}" target="_blank">
                <img src="{{ option.value ?: asset('images/placeholder.png') }}" alt="{{ option.name }}"/>
            </a>
        {% else %}
            {{ option.value }}
        {% endif %}
        <hr>
    {% endfor %}
{% endif %}
```

In addtion to having product's options, there might be `sub_products` along with any item/product. Following, is an example for displaying any sub products:

```php lineNumbers=true
{% if item.sub_products %}
    <h2>{{ trans('pages.orders.sub_products') }}</h2>
    {% for product in item.sub_products %}
        <a href="{{ product.url }}"> {{ product.name }} </a>
    {% endfor %}
{% endif %}
```

Another point related to the order's items is having attached `files` or `notes`. These elements can be displayed using `for-loop` as we see in the following example:

```php lineNumbers=true
{% if item.files %}
<h2>{{ trans('pages.orders.files') }}</h2>
{% for file in item.files %}
    <p>{{ file.name }}</p>
    <a href="{{ file.url }}" target="_blank">
        {{ trans('pages.thank_you.download') }}
    </a>
    <hr>
{% endfor %}

{% if item.codes %}
    <h2>{{ trans('pages.orders.codes') }}</h2>
    {% for code in item.codes %}
        <div>{{ code }}<span>{{ trans('common.copy_code') }}</span></div>
    {% endfor %}
{% endif %}

{% if item.note %}
    <p>{{ trans('common.note') }} : {{ item.note }}</p>
{% endif %}

{% if item.attachments %}
    {% for attachment in item.attachments %}
        <p>{{ trans('pages.products.attachments') }}</p>

        {% if attachment.type == 'image' %}
            <a href="{{ attachment.url }}" target="_blank">
                <img src="{{ attachment.url }}" alt="{{ item.name }}"/>
            </a>
        {% else %}
            {{ trans('pages.orders.file_url') }}
            <a href="{{ attachment.url }}">{{ item.name }}</a>
        {% endif %}
        <hr>
    {% endfor %}
{% endif %}
```

Also, the array variable `order.discounts` can be retrieved to check if there is any discount added to the order as below:

```php lineNumbers=true
{% for discount in order.discounts %}
    <span>{{ discount.name }}</span>
    <span>{{ discount.discount }}</span>
{% endfor %}
```

Multiple checks can be done in order to show more details about the order that is currently being handeled. For example, the variable `order.cod_cost` is evaluated to true in the case of selecting Cash on Delivery as the payment method. 
Also, the variable `order.shipping_cost` shows the shipping cost if there is any. Similarly, the variable `order.tax` shows the amount of any added tax. The following is an example of all of the above variables:

```php lineNumbers=true
{% if order.cod_cost %}
    <span>{{ trans('pages.orders.cod_cost') }}</span>
    <dd>{{ order.cod_cost|money }}</dd>
{% endif %}

{% if order.shipping_cost %}
    <span>{{ trans('pages.orders.shipping_cost') }}</span>
    <span>{{ order.shipping_cost|money }}</span>
{% endif %}

{% if order.tax %}
    <span>{{ trans('pages.cart.tax') }} ({{ order.tax.percent }}%)</span>
    <span>{{ order.tax.amount|money }}</span>
{% endif %}
```

The order item can also be reordered using `order.can_reorder`. However, if the customer has not paid for the order yet, the page will redirected to the payment page via the variable `order.payment_url` to finish the payment.

[`salla-modal`](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD) and [`salla-button`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) are used in here to show the user a modal to choose either to reorder or to cancel.

```php lineNumbers=true
{% if order.can_reorder %}
    <salla-button shape="link" onclick="document.querySelector('#reorder-modal').show()">
        <span>{{ trans('pages.orders.reorder') }}</span>
    </salla-button>

    <salla-modal id="reorder-modal" modal-title="{{ trans('pages.orders.reorder') }}">
        <div slot="footer">
            <salla-button>{{ trans('common.elements.ok') }}</salla-button>
        </div>
    </salla-modal>
{% endif %}
```
At this stage, the developer may show the cancellation option to the customer by using the variable `order.can_cancel`. 

:::tip[Note]
The developer may use the Salla component [`salla-button`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) in order to show buttons with actions. 
:::

```php lineNumbers=true
{% if order.can_cancel %}
    <salla-button shape="link" color="danger" onclick="document.querySelector('#modal-order-cancel').show()">
        <i class="sicon sicon-cancel-circle me-2"></i>
        <span>{{ trans('pages.orders.cancel') }}</span>
    </salla-button>

    {# Cancel Modal #}
    <salla-modal width="sm" sub-title="{{ trans('pages.orders.cancel_confirmation') }}"
                 icon="sicon-cancel" id="modal-order-cancel" icon-style="error"
                 modal-title="{{ trans('common.elements.warning') }}">
        <div slot="footer" class="grid grid-cols-2 gap-3">
            <salla-button color="danger">
                {{ trans('common.elements.ok') }}
            </salla-button>

            <salla-button ill="outline" color="light"
                          onclick="document.querySelector('#modal-order-cancel').hide()">
                {{ trans('common.elements.cancel') }}
            </salla-button>
        </div>
    </salla-modal>
{% endif %}
```
Another important section that can be added to this page is the order rating. Rating gives a better view for the useres on how popular the store and the shipping service are and how other customers liked them.
Order rating will enable the customer to rate the store and the shipping service by using the stars for rating.

:::tip[Note]
The [`salla-rating-stars`](https://docs.salla.dev/doc-422727?nav=01HNFTE06J4QC24T0D5BPRYKMD) component allows the developer to add a modal/button prompting customer to rate the order.
:::

```php lineNumbers=true
{% if order.rating.store.stars %}
   <section>
       <h2>{{ trans('pages.rating.rate_the_store') }}</h2>
       <p>{{ order.rating.store.content|raw }}</p>
       <salla-rating-stars value="{{ order.rating.store.stars }}">
      </salla-rating-stars>
   </section>
{% endif %} {% if order.rating.shipping.stars %}
   <section>
       <h2>{{ trans('pages.rating.rate_shipping') }}</h2>
       <p>{{ order.rating.shipping.content|raw }}</p>
       <salla-rating-stars value="{{ order.rating.shipping.stars }}">
       </salla-rating-stars>
   </section>
{% endif %}
```

---

## theme-architecture-pages-customer-pages/Themes-Customer-Profile-Page-Twilight-Documentation-Salla-Docs

# Profile

This [`profile template page`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/profile.twig) is for the customer's profile, which is utilised to show customer-related information including, name, email and phone number. The customer can also modify and update their information on this page. 

``` shell title = "🌐 Page URL: http://www.store-domain.com/profile"
└── src 
  ├── views
  |   ├── pages
  |   |   ├── customer
  |   |   |   ...
  |   |   |   ├── profile.twig
              ...
```

### Example
<!--
focus: false
-->
![Customer Profile](https://cdn.salla.network/docs/twilight/4/customer-profile-01.png)

### Variables


<DataSchema id="1383861" />


### Components
This page extends the default layout [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and accordingly, it takes the unified look-and-feel. For example, all of the [`header's`](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [`footer's`](https://docs.salla.dev/doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) components will be  added automatically to this page.

### JS Web Components
Customer's Profile page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.
- Date Time Picker [`<salla-datetime-picker>`](https://docs.salla.dev/doc-422702?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Tel Input [`<salla-tel-input>`](https://docs.salla.dev/doc-422739?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- File Upload [`<salla-file-upload>`](https://docs.salla.dev/doc-422703?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- User Settings [`<salla-user-settings>`](https://docs.salla.dev/doc-422741?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Verify [`<salla-verify>`](https://docs.salla.dev/doc-422742?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The  [`profile template page`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/profile.twig) calls for the following [hooks](https://docs.salla.dev/doc-422552) in order to inject extra information. These hooks are mainly used for processing the user profile `<form>`. Similarly, to add a submit  button to the form, the developer may simply use [`salla-button`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component.

```php
{% hook 'customer:profile.form.start' %}
{% hook 'customer:profile.form.fields.start' %}
{% hook 'customer:profile.form.fields.end' %}
{% hook 'customer:profile.form.submit.start' %}
{% hook 'customer:profile.form.submit.end' %}
{% hook 'customer:profile.form.end' %}
```

### Usage
The customer's profile page receives all of the `User` model information, which is accessible automatically on this page because it's included in the [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) layout file. This information can be displayed as per the developer's needs. Finally, to verify the form's input, the [`salla-verify-modal`](https://docs.salla.dev/doc-422742?nav=01HNFTE06J4QC24T0D5BPRYKMD) component can be used.
The following is a full example for all of the above.

For example, here we display customer's first name:

```php
<p> Welcome back {{ user.first_name }}! </p>
```

This page includes a form, by which the customer's profile can be updated. Below is an example for that. Note that the developer may utilize the [`salla-tel-input`](https://docs.salla.dev/doc-422739?nav=01HNFTE06J4QC24T0D5BPRYKMD) component to display the user's mobile field. 

```php lineNumbers=true
<form onsubmit="return salla.form.submit('profile.update')">
    <div>
        <label for="first-name"> {{ trans('pages.profile.first_name') }} </label>
        <input name="first_name" required="" type="text" value="{{ user.first_name }}"/>
    </div>
    <div>
        <label for="last-name"> {{ trans('pages.profile.last_name') }} </label>
        <input name="last_name" required="" type="text" value="{{ user.last_name }}"/>
    </div>
    <div>
        <label for="birthday"> {{ trans('pages.profile.birthday') }} </label>
        <input name="birthday" required="" type="text" value="{{ user.birthday }}"
               placeholder="{{ trans('pages.profile.birthday_placeholder') }}"/>
    </div>
    <div>
        <label for="email"> {{ trans('common.elements.email') }} </label>
        <input name="email" required="" type="email" value="{{ user.email }}"/>
    </div>

    <div>
        <label for="gender"> {{ trans('pages.profile.gender') }} </label>
        <select name="gender" required="">
            <option value="">
                {{ trans('pages.profile.gender_placeholder') }}
            </option>
            <option value="male">{{ trans('pages.profile.male') }}</option>
            <option value="female">{{ trans('pages.profile.female') }}</option>
        </select>
    </div>

    <div>
        <label for="international-mobile">
            {{ trans('common.elements.mobile') }}
        </label>
        <salla-tel-input mobile="{{ user.mobile }}"></salla-tel-input>
    </div>

    <salla-button type="submit" loader-position="end" class="w-full">
        {{ trans('common.elements.save') }}
    </salla-button>
</form>
{# its required in case the customer change his mobile when submit the form #}
<salla-verify-modal></salla-verify-modal>
```

---

## theme-architecture-pages-customer-pages/Wishlist-Page-Guide-Twilight-Documentation-Salla-Docs

# Wishlist

This [`wishlist page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/customer/wishlist.twig) can help customers save items that they wish to buy, this can greatly help to check the offers that apply to the items the customers are interested in as well as keeping track of the stock.

``` shell title = "🌐 Page URL: http://www.store-domain.com/wishlist"
└── src 
  ├── views
  |   ├── pages
  |   |   ├── customer
  |   |   |   ...
  |   |   |   ├── wishlist.twig
              ...
```

### Example
<!--
focus: false
-->
![Customer Wishlist](https://cdn.salla.network/docs/twilight/4/customer-wishlist-01.png)


### Variables
<DataSchema id="1383885" />


### Components
This page extends the default layout [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and accordingly, it takes the unified look-and-feel. For example, all of the [`headers`](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [`footers`](https://docs.salla.dev/doc-422602?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) components will be  added automatically to this page.

In addition, the `User` model is accessible automatically on this page because it's included in the [`master.twig`](https://docs.salla.dev/doc-421944?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) layout file.

### JS Web Components
Customer Wishlist page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Add Product [`<salla-add-product-button>`](https://docs.salla.dev/doc-422692?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The  `wishlist page template` may call the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject extra information.

```php lineNumbers=true
{% hook 'customer:wishlist.items.start' %}
{% hook 'customer:wishlist.items.end' %}
```

### Usage
This page simply receives the `products` object which represents the list of the products that the customer has added to his own wishlist. Based on that, we use a simple `for-loop` statement to display each product. 

The developer can show a button to encourage the customer to move a product from the wishlist into the cart. For this purpose [`salla-button`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component can be used.
 

```php lineNumbers=true
{% for product in products %}
    <a href="{{ product.url }}">
        <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
    </a>
    <h3>
        <a href="{{ product.url }}">{{ product.name }}</a>
    </h3>
    <div>
        {% if product.on_sale %}
            {{ product.sale_price|money }}
            <small>{{ product.regular_price|money }}</small>
        {% else %}
            {{ product.price|money }}
        {% endif %}
    </div>

    <salla-button onclick="salla.cart.addItem({{ product.id }})">
        {{ trans('pages.cart.add_to_cart') }}
    </salla-button>

    <salla-button onclick="salla.wishlist.remove({{ product.id }})">
        <i class="sicon-cancel">Remove</i>
    </salla-button>
{% else %}
    {{ trans('pages.profile.wishlist_placeholder') }}
{% endfor %}
```

---

