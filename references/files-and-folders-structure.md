# Files And Folders Structure

## Table of Contents

- [files-and-folders-structure/Themes-Directory-Structure-Twilight-Documentation-Salla-Docs](#files-and-folders-structure-themes-directory-structure-twilight-documentation-salla-docs)
- [files-and-folders-structure/Twilight.json-Twilight-Documentation-Salla-Docs](#files-and-folders-structure-twilight.json-twilight-documentation-salla-docs)

---

## files-and-folders-structure/Themes-Directory-Structure-Twilight-Documentation-Salla-Docs

# Directory structure

Salla theme is a collection of files and folders that define the theme's presentation layer. 

## 📙 What you'll learn
This article lists the files and folders that are found in a typical Salla theme.
<hr>

## Theme Directory Structure

<pre>
[root]
...
+---scr
    +---assets
    |   +---images      
    |   +---js      
    |   +---styles         
    +---locales
    |       ar.json
    |       en.json
    +---views
        +---components
        |   +---footer
        |   +---header
        |   +---home
        |   +---product
        |   comments.twig
        +---layouts
        |       master.twig
        +---pages
            |   cart.twig
            |   index.twig
            |   loyalty.twig
            |   page-single.twig
            |   thank-you.twig
            +---blog
            |       index.twig
            |       single.twig 
            +---brands
            |       index.twig
            |       single.twig 
            +---customer
               |   notifications.twig
               |   profile.twig
               |   wishlist.twig
               +---orders
               |      index.twig
               |      single.twig
            +---product
            |       index.twig
            |       single.twig     
 </pre>

---

## files-and-folders-structure/Twilight.json-Twilight-Documentation-Salla-Docs

# Twilight.json

The [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) file is included within the Twilight theme, and it is placed in the root directory. This setup file contains the main theme's information, features and components for the rendering purpose that occurs on the Theme. Use [Salla Partners Portal](https://salla.partners) to conduct visual modifications that includes [Theme settings](https://docs.salla.dev/apis/doc-421879), [Theme features](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), and [Theme components](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
In this article, we will explore the different parts of the [`twilight.json`](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) file.

## 📙 What you'll learn

- [Author settings](#author-settings)
- [Theme settings](#theme-settings)
- [Theme features](#theme-features)
- [Theme components](#theme-components)

<hr>
 
## Author settings

These settings contain both the theme owner and the theme basic information. That includes details about the `version`, `theme_name`, `repo_url`, and theme `support_url`, which is also included in the settings:
<Tabs>
    <Tab>
```json title=".\twilight.json"
{
  "version": "1.0.0",
  "theme_name": "Theme One",
  "repo_url": "https://github.com/SallaApp/theme-raed",
  "support_url": "https://salla.dev"
  ...
}
```
   </Tab>
    </Tabs>
    
:::tip[Educational Clip]
<Video src="https://www.youtube.com/watch?v=97k3NJLS_Q0&list=PLeAh6geWgZi3YdWKZAnG1leDuenBlCa_7&index=17"></Video>
:::

## Theme settings

The theme settings store information about global values that can be used anywhere in the theme. These values can be defined by their `type`, `label`, `id`, and `format`.

In the following example, there are two setting definitions:

- The first is for a boolean value with a `switch` format, which by default is not selected.
- The second setting is for a string value that represents the path to the theme's default image placeholder for any image.

<Tabs>
    <Tab>
        
```json title=".\twilight.json"
{
  ...
  "settings": [
      {
        "type": "boolean",
        "label": "شريط علوي داكن",
        "id": "topnav_is_dark",
        "format": "switch",
        "selected": false
      },
      {
        "type": "string",
        "id": "placeholder",
        "format": "hidden",
        "value": "images/img_placeholder.png"
      }
    ],
  ...
}
```
  </Tab>
    </Tabs>


### Retrive the theme setting values

There are several methods to retrieve, or get, the stored values of any of the theme settings. For example, in the below code, we have a setting defined as `topnav_is_dark`. This setting can be accessed by using any of the following methods:
<Tabs>
    <Tab>
        
```php
...
{{ theme.settings.get("topnav_is_dark") }}
...
```
</Tab>
    </Tabs>
    
:::tip[Educational Clip]
<Video src="https://youtu.be/7qazthdzXXg?si=7rJlqIoetwIYCiuT"></Video>
:::

## Theme Features

This part of the [twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) lists the theme features, which are [pre-defined components](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). It is a group of built-in components that come with Twilight for the [Home Page](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).


:::tip[Note]
As a best practice, ensure to use the [Theme features](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) which brings a smoother experience for all [Salla merchants](https://salla.sa).
:::



The Theme features components' names have the prefix `component-` inside twilight.json, and include only the components that are supported in your theme.

```json title=".\twilight.json"
{
  ...
  "features": [
      ...
      "component-featured-products",
      "component-fixed-banner",
      "component-fixed-products",
      "component-photos-slider",
      "component-products-slider",
      "component-parallax-background",
      "component-random-testimonials",
      "component-testimonials",
      "component-square-photos",
      "component-store-features",
      "component-youtube",
      "filters"
    ]
  ...
}
```
:::tip[Educational Clip]

<Video src="https://youtu.be/jDff8tr2gwY?si=ENpnfw2dI8_YwA9l"></Video>

:::

## Theme components

In addition to the [Theme features](#theme-features), which are the pre-defined components, the twilight.json file lists a group of [Theme Component(s)](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). These components are custom-built by the developer for the [Home Page](doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM). The developer has the option to use own, new, and [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) as per the store’s requirements.

The following is an example of a newly created Theme component, aka [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), named `custom-slider`.
As per the example, the `path` of this new component is mentioned in `"path": "home.custom-slider"`.
This means that the new component is located inside `views\components\home\custom-slider.twig`.
The developer has the option of creating components anywhere within the [`views\components\folder`](https://github.com/SallaApp/theme-raed/tree/master/src/views/components).

```json title=".\twilight.json"
{
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
}
```
:::tip[Educational Clip]

<Video src="https://youtu.be/-MYfQvgvSdo?si=t_BjjGNOJ477Z07Y"></Video>
:::

---

