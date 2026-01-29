# Theme Architecture Pages Blog Pages

## Table of Contents

- [theme-architecture-pages-blog-pages/Blog-Listing-Page-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-blog-pages-blog-listing-page-twilight-documentation-salla-docs)
- [theme-architecture-pages-blog-pages/Single-Blog-Article-Template-Twilight-Documentation-Salla-Docs](#theme-architecture-pages-blog-pages-single-blog-article-template-twilight-documentation-salla-docs)

---

## theme-architecture-pages-blog-pages/Blog-Listing-Page-Twilight-Documentation-Salla-Docs

# Blog listing

The [`blog listing page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/blog/index.twig) is used for rendering the list of all of the available blogs' articles. This template will show an excerpt for each blog article along with the article title, summary, image, and author name. The developer has complete control over the appearance of this page.


**Following is the page location and url:**

```shell title="🌐 Page URL: http://www.store-domain.com/blog"
└── src 
  ├── views
    ├── pages
    |   ├── blog
    |   |   ├── index.twig
    |   ...
    ...
```

### Example
<!--
focus: false
-->
![Blog listing](https://cdn.salla.network/docs/twilight/4/blog-listing-01.png)


### Variables


<DataSchema id="1383856" />


### Components
The blog page includes the [Breadcrumbs](doc-422601?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) component. Breadcrumbs are a set of links that indicate the current page and its "ancestors" leading back to the site's homepage.

```php lineNumbers=true
{% component 'header.breadcrumbs' %}
```

### JS Web Components
The Blog Listing page may include the following [JS Web Components](https://docs.salla.dev/doc-422688?nav=01HNFTE06J4QC24T0D5BPRYKMD), which are ready-made designs and style-sets of web components for Salla stores:

- Infinite Scroll [`<salla-infinite-scroll>`](doc-422706?nav=01HNFTE06J4QC24T0D5BPRYKMD)
- Slider [`<salla-slider>`](https://docs.salla.dev/doc-422735?nav=01HNFTE06J4QC24T0D5BPRYKMD)

### Hooks
The `blog listing page template` allows calling the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject more information:


```php lineNumbers=true
{% hook 'blog:index.items.start' %}
{% hook 'blog:index.items.end' %}

```
### Usage
The blog listing page receives several objects containing the details of the whole blog. These objects are `slides`, `articles`, `page`, and `categories`.

Using the `categories` object, the developer may start by listing all of the available categories for the blog.

```php lineNumbers=true
<div>Blog Categories</div>
{% for category in categories %}
    <li {{ category.is_current ? ' class="style-1"' : '' }}>
        <a href="{{ category.url }}">
            {{ category.name }}
        </a>
    </li>
{% endfor %}
```

In the case of the availability of the object `slides`, which can be checked by `slides.count`, the blogs' short information can be displayed in form of slider. This can be used to display only the article `image`, `summary`, and `author name` for each blog article.

```php lineNumbers=true
{% if slides|length %}
    <div class="slider-style">
        {% for article in slides %}
            <div class="slider-item">
                {% if article.has_image %}
                    <img src="{{ article.image.url }}" alt="{{ article.image.alt }}"/>
                {% else %}
                    <img  src="{{ asset('images/placeholder.png') }}" alt="placeholder">
                {% endif %}
                <span>{{ article.created_at|date }}</span>
                <span>{{ article.author.name }}</span>
                <span>{{ article.title }}</span>
                <span>{{ article.summary }}</span>
            </div>
        {% endfor %}
    </div>
{% endif %}
```

The core object for this page is the `article` object. Using the _for-loop_ statement, the developer can display an excerpt for each blog article.

```php lineNumbers=true
{% if articles.count %}
    {% for article in articles %}
        {% if article.has_image %}
            <img src="{{ article.image.url }}" alt="{{ article.image.alt }}"/>
        {% else %}
            <img src="{{ asset('images/placeholder.png') }}" alt="placeholder">
        {% endif %}
        <span>{{ article.created_at|date }}</span>
        <span>{{ article.author.name }}</span>
        <span>{{ article.title }}</span>
        <span>{{ article.summary }}</span>
        {% if article.tags is not empty %}
            {% for tag in article.tags %}
                <a href="{{ tag.url }}">
                    <span>{{ tag.name }}</span>
                </a>
            {% endfor %}
        {% endif %}
    {% endfor %}
{% else %}
    {{ trans('pages.blog_categories.no_articles') }}
{% endif %}
```

---

## theme-architecture-pages-blog-pages/Single-Blog-Article-Template-Twilight-Documentation-Salla-Docs

# Single blog

This [`single  blog page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/blog/single.twig) is to display the content of a single article from the store's blog. The content can be a mix of text and images. This is part of the internal marketing tool for the store owner to draw the customer's attention to specific products or ideas. Each article is displayed along with its tags, in the event of having tags. This template may also show any related articles to the current single article. 


**Following is the page location and url:**
``` shell title = "🌐 Page URL: http://www.store-domain.com/blog/c6576542"
└── src 
  ├── views
    ├── pages
    |   ├── blog
    |   |   ├── single.twig
    |   ...
    ...
```

### Example
<!--
focus: false
-->
![Sigle blog](https://cdn.salla.network/docs/twilight/4/blog-single-01.png)


### Variables



<DataSchema id="1383877" />


### Components
The category page includes the [Breadcrumbs](https://docs.salla.dev/doc-422601) component. Breadcrumbs are a set of links that indicate the current page and its "ancestors" leading back to the site's homepage.

```php lineNumbers=true
{% component 'header.breadcrumbs' %}
```

### Hooks
The `single  blog page template` may call the following [hooks](https://docs.salla.dev/doc-422552?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) in order to inject more information:

```php lineNumbers=true
{% hook 'blog:single.items.start' %}
{% hook 'blog:single.items.end' %}
```
### Usage
This page receives the object `article`, which contains the full content details of that single article. For example, `article.name`, `article.created_at`, `article.author.name`, and so on. The developer has complete control over how these elements can be displayed.

```php lineNumbers=true
<p>{{ article.title }}</p>
<p>{{ article.created_at|date }}</p>
<p>{{ article.author.name }}</p>

{% if article.has_image %} 
  <img src="{{ article.image.url }}" alt="{{ article.image.alt }}" />
{% endif %}

<p>{{ article.body|raw }}</p>
```

The variable `article.tags` can be used to display the article's attached tags. Below is an example of that.

```php lineNumbers=true
{% if article.tags|length %}
  {% for tag in article.tags %} 
    {{ tag.name }} 
  {% endfor %}
{% endif %}
```

In addition, the variable `article.related` retrieves an array of any related articles, which can be listed using a _for-loop_ statement.

```php lineNumbers=true
{% if related|length %}
    <h2>Related Articles</h2>

    {% for article in article.related %}
        {{ article.name }}
        {% if article.has_image %}
            <img src="{{ article.image.url }}" alt="{{ article.image.alt }}"/>
        {% else %}
            <img src="{{ asset('images/placeholder.png') }}" alt="placeholder">
        {% endif %}
        {{ article.created_at|date }}
        {{ article.title }}
    {% endfor %}
{% endif %}
```

---

