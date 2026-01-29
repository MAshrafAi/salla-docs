# Theme Architecture Components Home Components

## Table of Contents

- [theme-architecture-components-home-components/Brands-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-brands-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Enhanced-Slider-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-enhanced-slider-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Enhanced-Square-Banners-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-enhanced-square-banners-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Featured-Products-Style-1-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-featured-products-style-1-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Featured-Products-Style-2-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-featured-products-style-2-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Featured-Products-Style-3-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-featured-products-style-3-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Fixed-Banner-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-fixed-banner-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Fixed-Products-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-fixed-products-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Latest-Products-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-latest-products-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Main-Links-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-main-links-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Parallax-Background-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-parallax-background-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Photos-Slider-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-photos-slider-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Products-Slider-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-products-slider-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Slider-Products-with-Headers-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-slider-products-with-headers-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Square-Photos-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-square-photos-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Store-Features-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-store-features-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Testimonials-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-testimonials-component-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/Vertical-Menu-with-Slider-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-vertical-menu-with-slider-twilight-documentation-salla-docs)
- [theme-architecture-components-home-components/YouTube-Component-Twilight-Documentation-Salla-Docs](#theme-architecture-components-home-components-youtube-component-twilight-documentation-salla-docs)

---

## theme-architecture-components-home-components/Brands-Component-Twilight-Documentation-Salla-Docs

# Brands

The store brands' logos are displayed using this component. Developers may use any design to style it because this is a significant section to draw the customers' attention.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── brands.twig
          ...
```



### Example

<!--
focus: false
-->
![Brands Components](https://cdn.salla.network/docs/twilight/4/pages-components-home-custom-brands-01.png)

### Settings

This component is a [custom component](doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). Its configuration is described in the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) as follows:

```json lineNumbers
{
  "version": ...,
  "theme_name": ...,
  "repo_url": ...,
  "support_url": ...,
  ...
  "components": [
    {
      "name": "brands",
      "title": "Brands",
      "icon": "sicon-award-ribbon",
      "path": "home.brands",
      "fields": [
        {
          "id": "brands",
          "type": "items",
          "label": "Brand",
          "format": "dropdown-list",
          "multichoice": true,
          "required": true,
          "source": "Brands"
        }
      ]
    }
  ]
  
}

```
#### Theme Preview 

The components can be managed using the theme preview in the [Theme menu item](https://salla.partners/themes) of Salla Partners Portal. The developer can edit the component and enable it in the theme preview dashboard.
![Theme Preview Dashboard](https://i.imgur.com/lC1NlTE.png)

### Variables
The variables of this component are fetched from the twilight.json file as per the merchant settings. They are located in the components section's fields.


<DataSchema id="1383686" />
  

### Usage
This component lists the brands related to the merchant's store using a _loop_. Based on that, a brand _url_ and _logo_ will be displayed as per the developer style.


```php lineNumbers
<h2>{{ trans('blocks.home.browse_brands') }}</h2>
<a href="{{ link('brands') }}"> {{ trans('blocks.home.display_all') }} </a>
{% for brand in component.brands %}
    <a href="{{ brand.url }}">
        <img src="{{ brand.logo }}" alt=""/>
    </a>
{% endfor %}
```

---

## theme-architecture-components-home-components/Enhanced-Slider-Component-Twilight-Documentation-Salla-Docs

# Enhanced Slider

This component is similar to the [Photos slider](https://docs.salla.dev/doc-422586), which displays various images. However, it gives an extra option to add texts for the inner element of the pictures.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── enhanced-slider.twig
          ...
```


### Example
<!--
focus: false
-->
![Enhanced Slider](https://cdn.salla.network/docs/twilight/4/pages-components-home-custom-enhanced-links-01.png)


### Settings

This component is a [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). Its configuration is described in the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) as follows:

```json lineNumbers
{
  "version": ...,
  "theme_name": ...,
  "repo_url": ...,
  "support_url": ...,
  ...
  "components": [
    {
      "name": "enhanced-slider",
      "title": "Slider (Emhanced)",
      "icon": "sicon-image-carousel",
      "path": "home.enhanced-slider",
      "fields": [
        {
          "id": "is_wide",
          "type": "boolean",
          "text": "Wide Screen",
          "format": "switch",
          "selected": true
        },
        {
          "id": "slides",
          "type": "collection",
          "format": "collection",
          "required": true,
          "minLength": 1,
          "maxLength": 10,
          "label": "Images List",
          "fields": [
            {
              "id": "image",
              "type": "string",
              "format": "image",
              "required": true
            },
            {
              "id": "title",
              "type": "string",
              "label": "Header Title (optional)"
            },
            {
              "id": "description",
              "type": "string",
              "format": "textarea",
              "label": "Description (optional)"
            }
          ]
        }
      ]
    }
  ]
}
```
#### Theme Preview 

The components can be managed using the theme preview in the [Theme menu item](https://salla.partners/themes) of Salla Partners Portal. The developer can edit the component and enable it in the theme preview dashboard.
![Theme Preview Dashboard](https://i.imgur.com/BAtpVWB.png)

### Variables

The variables of this component are fetched from the `theme.json` file as per the merchant settings. They are located in the components section's fields.


<DataSchema id="1383687" />

### Usage
This component uses a slider to display the images, where the developer can use any slider library.

```php lineNumbers
{% for slide in component.slides %}
    <img src="{{ slide.image }}">
    <h3>{{ slide.title }}</h3>
    <p>{{ slide.description }}</p>
{% endfor %}
```

---

## theme-architecture-components-home-components/Enhanced-Square-Banners-Twilight-Documentation-Salla-Docs

# Enhanced Square Banners

The enhanced square banner component is similar to the [Square Photos](https://docs.salla.dev/doc-422588?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component, however it gives an extra option to add texts for the inner element of the smaller images.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── enhanced-square-banners.twig
          ...
```

### Example
<!--
focus: false
-->
![Enhanced Squared Banner](https://cdn.salla.network/docs/twilight/4/pages-components-home-custom-enhanced--banners-01.png)

### Settings

This component is a [custom component](doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). Its configuration is described in the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) as follows:

```json lineNumbers
{
  "version": ...,
  "theme_name": ...,
  "repo_url": ...,
  "support_url": ...,
  ...
  "components": [
    {
      "name": "enhanced-square-banners",
      "title": "Square images (enhanced)",
      "icon": "sicon-image",
      "path": "home.enhanced-square-images",
      "fields": [
        {
          "id": "banners",
          "type": "collection",
          "format": "collection",
          "required": true,
          "minLength": 1,
          "maxLength": 5,
          "label": "Images List",
          "fields": [
            {
              "id": "image",
              "type": "string",
              "format": "image",
              "required": true
            },
            {
              "id": "url",
              "type": "string",
              "format": "url",
              "label": "Link",
              "placeholder": "Enter the link here...",
              "inputType": "url",
              "required": true
            },
            {
              "id": "title",
              "type": "string",
              "label": "Main Header (optional)"
            },
            {
              "id": "description",
              "type": "string",
              "format": "textarea",
              "label": "Description text (optional)"
            }
          ]
        }
      ]
    }
  ]
}
```
#### Theme Preview 

The components can be managed using the theme preview in the [Theme menu item](https://salla.partners/themes) of Salla Partners Portal. The developer can edit the component and enable it in the theme preview dashboard.
![Theme Preview Dashboard](https://i.imgur.com/8gtLAxo.png)


### Variables
The variables of this component are fetched from the twilight.json file as per the merchant settings. They are located in the components section's fields.


<DataSchema id="1383691" />



### Usage
In this component, we use a _loop_ statement to go through banners and display both `banner.image` and `banner.url`.

```php lineNumbers
{% for banner in component.banners %}
<div style="background-image: url('{{banner.image}}');">
    <a href="{{banner.url}}">
        <h3>{{banner.title}}</h3>
        <p>{{banner.description}}</p>
    </a>
</div>
{% endfor %}
```

---

## theme-architecture-components-home-components/Featured-Products-Style-1-Twilight-Documentation-Salla-Docs

# Featured products - Style 1

Featured products list, which is a **_pre-defined component_**, is a collection created in a specific design to draw customers' attention to see a certain collection of products primarily.
Twilight comes with three pre-styled featured products components, and this is the _style-1_ component.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── featured-products-style1.twig
          ...
```

### Example
<!--
focus: false
-->
![Featured Products Style 1](https://cdn.salla.network/docs/twilight/4/pages-components-home-featured-style1-01.png)

### Variables


<DataSchema id="1383692" />


### Usage

In general, this pre-styled featured products component starts with checking if there is a _main product_ to display in bigger size:

```php lineNumbers
{% if main_product %}
    <div class="product-feature">
        <div>
            <h2>{{ main_product.title }}</h2>
        </div>
        <a href="{{ product.url }}">
            <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
            {% if product.promotion_title %} {{ product.promotion_title }} {% endif %}
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

        <salla-add-product-button product-id="{{ main_product.id }}"
                                  product-status="{{ main_product.status }}"
                                  product-type="{{ main_product.type }}">
        </salla-add-product-button>
    </div>
{% endif %}
```

After that, the component list the rest products as pre a pre-defined style. Developer has the option to edit that style.

```php lineNumbers
{% for section in items %}
    <h2>{{ section.title }}</h2>

    <div class="products-section">
        {% for product in section.products %}
            <div class="product-item">
                <a href="{{ product.url }}">
                    <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
                    {% if product.promotion_title %} {{ product.promotion_title }}
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

                <salla-add-product-button product-id="{{ product.id }}"
                                          product-status="{{ product.status }}"
                                          product-type="{{ product.type }}">
                </salla-add-product-button>
            </div>
        {% endfor %}
    </div>
{% endfor %}
```

---

## theme-architecture-components-home-components/Featured-Products-Style-2-Twilight-Documentation-Salla-Docs

# Featured Products - Style 2

Featured products list is a collection created in a specific design to draw customers' attention to see a certain collection of products primarily. This component is a **_pre-defined component_**
Twilight comes with three pre-styled featured products components, and this is the _style-2_ component. This style is mixd of `tabbed` and `slider` views.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── featured-products-style2.twig
          ...
```


### Example
<!--
focus: false
-->
![Featured Products Style 2](https://cdn.salla.network/docs/twilight/4/pages-components-home-featured-style2-01.png)


### Variables


<DataSchema id="1383693" />

### Usage 

The component list the products as per a pre-defined slider. Developer has the option to use any style, or slider base in the `is_slider` value. 

```php lineNumbers
{% for section in items %}
    <h2>{{ section.title }}</h2>

    <div class="products-section">
        {% for product in section.products %}
            <div class="product-item">
                <a href="{{ product.url }}">
                    <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
                    {% if product.promotion_title %} {{ product.promotion_title }}
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

                <salla-add-product-button product-id="{{ product.id }}"
                                          product-status="{{ product.status }}"
                                          product-type="{{ product.type }}">
                </salla-add-product-button>
            </div>
        {% endfor %}
    </div>
{% endfor %}
```

---

## theme-architecture-components-home-components/Featured-Products-Style-3-Twilight-Documentation-Salla-Docs

# Featured Products - Style 3

Featured products list is a collection, created in a specific design to draw customers' attention to see a certain collection of products primarily. This component is a **_pre-defined component_**
Twilight comes with three pre-styled featured products components, and this is the _style-3_ component.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── featured-products-style3.twig
          ...
```


### Example
<!--
focus: false
-->
![Featured Products Style 3](https://cdn.salla.network/docs/twilight/4/pages-components-home-featured-style3-01.png)

### Variables


<DataSchema id="1383694" />



### Usage
In general, this pre-styled featured products component with a _main product_ to display in bigger size, and then a column of products in smaller size:

```php lineNumbers
{% for section in items %}

    <h2>{{ section.title }}</h2>

    {% if section.featured_product %}
        <div id="featured-product-{{ section.featured_product.id }}">
            <a href="{{ section.featured_product.url }}">
                <img src="{{ 'images/s-empty.png' | asset }}"
                     data-src="{{ section.featured_product.image.url }}"
                     alt="{{ section.featured_product.image.alt }}"/>
            </a>
            {% if section.featured_product.promotion_title %}
                {{ section.featured_product.promotion_title }}
            {% endif %}
            <a href="{{ section.featured_product.url }}">{{ section.featured_product.name }}  </a>
            <h3>
                <a href="{{ section.featured_product.url }}">{{ section.featured_product.name }}</a>
            </h3>
            {% if section.featured_product.is_on_sale %}
                <div>
                    <h4>{{ section.featured_product.sale_price|money }}</h4>
                    <span>{{ section.featured_product.regular_price|money }}</span>
                </div>
            {% else %}
                <h4>{{ section.featured_product.price|money }}</h4>
            {% endif %}

            {% if section.featured_product.rating %}
                <div>{{ section.featured_product.rating|number }}</div>
            {% endif %}

            <salla-add-product-button product-id="{{ section.featured_product.id }}"
                    product-status="{{ section.featured_product.status }}"
                    product-type="{{ section.featured_product.type }}">
            </salla-add-product-button>
        </div>
    {% endif %}


    {% for product in section.products %}
        <div class="product-item">
            <a href="{{ product.url }}">
                <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
                {% if product.promotion_title %} {{ product.promotion_title }}
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
        </div>
    {% endfor %}
{% endfor %}
```

---

## theme-architecture-components-home-components/Fixed-Banner-Component-Twilight-Documentation-Salla-Docs

# Fixed banner

A fixed banner is a **_pre-defined component_** which is in charge of displaying a banner that is fixated on the Home Page.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── fixed-banner.twig
          ...
```


### Example
<!--
focus: false
-->
![Fixed Banner](https://cdn.salla.network/docs/twilight/4/pages-components-home-fixed-banner-01.png)

### Variables


<DataSchema id="1383695" />

### Usage
This fixed banner component receives the values of `image.url` and `image.alt` and displays it a background for this fixed area.

```php lineNumbers
<a href="{{ url }}" aria-label="Banner {{ image.alt }}">
    <img src="{{'images/s-empty.png' | asset}}" data-src="{{ image.url }}" alt="{{ image.alt }}" />
</a>
```
<br>

:::tip[Educational Clip]

<Video src="https://youtu.be/onCsXbZi_34?si=hTnZvYwNg_ZhHZHP"></Video>


:::

---

## theme-architecture-components-home-components/Fixed-Products-Component-Twilight-Documentation-Salla-Docs

# Fixed products

Use this **_pre-defined component_** to display a group of products that has no scrolling effect. Their location is fixed.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── fixed-products.twig
          ...
```


### Example
<!--
focus: false
-->
![Fixed Products](https://cdn.salla.network/docs/twilight/4/pages-components-home-fixed-products-01.png?updated)

### Variables


<DataSchema id="1383696" />


### Usage 
This component takes a list of the `products` that should be displayed, and then use **for-loop** statement to show them out. Developer has the option of styling them the way he may need.

```php lineNumbers
<div class="head">
    {% if title %}
        <h2>{{ title }}</h2>
    {% endif %}

    {% if display_all_url %}
        <a href="{{ display_all_url }}">{{ trans('blocks.home.display_all') }}</a>
    {% endif %}
</div>


{% for product in products %}
    <div class="item">
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
    </div>
{% endfor %}
```

---

## theme-architecture-components-home-components/Latest-Products-Component-Twilight-Documentation-Salla-Docs

# Latest Products

This **_pre-defined component_** is set to display the latest products added to the store automatically. It has a fixed, not scrolled, view. It comes with a pre-defined style, which can easily be modified by the developer.

**Following is the location of this component.**

```shell
└── src
  ├── views 
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── latest-products.twig
          ...
```


### Example

<!--
focus: false
-->
![Home Latest Products](https://cdn.salla.network/docs/twilight/4/pages-components-home-latest-products-01.png)

### Variables

<DataSchema id="1383697" />

### Usage
This component receives a list of new products, if any. Then it loops through them using *for-loop* in order to display paginated using `salla-infinite-scroll`:

```php lineNumbers
<h2>{{ trans('blocks.home.latest_products') }}</h2>
{% if products|length %}
    <salla-infinite-scroll next-page="{{ products.next_page }}" next-page.autoload>
        {% for product in products %}
            <a href="{{ product.url }}">
                <img src="{{ product.image.url }}" alt="{{ product.image.alt }}" />
                {% if product.promotion_title %}
                    {{ product.promotion_title }}
                {% endif %}
            </a>
            <h3>
                <a href="{{ product.url }}">{{ product.name }}</a>
            </h3>

            {% if product.on_sale %}
                <h4>{{ product.sale_price|money }}</h4>
                {{ product.regular_price|money }}
            {% else %}
                <h4>{{ product.price|money }}</h4>
            {% endif %}

            <salla-add-product-button product-id="{{ product.id }}"
                                      product-status="{{ product.status }}"
                                      product-type="{{ product.type }}">
            </salla-add-product-button>
        {% endfor %}
    </salla-infinite-scroll>
{% endif %}
```

---

## theme-architecture-components-home-components/Main-Links-Component-Twilight-Documentation-Salla-Docs

# Main Links

This component is part of the main view for the home page landing part. It helps to portray the store main categories links.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── main-links.twig
          ...
```


### Example

<!--
focus: false
-->
![Main Links](https://cdn.salla.network/docs/twilight/4/pages-components-home-custom-main-links-01.png)

### Settings

This component is a [custom component](doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). Its configuration is described in the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) as follows:

```json lineNumbers
{
  "version": ...,
  "theme_name": ...,
  "repo_url": ...,
  "support_url": ...,
  ...
  "components": [
    {
      "name": "main-links",
      "title": "Main Links",
      "icon": "sicon-layout-grid-rearrange",
      "path": "home.main-links",
      "fields": [
        {
          "id": "title",
          "type": "string",
          "label": "Title",
          "placeholder": "Enter the title here",
          "required": false
        },
        {
          "id": "links",
          "type": "collection",
          "format": "collection",
          "required": true,
          "minLength": 3,
          "maxLength": 6,
          "label":"Links and Icons",
          "fields": [
            {
              "id": "icon",
              "type": "string",
              "format": "string",
              "label": "Icon",
              "placeholder": "Tplacehoder text",
              "required": true
            },
            {
              "id": "title",
              "type": "string",
              "placeholder": "Enter link title here...",
              "label": "Link title",
              "required": true
            },
            {
              "id": "url",
              "type": "string",
              "format": "url",
              "label": "Link url",
              "placeholder": "Enter link url here...",
              "inputType": "url",
              "required": true
            }
          ]
        },
        {
          "type": "boolean",
          "label": "Merge with top component",
          "id": "merge_with_top_component",
          "format": "switch",
          "selected": true
        }
      ]
    },
  ]
}
```
#### Theme Preview 

The components can be managed using the theme preview in the [Theme menu item](https://salla.partners/themes) of Salla Partners Portal. The developer can edit the component and enable it in the theme preview dashboard.
![Theme Preview Dashboard](https://i.imgur.com/wqeT7pS.png)

### Variables
The variables of this component are fetched from the twilight.json file as per the merchant settings. They are located in the components section's fields.


<DataSchema id="1383698" />



### Usage
The main links are displayed using a pre-defined style, which can be edited by the developer. 
This component uses the `link url` and `link icon` for example, and displays them using a **for-loop**.


```php lineNumbers
{% for link in component.links %}
  <a href="{{ link.url }}"></a>
      <i class="{{ link.icon }}"></i>
      <h4>{{ link.title }}</h4>
  </a>
{% endfor %}
```

---

## theme-architecture-components-home-components/Parallax-Background-Component-Twilight-Documentation-Salla-Docs

# Parallax background

Parallax scrolling background is **_pre-defined component_** that functions as a graphics design method in which the background images move past the camera more slowly than foreground images, giving the impression of depth in a 2D scene from a distance.
This component can be used for a better effect to display the store items or related images.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components
   |  ├── home
   |  |   ...
   |  |  ├── parallax-background.twig
          ...    
```



### Example
<!--
focus: false
-->
![Parallax Background](https://cdn.salla.network/docs/twilight/4/pages-components-home-parallax-background-01.png)

### Variables


<DataSchema id="1383699" />


### Usage
This component receives `url` variable with `is_opacity`, and set them both as a background for a container `<div>`. That container is set to reflect the `parallax`.
In case of receiving the values of `title` and `link_text`, they will be displayed inside the parallax container.

```php lineNumbers
<div style="background-image: url('{{ image.url }}');">
    {% if title %}
        <h3>{{ title }}</h3>
    {% endif %}

    {% if url and link_text %}
        <a href="{{ url }}">{{ link_text }}</a>
    {% endif %}
</div>
```

---

## theme-architecture-components-home-components/Photos-Slider-Component-Twilight-Documentation-Salla-Docs

# Photos slider

Photos slider (also known as carousels or slideshows) are a simple way to display a variety of images. It's **_pre-defined component_**. The idea of large, magnificent, dazzling picture shows might be very appealing. Attractive photos can entice new visitors to your site by attracting their attention right away.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components
   |  ├── home
   |  |   ...
   |  |  ├── photos-slider.twig
          ...    
```



### Example
<!--
focus: false
-->
![Photo Slider](https://cdn.salla.network/docs/twilight/4/pages-components-home-photo-slider-01.png)

### Variables


<DataSchema id="1383700" />

### Usage
Using a **for-loop**, The slider's images within `items` will be displayed using `item.image.url`.


```php lineNumbers
<section id="photos-{{ position }}">
    <div data-id="photos-{{ position }}">
        <div class="swiper-wrapper">
            {% for item in items %}
                <div class="swiper-slide" data-src="{{ item.image.url }}"></div>
            {% endfor %}
        </div>
        <div class="swiper-pagination"></div>
        <button aria-label="Previous Slide" class="slider-prev">
            Previous
        </button>
        <button aria-label="Next Slide" class="slider-next">
            Next
        </button>
    </div>
</section>
```

---

## theme-architecture-components-home-components/Products-Slider-Component-Twilight-Documentation-Salla-Docs

# Products slider

This **_pre-defined component_** slider helps navigate between a list of products in the form of a scrolling list.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── products-slider.twig
          ...
```


### Example

<!--
focus: false
-->
![Product Slider](https://cdn.salla.network/docs/twilight/4/pages-components-home-products-slider-01.png)

### Variables


<DataSchema id="1383701" />


### Usage 
This component takes a list of the `products` that should be displayed, and then use **for-loop** statement to show them out.The method for displaying the products is `swiper-slide`. Developer has the option to use any other slider.

```php lineNumbers

<section id="best-offers-{{ position }}-slider">
    <div>
        {% if display_all_url %}
            <a href="{{ display_all_url }}">{{ trans('blocks.home.display_all') }}</a>
        {% endif %}
        <div>
            <button aria-label="Previous Slide"></button>
            <button aria-label="Next Slide"></button>
        </div>
    </div>
    <div data-id="{{ type }}-slider">
        {% for product in products %}
            <a href="{{ product.url }}">
                <img src="{{ product.image.url }}" alt="{{ product.image.alt }}"/>
                {% if product.promotion_title %} {{ product.promotion_title }} {% endif %}
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
</section>
```

---

## theme-architecture-components-home-components/Slider-Products-with-Headers-Twilight-Documentation-Salla-Docs

# Slider Products with Headers

This component comes with many attractive elements to display products for the customers. It has Headings to describe the sections and a swiper slider to list as much products as possible.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── slider-products-with-header.twig
          ...
```



### Example
<!--
focus: false
-->
![Slider Products](https://cdn.salla.network/docs/twilight/4/pages-components-home-custom-slider-headers-01.png)


### Settings

This component is a [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). Its configuration is described in the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) as follows:

```json lineNumbers
{
  "version": ...,
  "theme_name": ...,
  "repo_url": ...,
  "support_url": ...,
  ...
  "components": [
    {
      "name": "slider-products-with-header",
      "title": "Slider products with header",
      "icon": "sicon-list-play",
      "path": "home.slider-products-with-header",
      "fields": [
        {
          "id": "background",
          "type": "string",
          "format": "image"
        },
        {
          "id": "title",
          "type": "string",
          "label": "Header title (optional)"
        },
        {
          "id": "description",
          "type": "string",
          "format": "textarea",
          "label": "Header sub title (optional)"
        },
        {
          "id": "products",
          "type": "items",
          "icon": "sicon-list",
          "label": "Prducts",
          "format": "dropdown-list",
          "required": true,
          "source": "Products",
          "multichoice": true,
          "maxLength": 8
        }
      ]
    }
  ]
  
}

```
#### Theme Preview 

The components can be managed using the theme preview in the [Theme menu item](https://salla.partners/themes) of Salla Partners Portal. The developer can edit the component and enable it in the theme preview dashboard.
![Theme Preview Dashboard](https://i.imgur.com/9L0TzeF.png)

### Variables

The variables of this component are fetched from the `twilight.json` file as per the merchant settings. They are located in the `components` section's fields. 


<DataSchema id="1383702" />


### Usage
This component starts with showing the headers:
```php lineNumbers
<div style="background-image: url('{{component.background}}');">
    <h3>{{component.title}}</h3>
    <p>{{component.description}}</p>
</div>
```

Then it loops through a list of products to display them within a _slider_:

```php lineNumbers
{% for product in component.products %}
    <div class="product-item">
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
            <h4>{{ product.sale_price|money }}</h4>
            {{ product.regular_price|money }}
        {% else %}
            <h4>{{ product.price|money }}</h4>
        {% endif %}

        <salla-add-product-button product-id="{{ product.id }}"
                                  product-status="{{ product.status }}"
                                  product-type="{{ product.type }}">
        </salla-add-product-button>
    </div>
{% endfor %}
```

---

## theme-architecture-components-home-components/Square-Photos-Component-Twilight-Documentation-Salla-Docs

# Square photos

This **_pre-defined component_** simply displays square shape photos in form of a grid. The first photo will be the __ leading __ photo and will be bigger in size.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├──── home
   |  |  ├──── square-photos.twig
      ...
   ...
```


### Example
<!--
focus: false
-->
![Square Photos](https://cdn.salla.network/docs/twilight/4/pages-components-home-square-photos-01.png)

### Variables


<DataSchema id="1383703" />


### Usage
This component takes a list of photos as a collection of `items[]`. Each item in this collection has `url`, `link_type`, `image.url`, and `image.alt`. The first item represents the first image that will be the __leading__ photo and will be bigger in size, then a **for-loop** will be used to list the rest of the photos.

```php lineNumbers
{% for item in items %}
    <a href="{{ item.url }}" {% if item.link_type=='external_link' %} target="_blank" {% endif %}>
        <img src="{{ items[0].image.url }}" alt="{{ item.text }}">
        {% if item.text %}
            <h3>{{ item.text }}</h3>
        {% endif %}
    </a>
{% endfor %}
```

---

## theme-architecture-components-home-components/Store-Features-Component-Twilight-Documentation-Salla-Docs

# Store features

This **_pre-defined component_** is responsible for showcasing the store features such as payment methods, shipping methods and so on.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── store-features.twig
          ...
```

### Example
<!--
focus: false
-->
![Store Features](https://cdn.salla.network/docs/twilight/4/pages-components-home-store-features-01.png)

### Variables


<DataSchema id="1383706" />


### Usage 
This component is a simple component that takes the content of the store features as `icon`, `title`, and `text`. Then a **for-loop** to display each feature.

```php lineNumbers
{% for item in items %}
    <i class="{{ item.icon }}"></i>
    <h4>{{ item.title }}</h4>
    <p>{{ item.text }}</p>
{% endfor %}
```
:::tip[Educational Clip]
<Video src="https://youtu.be/nm0ja6rTqpo?si=nKZWYI6dTi86xyPl"></Video>
:::

---

## theme-architecture-components-home-components/Testimonials-Component-Twilight-Documentation-Salla-Docs

# Testimonials

This  **_pre-defined component_** displays testimonials, which are feedback given by customers. The display order is set as per newest.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── testimonials.twig
          ...
```


### Example
<!--
focus: false
-->
![Testimonials Components](https://cdn.salla.network/docs/twilight/4/pages-components-home-testimonials-01.png)

### Variables


<DataSchema id="1383704" />



### Usage
The file `src\views\components\home\testimonials.twig` receives a list of `testimonials`, which are the customers' feedbacks, in the form of a collection of `items[]`,and then displays them inside a slider. The sorting of this collection is as per the newest.

In the following code we see how we can easily display the values of `item.avatar`, `item.name`, `item.text` inside the slider uing **for-loop**. Also `salla-button` is used here to navigate between `previous slide` and `next slide`.

```php lineNumbers
<h2>{{ trans('blocks.home.testimonials') }}</h2>

{% for item in items %}
    <img src="{{ item.avatar }}" alt="{{ item.name }}"/>

    <p>{{ item.text }}</p>
    <div>
        <h4>{{ item.name }}</h4>
    </div>
    <div>
        {% for i in range(0, item.stars) %}
            <i>*</i>
        {% endfor %}
    </div>
{% endfor %}
```

---

## theme-architecture-components-home-components/Vertical-Menu-with-Slider-Twilight-Documentation-Salla-Docs

# Vertical Menu with Slider

This pre-defined component is used to display a menu for a group of the sub-pages' links in a vertical menu. It has a static view, which can easily be modified by the developer.

**Following is the location of this component.**

```shell
└── src
  ├── views 
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── vertical-menu-with-slider.twig
          ...
```

### Example

<!--
focus: false
-->
![image](https://cdn.salla.network/docs/twilight/4/pages-components-home-vertical-menu-with-slider-01.png.png)

### Variables


<DataSchema id="1383685" />

### Usage
This component renderes dynamic content with links and images by looping through items and conditionally adding classes.

``` php lineNumbers
<section>
  <div> {% component menu render_in 'home.vertical-cats'  with {title:title, icon:icon} %}
    <ul> {% for item in items %}
      <li>
        <a href="{{item.url}}">
          <img src="{{ item.image.url }}" alt="{{ item.image.alt }}" />
        </a>
      </li>
      {% endfor %}
    </ul>
  </div>
</section>
```

---

## theme-architecture-components-home-components/YouTube-Component-Twilight-Documentation-Salla-Docs

# Youtube

This **_pre-defined component_** is responsible for displaying Youtube videos that the developer preselects.

**Following is the location of this component.**

```shell
└── src 
  ├── views
   ├── components    
   |  ├── home
   |  |   ...
   |  |  ├── youtube.twig
          ...
```

### Example
<!--
focus: false
-->
![YouTube](https://cdn.salla.network/docs/twilight/4/pages-components-home-youtube-01.png)

### Variables


<DataSchema id="1383705" />


### Usage
This component needs the` youtube_id` variable, which is the video URL, in order to display the embedded YouTube video. Below we can see its code. The **default** look of this component in the following code:

```php lineNumbers
<section>
  <iframe width="560" height="349" src="https://www.youtube.com/embed/{{ youtube_id }}?rel=0&hd=1" frameborder="0" allowfullscreen></iframe>
</section>
```

---

