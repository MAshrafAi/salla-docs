# Theme Architecture Layouts

## Table of Contents

- [theme-architecture-layouts/Themes-CSS-Variables-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-css-variables-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Custom-Fonts-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-custom-fonts-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Global-Variables-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-global-variables-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Hooks-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-hooks-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Layouts-Overview-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-layouts-overview-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Localizations-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-localizations-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Master-Layout-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-master-layout-twilight-documentation-salla-docs)
- [theme-architecture-layouts/Themes-Salla-Icons-Twilight-Documentation-Salla-Docs](#theme-architecture-layouts-themes-salla-icons-twilight-documentation-salla-docs)
- [theme-architecture/Components](#theme-architecture-components)
- [theme-architecture/Layouts](#theme-architecture-layouts)
- [theme-architecture/Pages](#theme-architecture-pages)

---

## theme-architecture-layouts/Themes-CSS-Variables-Twilight-Documentation-Salla-Docs

# CSS Variables

Theme **CSS variables** allow the themes style to be modified by altering the font type and color code. This step provides options for the developer to apply changes on the Themes as well as enabling them using the Theme features in [Salla Partners Portal](https://salla.partners/). The **CSS variables** can be placed in the pages the developer wants to apply the styles on, or it can be placed in the master layout.


:::tip[A thing to know!]
 To make a unified theme style using **CSS variables**, it's advised to place the variables in the master layout which helps to apply it globally.
:::


This article walks through how the developer can change the theme styles using the Theme CSS variables and how to enable the features in the Partners Portal.


## 📙 What you'll learn

- [Assigning the Theme CSS variables](#assigning-the-themes-css-variables).
- [Enabling CSS variables in Salla Partners Portal](#enabling-css-variables-in-salla-partners-portal).

<hr>

### Assigning the themes CSS variables

Colors and fonts are the predominant features of the theme, which can be set by assigning the thems CSS variables. This section explains how he developer can assign CSS variables of the theme where the merchant has the ablility to change the font and color of theme once it's appiled in their store. As illustrated below:

``` php title = "master.twig" lineNumbers=true
... 
<style>
  :root {
  --font-main: {{theme.font.name}};
  --color-primary: {{ theme.color.primary }};
  --color-primary-dark: {{ theme.color.darker(0.15) }};
  --color-primary-light: {{ theme.color.lighter(0.15) }};
  --color-primary-reverse: {{ theme.color.reverse_text }};
  }
</style>
...

```
The developer can use the above CSS variables to assign their values as mentioned in the follwoing table.

|CSS Variable   | Description   |
|---|----|
|`--font-main`|This line will assign the font type to be applied in on the page|
|`--color-primary`| The primary color will be assigned to the font|
| `--color-primary-dark`|This line modifes the primary color to suit the dark mode for the theme, in this case it darkens the color by 15% |
|`--color-primary-light`|This line modifes the primary color to suit the day mode for the theme, in this case it brightens the color by 15%  |
|`--color-primary-reverse`|This line selects the reverse color for the primary color which is the oppoist of the primary color |


Another possibility is that the developer provids fixed values to the CSS variables. This would prevent the merchant from altering the theme's typeface or color scheme, as demonstrated by the following line of code:

``` php title = "master.twig" lineNumbers=true
...
<style>
:root {
  --font-main: 'Times New Roman';
  --color-primary: #da8f81;
  --color-primary-dark: #b3685a;
  --color-primary-light: #ffb5a7;
  --color-primary-reverse: #5a0f01;
  }
</style>
...
```

The CSS variables assignes the `font-main` with 'Times New Roman' and the colors with the specific color code in HEX form, the font and color will then be applied to the theme. 

### Enabling CSS variables in Salla Partners Portal

Twilight themes grants the ability for the merchant to adjust the store theme fonts and colors which is available with the help of CSS variables that were assigned by the developer in the [previous](#enabling-css-variables-in-salla-partners-portal) section. After assigning the CSS variables by the developer, the font and color can be enabled by using the Theme features in the [partners portal](https://salla.partners/) 
<!--
focus: false
-->
![Themes Features](https://cdn.salla.network/docs/twilight/4/css-variables-01.jpg)

By enabling the features, it allows the merchant to make changes to the themes fonts and colors.

:::tip[Educational Clip]

<Video src="https://www.youtube.com/watch?v=Uj397TxiOww
"></Video>

:::

---

## theme-architecture-layouts/Themes-Custom-Fonts-Twilight-Documentation-Salla-Docs

# Custom Fonts

Adding your own custom icons to your theme development is a straightforward process that can be accomplished in just three easy steps. This will give your theme a more unique and personalized feel. In this article, we will walkthrough how to add  [icomoon](https://icomoon.io/) icons.

## 📙 What you'll learn

- Add `fonts` folder under `assets`
- `webpack.config.js` Modification
- `master.twig` Modification 

<hr>

### assets folder in fonts

A new folder will be created within the assets folder and designated as "fonts."

<!-- focus: false -->
![IMAGE](https://cdn.salla.network/docs/twilight/4/custome-fonts-01.png)

### `webpack.config.js` Modification

Code addition to the webpack.config.js file will be implemented, in which the following code is placed on line `61` of the file to transfer the fonts folder from `assets` to `public` _(This is the case if the file has never been altered)_

```css title= "webpack.config.js " lineNumbers= True
new CopyPlugin({patterns: [{from: asset('fonts'), to: public('fonts')}]})
```

<br>

<!-- focus: false -->
![IMAGE](https://cdn.salla.network/docs/twilight/4/custome-fonts-02.png)

### `master.twig` Modification 

Insert the newly defined font into the `<head>` section of the `master.twig` file as follows:

```css title= "master.twig " lineNumbers= True

<style>@font-face {
  
  font-family: 'sallamenuthemeicons';
  src: url({{ 'fonts/themefonticons.ttf' | asset }}) format("truetype"),
  url({{ 'fonts/themefonticons.eot' | asset }}) format("embedded-opentype"),
  url({{'fonts/themefonticons.woff' | asset }}) format("woff");
}

</style>
```

We will now have established links between the new font files. It will continue to establish a link to the font's CSS file. In order to directly utilize the icon classes, we integrate it within the `app.css` file.

---

## theme-architecture-layouts/Themes-Global-Variables-Twilight-Documentation-Salla-Docs

# Global Variables


In ths article we will list all of the global variables provided with the Twilight theme engine. 
:::tip[Tip]
These varibles can be used within any of the Theme's pages.
:::
<br>


<DataSchema id="1383862" />

:::tip[Educational Clip]

<Video src="https://youtu.be/eCB7_SR8QUE?si=LSYkWwq7dcS3OFqi"></Video>
:::

---

## theme-architecture-layouts/Themes-Hooks-Twilight-Documentation-Salla-Docs

# Hooks

Hooks are a powerful tool used in theme development for the [Salla Store Theme](https://s.salla.sa/marketplace/themes/tag-all). They allow developers to inject code and content into specific areas of a webpage's template without having to modify the original code. For example, adding meta-data and SEO-related tags into a webpage's `<head>` section. These pieces of code can be "hooked" to the theme by calling them using the template's _hooks_.

:::tip[]
The Twig code syntax `{% hook 'hook.name' %}` is used to add a hook to a specific point. It allows developers to trigger custom code or content at that point without modifying the core code.
:::


In nutsell, template hooks can be used to add content to different parts of the theme to make it more useful. Twilight theme has pre-defined a list of template hooks and made them available in the default templates. 

## 📙 What you'll learn

This article explores the following template hooks:

  - [Head hooks](#head-hooks) 
  - [Body hooks](#body-hooks)
  - [Customer Pages Hooks](#customer-pages-hooks)
  - [Product Pages Hooks](#product-page-hooks)
  - [Cart Page Hooks](#cart-page-hooks)
  - [Thank You Pages Hooks](#thank-you-pages-hooks)
  - [Brand Pages Hooks](#brand-pages-hooks)
  - [Twilight Components Hooks](#twilight-components-hooks)

<hr>

### Head hooks
In HTML, the `<head>` element is used to define the webpage's head section, which contains information about that webpage. Other head elements in the head element include `<title>`, `<meta>`, `<link>`, `<style>`, and so on. 

The Head hooks are commonly used to add meta-data and SEO-related tags into the <head> section of a webpage. They provide an easy and flexible way to add or remove content from the <head> section of the theme template without altering the core code.

The three head hooks, `{% hook 'head:start' %}`, `{% hook head %}`, and `{% hook 'head:end' %}` are used to manage the different sections of the `<head>` area as follows:

| No. | Hook Code                 | Description                                               |
| --- | ------------------------- | --------------------------------------------------------- |
| 1.  | `{% hook 'head:start' %}` | Indicates the start of the `<head>` section in a webpage. |
| 2.  | `{% hook head %}`         | Adds content to the `<head>` section of a webpage.        |
| 3.  | `{% hook 'head:end' %}`   | Indicates the end of the `<head>` section in a webpage.   |



### Body hooks

In HTML, the `<body>` tag is used to define the webpage's content area. In addition to the actual content, the style of content appearance is defined here as well. There are hooks in Twilight that allow the developer to add content to the main area of a webpage.

| No. | Hook Code                   | Description                                               |
| --- | --------------------------- | --------------------------------------------------------- |
| 1.  | `{% hook 'body:classes' %}` | Adds classes to the `<body>` tag of a webpage.            |
| 2.  | `{% hook 'body:start' %}`   | Indicates the start of the `<body>` section in a webpage. |
| 3.  | `{% hook 'body:end' %}`     | Indicates the end of the `<body>` section in a webpage.   |


For example, the hook `body:classes` allows the developer to add specific CSS classes that customise the appearance of that specific page, for instance , the home page or product page. This is done so there is no need for the store's owner to create a child theme or worry about theme updates overwriting the customizations. 

### Customer Pages Hooks
These hooks are used in Salla Store Theme development to modify and extend the functionality of the customer pages.

| No. | Hook                                              | Description                                                                              |
| --- | ------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| 1.  | `{% hook 'customer:profile.form.start' %}`        | Used to add custom content or fields to the customer profile form.                       |
| 2.  | `{% hook 'customer:profile.form.fields.start' %}` | Used to add custom content or fields to the customer profile form.                       |
| 3.  | `{% hook 'customer:notifications.items.start' %}` | Used to trigger custom code or content at the start of the customer notifications items. |
| 4.  | `{% hook 'customer:notifications.items.end' %}`   | Used to trigger custom code or content at the end of the customer notifications items.   |
| 5.  | `{% hook 'customer:wishlist.items.start' %}`      | Used to add custom content or code to the customer wishlist items.                       |
| 6.  | `{% hook 'customer:wishlist.items.end' %}`        | Used to add custom content or code to the end of the customer wishlist items.            |
| 7.  | `{% hook 'customer:orders.index.items.start' %}`  | Used to modify or add content to the start of the customer orders index items.           |
| 8.  | `{% hook 'customer:orders.index.items.end' %}`    | Used to modify or add content to the end of the customer orders index items.             |

### Product Pages Hooks
**Twilight** offers several hooks for customizing the product pages on an online store. 
| No. | Hook                                            | Description                                                                        |
| --- | ----------------------------------------------- | ---------------------------------------------------------------------------------- |
| 1.  | `{% hook 'product:index.items.start' %}`        | Used to trigger custom code or content at the start of the product index items.    |
| 2.  | `{% hook 'product:index.items.end' %}`          | Used to trigger custom code or content at the end of the product index items.      |
| 3.  | `{% hook 'product:single.description.start' %}` | Used to add custom content or code to the start of the product single description. |
| 4.  | `{% hook 'product:single.description' %}`       | Used to add custom content or code to the product single description.              |

### Cart Page Hooks
Twilight  provides two hooks for customizing the cart page. The `{% hook 'cart:items.start' %}` hook is used to add custom content or code at the start of the cart items. The `{% hook 'cart:items.end' %}` hook is used to add custom content or code at the end of the cart items.

| No. | Hook                            | Description                                                        |
| --- | ------------------------------- | ------------------------------------------------------------------ |
| 1.  | `{% hook 'cart:items.start' %}` | Used to add custom content or code at the start of the cart items. |
| 2.  | `{% hook 'cart:items.end' %}`   | Used to add custom content or code at the end of the cart items.   |

### Thank You Pages Hooks
Moreover, Twilight provides four hooks to customize the thank you pages.

| No. | Hook                                 | Description                                                                                                                     |
| --- | ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| 1.  | `{% hook 'thank-you:start' %}   `    | Used to declare the beginning of the thank-you template to add custom content.                                                   |
| 2.  | `{% hook 'thank-you:items.start' %}` | Used to list down the items within the thank-you page template, such as order items.                 |
| 3.  | `{% hook 'thank-you:items.end' %}`   | Used to state the end of listing the items after the list of items has been rendered. |
| 4.  | `{% hook 'thank-you:end' %}   `      | Used to declare the end of the thank-you template to add content to the bottom of the template.                                 |
<br>
    
:::info[]
Moreover, the `thank-you:end` hook injects two buttons (Go Back to the store and Create Salla store) in the thank-you page template and that is only in the case of having a Salla store in the "basic" plan 
:::
    
   

### Brand Pages Hooks
**Twilight** also provides four hooks to customize the brand pages of an online store.
| No. | Hook                                       | Description                                                                  |
| --- | ------------------------------------------ | ---------------------------------------------------------------------------- |
| 1.  | `{% hook 'brands:index.items.start' %}`    | Used to add custom content or code at the start of the brand index items.    |
| 2.  | `{% hook 'brands:index.items.end' %}`      | Used to add custom content or code at the end of the brand index items.      |
| 3.  | `{% hook 'brands:single.details.start' %}` | Used to add custom content or code at the start of the single brand details. |
| 4.  | `{% hook 'brands:single.details.end' %}`   | Used to add custom content or code at the end of the single brand details.   |

### Twilight Components Hooks
By default, **Twilight** automatically adds two hooks to any component that is rendered in a template. These hooks, `{% hook 'component.path.start' %}` and `{% hook 'component.path.end' %}`, indicate the start and end of the component's path. You can use these hooks to trigger custom code or content at specific points in the component, without modifying the core code. For example the following hooks can be used to add custom content before and after the header menu component.:

```js
{% hook 'component:header.menu.start' %}
...
{% hook 'component:header.menu.end' %} 
```

---

## theme-architecture-layouts/Themes-Layouts-Overview-Twilight-Documentation-Salla-Docs

# Overview

Layouts are considered the foundation for Salla theme, through which all of the [theme pages](doc-422556?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) will share the same [layout](https://docs.salla.dev/doc-422576?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). When building a Salla theme, you will need to start by planing for your layouts, so then you can use them to unify your pages' look-and-feel.

## 📙 What you'll learn about
- [Locate Layout files](#locate-layout-files) .
- [Master layout hooks](#master-layout-hooks).
- [Using layouts](#using-layouts).
- [Embed theme pages within the layout](embed-theme-pages-within-the-layout.).
- [Build a new layout](#build-a-new-layout).

<hr>

## Locate Layout files
According to the Twilight [directory structure](https://docs.salla.dev/doc-421918?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), all of the layouts should be stored in the [`src/views/layouts/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/layouts) folder.

```shell
└── src
  ├── views
  |    ...
  |  ├── layouts
  |   ...

```

## Master layout hooks
Most of the theme [hooks](https://docs.salla.dev/422552m0?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) are used within the [master layout](https://docs.salla.dev/421944m0?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). This is due to the fact that this layout, which can be overwritten by the developer, is used across all of the website pages. It means that all of the hooks' contents will be injected into all of the website pages. 


## Using layouts
As we saw in the [Twig basic syntax](https://twig.symfony.com/doc/3.x/), template inheritance is one of twigs perks; it allows you to set a base code that contains all of the elements for your website and define blocks that can override from child templates.

Inheritance is the main concept of building layouts. The developer starts by creating an HTML page with the overall skeleton of the theme pages, with creating `blocks` inside it for future content. These future contents will be filled by the page that will inherit this layout page.

:::info[Information]
A [default layout](https://docs.salla.dev/421944m0?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) is created at [`src/views/layouts/master.twig`](https://github.com/explore).
:::

## Embed theme pages within the layout.
In order to embed the theme pages within the layout page, first we need to extend, inherit, the layout page. In the following example, we have a `mylayout.twig` file where we define three blocks: `head`, `title` and `footer`. 
```php title= "mylayout.twig " lineNumbers= True
<!DOCTYPE html>
<html>

<head>
  <title>{% block title %}{% endblock %} - My Webpage</title>
  {% block block_with_default_content %}
  <link rel="stylesheet" href="style.css" />
  {% endblock %}
  {% block head %}{% endblock %}
</head>

<body>
  <div id="content">
    {% block content %}{% endblock %}
  </div>
  <div id="footer">
    {% block footer %}{% endblock %}
    &copy; Copyright 2011 by <a href="http://domain.invalid/">you</a>.
  </div>
</body>

</html>
```
To embed the theme pages within this layout, we start by extending them. Then we will enject the content into the defined three blocks: `head`, `title` and `footer`.

```js title ="template_page.twig"
{% extends "mylayout.twig" %}

{% block title %}Index{% endblock %}

{% block head %}
<style type="text/css">
  .important {
    color: #336699;
  }
</style>
{% endblock %}

{% block block_with_default_content %}
{{ parent() }}
<div>lets append a new content to our main block</div>
{% endblock %}

{% block content %}
<h1>Index</h1>
<p class="important">
  Welcome to my awesome homepage.
</p>
``` 

## Build a new layout
Building layouts is easy with Twilight; we simply need to create any new layout file inside the folder [`src\views\layouts\`](https://github.com/SallaApp/theme-raed/tree/master/src/views/layouts). This step will make the layout available throughout the theme pages. 

:::tip[]
Note that all of the new files are nothing but `*.twig` files.
:::


The main two steps for building layouts are:
- Create an HTML file, with the extension `*.twig`, that contains the main skeleton of your theme with creating `blocks` inside it for future contents.
- Extend this layout page inside your theme's pages, and enject the content within the predefined `blocks`.

---

## theme-architecture-layouts/Themes-Localizations-Twilight-Documentation-Salla-Docs

# Localizations

Twilight's localization feature makes it simple to extract strings in other languages, allowing Salla theme developers to effortlessly support multiple languages. 


:::info[Information]
In order to help merchants reach more people, Salla has chosen to support multilingual stores. This is a very effective way for them to reach a larger audience.
:::
 


In this article, we will explore the localization:
- [Files location](#localization-files-location)
- [Configuration](#configuration)
- [Translation retrieval](#translation-retrieval)
- [Supported Languages](#supported-languages)

## Localization files location

The localization files, which are JSON based files, are located in the locales directory [`src/locales/`](https://github.com/SallaApp/theme-raed/tree/master/src/locales) and are used to define translation strings. This directory will contain a JSON file for each language supported by the theme. For applications with a large number of translatable strings, this strategy is recommended.
:::info[Information]
Supporting multiple languages is known as **internationalization**, or **i18n** (18 letters separate the i and n). [Twilight i18n](https://github.com/SallaApp/twilight-i18n) provides the developer with access to many translations that are ready made for your Twilight Theme.
:::

:::tip[Note]
You can find a complete list of all the language translation files supported by Twilight [here](https://localazy.com/p/twilight)
:::

Following is the location of the localization files:

```sh
...
└── src 
    ├── locales
      ├── ar.json
      ├── en.json
      .....
      ├── your-language-code.json  
...
```

## Configuration 

The localization file is a list of key-value pairs, e.g. `"Key":"Value"`, that can be found in a JSON string file. A colon sign `:` separates the key and value strings, which are then enclosed by a main key value that groups the key-value pairs according to their intended purpose. Below is a very basic JSON structure with a main key value and a list of key-value pairs for translation.

```js
{
"common": {
  "modal": {
    "remember_my_choice": "لا تذكرني مرة اخرى",
    "note": "ملاحظة",
    "country_code":"كود الدولة",
    "copy_code": "نسخ الكود"
  }
 }
}
```

For example, the localization file for the Arabic language [`locales/ar.json`](https://github.com/SallaApp/theme-raed/blob/master/src/locales/ar.json) can be as follows:

```js
{
  "blocks": {
    "header": {
      "cart": "السلة",
      "login_by_sms": "تسجل الدخول برسالة نصية",
      "login_by_email": "تسجل الدخول بالبريد الإلكتروني"
    },
    "home": {
      "browse_brands": "تصفح من خلال العلامات التجارية"
    }
  }
}
```
<br>

:::tip[Best practices for Localizations]
- 1. All texts should be in 3 levels, eg. level1.level2.level3.
- 2. All keys used on Salla platforms can be found [here](https://localazy.com/p/twilight/phrases/56). In this essential directory, use the search box to find the specific key you need, then click to copy it. Additionally, ensure you incorporate the Localization file into the designated filepath.
:::

### Translation retrieval
For retrieving the translation strings, the developer can simply use the default helper [trans()](https://docs.salla.dev/doc-421929?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) function. This helper translates the passed key to the current store language. Retrieving the translation can be done in different ways:
- Simple key: 
```js
<!-- simple key -->
<span>{{ trans('common.remember_my_choice') }}</span>
```

- Key with variable:
```js
<!-- key with variable -->
<span>{{ trans('blocks.header.cart', ['word' => 'Products']) }}</span>
```
- Key with enforced locale/language:
```js
<!-- key with enforced locale/language -->
<!-- this will always print the result of key in English even if the store has different default language -->
<span>{{ trans('common.titles.orders', [], en) }}</span>
```


:::tip[A thing to know!]
 - Arabic and English Languages should be supported when adding new keys.
 - By default English Language is set as a fallback language.
 - The developer can override, an existing translation, for example override `الإضافة إلى السلة` to `تبرع الآن`. Learn more about overriding process [here](https://github.com/SallaApp/theme-ihsan/blob/master/src/locales/ar.json).
:::

 
### Supported Languages

Following is the list of the supported langauges by Twilight:

|Code|Language|
|----|------|
|ar| العربية|
|en| English|
|sq| shqip|
|hy| հայերէն|
|bg| български|
|zh| 汉语|
|hr| hrvatski|
|cs| čeština|
|da| dansk|
|nl| dutch|
|et| eesti keel|
|fi| suomen kieli|
|fr| français|
|de| Deutsch|
|el| Ελληνικά|
|he| עִבְרִית|‎
|hi| हिन्दी|
|hu| magyar|
|ind| bahasa Indonesia|
|ga|Gaeilge|
|it| italiano|
|ja| 日本語|
|ko| 한국어|
|lv| latviešu|
|mt|Maltese|
|fa| فارسی|
|pl| Polish|
|pt| português|
|ro| română|
|ru| русский|
|sl| slovenščina|
|es|español|
|sv| svenska|
|tl| Tagalog (Filipino)|
|tr| Türkçe|
|uk|украї́нська|
|ur| اُردُو|

:::tip[Educational Clip]

<Video src="https://youtu.be/pXlxVCLu2QA?si=kLvlxWkvur4AKcD0"></Video>

:::

---

## theme-architecture-layouts/Themes-Master-Layout-Twilight-Documentation-Salla-Docs

# Master Layout

The [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig) is the default "layout" which comes with Twilight theme and applies it on all of the theme's pages. It calls many of the main [global variables](https://docs.salla.dev/doc-421938?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). This is to set the main look-and-feel settings for the theme. Below is its location inside the "layouts" folder:

```shell title="src\views\layouts\master.twig"
└── src
  ├── views
  |   ├── layouts
  |   |   ...
  |   |   ├── master.twig
          ...
```

## 📙 What you'll learn

By the end of this article, you will learn about:
- Global variables
- The main blocks of the [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig) layout
- Example of using [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig) layout

<hr>

## Global Variables
The [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig) file is considered the file that sets the shared layout and look-and-feel of the whole website. As a result of that, the developer may call within this master view any [global variable](https://docs.salla.dev/doc-421938?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) or theme setting variable. These values will be used on all of the pages that extend this layout. 

The theme settings variables are part of the [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) file as we can see in the [theme settings](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) section. For example, we have a setting defined as `topnav_is_dark`. The developer may use any of the following methods to retrieve, get, its value: 


```js
...
{{ theme.settings.get("topnav_is_dark") }}
...
```
<hr>

## Main Blocks

The developer has the option to create a new theme's layout. However, it's essential to be inspired by the default master.twig layout file because it shows the main blocks that the developer should include with any new main layout.

The default [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig) layout file includes predefined blocks  used by any page that extends this layout. These blocks are:

- Styles Block: used in pages to inject the needed css-style.
```js
{% block styles %}{% endblock %}
```

- Head Block: used in pages to inject the needed code to be added into the `<head>` section.

```js
{% block head %}{% endblock %}
```

- Content Block: used in pages to inject the needed code to be added into the <body> section.

```js
{% block content %}{% endblock %}
```

- Script Block: used in pages to inject the needed js-script.

```js
{% block scripts %}{% endblock %}
```
<br/>

In addition to the above requirements, it is a must to add some [hooks](https://docs.salla.dev/doc-422552) blocks to the master layout. In general, hooks are Twig tags that can have content injected into the Twilight theme. For example, the following are hooks responsible for adding the SEO-related meta data to the page header section:


```js
<head>
...
{% hook 'head:start' %}
...
{% hook 'head' %}
...
{% hook 'head:end' %}
    
</head>
```

## Usage

By exploring the [`src/views/layouts/master.twig
`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/index.twig) file, which is the [Home Page](https://docs.salla.dev/doc-422558) is of the theme, we can see the following:

```js lineNumbers
{% extends "layouts.master" %}
{% block content %}
    {% component home %}
{% endblock %}
{% block scripts %}
    <script type="text/javascript" defer src="{{ home.js |asset('dist/home.js') }}"></script>
{% endblock %}
```

- Line #1: extending the "layouts.master", which is [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig).
- Lines #2 to #4: injecting the `{% component home %}` inside the block `{% block content %}`. This mean that all of the home-releadted components will be insterted inside the block content as per the layout design of [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig).
- Lines #5-#7: injecting a javascript codes to the page inside this block.


<!---
## Customization
The [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/views/layouts/master.twig) layout is considered The file that sets the main values used within the main layout. For example, the theme language, colors, fonts, etc. Below is a part of the example code:

```js
{{ theme.set('topnav_bg', '') }}
{{ theme.set('topnav_text_color', '') }}
{{ theme.set('topnav_link_hover', '') }}
{{ theme.set('topnav_bg_gradient', false) }}
{{ theme.set('topnav_bg_gradient_from', '#0093E9') }}
{{ theme.set('topnav_bg_gradient_to', '#80D0C7') }}
    

{{ theme.set('mainnav_is_dark', false) }}
{{ theme.set('mainnav_bg', '') }}
{{ theme.set('mainnav_text_color', '') }}
{{ theme.set('mainnav_link_hover', '') }}
```
-->

---

## theme-architecture-layouts/Themes-Salla-Icons-Twilight-Documentation-Salla-Docs

# Salla Icons

**Salla Icons** is an icon library that can be easily integrated into a Twilight theme. It allows developers to add scalable vector icons to their website without the need for additional images. In this article, we'll go over the steps to add Salla Icons to a Twilight theme and show some examples of how to use it.

> To see a full example of the available icons, the developer can check out the following Codepen example <a href="https://codepen.io/CGLion/pen/xxJeQPM">here</a>.


:::tip[A thing to know!]
The above example provides a comprehensive list of the icons available in Salla Icons and demonstrates how to use them in a variety of contexts.
:::


## 📙 What you'll learn

- [How to use Salla Icons](#how-to-use-salla-icons)
- [How to browse Salla Icons in an IcoMoon App](#browsing-salla-icons-in-an-icomoon)
<hr>

## How to use Salla Icons

The first step to using Salla Icons in a Twilight theme is to make sure that icons library's [CSS file](https://cdn.salla.network/fonts/sallaicons.css) in the theme's `head` section. Developer can either link to the CSS file hosted on the Salla Icons website or download it and host it on your own server:

```html
<link rel="stylesheet" href="{{ 'fonts/sallaicons.css'|cdn }}"/>
```

Once the CSS file is linked, you can start using Salla icons on the theme by using the appropriate class names.

:::info[Information]
 **By default**, each Twilight theme includes the Salla Icons library
:::
### Usage

For example, to add a `sicon-discount-calculator` icon, the developer can use the following code:

```html
<i class="sicon-discount-calculator"></i>
```

Developer can also use Salla Icons in conjunction with other HTML elements, such as buttons. For example, to create a "Add to Cart" button with a shopping cart icon `sicon-add-to-cart`, you can use the following code:

```html
<button>
  <i class="sicon-add-to-cart"></i> Add to Cart
</button>
```

Developer can also use Font Salla Icons with liquid variables, for example, to show the number of items in the cart:

```html
<span class="sicon-cart"></span> {{ cart.items|length }} items
```

## Browsing Salla Icons in an IcoMoon

Salla Icons can be browsed and used from IcoMoon, a popular online icon library and tool for creating custom icon fonts. First, visit [IcoMoon](https://icomoon.io/), and then follow the following steps:

1. Download the Salla Icons Library from [here](https://cdn.salla.network/fonts/lib/sallaicons/sallaicons.svg).  **Note:** Click "s+ctrl" in windows or "Cmd -t" in Mac OS, to save the file locally.
2. Inside IcoMoon, go to [IcoMoonApp](https://icomoon.io/app/#/select).
3. Click on `Import Icon` on the upper left of the page.
4. Import the file downloaded in step 1.
5. Choose the Icons you wish to use by clicking on the Icon. The selected Icons will chage color if selected.
<!--
focus: false
-->
![image.png](https://cdn.salla.network/docs/twilight/4/salla-icons-01.png?v=1-10-2022)
<!--
focus: false
-->
7. Click on `Generate Font F` on th bottom right of the page
<!--
focus: false
-->
![image.png](https://cdn.salla.network/docs/twilight/4/salla-icons-02.png?v=1-10-2022)
<!--
focus: false
-->
8. Click on `prefrences` to enter a prefix
<!--
focus: false
-->
![image.png](https://cdn.salla.network/docs/twilight/4/salla-icons-03.png?v=1-10-2022)
<!--
focus: false
-->
9. Enter prefix `"sicon-"`
<!--
focus: false
-->
![image.png](https://cdn.salla.network/docs/twilight/4/salla-icons-04.png?v=1-10-2022)

10. Click `Download` to download the zip file for the Icons
<!--
focus: false
-->
![image.png](https://cdn.salla.network/docs/twilight/4/salla-icons-05.png?v=1-10-2022)

11. Extract the floder

12. Open Demo file, which will display the list of Icons with Salla Icon prefix
<!--
focus: false
-->
![image.png](https://cdn.salla.network/docs/twilight/4/salla-icons-06.png?v=1-10-2022)

The list of Salla Icons are now available for the developer to use in the themes.

---

## theme-architecture/Components

# Components

## Docs

- [Overview](https://docs.salla.dev/422580m0.md): In general, _components_ are independent and reusable bits of code. **Twilight** theme defines a number of _components_ in [`src/views/components/`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components) that have properties with strict typing and default values. A property is only required if you mark it required. You can set default values otherwise.
- [Home Components](https://docs.salla.dev/849333f0.md): 
- [Product Components](https://docs.salla.dev/849335f0.md): 
- [Common Components](https://docs.salla.dev/849334f0.md):

---

## theme-architecture/Layouts

# Layouts

## Docs

- [Overview](https://docs.salla.dev/421943m0.md): Layouts are considered the foundation for Salla theme, through which all of the [theme pages](doc-422556?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) will share the same [layout](https://docs.salla.dev/doc-422576?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). When building a Salla theme, you will need to start by planing for your layouts, so then you can use them to unify your pages' look-and-feel.
- [Master Layout](https://docs.salla.dev/421944m0.md): The [`master.twig`](https://github.com/SallaApp/theme-raed/blob/master/src/views/layouts/master.twig) is the default "layout" which comes with Twilight theme and applies it on all of the theme's pages. It calls many of the main [global variables](https://docs.salla.dev/doc-421938?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). This is to set the main look-and-feel settings for the theme. Below is its location inside the "layouts" folder:
- [Global Variables](https://docs.salla.dev/421938m0.md): 
- [CSS Variables](https://docs.salla.dev/421945m0.md): Theme **CSS variables** allow the themes style to be modified by altering the font type and color code. This step provides options for the developer to apply changes on the Themes as well as enabling them using the Theme features in [Salla Partners Portal](https://salla.partners/). The **CSS variables** can be placed in the pages the developer wants to apply the styles on, or it can be placed in the master layout.
- [Salla Icons](https://docs.salla.dev/422550m0.md): **Salla Icons** is an icon library that can be easily integrated into a Twilight theme. It allows developers to add scalable vector icons to their website without the need for additional images. In this article, we'll go over the steps to add Salla Icons to a Twilight theme and show some examples of how to use it.
- [Custom Fonts](https://docs.salla.dev/422551m0.md): Adding your own custom icons to your theme development is a straightforward process that can be accomplished in just three easy steps. This will give your theme a more unique and personalized feel. In this article, we will walkthrough how to add  [icomoon](https://icomoon.io/) icons.
- [Hooks](https://docs.salla.dev/422552m0.md): Hooks are a powerful tool used in theme development for the [Salla Store Theme](https://s.salla.sa/marketplace/themes/tag-all). They allow developers to inject code and content into specific areas of a webpage's template without having to modify the original code. For example, adding meta-data and SEO-related tags into a webpage's `<head>` section. These pieces of code can be "hooked" to the theme by calling them using the template's _hooks_.
- [Localizations](https://docs.salla.dev/422553m0.md): Twilight's localization feature makes it simple to extract strings in other languages, allowing Salla theme developers to effortlessly support multiple languages.

---

## theme-architecture/Pages

# Pages

## Docs

- [Overview](https://docs.salla.dev/422556m0.md): Twilight theme engine comes with pre-defined list of pages that form together the Salla theme pages.
- [Home Page](https://docs.salla.dev/422558m0.md): The [`home page template`](https://github.com/SallaApp/theme-raed/blob/master/src/views/pages/index.twig) renders the first page which the customer encounters. This page is essential to give the first impact of the store's look-and-feel. The main store attractions are located on this page to showcase the ease of accessibility to go around the store. 
- [Product Pages](https://docs.salla.dev/849311f0.md): 
- [Customer Pages](https://docs.salla.dev/849314f0.md): 
- [Blog Pages](https://docs.salla.dev/849315f0.md): 
- [Brand Pages](https://docs.salla.dev/849319f0.md): 
- [Common Pages](https://docs.salla.dev/849323f0.md):

---

