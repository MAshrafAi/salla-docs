# Theme Architecture Pages Brand Pages

## Table of Contents

- [theme-architecture-pages-brand-pages/Brands-Listing-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-brand-pages-brands-listing-page-template-twilight-documentation-salla-docs)
- [theme-architecture-pages-brand-pages/Single-Brand-Page-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-brand-pages-single-brand-page-template-twilight-documentation-salla-docs)

---

## theme-architecture-pages-brand-pages/Brands-Listing-Page-Template-Twilight-Documentation-Salla-Docs

# Brands listing

The [`brand listing page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/index.twig) is used to render the list of all of the available brands in the store. This template shows the list of the alphabet characters, which represent the first characters of each available brand. Then comes the list of the brands' logos for the chosen letter. The developer has complete control over the appearance of this page.

``` shell title = "🌐 Page URL: http://www.store-domain.com/brands"
└── src 
  ├── views
    ├── pages
    |   ├── brands
    |   |   ├── index.twig
    |   ...
    ...
```

### Example
<!--
focus: false
-->
![Single blog](https://cdn.salla.network/docs/twilight/4/brand-listing-01.png)

### Variables


<DataSchema id="1383858" />


### Components
The category page includes the [Breadcrumbs](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component. Breadcrumbs are a set of links that indicate the current page and its "ancestors" leading back to the site's homepage.

```php
{% component 'header.breadcrumbs' %}
```

### Hooks
The [`brand listing page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/index.twig) calls for the following [hooks](https://docs.salla.dev/doc-422552) in order to inject extra information:

```php
{% hook 'brands:index.items.start' %}
{% hook 'brands:index.items.end' %}
```
### Usage
This page receives the object `brands` which is a collection grouped by character, for example:

```json
{a:[{'name':'Apple',...}, b:[{'name':'Beek',...},...]}
```

Each character is for a group of brands that start with that character. Using `nested _for-loop` statements, the developer can retrive the list of the characters, and for each character, the internal loop can retriv the list of the brands.
For example, brands with the letter "a", would display the brands which names start with the letter "a" such as `Apple,Armani, etc..`.<br>

```php lineNumbers=true
{% if brands|length %}
    {% for char,brandGroup in brands %}
        {{ char }}
        {% for brand in brandGroup %}
            {{ brand.name }}
        {% endfor %}
    {% endfor %}
{% else %}
{% endif %}
```

The object `page` here is used to show the current page deatiles, for example: the page title:

```php
{{ page.title }}
```

---

## theme-architecture-pages-brand-pages/Single-Brand-Page-Template-Twilight-Documentation-Salla-Docs

# Single brand

This [`single brand page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/brands/single.twig) is to display the details of a single brand within the store's list of brands. These details can be a short blurb about that brand and a marketing banner for it. It also shows the list of that brand's products as well. The goal here is to group the products of that brand along with information about them on one page for the customer's reference.


``` shell title = "🌐 Page URL: http://www.store-domain.com/brand/c757667"
└── src 
  ├── views
    ├── pages
    |   ├── brands
    |   |   ├── single.twig
    |   ...
    ...

```

### Example
<!--
focus: false
-->
![Single brand](https://cdn.salla.network/docs/twilight/4/brand-single-01.png)



### Variables


<DataSchema id="1383881" />


### Components
The category page includes the [Breadcrumbs](https://docs.salla.dev/doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component. Breadcrumbs are a set of links that indicate the current page and its "ancestors" leading back to the site's homepage.

```php
{% component 'header.breadcrumbs' %}
```

### JS Web Components
Single Brand page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Products List [`<salla-products-list>`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
Several hooks can be automatically injected into the Brand page in order to display information about that particular Brand.
For example, the brand details can be displayed before and after the brand information:

```php
{% hook 'brands:single.details.start' %}
{% hook 'brands:single.details.end' %}
```

Similarly, the details of the brand's products can be displayed before and after, as shown below:

```php
{% hook 'brands:single.items.start' %}
{% hook 'brands:single.items.end' %}
```

### Usage
This page shows brand information along with its products. The object `brands` contains all of these information. For example, `brand.name`, `brand.description`, and brand `brand.banner`.

Show brand detail, banner in case of any
```php lineNumbers=true
{% if brand.banner %}
    <img src="{{ brand.banner }}" alt="{{ brand.name }}"/>
{% endif %}
{{ brand.name }}
{{ brand.description|raw }}
```

In addition, this page template receives the object `products` which represents the list of the brand's products using *for-loop*. Note that the `salla-infinite-scroll` is the Salla component that is used to paginate the long list of products.

```php lineNumbers=true
{% if products|length %}
    <salla-infinite-scroll next-page="{{ products.next_page }}" next-page.autoload>
        {% for product in products %}
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
    </salla-infinite-scroll>
{% endif %}
```

Beside that, the object `page` can be used to display informtion about that page.

```php
{{ page.title|raw }}
```

---

