# Theme Architecture Pages Product Pages

## Table of Contents

- [theme-architecture-pages-product-pages/Themes-Product-Listing-Page-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-product-pages-themes-product-listing-page-twilight-documentation-salla-docs)
- [theme-architecture-pages-product-pages/Themes-Single-Product-Page-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-product-pages-themes-single-product-page-twilight-documentation-salla-docs)

---

## theme-architecture-pages-product-pages/Themes-Product-Listing-Page-Twilight-Documentation-Salla-Docs

# Products listing

Twilight Theme includes a [`products listing template page`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/index.twig). This page template is based on a category or search query. It is created to produce better products listings based on a specific need or purpose set by the developer. 
This page is a key feature for a better customer experience as it funnels site visitors to product detail pages and closer to conversion.

Following is the page location and url:

``` shell title = "🌐 Page URL: http://www.store-domain.com/products-listing-slug/c1825487583"
└── src
    ├── views
      ├── pages
      |  ├── product
      |    ...
      |    ├── index.twig
      |    ...
    ...
```

In the Twilight, this page template shows a list of products based on pre-defined filters, which are:

- **Category:** shows products that are from the same category, for example, women's tops, men's shoes, and sports wear. 

- **Offers:** displays products that have special offers, such as buy two for the price of one or get 60% off the second item.

- **Tags:** used to display the products that have been tagged with the same "tag". Product tags are keywords for product identification, so that they are easier to find. For example, for apparel products, users may create tags for T-shirt products, such as "t-shirt", "cotton", "polo", etc.

-  **Search results:** displays the search results based on the user's manual search using special keywords.

### Example

<!-- focus: false -->
![Products listing](https://cdn.salla.network/docs/twilight/4/pages-product-listing-01.png)

### Variables


<DataSchema id="1383872" />

### Components

The product listing page includes the [breadcrumbs component](https://docs.salla.dev/doc-422601?nav=01HNFTE06J4QC24T0D5BPRYKMD). Breadcrumbs are a set of links that indicate the current page and its "ancestors" leading back to the site's homepage.

```php
{% component 'header.breadcrumbs' %}
```

In addition, this page template includes the [testimonials](https://docs.salla.dev/doc-422584?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component. This component helps to display the testimonials the developer chooses to display.

```php
{% component 'home.testimonials' %}
```
### JS Web Components
Product Listing page may include the following [JS Web Components](https://docs.salla.dev/doc-422580?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.

- Products List [`<salla-products-list>`](https://docs.salla.dev/doc-422719?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The `products listing template page` calls for the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject extra information.

```php
{% hook 'product:index.items.start' %}
{% hook 'product:index.items.end' %}
```

### Usage
This page template receives an object `products` that contains all of the products that need to be listed on this page. As we explained before, these products have a common category, offers, tags, or search result. 

Initially, the developer can display the name of the page using the variable `page.title`. This is to show the type of listing being used, filteration, on this page.

```php
{{ page.title|raw }}
```

Next, the products listing sorting method should be set. The array `sort_list` contains the sorting methods for the product listing, which can be displayed with a `for-loop` statement. Each element inside that array consists of an object that contains a pair of values, which indicates the sorting method. 

The available sorting methods are: `ourSuggest`, `bestSell`, `topRated`, `priceFromTopToLow`, `priceFromLowToTop`. The developer may retrieve the value of `sort.is_selected` in order to check if a specific sorting method has already been selected.

```php
{% if sort_list|length %}
  {% for sort in sort_list %}
    <option value="{{ sort.value }}" {{ sort.is_selected?'selected':'' }}>{{ sort.label }}</option>
  {% endfor %}
{% endif %}
```

At this point, the list of the given products can be displayed. The `products` object within a `for-loop` statement can be used to display a list of the received products. The developer may use any style for display purposes.

 Many details for the product can be displayed as per the developer's need, for example: `product.name`, `product.image.url`, `product.url`, `product.price`, and many more.

The developer may use the value `trans('pages.categories.no_products')` in the case of no products in the listing. This is to make sure that the page is showing the correct content for the end user.

```php lineNumbers
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
{% else %}
    {{ trans('pages.categories.no_products') }}
{% endif %}
```

Finally, if the testimonials are enabled by the store settings, the developer may display them as below:

```php lineNumbers
{% if store.settings.category.testimonial_enabled %}
  {% component 'home.testimonials' %} 
{% endif %}
```

:::tip[Educational Clip]
<Video src="https://youtu.be/OE2KaZSly9s?si=VkQ6jZz9Nk5r5ZC2"></Video>
:::

---

## theme-architecture-pages-product-pages/Themes-Single-Product-Page-Twilight-Documentation-Salla-Docs

# Single product

The [`single product page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/single.twig) is designated to view product details such as the title, description, type, color, size, price, and quantity. Each product will have its own details displayed on this page.

The main structure of this product page template is showing the product primary components, and then showing the related essential components, options components, and related offers components.

Following is the page location and url:

``` shell title = "🌐 Page URL: http://www.store-domain.com/product-slug-name/c1825487583"
└── src
    ├── views
      ├── pages
      |  ├── product
      |    ...
      |    ├── single.twig
      |    ...
      ...
```

### Example
<!-- focus: false -->
![Single product](https://cdn.salla.network/docs/twilight/4/pages-single-product-01.png)


### Variables


<DataSchema id="1383883" />


### Components
This page starts by displaying the `breadcrumbs` component. The `{% component breadcrumbs %}` line returns the current navigation for the user:

```php
{% component 'header.breadcrumbs'%}
```

In addition, the developer may show the `product.offer` component:

```php
{% component 'product.offer' %}
```

Also, the customers' comments on a specific product may be displayed using the component `comments`:

```php
{% component 'comments' %}
```

Similary, this page may show similar products to the current product using the component `product.similar-products`. This will make it more and more reachable for the customers:

```php
{% component 'product.similar-products' %}
```

### JS Web Components
Single Product page may include the following [JS Web Components](https://docs.salla.dev/doc-422556?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores.
- Add Product [`<salla-add-product>`](https://docs.salla.dev/doc-422692?nav=01HNFTE06J4QC24T0D5BPRYKMD)

- Button [`<salla-button>`](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD)

- Gifting [`<salla-gifting>`](https://docs.salla.dev/doc-422705?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Installment [`<salla-installment>`](https://docs.salla.dev/doc-422707?nav=01HNFTE06J4QC24T0D5BPRYKMD)

- Products Slider [`<salla-products-slider>`](https://docs.salla.dev/doc-422722?nav=01HNFTE06J4QC24T0D5BPRYKMD)

- Quick Order [`<salla-quick-order>`](https://docs.salla.dev/doc-422726?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Quantity Input [`<salla-quantity-input>`](https://docs.salla.dev/doc-422724?nav=01HNFTE06J4QC24T0D5BPRYKMD)

- Rating Stars [`<salla-rating-stars>`](https://docs.salla.dev/doc-422727?nav=01HNFTE06J4QC24T0D5BPRYKMD)

- Slider [`<salla-slider>`](https://docs.salla.dev/doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD)
 - Social Share [`<salla-social-share>`](https://docs.salla.dev/doc-422736?nav=01HNFTE06J4QC24T0D5BPRYKMD)



### Hooks
In the [single product](https://docs.salla.dev/doc-422561?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) template page, the developer displays the product details such as the title, description, color, size, price, and quantity. Each product will have its own details displayed on this page. 
In some cases, the product may include "extra" services related, for example, to the payment services. Using [hook](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) `{% hook 'product:single.description.start' %}` in the [single product](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/product/single.twig) code shows these extra services, as we see in the following example:


```php
{% hook 'product:single.description.start' %}
{% hook 'product:single.description.end' %}
```

In addition, the `single product page template` may call the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject extra information:

```php
{% hook 'product:single.description' %}
{% hook 'product:single.form.start' %}
{% hook 'product:single.form.end' %}
```

### Usage
This page template starts with extracting main variables from the `product` object, such as product title and id. Using this. object, the developer has the ability to perform many tasks related to the product page, as we will see in the following parts.


#### Product description
Initially, several variables, such as `product.promotion_title`, `product.brand`, `product.name`, `product.rating`, `product.subtitle`, `product.description`, and `product.tags`, can be used by the developer to display multiple pieces of information about a single product.

```php lineNumbers
{% if(product.promotion_title) %}
    {{ product.promotion_title }}
{% endif %}

{% if product.brand %}
    <img title="{{ product.brand.name }}" src="{{ product.brand.logo }}" alt="{{ product.brand.name }}"/>
{% endif %}

<h1>{{ product.name }}</h1>

{% if product.rating %}
    {{ product.rating }}
{% endif %}

{% if product.subtitle %}
    <h3>{{ product.subtitle }}</h3>
{% endif %}

{% if product.has_read_more %}
    <p>{{ product.description|raw }}</p>
    {# Read More Button #}
    <a> {{ trans('pages.products.read_more') }} </a>
{% else %}
    {{ product.description|raw }}
{% endif %}

{% if product.tags|length %}
    {% for tag in product.tags %}
        <a href="{{ tag.url }}"> {{ tag.name }} </a>
    {% endfor %}
{% endif %}
```

#### Product images
The variable `product.images` contains the product's several images, which can be displayed using a for-loop statement.

```php lineNumbers
{% for image in product.images %}
  <img src="{{ image.url }}" alt="{{ image.alt }}" />
{% endfor %}
```

#### Add product to the cart form (Options and Quantity)
The important part of this page is the *form* for adding the product to the cart. This `<form>` basically consists of two main sections. The first section is to show the product's options, and the product price and quantity.

The `product.options` uses a `for-loop` statement in order to show each available option for the product. Both hooks `{% hook 'product:single.form.start' %}` and `{% hook 'product:single.form.end' %}` are enclosing this part.

The second section is to show the product price and availability. If the product is on sale, the variable `product.is_on_sale` returns the boolean value *true*. The developer can use the `if` statement to check that and then display `product.price`, `product.sale_price`, `product.regular_price`, or any other value as needed.

The variables `product.sold_quantity` and `product.can_show_remained_quantity` reflect the available quantity of the product. The developer may display the product's price along with its available quantity after checking if `product.is_available` is *true*. It is worth mentioning here that the variable `product.notify_availability` can be checked in order to give the user the option of being notified about receiving a new quantity of that product.

```php lineNumbers
<form enctype="multipart/form-data" method="post"
      onchange="salla.product.getPrice(new FormData(event.currentTarget))"
      onsubmit="return salla.form.submit('cart.addItem');">

    <input name="id" type="hidden" value="{{ product.id }}"/>

    {% hook 'product:single.form.start' %}

    {% if product.options|length %}
        {% for option_index, option in product.options %}
            {% if option.type in ["splitter"] %}
                {{ option.element|raw }}
            {% else %}
                {% if option.type != "donation" %}
                    <label for="options[{{ option.id }}]">
                        <strong>
                            {{ option.name }}
                            {% if option.required %}<span>*</span>{% endif %}
                        </strong>
                        <small>{{ option.placeholder }}</small>
                    </label>
                {% endif %}
                {{ option.element(product.id)|raw }}
            {% endif %}
        {% endfor %}
    {% endif %}

    {% if product.can_add_note or product.can_upload_file %}

        <strong>{{ trans('pages.products.attachments') }}</strong>
        {% if product.can_add_note %}
            <button type="button" data-show="note_{{ product.id }}">
                {{ trans('pages.products.add_note') }}
            </button>
        {% endif %}

        {% if product.can_upload_file %}
            <button type="button" data-show="file_{{ product.id }}"> {{ trans('pages.products.add_file') }} </button>
        {% endif %}

        {% if product.can_add_note %}
            <textarea cols="30" name="notes" rows="10"
                      placeholder="{{ trans('pages.products.notes_placeholder') }}">
    {{ product.notes }}</textarea>
        {% endif %}

        {% if product.can_upload_file %}
            <input name="{{ is_cart?'image_file':'file' }}" type="file"
                   data-url="{{ link('cart/image') }}" data-instant-upload=""
                   data-files="{{ product.attachments }}" data-item-id="{{ product.id }}"
                   data-max-file-size="3MB"/>
        {% endif %}
    {% endif %}
    {% hook 'product:single.form.end' %}

    {# Quantity #}
    {% if product.is_hidden_quantity %}
        <input name="quantity" type="hidden" value="1"/>
    {% else %}
        {{ trans('pages.products.quantity') }}
        <salla-quantity-input max="{{ product.max_quantity }}" value="1" name="quantity">
        </salla-quantity-input>
    {% endif %}

    {# Price #}
    {{ trans('pages.products.price') }}

    {% if product.is_on_sale %}
        <h4>{{ product.sale_price|money }}</h4>
        {{ product.regular_price|money }}
    {% else %}
        <h4>{{ product.price|money }}</h4>
    {% endif %}

    
    <salla-add-product-button product-id="{{ product.id }}"
                              product-status="{{ product.status }}"
                              product-type="{{ product.type }}">
    </salla-add-product-button>
</form>
```

#### Product Meta Data

Merchants are able to introduce custom fields for the product, and you can render such fields by using the [`<salla-metadata>`](https://docs.salla.dev/doc-464599?nav=01HNFTE06J4QC24T0D5BPRYKMD) JS Web Component in the following manner:

```html
{% if product.has_metadata %} <salla-metadata></salla-metadata> {% endif %}
```

:::tip[Educational Clip]
<Video src="https://youtu.be/Nx6VgNBki2I?si=Hg_98HNsMTfb4e3t"></Video>
:::

---

