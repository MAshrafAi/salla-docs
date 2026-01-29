# Theme Architecture Components Common Components

## Table of Contents

- [theme-architecture-components-common-components/Comments-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-common-components-comments-component-twilight-documentation-salla-docs)
- [theme-architecture-components-common-components/Footer-Components-Twilight-Documentation-Salla-Docs](#theme-architecture-components-common-components-footer-components-twilight-documentation-salla-docs)
- [theme-architecture-components-common-components/Header-Components-Twilight-Documentation-Salla-Docs](#theme-architecture-components-common-components-header-components-twilight-documentation-salla-docs)
- [theme-architecture-components-product-components/Essentials-Components-Donation,-Offers-&-Similar-Products-Twilight-Documentation-Salla-Docs](#theme-architecture-components-product-components-essentials-components-donation,-offers-&-similar-products-twilight-documentation-salla-docs)
- [theme-architecture-components-product-components/Options-Components-Product-Customization-Fields-Twilight-Documentation-Salla-Docs](#theme-architecture-components-product-components-options-components-product-customization-fields-twilight-documentation-salla-docs)

---

## theme-architecture-components-common-components/Comments-Component-Twilight-Documentation-Salla-Docs

# Comments component

This component is used to display a threaded comments section that also allows adding comments and rating them. It can be displayed as a feedback of products or testimonial which are shown in [Single product page](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and [Single page](https://docs.salla.dev/doc-422578?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).


**The following is the location of the Comments component**

``` shell
└── src 
    ├── views
      ├── components
      |   ...
      |   └── comments.twig     
      |   ...
      ...

```

## Example

<!-- focus:false -->
![Comments](https://cdn.salla.network/docs/twilight/4/pages-components-comments-01.png)

## Variables



<DataSchema id="1384762" />

## Usage 
This component will check the eligibility of the user to create comments. If the user is allowed, the component will display comment section contaiting the text field to allow user to comment and submit the comment using `salla-button`. 

```php lineNumbers
{% if user.can_comment %}
<form onsubmit="return salla.form.onSubmit('comment.send', event);">
  <input name="type" type="hidden" value="{{ type }}" />
  <input name="id" type="hidden" value="{{ id }}" />

  <h2>{{ trans('blocks.comments.title') }}</h2>
  <textarea placeholder="{{ trans('blocks.comments.placeholder') }}" name="comment" required maxlength="500" cols="30" rows="30"></textarea>
  <div>
    <salla-button type="submit" loader-position="end">
      {{ trans('blocks.comments.submit') }}
    </salla-button>
  </div>
</form>
{% endif %}
```

Next, the component checks comments availability then uses `salla-infinite-scroll` to display the comments in a `for-loop`. It will also display the comments' details such as `name`, `avatar`, `has-order`, `rating star`, `created date`, `comment content` and checks if the `user type` is admin. As shown in the below code.

```php lineNumbers
{% if comments|length %}
<salla-infinite-scroll next-page="{{ comments.next_page }}">
  <h2>{{ pluralize('blocks.comments.comment', comments.total|number)|raw }}</h2>
  {% for comment in comments %} 
  {# you can check the full exmaple in the starter theme #} 
  {% set is_admin = comment.type=='admin' %} 
  {% if not is_admin %}
  <div>
    {% endif %}
    <div
      class="{% if is_admin %} nested-comment reply ps-8 md:ps-16 mt-8 admin 
              {% else %} comment 
              {% endif %} flex text-sm space-s-3 comment_id_{{ comment.id }}">
      {% if is_admin %} <i></i>
      {% endif %}
      <div>
        <img data-src="{{ comment.avatar|is_placeholder ? 'images/avatar.png' | cdn : comment.avatar }}" alt="{{ comment.name }}" src="{{ 'images/s-empty.png' | asset }}" />
      </div>
      <div>
        <h3>{{ comment.name }}</h3>
        {% if comment.has_order or comment.stars %}
        <div>
          {% if comment.has_order %}
          <i></i>
          <span>
            {{ trans('blocks.comments.has_bought') }}{{ comment.stars?', ':'' }}
          </span>
          {% endif %} {% if comment.stars %}
          <span>{{ trans('pages.rating.rated') }}</span>
          {% endif %}
        </div>
        {% endif %}
      </div>
      <p>{{ comment.created_at|time_ago }}</p>
      {% if comment.stars %}
      <div>
        {% for i in 1..5 %}
        <i></i>
        {% endfor %}
      </div>
      {% endif %}
      <p>{{ comment.content|raw }}</p>
      {% if comment.is_pending %}
      <span>{{ trans('blocks.comments.waiting_approval') }}</span>
      {% endif %}
      {% if comment.has_order %}
      <i data-toggle="tooltip" data-placement="right" title="{{ trans('blocks.comments.has_order') }}"></i>
      {% endif %}
    </div>
    {% if not is_admin %} 
    {% for replay in comment.replies %} 
    {% include _self with {comment:replay} %}
    {% endfor %}
  </div>
  {% endif %} {% endfor %}
</salla-infinite-scroll>
{% else %}
<div>
  <i></i>
  <p>{{ trans('blocks.comments.no_comments') }}</p>
</div>
{% endif %}
```

---

## theme-architecture-components-common-components/Footer-Components-Twilight-Documentation-Salla-Docs

# Footer Components

By default, themes created with **Twilight** include a footer section. The footer section includes  components such as the `contacts`, `payment-methods`, `social media links`, and many more.

**Following is the location of the footer components:**

``` shell
└── src 
    ├── components
    |   ...
    |   └── Footer                   
    |       ├── footer.twig
    |       ├── contacts.twig
    |       ├── mobile-apps.twig
    |       ├── menu.twig
    |       ├── payment-methods.twig          
    |       └── social.twig            
    |   ...
    ...

```

## Footer Components Example
In the following example we can see that the footer includes:
- [Footer](#footer)
- [Contacts](#contacts)
- [Mobile Apps](#mobile-app)
- [Menu](#menu)
- [Payment Methods](#payment-methods)
- [Social](#social-links)

<!--
focus: false
-->
![Footer Components](https://cdn.salla.network/docs/twilight/4/pages-components-footer-01.png)

<hr/>

## Footer
This part is the footer's main component, which embeds several parts, such as `contacts`, `payment-methods`, and `social`.

```php title="Call Command"
{% component "footer.footer" %} 
```

### Usage
In general, the footer section is a container for all of the footer-related components. These element components can easily be called there as per the developer style and design. Below is an example of including these components.

```php lineNumbers
<div>
    <a href="{{ link('/') }}">
        <img src="{{ store.logo }}" alt="{{ store.name }}">
    </a>
    {% if store.description %}
        <p>
            {{ store.description|raw }}
        </p>
    {% endif %}
    {% component 'footer.social' %}

    {% if store.settings.tax.number %}
        <div>
            {% if store.settings.tax.certificate %}
                <a onclick="document.querySelector('#modal-value-tax').show()" href="#!"
                   alt="{{ store.settings.tax.number }}">
                    <img src="{{ 'images/tax.png' | cdn }}" alt="value added tax"/>
                </a>
            {% endif %}
            <div>
                <p>{{ trans('common.elements.tax_number') }}</p>
                <b>{{ store.settings.tax.number }}</b>
            </div>
        </div>

        {% if store.settings.tax.certificate %}
            <salla-modal sub-title-first sub-title="{{ trans('common.elements.tax_number') }}"
                         modal-title="{{ store.settings.tax.number }}" id="modal-value-tax">
                <div>
                    <img src="{{ store.settings.tax.certificate }}" alt="{{ store.settings.tax.number }}"/>
                </div>
            </salla-modal>
        {% endif %}
    {% endif %}
</div>

{% component 'footer.pages' %}
{% component 'footer.contacts' %}
{% component 'footer.mobile-apps' %}
{% hook copyright %}
{% component 'footer.payment-methods' %}
```
:::tip[Educational Clip]
<Video src="https://youtu.be/bEKtudlK_ts?si=tz5kiik4GdmUkfwD"></Video>

:::

<hr/>

## Contacts
This component shows the "contact us" details provided by the store owner. These details can be a WhatsApp contact number, a mobile or phone number, a Telegram channel, or even an email address.

```php title="Call Command"
{% component "footer.contacts" %} 
```

### Variables


<DataSchema id="1383641" />


### Usage
This component receives an array for `contacts`. Each option in the array represents a specific contact detail. The developer can use a *loop* statement to display all of the contacts details. Below is an example of that.

```php lineNumbers
{% if is_header %}
    {% for contact in contacts|filter(contact => contact.type in ['email', 'phone']) %}
        <a href="{{ contact.url }}">
            {% if contact.type == 'email' %}
                {{ contact.value }}
            {% else %}
                <span>{{ trans('blocks.footer.social') }}:</span>
                <span>{{ contact.value }}</span>
            {% endif %}
        </a>
    {% endfor %}
{% else %}
    <h3>{{ trans('blocks.footer.social') }}</h3>
    {% for contact in contacts %}
        <a href="{{ contact.url }}">
            <i class="{{ contact.icon }}"></i>
            <span>{{ contact.value }}</span>
        </a>
    {% endfor %}
{% endif %}
```

<hr/>

## Mobile-app
This component lists the links of the mobile applications of the store. For example, it may show the store's iOS application link in the App Store.

```php title="Call Command"
{% component "footer.mobile-apps" %} 
```

### Variables


<DataSchema id="1383659" />


### Usage
This component receives an array of `apps`, and then display each element using a *for-loop* statement.

```php lineNumbers
<h3>{{ trans('blocks.footer.download_apps') }}</h3>
<ul>
    {% for app in apps %}
        <li>
            <a href="{{ app.url }}" rel="noreferrer" target="_blank">
                <img src="{{ app.name }}.png" alt="{{ app.name }}"/>
            </a>
        </li>
    {% endfor %}
</ul>
```

<hr/>

## Menu 
In this section of the footer, we list a group of links to some internal pages. For example, a link to the "Privacy Policy" page.

```php title="Call Command"
{% component "footer.menu" %} 
```

### Variables


<DataSchema id="1383658" />

### Usage
This component receives an array of pages as `items`, and then display each element using a *for-loop* statement.

```php lineNumbers
{% if is_header %}
    {% if items|length %}
        {% for key, item in items|slice(0,3) %}
            <a href="{{ item.url }}">{{ item.title }}</a>
        {% endfor %}
    {% endif %}
{% else %}
    <h3>{{ trans('blocks.footer.pages_links') }}</h3>
    <div>
        {% for item in items %}
            <a href="{{ item.url }}">{{ item.title }}</a>
        {% endfor %}
    </div>
{% endif %}
```

<hr/>

## Payment-methods 
This component lists the available payment methods provided by the store. For example, "Cash On Delivery" or/and "Credit Cards".

```php title="Call Command"
{% component "footer.payment-methods" %}
```

### Variables


<DataSchema id="1383662" />


### Usage 
This component receives an array of `payment_methods`, and then display each element using a *for-loop* statement.

```php lineNumbers
<ul>
    {% for method in payment_methods %}
        <li>
            <img src="{{ ('images/payment/'~ method ~'_mini.png') | cdn }}" alt="{{ method }}" />
        </li>
    {% endfor %}
    {% if store.social.maroof %}
        <li>
            <a href="{{ store.social.maroof }}" target="_blank" rel="noreferrer">
                <img src="{{ 'images/maroof-footer.png' | cdn }}" alt="maroof" />
            </a>
        </li>
    {% endif %}
</ul>
```

<hr/>

## Social Links
This component lists all of the social media links provided by the store. For example, Instagram, Twitter, Snapchat, Tiktok, Youtube, Facebook, and Pinterest links.

```php title="Call Command"
{% component "footer.social" %}
```

### Variables


<DataSchema id="1383663" />



### Usage
This component receives an array of `links`, and then display them our using a *for-loop* statement.
```php lineNumbers
<ul>
    {% for link in links %}
        <li>
            <a href="{{ link.url }}" title="link.name" aria-label="{{ link.name }}">
                <i class="sicon-{{ link.type }}"></i>
            </a>
        </li>
    {% endfor %}
</ul>
```

---

## theme-architecture-components-common-components/Header-Components-Twilight-Documentation-Salla-Docs

# Header Components

The default header which comes with **Twilight** includes all of header-related components such as `header`,`breadcrumbs`,`menu` and many more. Developers can easily modify these components, as we see in this article.


**Following is the location of the header components:**

``` shell
└── src
  ├── views 
    ├── components
    |   ...
    |   └── header
    |       ├── header.twig
    |       ├── advertisement.twig
    |       ├── breadcrumbs.twig
    |       ├── menu.twig
    |       ├── menu-item.twig
        ...
    

```

## Header Components Example
In the following example we can see that the header includes:
- [Header](#header)
- [Advertisement](#advertisement)
- [Breadcrumbs](#breadcrumbs)
- [Menu](#menu)
- [Menu Item](#menu-item)

<!--
focus: false
-->

![Header Component](https://cdn.salla.network/docs/twilight/4/header-component-01.png?v=1-10-2022)

<hr/>

## Header
This part is the main component of the header which _embeds_ several parts, such as `breadcrumbs` and `main menu`.

```php title="Call Command"
{% component "header.header" %} 
```

### Troubleshooting Tip

The `header` design can occasionally be hidden. You can see `twilight::errors` in the browser's console logs, where you can investigate the problem. The following illustrates the error as follows:

`Array to string conversion in File [src/views/components/header/header.twig] at line 7`

The below code should solve the issue:

```js
  {% set nav_type = theme.settings.get('your_arrayable_key') %}
  {% if nav_type is iterable %}
  {% set nav_type = nav_type|first %}
  {% endif %}
```

The line `{% set nav_type = theme.settings.get('your_arrayable_key') %}` retrieves the value of a setting from the Twilight theme settings. The developer needs to replace `your_arrayable_key` with the actual key representing the setting that contains the array.

By using this code, the developer handles the scenario where `nav_type` is an array. If it is an array, you are setting `nav_type` to its first item. This way, you avoid the error related to converting the array to a string.

:::tip[Educational Clip]

<Video src="https://www.youtube.com/watch?v=qJIfLB_kzVM&list=PLeAh6geWgZi3YdWKZAnG1leDuenBlCa_7&index=4"></Video>

:::
<hr/>

## Advertisement
This component receives an object representing an advertisement's **text**, and then displays its details.

```js title="Call Command"
{% component "header.advertisement" %}
```

### Variables


<DataSchema id="1387912" />


### Usage
Using the `advertisement` object, we can get the details of `advertisement.icon`, `advertisement.url`, `advertisement.description`, and so on. The developer can use these data within any style designed by them.

```php lineNumbers
{% if advertisement.icon %}
  <span class="{{ advertisement.icon }}"></span>
{% endif %}
{% if advertisement.url %}
  <a href="{{ advertisement.url }}" {% if advertisement.is_new_window %} target='_blank' {% endif %}>
    {{ advertisement.description }}
  </a>
{% else %}
  {{ advertisement.description }}
{% endif %}
```

<hr/>

## Breadcrumbs
Breadcrumbs are a set of links that indicate the current page and its "ancestors" (parent, grandparent, and so on), usually leading back to the site's homepage.

```js title="Call Command"
{% component "breadcrumbs" %}
```

### Variables


<DataSchema id="1383665" />


### Usage
This component receives `breadcrumbs `, which is an array of breadcrumb described by their title and url. A loop goes through this object and display its parts. Developer has the option to edit the look-and-feel of this object.

```php lineNumbers
{% for breadcrumb in breadcrumbs %}
    {% if not loop.last %}
        <li><a href="{{ breadcrumb.url }}" class="...">{{ breadcrumb.title }}</a></li>
        <li><i class="..."></i></li>
    {% else %}
        <li><span class="...">{{ breadcrumb.title|raw }}</span></li>
    {% endif %}
{% endfor %}
```

<hr/>

## Menu
This component represents the store's main menu, which is usually for the store categories pages. It's considered as the primary roadmap for the customers to the store's internal categories. It comes with many options, such as a list of products to be displayed on the menu.

```js title="Call Command"
{% component "header.menu" %} 
```


### Variables


<DataSchema id="1383682" />


### Usage
For this component,  the object `menus` contains the details of each item in the menu. Using a loop these menu items can be displayed.

```php lineNumbers
<ul>
    {% for menu in menus %}
        <li {{ menu.attrs }}>
            {% if menu.has_children %}
                <span>{{ menu.title }}</span>
                <ul>
                    <li><a href="{{ menu.url }}">{{ menu.title }}</a></li>
                    {% for submenu in menu.children %}
                        {# to make sure you are support three level of item you can use _self to render the same #}
                        {# twig file again and again for each level #}
                        {% include _self with {menu:submenu} %}
                    {% endfor %}
                </ul>
            {% else %}
                <a {{ menu.link_attrs }} href="{{ menu.url }}">{{ menu.title }}</a>
            {% endif %}

            {% if menu.mega_menu %}
                <div class="product-item-menu">
                    {% for product in menu.mega_menu|slice(0, 4) %}
                        <a href="{{ product.url }}">
                            <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
                            {% if product.promotion_title %}
                                {{ product.promotion_title }}
                            {% endif %}
                        </a>
                        <h3>
                            <a href="{{ product.url }}">{{ product.name }}</a>
                        </h3>
                        {% if product.on_sale %}
                            <div>
                                <h4>{{ product.sale_price|money }}</h4>
                                {{ product.regular_price|money }}
                            </div>
                        {% else %}
                            <h4>{{ product.price|money }}</h4>
                        {% endif %} 
                    {% endfor %}
                </div>
            {% endif %}
        </li>
    {% endfor %}
</ul>
```

:::tip[Educational Clip]

<Video src="https://www.youtube.com/watch?v=IPos8G2AvZ8&list=PLeAh6geWgZi3YdWKZAnG1leDuenBlCa_7&index=5"></Video>

:::


<hr/>

## Menu Item
The Menu Item component plays a vital role in navigation and user experience. It helps create dynamic menus by organizing individual menu items.

### Usage
The menu item component is used for both mobile and desktop devices. It generates menu items with corresponding links and handles child menu items and associated products, adapting to different screen sizes.

```php lineNumbers
{# MOBILE #}
    <li  {{ menu.attrs }}>
        {% if not menu.has_children %}
            <a {{ menu.link_attrs|raw }} href="{{ menu.url }}>{{ menu.title }}</a>
        {% else %}
            <span>{{ menu.title }}</span>
            <ul>
                <li><a {{ menu.link_attrs|raw }} href="{{ menu.url }}>{{ menu.title }}</a></li>
                {% for submenu in menu.children %}
                    {% include _self with {menu:submenu} %}
                {% endfor %}
            </ul>
        {% endif %}
    </li>

{# DESKTOP #}
    <li    {{ menu.attrs|raw }}>
        <a {{ menu.link_attrs|raw }} href="{{ menu.url }}">
            <span>{{ menu.title }}</span>
        </a>
        {% if menu.has_children %}
            <div>
                <ul>
                    {% for submenu in menu.children %}
                        {% include _self with {menu:submenu, is_root_menu:false} %}
                    {% endfor %}
                </ul>
                {% if menu.products %}
                    <div class="grow p-8">
                        <div class="grid gap-4 grid-cols-4">
                            {% for product in menu.products|slice(0, 4) %}
                                <salla-product-card shadow-on-hover product="{{product}}"></salla-product-card>
                            {% endfor %}
                        </div>
                    </div>
                {% endif %}

            </div>
        {% endif %}
    </li>
```



<hr/>

<!-- ## User Menu
The user menu components displays the notifications icon which comes at top of store where users can check the received notification related to the store interactions.

```js title="Call Command"
{% component "header.user-menu" %}
```

### Variables
```json json_schema
{
  "type": "object",
  "properties": {
    "new_notifications_count": {
      "type": "integer",
      "description": "The number of notifications for the user display."
    },
    "pending_orders_count": {
      "type": "integer",
      "description": "The number of the pending orders for the user display."
    }
  },
  "required": [
    "new_notifications_count",
    "pending_orders_count"
  ]
}
```

### Usage
Using the variables `new_notifications_count`, we can check if we need to highlight this for the user using any style we may choose.

```php lineNumbers
{% if new_notifications_count %}
<span>{{new_notifications_count }}</span>
{% endif %}
```
In addtion to that, we can use the `pending_orders_count` to highlight if there is any orders waiting for payment.

```php lineNumbers
<a href="{{ link('orders.index.pending') }}" class="menu-item {{ is_current_url('orders.index.pending')? 'is-active':'' }}">
  <i></i>
  <span>{{ trans('common.titles.pending_orders') }}</span>
  {% if pending_orders_count %}
  <span>{{ pending_orders_count }}</span>
  {% endif %}
</a>
```

<hr/> -->

---

## theme-architecture-components-product-components/Essentials-Components-Donation,-Offers-&-Similar-Products-Twilight-Documentation-Salla-Docs

# Essentials

The product page template consists of several essential components that give a look at the product details. For example, the product's brands, similar products, and product tags components.

In this article, we will explore the essential components for every product template page.

**Following is the location of the header components:**

```shell
└── src 
  ├── views
    ├── components
    |   ...
    |   └── product
    |   |   ├── donation-progress-bar.twig
    |   |   ├── offer.twig
    |   |   └── similar-products.twig                            
    |   ...
    ...
```


Following are the essential components which can be used within product page template:
- [Donation Progress Bar](#donation-progress-bar)
- [Offer](#offer)
- [Similar Products](#similar-products)

<hr/>

## Donation Progress Bar
The donation progress bar is used to show a donation's amount up to date, as well as how much time is left in which a user can contribute towards the fundraising campaign.

### Example
<!--
focus: false
-->
![Essentials Components](https://cdn.salla.network/docs/twilight/4/pages-components-products-essentials-01.png)



### Variables


<DataSchema id="1384771" />


### Usage

The `donation` object contains all of the donation related values and messages. For example;

- `product.donation.collected_amount`: shows the collected amount up to date.
- `product.donation.target_amount`: shows the targeted amount to be collected.
- `product.donation.target_percent`: shows the percentage of the targeted amount.

```js
{% if product.donation.target_message %}
    <span>{{ product.donation.target_message }}</span>
{% else %}
    <div class="...">
        <span>{{ product.donation.collected_amount|money }}</span>
        <span>{{ product.donation.target_amount|money }}</span>
    </div>
    <div class="...">
        <div class="..." style="width: {{ product.donation.target_percent }}%">
        </div>
    </div>
    {% if product.donation.target_end_date %}
        <small class="...">{{ pages.products.donation_target_date }} {{ product.donation.target_end_date|date }}</small>
    {% endif %}
{% endif %}
```

## Offer 
This component shows a slider of products that have special offers. In this way, the customer is able to check all of the offers related to the currently being viewed product in one place.

### Example
<!--
focus: false
-->
![Footer](https://cdn.salla.network/docs/twilight/4/pages-components-products-essentials-02.png)


### Variables


<DataSchema id="1384784" />

### Usage
For this component, the main variable is the `offer` object. Using this component, the developer can show both `offer.name` and `offer.description`. It contains a list of the related products that include offers. Using _for-loop_ statement such as `{% for product in offer.products %}` , the list of the offered products can be retrieved and displayed using a slider with cards, for example. 

```js
<div>
    <p>{{ offer.name }}: {{ offer.description|raw }}</p>
    {% if offer.products|length %}
        <div>
            <div>
                {% for product in offer.products %}
                    <div>
                        {% include 'pages.partials.product.card' %}
                    </div>
                {% endfor %}
            </div>

        </div>
    {% else %}
        {% for category in offer.categories %}
            <a href="{{ category.url }}">
                <span>{{ category.name }}</span>
            </a>
        {% endfor %}
    {% endif %}
    <div>
        <div> Special Offer' </div>
    </div>

</div>
```
<hr/>


## Similar Products
This component displays a list of similar and related products to the currently beviewed product. This is to assist the customers in discovering and buying products that best meet their needs. Showing similar products helps to find complementary products to the ones the customer is viewing, `Cross-selling`, or offer a better and more expensive alternative product, `Upsells`.


### Example
<!--
focus: false
-->
![image](https://cdn.salla.network/docs/twilight/4/pages-components-products-essentials-03.png)

### Variables


<DataSchema id="1384787" />


### Usage
In order to display the list of similar products, a for-loop is used to iterate through the `products` objects, and then display the information for each product in the list.

```js
{% for product in products %}
<div class="...">
    {% include 'pages.partials.product.card' %}
</div>
{% endfor %}
```

---

## theme-architecture-components-product-components/Options-Components-Product-Customization-Fields-Twilight-Documentation-Salla-Docs

# Options

In this article, we will list the group components in order to create the options related to the product. For example, the product's colors and size, which we need some special text components to display them. 


**Following is the location of a product's options components:**

```shell
└── src
  ├── views 
    ├── components
    |   ...
    |   └── product
    |   |   └── options
    |   |       ├── color.twig
    |   |       ├── date.twig
    |   |       ├── datetime.twig
    |   |       ├── donation.twig
    |   |       ├── image.twig
    |   |       ├── multiple-options.twig
    |   |       ├── number.twig
    |   |       ├── single-option.twig
    |   |       ├── splitter.twig
    |   |       ├── text.twig
    |   |       ├── textarea.twig
    |   |       ├── thumbnail.twig
    |   |       └── time.twig                               
    |   ...
    ...

```

Following are the option components which can be used to create a product's options :
- [Color](#color)
- [Date](#date)
- [Datetime](#datetime)
- [Donation](#donation)
- [Image](#image)
- [Multiple Options](#multiple-options)
- [Number](#number)
- [Single Option](#single-option)
- [Splitter](#splitter)
- [Text](#text)
- [Textarea](#textarea)
- [Thumbnail](#thumbnail)
- [Time](#time)

<hr/>

## Color
This component is a set of options rendered as colors, in which the customer can select the color they want. It can be useful to present a product's color.

### Example

<!--
focus: false
-->

![Color Options Components](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-01.png)

### Variables


<DataSchema id="1384760" />

### Usage
The HTML element _input_radio_ is used to allow customers to select one item at a time. The details of the product's colors can be displayed using a _for-loop_ statement through the `details` object.

```js
{% for detail in option.details %}
<div>
    <input type="radio"
           {{ detail.is_selected?'checked':'' }} 
           {{ detail.is_out?"disabled":"" }} 
           name="options[{{ option.id }}]"
           value="{{ detail.id }}" ... />

    <p>{{ detail.name }}</p>
    
    {% if detail.is_out %}
    <small>Out of stock</small>
    {% endif %}
</div>
{% endfor %}
```

## Date
This component works as a date picker to allow customers to select a date. It can be used as an input field for the delivery date, as an example.

### Example
<!--
focus: false
-->
![Date](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-02.png)

### Variables


<DataSchema id="1307388" />

### Usage
The HTML element _input_ is used to show this component with some predefined attributes.
```js
<input class="form-input date-element{{ required?' required':'' }}"
       id="..."
       data-min-date="today"
       placeholder="{{ option.placeholder }}"
       name="options[{{ option.id }}]" {{ attirubtes|raw }}
       readonly="readonly"
       value="{{ value }}"
       type="text"
/>
```

## Datetime
This component works as a date-and-time picker to allow customers to select a date and time. It can be used as an input field for the delivery date and time, as an example.
### Example

<!--
focus: false
-->

![Datetime](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-03.png)

### Variables


<DataSchema id="1384766" />


### Usage
The HTML element _input_ is used to show this component with some predefined attributes. Some of the main variables here are `option.placeholder` and `order_times`. 

```js
<input class="form-input date-time-element{{ required?' required':'' }}"
       placeholder="{{ option.placeholder }}"
       data-order-times="{{ order_times|json_encode }}"
       data-timezone="{{ time_zone }}"
       name="options[{{ option.id }}]"
        {{ attirubtes|raw }}
       {% if from_date_time %}
       data-from-date-time='{{ from_date_time }}'
       data-to-date-time='{{ to_date_time }}'
       {% endif %}
       readonly="readonly"
       value="{{ value }}"
       type="text"
/>
```
## Donation
The donation component is a track bar that allows customers to set or adjust a donation value. When the customer changes the value, the donation amount will take the value of this track bar.

### Example

<!--
focus: false
-->

![Donation](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-04.png)

### Variables


<DataSchema id="1384772" />

### Usage
In order for the customer to make a donation using the currently being viewed product, that product should allow donations. This can be checked by checking the variable `product.can_donate`. The price of that product can also be used as a default value by using `<input type="text"  value="{{ product.price }}" />`.

To check if the donation target has been accomplished, the developer can use the variable `product.donation.completed`.

```js
{% if product.can_donate %}
<div>
    <p>Donation Amount</p>
    <div>
        <input type="text"  value="{{ product.price }}" />
        ...
    </div>
</div>
{% else %}
<h4 class="...">
    {% if product.donation.completed %}
        <p>Donation Exceed Target Amount</p>
    {% else %}
        <p>Donation Exceed Target Date</p>
    {% endif %}
</h4>
{% endif %}
```

## Image
This component gives the user the ability to upload an image from the product page. It can be used in many ways, such as allowing customers to send more details about the product they require.

### Example

<!--
focus: false
-->

![Image](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-05.png)

### Variables

<DataSchema id="1384774" />

### Usage
The HTML element _input_ is used to show this component with some predefined attributes. 
```js
<input name="options[{{ option.id }}]"
       class="...""
       {% if value %}
            data-default="{{ value }}"
       {% endif %}
            {{ attirubtes|raw }}
       type="file"
/>
```

## Multiple Options
This component works similarly to "checkboxes" to allow the user to select one or more options from a set. 

### Example

<!--
focus: false
-->

![Multiple Options](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-06.png)

### Variables


<DataSchema id="1384775" />

### Usage
The list of given options to the user can be retrieved and displayed using the _for-loop_ statement through the `option object. This list of options includes details such as `full_name`.
```js
<div>
    {% for key,detail in option.details %}
    <div >
        <input  id="..." 
                {{ disabled?"disabled":"" }} {{detail.is_selected?"checked":"" }} 
                name="options[{{ option.id }}]" data-option="{{ option.id }}"
                value="{{ detail.id }}" type="checkbox" {{ attirubtes|raw }} />
        
        <p>{{ detail.full_name }}</p>
            
    </div>
    {% endfor %}
</div>
```

## Number
This component gives the user the ability to enter numbers, which can be used in many cases, such as entering the required quantity for a product.

### Example

<!--
focus: false
-->

![Number](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-07.png)

### Variables

<DataSchema id="1384780" />


### Usage
The HTML element _input_ is used to show this component with some predefined attributes. 

```js
<input placeholder="{{ option.placeholder }}"
       name="options[{{ option.id }}]"
       value="{{ value }}"
       type="text"
       {{ attirubtes|raw }}
/>
```

## Single Option
This component shows a list of options where the customer is allowed to select a single option at a time. The list is more compact and can support a longer list of options if needed.

### Example

<!--
focus: false
-->

![Single Option](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-08.png)


### Variables

<DataSchema id="1384788" />


### Usage
The HTML element _select_ is used to show this component with some predefined attributes. Inside this element, a _for-loop_ is used to iterate through the `options` which contains the list of the given options.
```js
<select name="options[{{ option.id }}]"
        data-option="{{ option.id }}" {{ attirubtes|raw }}>
    <option placeholder value="">{{ option.placeholder }}</option>
    {% for key,detail in option.details %}
        <option {{ detail.is_selected ? "selected" : "" }} value="{{ detail.id }}">
            {{ detail.full_name }}
        </option>
    {% endfor %}
</select>
```

## Splitter
This component defines a thematic break in a product page. It works similarly to the _hr_ HTML tag in order to create a splitter.

### Example

<!--
focus: false
-->

![Splitter](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-09.png)

### Variables


<DataSchema id="1384789" />

### Usage
The developer has the ability to create a _css class_ to style a break line. As shown below, we can apply this splitter class to any _div_ element.

```js
<div class="splitter"></div>
```

## Text
This component allows users to enter text. It can allow a single line and can be used to enter a product name, for example.

### Example

<!--
focus: false
-->

![Text](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-10.png)

### Variables


<DataSchema id="1384791" />


### Usage
The HTML element _input_ is used to show this component with some predefined attributes. The `option` object is used to show any detail related to the component, for example, `option.placeholder` to set a default text as a start.

```js
<input placeholder="{{ option.placeholder }}"
       name="options[{{ option.id }}]" {{ attirubtes|raw }}
       value="{{ value }}"
       type="text"/>
```
## Textarea
This component allows users to enter multiple line text. It allows the user to enter multiple lines of text and can be used to enter a note about a product, for example.

### Example

<!--
focus: false
-->

![Textarea](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-11.png)

### Variables


<DataSchema id="1384792" />


### Usage
The HTML element _input_ is used to show this component with some predefined attributes. The `option` object is used to show any detail related to the component, for example, `option.placeholder` to set a default text as a start.

```js
<textarea placeholder="{{ option.placeholder }}"
          name="options[{{ option.id }}]" {{ attirubtes|raw }}>
          {{ value }}
</textarea>
```

## Thumbnail
A thumbnail is a small image that represents a larger image when clicked on, and is commonly identified with a border around it. This component can be used to show example images of a product's options.

### Example

<!--
focus: false
-->

![Thumbnail](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-12.png)

### Variables


<DataSchema id="1384793" />

### Usage
The list of given thumbnails for a product's options can be retrieved and displayed using the _for-loop_ statement through the `option object. This list of options includes details such as `detail.image` to display the thumbnail's image. This component may use the  _html input radio_ element in order to restrict the user to selecting one image, option, at a time.

```js
{% for detail_index, detail in option.details %}
<input {{ detail.is_selected?'checked':'' }} 
       required type="radio" 
       id="option_{{ detail.id }}-{{ key_prefix }}" 
       {{ detail.is_out?"disabled":"" }} 
       data-itemid="{{ detail.id }}" 
       name="options[{{ option.id }}]"
       data-img-id="{{ detail.option_value }}" 
       value="{{ detail.id }}" 
/>

<img data-src="{{ detail.image }}" src="{{ asset('images/s-empty.png') }}" class="object-cover h-full w-full lazy-load"
    title="{{ detail.name }}" alt="{{ detail.name }}" />

<p>{{ detail.name }}</p>
{% if detail.is_out %}
<small>Out of stock</small>
{% endif %}
{% endfor %}
```
## Time
This component works as a time picker to allow customers to enter a specific time. It can be used as an input field for the delivery time, as an example.

### Example

<!--
focus: false
-->

![Time](https://cdn.salla.network/docs/twilight/4/pages-components-products-options-13.png)

### Variables


<DataSchema id="1384794" />

### Usage
The HTML element _input_ is used to show this component with some predefined attributes along with the `option` object.

```js
<input placeholder="{{ option.placeholder }}"
       name="options[{{ option.id }}]" {{ attirubtes|raw }}
       readonly="readonly"
       value="{{ value }}"
       type="text"/>
```

---

