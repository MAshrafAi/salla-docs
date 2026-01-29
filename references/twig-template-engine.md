# Twig Template Engine

## Table of Contents

- [twig-template-engine/Themes-Basic-Syntax-Twilight-Documentation-Salla-Docs](#twig-template-engine-themes-basic-syntax-twilight-documentation-salla-docs)
- [twig-template-engine/Twilight-flavoured-twig-Twilight-Documentation-Salla-Docs](#twig-template-engine-twilight-flavoured-twig-twilight-documentation-salla-docs)

---

## twig-template-engine/Themes-Basic-Syntax-Twilight-Documentation-Salla-Docs

# Basic syntax

[Twig](https://twig.symfony.com/doc/3.x/templates.html) is a "template engine" the template contains variables and functions which get replaced when the template is evaluated it also uses tags to manage the template logic. In other words, Twig helps buliding interactive interfaces with feasible connections to the underlying programming. It's meant to be used with a js class that sends the variables to be displayed on an HTML page, and the HTML just displays the data.


:::tip[A thing to know!]
**Twilight** uses [Twig](https://twig.symfony.com/doc/3.x/templates.html) as its "template engine"
:::


## 📙 What you'll learn
In this article, you will learn the basic syntax of Twig.

<hr>

### Delimiters
Twig defines three kinds of delimiters:

- `{{ ... }}` prints the result of an expression evaluation.
- `{% ... %}` to execute statements, such as for-loops.
- `{# ... #}` to add comments in the templates. These comments aren't included on the rendered page.

### Basic Twig Template

```js title ="template_page.twig" lineNumbers=true
<!DOCTYPE html>
<html>
<head>
  <title>My Twilight Template</title>
</head>
<body>
My name is {{ name }} and I love Twilight.
My favorite flavors of cookies are:
<ul>
  {% for cookie in cookies %}
    <li>{{ cookie.flavor }}</li>
  {% endfor %}
</ul>
<h1>Cookies are the best!</h1>
</body>
</html>
```

### Twig Basic Tags

Tags tell Twig what it needs to do. It allows setting which code Twig should handle and which code it should ignore during evaluation.

There are several different kinds of tags, and each has its own specific syntax that sets them apart. These are the tags to be used:

| Basic Tags                             | Description |
| -------------------------------------- | ----------- |
| [set](https://docs.salla.dev/doc-421928?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#set)                            | Assigns values to variables.         |
| [extends & blocks](#extends--blocks)   | Sets the base code for the site and defines the blocks that inherit from child blocks.                            |
| [blocks](#blocks)                      |   Used for inheritance and act as placeholders and replacements at the same time      |
| [include](https://docs.salla.dev/doc-421928?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#include)                    | Used to include a file's content inside a block tag.         |
| [for-loop](#for-loop)                  | Used to loop over multiple items in an array using the `for` tag.        |
| [if-else](#if-else)                    | Executes the code if the expression in place is `true` and assigns fallback conditions if it's `false`   .    |


#### set
As an initial point, `set` tags are used to assign values to variables within blocks:
```js title ="template_page.twig"
{% set Lion = 'King' %}
{{Lion}} /* Lion will be King */
```
#### extends & blocks 

Template inheritance is one of twigs perks. It allows setting a base code that contains all the elements for your website and defining blocks that inheritance can override from child templates.

Let's define a base template, `master.twig`, which defines an HTML skeleton document that might be used for a two-column page:

```js title= "master.twig " lineNumbers= True
<!DOCTYPE html>
<html>
<head>
  {% block head %}
    <link rel="stylesheet" href="style.css"/>
    <title>{% block title %}{% endblock %} - My Webpage</title>
  {% endblock %}
</head>
<body>
<div id="content">{% block content %}{% endblock %}</div>
<div id="footer">
  {% block footer %}
      &copy; Copyright 2011 by <a href="http://domain.invalid/">you</a>.
  {% endblock %}
</div>
</body>
</html>
```

In this example, the `block` tags define blocks that child templates can fill in. All the `block` tag tells the template engine that a child template may override those portions of the template.

A child template might look like this:

```js title ="template_page.twig" lineNumbers=true
{% extends "master.twig" %}

{% block title %}Index{% endblock %}
{% block head %}
  {{ parent() }}
  <style type="text/css">
    .important { color: #336699; }
  </style>
{% endblock %}
{% block content %}
  <h1>Index</h1>
  <p class="important">
      Welcome to my awesome homepage.
  </p>
{% endblock %}
```

#### blocks
`block` is used for inheritance and acts as placeholders and replacements at the same time.


The block function allowes to print a block mutiple times in templates that uses inheritance.
``` js 
<h1>{{ block('title') }}</h1>

{% block body %}

{% endblock %}

```
The defines test cheks if a block exists in the context of the current template:

``` js 
{% if block("footer") is defined %}
{% endif %}

{% if block("footer", "common_blocks.twig") is defined %}
{% endif %}
```

The block function can also be used to display one block from another template:

```js
{{ block("title", "common_blocks.twig") }}
```
#### include

`include`  is used to include a file's content inside a block tag. 

```js title ="Animal.twig" lineNumbers=true
{% block header %}
  {{ include 'lion' }}
{% endblock %}
```
#### for-loop
`for-loop` is used to loop through multiple items of array or hash and produces results based on the expression. 

For example, the below code loops through products array using `for-loop` which is passed from the server. Then prints out the products id.

```js title= "template_page.twig"  lineNumbers=true
{% for product in products %}
  <div class="card shadow">
    <a href="/products/{{ product.id }}">View The Product</a>
  </div>
{% endfor %}
```
#### if-else
Executes the code if the expression in place is `true` and assigns fallback conditions if it's `false`. 

```js title= "template_page.twig" lineNumbers=true
{% if order %}
  <div>{{ order.id }}</div>
{% endif %}
```

### Filters
Twig filters allow you to apply functionality to the variable on the left side of the pipe (|) symbol. They are handy when dealing with manipulating text or variables. 
The first argument to the filter is always the item on the left, but subsequent arguments can be passed in parentheses. Filters have some special capabilities, including being environmentally aware.

Examples of built-in Twig filters include `raw`, `length`, `date`, `split`, `join`, `lower`, `slice`, and many more. 

Examples:

- The _raw_ filter marks the value as being "safe", which means that in an environment with automatic escaping enabled this variable will not be escaped if raw is the last filter applied to it:

```js
{% autoescape %}
  {{ var|raw }} {# var won't be escaped #}
{% endautoescape %}
```

- The `length` filter returns the number of items of a sequence or mapping, or the length of a string.

```js
{% if products|length > 10 %}
  <h3>{{ product.name }}</h3>
{% endif %}

```

- The `date` filter formats a date to a given format:

``` js title = " Using Date filter"
{{ comment.published_at|date("m/d/Y") }} 
{# outputs 4/4/2022 #}

```
- The `split` filter splits a string by the given delimiter and returns a list of strings:
```js
{% set foo = "one,two,three"|split(',') %}
{# foo contains ['one', 'two', 'three'] #}

```

### Functions

Twig functions are another way to implement functionality in Twig. They are similar to filters; however, rather than acting on a variable via the pipe (|) symbol, you would call these functions directly and pass in any attributes they support between the parentheses after the function name. 

Examples of built-in Twig filters include `block`, `dump`, `parent`, `random`, `range`, and more. 

Examples:

- The `random` filter returns a random value.
in the example below it returns a random number
```js
<div class="price">
  {{ random(10) }}
  
  {# random(10) returns a number from 0 to 10 #}
</div>
```

- The `range` filter returns a list containing an arithmetic progression of integers:

``` js

{% for i in range(0, 3) %}
  {{ i }},
{% endfor %}

{# outputs 0, 1, 2, 3, #}
```

<br/>
You are now prepared to use the tags commonly used by twig to build your theme.

---

## twig-template-engine/Twilight-flavoured-twig-Twilight-Documentation-Salla-Docs

# Twilight flavoured twig

Although Twig already provides a large list of helper functions and filters, Twilight also has added a selection of useful helpers and filters to make theming easier.

:::tip[Note]
Twig helper functions are called directly with any parameters passed in via parenthesis.
:::

## 📙 What you'll learn
In this article, you'll learn how to use:
- [Twilight flavoured helper functions.](#helpers)
- [Twilight flavoured filter.](#filters)
<hr>

## Helpers
In general, helpers are Twig functions by which we can implement functionality in Twig. 

Following are the helper functions available on all Twilight `.twig` files.

| Helper Available                  | Description                                        |
| --------------------------------- | -------------------------------------------------- |
| [is_current_url](#is_current_url) | Checks the link.                                   |
| [is_page](#is_page)               | Displays the page name.                            |
| [link](#link)                     | Creates links.                                     |
| [old](#old)                       | Keeps previous inputs.                             |
| [pluralize](#pluralize)           | Transforms the word into singular or plural forms. |
| [page](#page)                     | Creates a link to the page.                        |
| [trans](#trans)                   | Translates texts to the current store language.    |

### is_current_url
Checks if the current link matches the passed pattern.
```js
is_current_url(string $pattern)
```

Examples:
```js
{% if is_current_url('orders',{refund:'true'}) %}
    ...
{% endif %}
```

### is_page

This helper displays the page name on the page.

Example:

```js
{% if is_page('product.single') %}
{%endif%}
```

### link
Combine strings to generate a full link.
```js
link(?string $url, ?array $parameters)
```

Examples:
```js
<!-- basic use -->
link("page_url", {by:"test"}) 
<!-- https://my_store.com/page_url?by=test --> 
```

### pluralize
Similar to trans, it takes a `$count` argument to change the message in plural or singular form in-store language.
```js
pluralize(string $key, int $count)
```
Examples:
```js
<!-- basic use -->
{{ pluralize('blocks.comments.comment', comments.total)|number }}
<!-- <span>21</span> Comment --> 
```

### page
This helper generates the link to a specific page as follows:

Example
```js
<a href={{ page('cart') }}>Cart</a>
```

The generated link will be the cart's page url for the store, as follows:
```https://www.my-store.com/cart```

### old
This helper function keeps previous input from one request during the next request. This feature is particularly useful for re-populating forms after detecting validation errors.

Examples:
```js
old("name")
```

Example
```js
<input type="text" name="username" value="{{ old('username') }}">
```

### trans
This helper translates the passed key to the current store langauge. 
Here are more information about [Localization](https://docs.salla.dev/doc-422553?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
```js
trans(string $key, $replace = [], $default = null)
```
Examples:
```js
<!-- simple key -->
<span>{{ trans('common.titles.orders') }}</span>

<!-- key with variable -->
<span>{{ trans('pages.gift.sent_you_a_gift', ['name' => 'Mohammed']) }}</span>

<!-- key with enforced locale/language -->
<!-- this will always print the result of key in English even if the store has different default language -->
<span>{{ trans('common.titles.orders', [], en) }}</span>
```

## Filters

These special filters are available on all `.twig` files. Use the the pipe sign, `|`, to use them.

Following are the filters available by Twilight.


| Filters Available                   | Description |
| --------------------------------- | ----------- |
| [asset](#asset)                   | Creates links to Salla's theme files.         |
| [camel_case](#camel_case)         | Replaces punctations and spaces with letters in uppercase.       |
| [cdn](#asset)                     | Retrives links of pre-defined files such as `font` and `saicon`. |
| [currency](#currency)             | Adds currency sign.        |
| [date](#date)                     | Displays the dates in the current page language.      |
| [is_placeholder](#is_placeholder) | Checks if image url is placeholder or image.          |
| [kebab_case](#kebab_case)         | Replaces the spaces with a dash.         |
| [money](#money)                   | An alias for currency filter.         |
| [number](#number)                 | Parses numbers into Arabic numbers.       |
| [snake_case](#snake_case)         | Replaces spaces in texts with underscore and keeps first letter in lowercase.|
| [studly_case](#studly_case)       | Capilaizes first letters in each subword.        |
| [time_ago](#time_ago)             | Shows the time of and action execution.        |


### asset

This filter creates links to Salla theme files. 

```js
'dist/app.css' | asset
```

### camel_case
This filter removes each spaces or punctuation in a given string, indicating the separation of words with a single capitalized letter, and the first word starting with either case. Common examples include "iPhone" and "eBay".
```js
<!-- phone.brand is 'i phone' -->
{{ phone.brand | camel_case }}
<!-- the result is: iPhone -->
```

### cdn

This filter retrives links of pre-defined files such as `font` and `saicon`.

```js
'images/maroof-footer.png' | cdn 
```

### currency
This filter add the currency sign 'SAR' to the passed value.
```js
<!-- order.total is '100' -->
{{ order.total | currency }}
<!-- the result is: 100SAR -->
```

### date
This filter overrides the default [date filter](https://twig.symfony.com/doc/3.x/filters/date.html) given with Twig. It formats a date to a given format with concidering the page's selected language.

```js
<!-- order.created_at -->
{{ order.created_at | date("'j F Y'") }}
<!-- the result is: ١٧ مارس ٢٠٢١ -->
```

### is_placeholder

This filter is used to know if the image url is placeholder or actual image

```js
<!-- is_placeholder -->
{{product.image.url|is_placholder}}

<!-- the result is: Photo is placed -->

```

:::tip[Tip]
We have default placeholder image, developer may want to use another image, it can be replaced by calling:
```js
<!-- is_placeholder -->
{{theme.set('placeholder','images/img_placeholder.png')}}
<!-- the result is: the path images/img_placholder.png is inside assets folder-->
```
:::


### kebab_case
This filter replaces the spaces between words with a dash.
```js
<!-- user.name is 'Mohamed Ali' -->
{{ user.name | kabab_case }}
<!-- the result is: Mohamed-Ali -->
```


### money 
This an alias for currency filter.
```js
<!-- order.total is '100' -->
{{ order.total | money }}
<!-- the result is: 100SAR -->
```

### number
This filter will always parse any number given to Arabic number if merchants enables it and the current language is Arabic. It will also parse decimal number representation to a decimal point in Arabic (,)
```js
<!-- user.mobile is '966567891011' -->
{{ user.mobile | number }}
<!-- the result is: ٩٦٦٥٦٧٨٩١٠١١ -->

<!-- decimal.number is '100.10' -->
{{ decimal.number | number ({“search”:”replacewith”})}}

<!-- the result is: ١٠٠.١٠ -->
```

### snake_case
This filter replaces each space in a given string with an underscore character, and the first letter of each word written in lowercase.
```js
<!-- user.code is 'This is a Test' -->
{{ user.code | snake_case }}
<!-- the result is: this-is-a-test -->
```


### studly_case
Also known as [PascalCase](https://techterms.com/definition/pascalcase), which implies that the first capital of each subword is capitalized.
```js
<!-- phone.brand is 'i phone' -->
{{ phone.brand |  studly_case }}
<!-- the result is: iPhone -->
```

### time_ago

This filter shows the time of and action execution, for example, "Comment created 10 minutes ago."

```js
<!-- time_ago -->
{{ comment.created_at|time_ago }}
<!-- the result is: Comment created 10 min ago -->
```

---

