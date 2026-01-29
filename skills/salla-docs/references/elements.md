# Elements

## Table of Contents

- [elements/Salla-App-Icons-Salla-Storefront-Twilight-Documentation-Salla-Docs](#elements-salla-app-icons-salla-storefront-twilight-documentation-salla-docs)
- [elements/Salla-Bread-Crumb-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-bread-crumb-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Color-Picker-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-color-picker-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Conditional-Fields-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-conditional-fields-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Count-Down-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-count-down-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Filters-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-filters-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Infinit-Scroll-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-infinit-scroll-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-List-tile-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-list-tile-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Loading-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-loading-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Placeholder-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-placeholder-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Progress-Bar-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-progress-bar-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Rating-Star-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-rating-star-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Reviews-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-reviews-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Reviews-Summary-Component-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-reviews-summary-component-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Sheet-Component-Guide-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-sheet-component-guide-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Skeleton-Component-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-skeleton-component-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Slider-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-slider-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Social-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-social-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Social-Share-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-social-share-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-Tabs-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-tabs-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-map-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-map-salla-storefront-web-components-twilight-documentation-salla-docs)
- [elements/Salla-modal-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#elements-salla-modal-salla-storefront-web-components-twilight-documentation-salla-docs)

---

## elements/Salla-App-Icons-Salla-Storefront-Twilight-Documentation-Salla-Docs

# Apps Icons

 
The `<salla-apps-icons>` web component allows users to display Google Play Store and Apple store icons to download the store's apps.

## Example 
![](https://cdn.salla.network/docs/twilight/6/js-web-app-icon-01.png)

## Usage

<Tabs>

  <Tab title="HTML">

```html
<salla-apps-icons apps-title=“Icon 101” hide-title=“false” vertical=“true”>
</salla-apps-icons>
```

  </Tab>

  <Tab title="SASS">

This JS web component can be targeted for styling by its `:host` class. Following is a complete source code for customizing this component:

```js
:host {
    display: block;
}
```
  </Tab>

</Tabs>

## Properties

| Property	| Attribute	| Description                      	| Type  	| Default 	|
| ----------- | ------------ | ------------------------------------ | --------- | ----------- |
| Apps' Title | `apps-title` | The title to display.            	| `string`  | `undefined` |
| Hide Title | `hide-title` | Flag to show or hide title.      	| `boolean` | `undefined` |
| Vertical  | `vertical`   | Display flag to horizontal/vertical. | `boolean` | `undefined` |


## Slots
The`slots` makes it customizable to modify certain labels, such as `app`.

| Slot	| Description                                              	|
| ------- | ------------------------------------------------------------ |
| `app` | Replaces the slot with properties such as `icon` and `name`. |

---

## elements/Salla-Bread-Crumb-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Breadcrumb

The `<salla-breadcrumb>` web component is used as a navigational helper and hierarchy for pages. Breadcrumbs are used as a high-level representation of where users have navigated. Users can click the pages' texts to go back to previous pages.

## Example

<!--
focus: false
-->

![Alt text](https://cdn.salla.network/docs/twilight/6/js-web-breadcrumbs-01.png)


## Usage


<Tabs>
  <Tab title="HTML">
      
      
<Tabs>
  <Tab title="Simple Example">

```html
  <salla-breadcrumb></salla-breadcrumb>
```
      
  </Tab>
    
  <Tab title="Advanced Example | Using `slots`">

```html
<salla-breadcrumb>
   <div slot="item">
     <salla-button fill="outline" color="success" href={url}>{title}</salla-button>
   </div>
   <i slot="icon" class="sicon-cancel"></i>
 </salla-breadcrumb>
```
  </Tab>
</Tabs>


  </Tab>
  <Tab title="SASS">
 This JS web component can be targeted for styling by its `:host` class. Following is a complete source code for customizing this component:

```js
:host {
  display: block;
}
```
  </Tab>

</Tabs>


<!--
type: tab
title: TWIG
-->




<!--
type: tab
title: SASS
-->




<!-- type: tab-end -->


<!-- ## Properties

| Property | Attribute | Description | Type    | Default |
| -------- | --------- | ----------- | ------- | ------- |
| Items     | `items`    | Breadcrumb items in an array of object where you specify the page title and URL        | `string` |`undefined`| -->


## Slots
The`slots` makes it customizable to modify certain labels, such as `icon`.

| Slot   | Description |
| ------ | ----------- |
| `icon` | Replaces the breadcrumb arrow icon with a customized icon. Find a list of Salla Icons [here](https://docs.salla.dev/docs/twilight-themes-documentation/5ace16b196fa5-salla-icons)        |
| `item` | Replaces breadcrumb item, with replaceable props which are `{url}`, `{title}`.|

:::info[Note]
Breadcrumbs in your theme configuration are managed with the following method: 
`salla.config.get('theme.settings.is_breadcrumbs_enabled')` to toggle their visibility.

Once enabled in your theme, breadcrumbs are automatically generated based on the `previous` page or by retrieving the parent page using: 
`salla.config.get('page.parent')`.

:::

---

## elements/Salla-Color-Picker-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Color Picker

The `<salla-color-picker>` web component is used to select a color using a variety of input methods in a [pop-up modal](https://docs.salla.dev/doc-422714?nav=01HNFTE06J4QC24T0D5BPRYKMD). Listen to events when the user changes the color or when the modal is either closed, open, or the chosen color has been submitted. Several methods can be used as well as customizable properties.



## Example

<!--focus: false -->

![Color Picker](https://cdn.salla.network/docs/twilight/6/js-web-color-picker-01.jpeg)

## Usage



<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Color Picker component usage -->
<salla-color-picker
  format="hex"
  required="true">
</salla-color-picker>
```
  </Tab>
  
</Tabs>


## Properties

| Property           | Attribute            | Description                                                                                                                                             | Type                                                | Default     |
| ------------------ | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- | ----------- |
| Color            | `color`              | The initial color for the color picker component.                                                                                                       | `string`                                            | `'#5dd5c4'` |
| Enable Alpha      | `enable-alpha`       | Whether or not to enable the adjustment of the alpha channel.                                                                                           | `boolean`                                           | `false`     |
| Format           | `format`             | Displays the color picker component in a specific satndard coloring format.                                                                             | `"hex" \| "hsl" \| "rgb"`                           | `'hex'`     |
| Name           | `name`             | File input name for the native `formData`                                                                             | `string`                           | `'color'`     |
| Required           | `required`             | Whether or not to set the color picker to be required                                                                             | `boolean`                           | `false`     |
| Show Cancel Button | `show-cancel-button` | Whether or not to have a "Cancel" button, which closes the popup modal.                                                                                 | `boolean`                                           | `false`     |
| Show Text Field    | `show-text-field`    | Whether or not to show a text field for the color value when being edited.                                                                              | `boolean`                                           | `true`      |

## Events


| Event          | Description                                                          | Type                 |
| -------------- | -------------------------------------------------------------------- | -------------------- |
| `colorChanged` | This event will be fired when the color changes.                        | `CustomEvent<Color>` |
| `popupClosed`  | This event will be fired when the popup modal closes.                   | `CustomEvent<Color>` |
| `invalidInput`  | This event will be fired when the input is invalid.                   | `CustomEvent<any>` |
| `popupOpened`  | This event will be fired when the popup modal opens.                    | `CustomEvent<Color>` |
| `submitted`    | This event will be fired when the user clicks on the "Ok" button label. | `CustomEvent<Color>` |

## Methods
The pre-defined methods `allow` for calling functions built by Salla to carry out certain actvities, such as `openPicker` which shows or opens the color picker modal.


| Method                                                                 | Description                                                                                                                 | Return Type     |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------- |
| `openPicker()`                                                         | Shows / opens the color picker modal.                                                                                       | `Promise<void>` |
| `closePicker()`                                                        | Closes / hides the color picker modal.                                                                                      | `Promise<void>` |
| `destroyPicker()`                                                      | Releases all resources used by the color picker instance.                                                                   | `Promise<void>` |
| `movePopUp(options: Options, openImmediately: boolean) `               | Moves the popup modal to a different parent class. It also has option of opening the component at the same time.            | `Promise<void>` |
| `setColorValue(color: string, triggerEvent: boolean)` | Sets / initializes the color picker component's color, which includes the Color name in RGBA/HSLA/HEX string or RGBA array. | `Promise<void>` |
| `setPickerOption(options: Options) `                                   | Sets the color picker component's options.                                                                                  | `Promise<void>` |

---

## elements/Salla-Conditional-Fields-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Conditional Fields

The `<salla-conditional-fields>` web component allows for hiding / displaying certain features in a product, such as size, where it only works if the product has, for instance, a specific value for the color.

## Example

![Conditional Fields](https://cdn.salla.network/docs/twilight/6/js-web-conditional-fields-01.gif)

<Tabs>
  <Tab title="HTML">
      
```html
<salla-conditional-fields>
    {% hook 'product:single.form.start' %}
         // options available
    {% hook 'product:single.form.end' %}
</salla-conditional-fields>
```
  </Tab>
  
</Tabs>

---

## elements/Salla-Count-Down-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Count Down

The `<salla-count-down>` web component is used to show the amount of time left until a given date. It's perfect for tracking important events, or counting down to special occasions like birthdays and anniversaries. It displays the days, hours, minutes, and seconds left with an easy-to-read countdown timer, as well as customized color, size, and labeled text properties.



## Example

<!--focus: false -->
![Count Down](https://cdn.salla.network/docs/twilight/6/js-web-countdown-01.png)

## Usage
<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Count Down component usage -->
<salla-count-down
  color="#baf2e5"
  boxed=true
  digits="en"
  size="md">
</salla-count-down>
```
  </Tab>
  <Tab title="SASS">
 
This JS web component can be targeted for styling by its `.s-count-down` class. Following is a complete source code for customizing this component:

```css
.s-count-down{
  &-wrapper{
    
  }
  &-boxed{

  }
  &-ended{
    
  }
  &-list{

  }
  &-item{

  }
  &-item{
    &-value{

    }
    &-label{

    }
  }
  &-end-text{

  }
}
```
     
  </Tab>
  
</Tabs>


## Properties

| Property | Attribute  | Description                                                                                                | Type                             | Default     |
| -------- | ---------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------- | ----------- |
| Boxed    | `boxed`    | The count down numbers will appear in boxes, if the value is set to `true`. | `boolean`                        | `undefined` |
| Color    | `color`    | The color of the count down. | `"dark" \| "light" \| "primary"` | `'dark'`    |
| Date     | `date`     | The count down date format, which is the following: MMM DD, YYYY HH:mm:ss. (Example: Jan 2, 2023 16:37:52). | `string`                         | `undefined` |
| Digits   | `digits`   | The digits language format standard to show in the count down. | `"auto" \| "en"`                 | `'auto'`    |
| End of Day  | `end-text` | the count down will end at the end of the day, if value set to `true`. | `boolean`                         | `undefined` |
| End Text  | `end-text` | The text to show when the count down ends. | `string`                         | `undefined` |
| Labeled  | `labeled`  | Shows labels for each count down number. | `boolean`                        | `undefined` |
| Size     | `size`     | The count down size. | `"lg" \| "md" \| "sm"`           | `'md'`      |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `endCountDown` which ends the cound down set by the developer.


| Method           | Description         | Return Type     |
| ---------------- | ------------------- | --------------- |
| `endCountDown()` | Ends the count down. | `Promise<void>` |

---

## elements/Salla-Filters-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Filters

The `<salla-filters>` web component is used to filter data in a variety of ways, such as by text, by date, or by number. They can also be used to filter data based on the user's input. They are easy to use and can be customized to meet the specific needs of the Theme.



## Example

<!--focus: false -->
![Filters image](https://cdn.salla.network/docs/twilight/6/js-web-filters-01.jpg)

<br>

:::caution[Alert]
It is important to **ensure** adding the filters component in the [Twilight.json](https://github.com/SallaApp/theme-raed/blob/master/twilight.json) file, for the component to work when calling the `<salla-filters>` web component. **Skipping this step could lead to the component's inability to work**.
:::

## Usage
<Tabs>
  <Tab title="HTML">
     
```html
<!-- Basic Filters component usage -->
<salla-filters
    filters='[{
      "label":"by brand",
      "key":"categories",
      "inputType":"checkbox",
      "type":"variants",
      "value":[{
      "key":"114",
      "count":2,
      "value":"abc",
      "from":"*",
      "to":"*"}]
      }]'>
</salla-filters>
```
      
  </Tab>
 
  <Tab title="SASS">
      
This JS web component can be targeted for styling. Following is a complete source code for customizing this component:

```css
:host {
  display: block;
}

.s-rating-stars-small {
  line-height: 12px;
}
.s-filters-radio{
  background-image: none !important;
}
```

  </Tab>
  

</Tabs>

## Properties

| Property | Attribute  | Description                                                                                                | Type                             | Default     |
| -------- | ---------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------- | ----------- |
| Filters    | --    | Lists down the filter values  | `Filter[]` | `undefined` |

## Events

| Event                    | Description                                                 | Type               |
| ------------------------ | ----------------------------------------------------------- | ------------------ |
| `changed` | This event will be fired when the selected filter changes in its value | `CustomEvent<any>` |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `getFilters` which gets the data for filtering.


| Method           | Description         | Return Type     |
| ---------------- | ------------------- | --------------- |
| `applyFilters()` | Applies a filter to a view.  | `Promise<void>` |
| `getFilters()` | Gets the data that is available for filtering.  | `Promise<object>` |
| `resetFilters()` | Resets the selected filter to its default state. | `Promise<void>` |

---

## elements/Salla-Infinit-Scroll-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Infinite Scroll

The `<salla-infinite-scroll>` web component allows for infinite scrolling to load content continuously as the user scrolls down the page, eliminating the need for pagination, and that can be customized using the properties' parameters available.

## Example

<!--
focus: false
-->

![Infinite Scroll](https://cdn.salla.network/docs/twilight/6/js-web-infinite-scroll-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">


```html
<!-- infinite Scroll Settings-->
<salla-infinite-scroll
  next-page="infinit-scroll.html?page=2"
  container=".container"
  item=".item"
  next-page.autoload
>
  <!--  container Class Selector-->
  <div class="container">
    {% for product in products %} <!-- inner Item Class Selector -->
    <div class="item">
      <p>{{ product.image }}</p>
      <p>{{ product.name }}</p>
      <p>{{ product.price }}</p>
    </div>
    {% endfor %}
  </div>
</salla-infinite-scroll>
```
  </Tab>
    
  <Tab title="SASS">
      
This JS web component can be targeted for styling by its `.s-infinite-scroll` class. Following is a complete source code for customizing this component:

```js

.s-infinite-scroll {
  &-wrapper {

  }
  // last & error message wrapper.
  &-status{

  }
  // the message that displys after reaching the last page.
  &-last {

  }
  // the message that displys if there is an error on loading
  &-error {

  }
  // Load more button
  &-btn{
    // button text
    &-text{

    }
    // spinner loader
    &-loader{

    }
  }
}
```

  </Tab>
  
</Tabs>




:::tip[Note]
You may set the property `autoload` to be `true` for loading content as customers scroll through the content, or set it to `false` and add a [Button Component](Button.md) to activiate the content auto-scrolling capability.
:::


<!-- Auto Generated Below -->

## Properties

| Property  | Attribute   | Description                                                                             | Type      | Default                          |
| --------- | ----------- | --------------------------------------------------------------------------------------- | --------- | -------------------------------- |
| Autoload  | `autoload`  | Whether or not to autoload the next page's content when scrolling to its view           | `boolean` | `'false'`                        |
| Container | `container` | Class selector to know if the container is or is not the host `<salla-infinite-scroll>` | `string`  | `'.s-infinite-scroll-container'` |
| Item      | `item`      | Class selector to list items                                                            | `string`  | `'salla-infinite-scroll > *'`    |
| Load More Text | `load-more-text` | Informs the user that more data is available, and to prompt them to click on the button to load it.                                                                              | `string`  | `undefined`                   |
| Next Page | `next-page` | Loads content from a next page path URL                                                 | `string`  | `''`                             |

---

## elements/Salla-List-tile-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# List Tile

The `<salla-list-tile>` web component is used to display listing items in a tile form, which is one of the popular ways used in E-commerce. List tile component allows this style of display to be applied while supporting various properties and slots to customize the component.

## Example

<!--
focus: false
-->

![List Tile](https://cdn.salla.network/docs/twilight/6/js-web-list-tile-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
 
```html
<!-- Basic List Tile component usage -->
<salla-list-tile href="https://salla.dev">
  
  <div slot="icon">
    <img class="user-avatar" src="https://salla.dev/image" alt="">
  </div>

  <div slot="title">
    <div>Title</div>
  </div>

  <div slot="subtitle">
    <div class="">Content</div>
  </div>

  <div slot="action">
    <salla-button>Learn more</salla-button>
  </div>

</salla-list-tile>
```     
  </Tab>
  
</Tabs>


## Properties

| Property | Attribute | Description                                                                                | Type                                                        | Default     |
| -------- | --------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------- | ----------- |
| Href     | `href`    | Designates the component as anchor and applies the `href` attribute.                       | `string`                                                    | `undefined` |
| Target   | `target`  | Designates the `target` attribute. This should only be applied when using the `href` prop. | `"_blank" \| "_parent" \| "_self" \| "_top" \| "framename"` | `"_self"`   |

## Slots
The`slots` makes it customizable to modify certain labels, such as `action`.

| Slot         | Description                                   |
| ------------ | --------------------------------------------- |
| `action`   | An element to display after the title.        |
| `icon`     | An icon to display before the title.          |
| `subtitle` | Additional content displayed below the title. |
| `title`    | The primary content of the list tile.         |

---

## elements/Salla-Loading-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Loading

The `<salla-loading>` web component is used to convey that some data is currently loading to the user, and that can be customized using the properties' parameters available.

## Example

<!--
focus: false
-->

![Loading](https://cdn.salla.network/docs/twilight/6/js-web-loading-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
 
```html
<!-- Basic Loading component usage -->
<salla-loading
  size="120"
  width="16"
  color="pink"
  bg-color="black">
</salla-loading>
```
     
  </Tab>
  
  <Tab title="SASS">
   
This JS web component can be targeted for styling by its `.s-loading` class. Following is a complete source code for customizing this component:

```css
.s-loading {
  animation: spin 1s linear infinite;
  fill: var(--color-primary)
}

.s-loading-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```
   
  </Tab>
  
</Tabs>

## Properties

| Property  | Attribute  | Description                                           | Type               | Default     |
| --------- | ---------- | ----------------------------------------------------- | ------------------ | ----------- |
| Background Color | `bg-color` | Spinner background color.                             | `string`           | `"#e5e7eb"` |
| Color   | `color`    | Spinner content color.                                | `string`           | `undefined` |
| Size    | `size`     | Sets the diameter of the circle in pixels.            | `number \| string` | `32`        |
| Width   | `width`    | Sets the stroke of the circle, aka border, in pixels. | `number \| string` | `2`         |

---

## elements/Salla-Placeholder-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Placeholder

The `<salla-placeholder>` web component is used to reserve space for content that soon will appear in a layout soon. It may include a paragraph, a header, and an image, depending on the content type. It emphasizes that the content is to be loaded and can be customized using the properties' parameters available.

<!-- Available Endpoints 

- 1
- 2
- 3 -->

## Example

<!--
focus: false
-->
![Placeholder Image](https://cdn.salla.network/docs/twilight/6/js-web-placeholder-01.png)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Placeholder component usage -->
<salla-placeholder icon="s-icon inbox" icon-size="md" alignment="center">
  <span slot="title">No orders found</span>
  <span slot="description">Oh! You have not ordered yet!</span>
</salla-placeholder>
```

  </Tab>
  
</Tabs>


## Properties

| Property  | Attribute   | Description                                   | Type                                   | Default |
| --------- | ----------- | --------------------------------------------- | -------------------------------------- | ------- |
| Alignment | `alignment` | Defines the alignment of contents.            | `"center" \| "left" \| "right"`        | `left`  |
| Icon      | `icon`      | Customizes the icon to display in SVG format. | `string`                               | `Inbox` |
| Icon Size | `icon-size` | Adjusts the size of the icon.                 | `"lg" \| "md" \| "sm" \| "xl" \| "xs"` | `"md"`  |

## Slots
The`slots` makes it customizable to modify certain labels, such as `description`.

| Slot            | Description                                   |
| --------------- | --------------------------------------------- |
| `description` | Additional content displayed below the title. |
| `title`       | The primary content of the placeholder.       |

---

## elements/Salla-Progress-Bar-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Progress Bar

The `<salla-progress-bar>` web component is used to convey data visually to users. It is also designed to help users quickly interpret numerical data at a glance, and can be customized according to the color and unit of the bar, as well as the unit, value, and textual representation. 

## Example

<!--
focus: false
-->

![Progress Bar](https://cdn.salla.network/docs/twilight/6/js-web-progress-bar-01.png?v=1-10-2022)

## Usage

<Tabs>
  <Tab title="HTML">
 
```html
<!-- Basic Salla Progress Bar component Usage -->
<salla-progress-bar
  color="#baf2e5"
  header="Points Left"
  value="100">
</salla-progress-bar>
```

  </Tab>
  <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-progress-bar` class. Following is a complete source code for customizing this component:

```css
.s-progress-bar{
  &-header{
    font-size: 0.875rem;
    line-height: 1.25rem;
    color:#6b7280;
    font-weight: bold;
  }
  &-target-section {
    display: flex;
    margin-bottom: 0.625rem;
    font-size: 0.875rem;
    line-height: 1.25rem;
    justify-content: space-between;
  }

  &-container {
    margin-bottom: 0.625rem;
  }

  &-wrapper {
    background-color: #E5E7EB;
    width: 100%;
    height: 0.625rem;
    border-radius: 9999px;
    margin-bottom: 0.375rem;
  }

  &-progress {
    // background-color: #5dd5c4;
    height: 0.625rem;
    border-radius: 9999px;
  }

  &-message {
    color: #a2a8b4;
    font-size: 0.75rem;
    line-height: 1rem;
    display: block;
    margin-bottom: 0.625rem;
  }
}
``` 
  </Tab>
</Tabs>


## Properties

| Property | Attribute  | Description                                                                                                                                                                                                         | Type                 | Default                                              |
| -------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | ---------------------------------------------------- |
| Color    | `color`    | Progress bar color.                                                                                                                                                                                                 | `string`             | `salla.config.get('theme.color.primary', "#ffd5c4")` |
| Donation | `donation` | Pass the Donation object as a JSON string in the following format: `{"target_message":null,"target_date":"2023-04-18","target_end_date":"2023-04-18","target_amount":400,"collected_amount":380,"can_donate":true}` | `Donation \| string` | `undefined`                                          |
| Header   | `header`   | Header Title that appears before the progress bar.                                                                                                                                                                  | `string`             | `undefined`                                          |
| Height   | `height`   | Sets the height for the wrapper.                                                                                                                                                                        | `string`             | `"10px"`    |
| Message  | `message`  | Subtitle text that comes under the progress bar or instead of it if the `target` is not set.                                                                                                                        | `string`             | `undefined`                                          |
| Stripped | `stripped` | A stripped effect for the progress bar.                                                                                                                                                              | `boolean`            | `undefined` |
| Target   | `target`   | Progress bar's goal.                                                                                                                                                                                                | `number`             | `undefined`                                          |
| Unit     | `unit`     | The unite to be added after the numbers.                                                                                                                                                                            | `string`             | `salla.config.currency().symbol`                     |
| Value    | `value`    | The progress so far as of the goal.                                                                                                                                                                                 | `number`             | `undefined`                                          |

---

## elements/Salla-Rating-Star-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Rating Stars

This web component is used to display a form of rating scale using a star glyph or similar typographic symbol that is customizable in terms if `name`, `size`, and `value`, and that can be customized using the properties' parameters available.

## Example

<!--
focus: false
-->

![Rating Stars Example](https://cdn.salla.network/docs/twilight/6/js-web-rating-stars-01.gif)

## Usage
<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Rating Stars component usage -->
<salla-rating-stars
  name="large"
  size="large">
</salla-rating-stars>
```

  </Tab>
  <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-rating-stars` class. Following is a complete source code for customizing this component:

```js
.s-rating-stars{
  &-wrapper{

  }
  &-btn-star{

  }
  &-large{
    
  }
  &-medium{
    
  }
  &-small{
    
  }
  &-hovered{
    
  }
  &-selected{

  }
}
```
      
  </Tab>  
</Tabs>

## Properties

| Property | Attribute | Description                                    | Type     | Default     |
| -------- | --------- | ---------------------------------------------- | -------- | ----------- |
| Name     | `name`    | Sets the input name                            | `string` | `'rating'`  |
| Reviews     | `reviews`    | Number of reviews to display.                            | `number` | `'0'`  |
| Size     | `size`    | Adjusts the height and width of the component to fixed, standardized size. | `"large" \| "medium" \| "mini" \| "small"` | `'medium'`  |
| Value    | `value`   | Controls the numbers of rating stars           | `number` | `undefined` |

---

## elements/Salla-Reviews-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Reviews

The `<salla-reviews>` web component displays a vertically scrollable reviews, which you can customize its data source using the properties available.

:::tip[API Usage]
Learn more about the Reviews API usage from [here](https://docs.salla.dev/doc-705836?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::

## Example

<!--
focus: false
-->


![Reviews Component](https://cdn.salla.network/docs/twilight/6/js-web-reviews.png)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<salla-reviews><salla-reviews/>
```
  </Tab>      
  
</Tabs>



## Properties

| Property         | Attribute          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Type                                                       | Default     |
| ---------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- | ----------- |
| Display All Link | `display-all-link` | Controls the visibility of a link to the reviews page. When set to `true`, a link will be displayed allowing users to navigate to the reviews' section.                                                                                                                                                                                                                                                                                                                            | `boolean`                                                  | `undefined` |
| Limit            | `limit`            | Defines the maximum number of reviews to retrieve from the API.                                                                                                                                                                                                                                                                                                                                                                                                                    | `number`                                                   | `5`         |
| Source           | `source`           | Specifies the data source for reviews. Valid options include: • `store`: Retrieves reviews for the entire store. <br>• `all`: Retrieves reviews from all sources. <br>• `categories`: Retrieves reviews for specific product categories. <br>• `products`: Retrieves reviews for individual products. <br>• `json`: Retrieves reviews from a custom JSON payload. <br> <br>📝 **Note** that when using `json` as the source, a valid payload must be provided in the `sourceValue` property. | `"all" \| "categories" \| "json" \| "products" \| "store"` | `"store"`   |
| Source Value     | `source-value`     | Provides the data specific to the chosen source. Required when using `categories`, `products`, or `json` as the source: <br> • `categories`: An array of category IDs. <br> • `products`: An array of product IDs.  <br> • `json`: A custom JSON object containing the reviews' data.                                                                                                                                                                                                  | `(string \| number)[] \| number \| object \| string`       | `undefined` |

---

## elements/Salla-Reviews-Summary-Component-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Reviews Summary

The `<salla-reviews-summary>` web component allows users to display the general rating out of 5 stars on the product details page. This makes it easier for customers to quickly find the information they need by highlighting the main topics that appear across existing reviews.


## Example 
![](https://cdn.salla.network/docs/twilight/6/js-web-reviews-summary.png)

## Usage

<Tabs>

  <Tab title="HTML">

```html
<salla-reviews-summary> </salla-reviews-summary>
```

  </Tab>

  <Tab title="SASS">

This JS web component can be targeted for styling by its `:host` class. Following is a complete source code for customizing this component:

```js
:host {
    display: block;
}
```
  </Tab>

</Tabs>

## Properties


| Property              | Attribute | Description | Type     | Default     |
| --------------------- | --------- | ----------- | -------- | ----------- |
| Item ID _(required)_ | `item-id` | Product ID to fetch its summary  | `number` | `undefined` |

---

## elements/Salla-Sheet-Component-Guide-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Sheet

The `<salla-sheet>` component is the baseline for numerous components such as the [Button component](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD). It is a transformable layout, based on the `position` property, that provides a basic foundation for other components to be set on.


## Example

![Sheet](https://cdn.salla.network/docs/twilight/6/js-web-sheet-01.jpeg)

## Usage

<Tabs>
  <Tab title="HTML">
    
```html
<!-- Basic Salla Sheet usage-->
<salla-sheet
  position="right"
  persistent="true"
  width="450">
</salla-sheet>
```
      
  </Tab>
    <Tab title="SASS">
    
```css
.s-sheet-overlay {
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  background-color: #00000080;
  display: flex;
  align-items: flex-end;
  justify-content: center;
  display: none;
}

.s-sheet-overlay.active {
  display: flex;
}

.s-sheet-container {
  width: 100%;
  height: 40%;
  background-color: #ffffff;
  transform: translateY(100%);
  transition: transform 0.4s ease-in-out;
}
```
  
  </Tab>
</Tabs>



## Properties

| Property    | Attribute     | Description                                                                   | Type                                     | Default     |
| ----------- | ------------- | ----------------------------------------------------------------------------- | ---------------------------------------- | ----------- |
| Height      | `height`      | Sets the vertical height of the component                                     | `number`                                 | `300`       |
| Persistent  | `persistent`  | Whether or not the component is in a force view mode where it is not closable | `boolean`                                | `false`     |
| Position    | `position`    | Positions the component for different UI layout usecases, such as mobile view | `"bottom" \| "left" \| "right" \| "top"` | `'bottom'`  |
| Sheet Color | `sheet-color` | Customizable coloring of the component                                        | `string`                                 | `"#ffffff"` |
| Width       | `width`       | Sets the horizontal height of the component                                   | `number`                                 | `600`       |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `open` and `close` which opens and closes the sheet layout.


| Method  | Description             | Return Type     |
| ------- | ----------------------- | --------------- |
| `open`  | Opens the sheet layout  | `Promise<void>` |
| `close` | Closes the sheet layout | `Promise<void>` |

---

## elements/Salla-Skeleton-Component-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Skeleton

The `<salla-skeleton>` web component is used to display an indication to the user that something is coming but not yet available, which means that the content is to be loaded and can be customized using the properties' parameters.

## Example

<!--focus: false -->
![Skeleton](https://cdn.salla.network/docs/twilight/6/js-web-skeleton-01.png)

## Usage
<Tabs>
  <Tab title="HTML">
      
```html
<!-- Skeleton component usage -->
<salla-skeleton height='9rem'></salla-skeleton>
<salla-skeleton height='15px' width='100%'></salla-skeleton>
<salla-skeleton height='9px' width='50%'></salla-skeleton>
```
      
  </Tab>
    <Tab title="SASS">

```css
:host {
  display: block;
}
```
      
  </Tab>
</Tabs>


## Properties

| Property | Attribute | Description                                                | Type                   | Default    |
| -------- | --------- | ---------------------------------------------------------- | ---------------------- | ---------- |
| Height | `height`  | Sets the skeleton height                                   | `string`               | `'100%'`   |
| Type   | `type`    | Sets the shape type of the skeleton is it circle or normal | `"circle" \| "normal"` | `'normal'` |
| Width  | `width`   | Sets the skeleton width                                    | `string`               | `'100%'`   |

---

## elements/Salla-Slider-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Slider

The `<salla-slider>` component allows you to create a slider that can display multiple slides, which can be navigated by the Merchant using arrows or thumbnails.


<!--focus: false -->
![Slider](https://cdn.salla.network/docs/twilight/6/js-web-slider-04.png?v)

## Usage

<Tabs>
  <Tab title="HTML">


```html
<!-- Basic Salla Slider component Usage -->
<salla-slider id="thumbs" show-controls="true" type="thumbs">
  <div slot="items">
    <img src="https://picsum.photos/600/400?">
    <img src="https://picsum.photos/600/400?">
    <img src="https://picsum.photos/600/400?">
    <img src="https://picsum.photos/600/400?">
  </div>
  <div slot="thumbs">
    <img src="https://picsum.photos/600/400?">
    <img src="https://picsum.photos/600/400?">
    <img src="https://picsum.photos/600/400?">
    <img src="https://picsum.photos/600/400?">
  </div>
</salla-slider>
```
      
  </Tab>
   <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-slider-wrapper` class. Following is a complete source code for customizing this component:

```css
.s-slider-wrapper {
  &-container{

  }
  &-thumbs{
    &-container{

    }
  }
  &-button-next{
    svg{

    }
  }
  &-button-prev{
    svg{
      
    }
  }
}
```
      
  </Tab> 
</Tabs>



## Properties

| Property                    | Attribute                     | Description                                                                                                                                                                                                                | Type                                                                                                             | Default     |
| --------------------------- | ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ----------- |
| Arrows Centered             | `arrows-centered`             | Whether or not to center the slider's arrows                                                                                                                                                                               | `boolean`                                                                                                        | `false`     |
| Auto Height                 | `auto-height`                 | Whether or not to auto the height of the slider                                                                                                                                                                            | `boolean`                                                                                                        | `false`     |
| Auto Play                   | `auto-play`                   | Whether or not to enable autoplay, which only works with the following: `type="carousel" ` only                                                                                                                            | `boolean`                                                                                                        | `false`     |
| Block Subtitle              | `block-subtitle`              | Whether or not to show the slider's block sub title                                                                                                                                                                        | `string`                                                                                                         | `''`        |
| Block Title                 | `block-title`                 | Whether or not to show the slider's block title                                                                                                                                                                            | `string`                                                                                                         | `''`        |
| Centered                    | `centered`                    | Whether or not to enable the center mode, which only works with `type="carousel"` only                                                                                                                                     | `boolean`                                                                                                        | `false`     |
| Controls Outer              | `controls-outer`              | Whether or not to show arrow controls on the outerside of the slider                                                                                                                                                       | `boolean`                                                                                                        | `false`     |
| Direction                   | `direction`                   | The slider's direction, which is defaulted to: `document.documentElement.dir`                                                                                                                                              | `string`                                                                                                         | `undefined` |
| Display All Url             | `display-all-url`             | Whether or not to display all button beside arrows                                                                                                                                                                         | `string`                                                                                                         | `''`        |
| Grid Thumbs                 | `grid-thumbs`                 | Whether or not to disable the thumbs slider and rather show it as a grid                                                                                                                                                   | `boolean`                                                                                                        | `false`     |
| Listen To Thumbnails Option | `listen-to-thumbnails-option` | Whether or not to enable the calling of a specific slide by index from thumbnails option in the `salla-slider-options` component, which only works if `data-img-id` and `data-slid-index` attributes are set on each slide | `boolean`                                                                                                        | `false`     |
| Loop                        | `loop`                        | Run the slider in loop. It is recommended not to use it for slides with custom components inside of it, because that may cause some re-rendering issues                                                                    | `boolean`                                                                                                        | `false`     |
| Pagination                  | `pagination`                  | Whether or not to enable slide pagination. <TipInfo>Pagination will not be displayed unless the slider has an ID </TipInfo>                                                                                                                                                                                   | `boolean`                                                                                                        | `false`     |
| Show Controls               | `show-controls`               | Whether or not to show slider arrow controls                                                                                                                                                                               | `boolean`                                                                                                        | `true`      |
| Show Thumbs Controls        | `show-thumbs-controls`        | Whether or not to show thumbs slider controls                                                                                                                                                                              | `boolean`                                                                                                        | `true`      |
| Slider Config               | `slider-config`               | Set the slider's configurations. Refer to `https://swiperjs.com/swiper-api#parameters` and pass the entire `config` object                                                                                                 | `any`                                                                                                            | `undefined` |
| Slides Per View             | `slides-per-view`             | Show slides per view based on the user's interactivity with the slides                                                                                                                                                     | `string`                                                                                                         | `"auto"`    |
| Thumbs Config               | `thumbs-config`               | Set thumbs slider configurations Refer to `https://swiperjs.com/swiper-api#parameters` and pass the entire `config` object                                                                                                 | `any`                                                                                                            | `undefined` |
| Type                        | `type`                        | Set the type of the slider, which is defaulted to: ''                                                                                                                                                                      | `"" \| "blog" \| "carousel" \| "default" \| "fullscreen" \| "fullwidth" \| "hero" \| "testimonials" \| "thumbs"` | `''`        |
| Vertical                    | `vertical`                    | Align the main slider in either vertical or horizontal mode                                                                                                                                                                | `boolean`                                                                                                        | `false`     |
| Vertical Thumbs             | `vertical-thumbs`             | Align the thumbs slider in either vertical or horizontal mode                                                                                                                                                              | `boolean`                                                                                                        | `false`     |

## Events

| Event                        | Description                                                                                                       | Type               |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------ |
| `afterInit`                  | This event will be fired when the Slider is initialized immediately.                                              | `CustomEvent<any>` |
| `reachBeginning`             | This event will be fired when the Slider reaches its beginning (initial position)                                 | `CustomEvent<any>` |
| `reachEnd`                   | This event will be fired when Slider reaches last slide                                                           | `CustomEvent<any>` |
| `slideChange`                | This event will be fired when currently active slide is changed                                                   | `CustomEvent<any>` |
| `slideChangeTransitionStart` | This event will be fired when the animation starts to transition (either to the next or from the previous slide). | `CustomEvent<any>` |
| `slideChangeTransitionEnd`   | This event will be fired when the animation ends its transition (either to the next or from the previous slide).  | `CustomEvent<any>` |
| `slideNextTransitionStart`   | This event will be fired when the slide animation's transition starts onto the next slide.                        | `CustomEvent<any>` |
| `slideNextTransitionEnd`     | This event will be fired when the slide animation's transition ends onto the next slide.                          | `CustomEvent<any>` |
| `slidePrevTransitionStart`   | This event will be fired when the slide animation's transition ends onto the previous slide.                      | `CustomEvent<any>` |
| `slidePrevTransitionEnd`     | This event will be fired when the slide animation's transition starts onto the previous slide.                    | `CustomEvent<any>` |
| `sliderMove`                 | This event will be fired when the user touches and moves the mouse pointer the slider and interacts with it.      | `CustomEvent<any>` |
| `sliderTransitionEnd`        | This event will be fired after the transition ends.                                                               | `CustomEvent<any>` |
| `sliderTransitionStart`      | This event will be fired in the beginning of the transition.                                                      | `CustomEvent<any>` |
| `touchSliderEnd`             | This event will be fired when the slider's mouse pointer is released from the Slider.                             | `CustomEvent<any>` |
| `touchSliderMove`            | This event will be fired when the slider's mouse pointer touches moves over the Slider.                           | `CustomEvent<any>` |
| `touchSliderStart`           | This event will be fired when the slider's mouse pointer touches the Slider.                                      | `CustomEvent<any>` |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `getSlides` which gets all of the slider slides.


| Method                                                               | Description                                                                                                                                                                | Return Type     |
| -------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------- |
| `getSlides()`                                                        | Gets all of the slider's slides                                                                                                                                            | `Promise<any>`  |
| `slideNext(speed?: number, runCallbacks?: boolean)`                  | Runs a transition to the next slide.                                                                                                                                       | `Promise<void>` |
| `slideNextLoop(speed?: number, runCallbacks?: boolean)`              | Runs a transition to the next slide in an enabled looped condition.                                                                                                        | `Promise<void>` |
| `slidePrev(speed?: number, runCallbacks?: boolean)`                  | Runs a transition to the previous slide.                                                                                                                                   | `Promise<void>` |
| `slidePrevLoop(speed?: number, runCallbacks?: boolean)`              | Runs a transition to the previous slide in an enabled looped condition.                                                                                                    | `Promise<void>` |
| `slideReset(speed?: number, runCallbacks?: boolean)`                 | Resets the slider position to the currently active slide for the duration equal to the `speed` parameter.                                                                  | `Promise<void>` |
| `slideTo(index: number, speed?: number, runCallbacks?: boolean)`     | Runs a transition to the slide with the index number equal to the `index` parameter for the duration equal to `speed` parameter.                                           | `Promise<any>`  |
| `slideToClosest(speed?: number, runCallbacks?: boolean)`             | Resets the slider position to the closest slide / snap point for the duration equal to the `speed` parameter.                                                              | `Promise<void>` |
| `slideToLoop(index: number, speed?: number, runCallbacks?: boolean)` | Runs a looped condition transition to the slide with the index number equal to the `index` parameter for the duration equal to `speed` parameter                           | `Promise<void>` |
| `update()`                                                           | Either call this method after adding / removing or showing / hiding the slides manually. Also, any custom DOM modification has to have this method called upon the update. | `Promise<void>` |
| `updateAutoHeight(speed?: number)`                                   | Forces the slider to update its height, when `autoHeight` enabled, for the duration equal to the `speed` parameter.                                                        | `Promise<void>` |
| `updateProgress()`                                                   | Recalculates the slider's progress.                                                                                                                                        | `Promise<void>` |
| `updateSlides()`                                                     | Recalculates the number of slides and their offsets. Useful after adding / removing slides with JavaScript                                                                 | `Promise<void>` |
| `updateSlidesClasses()`                                              | Updates `active` / `prev` / `next` classes on the slides and bullets                                                                                                       | `Promise<void>` |

## Slots

The`slots` makes it customizable to modify certain labels, such as `items`.

| Slot       | Description                           |
| ---------- | ------------------------------------- |
| `items`  | Customizing the Slider items.         |
| `thumbs` | Customizing the Thumbs' slider items. |

---

## elements/Salla-Social-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Social

The `<salla-social>` web component allows users to click on the Store's social media accounts, such as YouTube, X _(formerly Twitter)_, and Instagram.

<!--focus: false -->
![Social Image](https://cdn.salla.network/docs/twilight/6/js-web-social-001.png?=ve)


## Usage

<Tabs>
  <Tab title="HTML">


```html
<salla-social></salla-social>
```
      
  </Tab>
   
</Tabs>

## Slots
The`slots` makes it customizable to modify certain labels, such as `social-item`.

| Slot            | Description                                                               |
| --------------- | ------------------------------------------------------------------------- |
| `social-item` | Customize the social-item with replaceable keys such as `{icon}`, `{type}` and `{link}` |

---

## elements/Salla-Social-Share-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Social Share

The `<salla-social-share>` web component is used to display a menu with social media platforms and sharing capabilities in the form of email and copyable links. This can be customized using the properties' parameters.


## Example

![Social Share](https://api.apidog.com/api/v1/projects/451700/resources/343652/image-preview)

<!--
![Social Share](https://cdn.salla.network/docs/twilight/6/js-web-social-share-001.webp) -->

## Usage
<Tabs>
  <Tab title="HTML">
      
```html
<!-- Show soical share for large screen only
     mobile has native share via browser -->
<salla-social-share platforms="whatsapp, facebook, twitter"></salla-social-share>
```      
  </Tab>
  
</Tabs>




## Properties

| Property  | Attribute  | Description                                                                                | Type       | Default             |
| --------- | ---------- | ------------------------------------------------------------------------------------------ | ---------- | ------------------- |
| Platforms | `platforms`         | Selected platforms to share the content on, such as Facebook, Twitter, WhatsApp, Email, and shareable link | `string` | `'facebook,twitter,whatsapp,email,copy_link'` |
| URL       | `url`      | Custom Page URL that is to be shared                                                       | `string`   | `""`                 |
| URL Name  | `url-name` | Custom Page URL name that is be shared                                                     | `string`   | `""`                 |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `open` which opens or activates the share menu. 


| Method   | Description                      | Return Type     |
| -------- | -------------------------------- | --------------- |
| `open()` | Opens / Activates the share menu | `Promise<void>` |
| `refresh()` | Refreshs the URL and URL Name after re-rendering the component | `Promise<void>` |


## Slots
The`slots` makes it customizable to modify certain labels, such as `widget`.

| Slot       | Description                                                                                |
| ---------- | ------------------------------------------------------------------------------------------ |
| `widget` | An action that can be used to activete or open the component by calling the `open` method. |

---

## elements/Salla-Tabs-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Tabs

The `<salla-tabs>` web component makes it possible to have several panes inside a single view. This implies the content is presented in several independent panes, each of which can be seen independently of the others. If the user wants to see a certain section of the page, they click on that tab's header. The component groups several tabs/panes that each consists of `<salla-tabs-header>` and `<salla-tabs-content>` where:

- **Salla Tabs Header**: The `<salla-tabs-header>` web sub-component represents the tab for a specific tab/pane within the `<salla-tabs>` web component, allowing users to select and navigate to a particular section of the page.
- **Salla Tabs Content**: The `<salla-tabs-content>` web sub-component represents the content or tab/pane associated with a specific header within the `<salla-tabs>` web component, displaying the relevant information or functionality when the corresponding tab is selected.


## Example

<!--
focus: false
-->

![Tabs](https://cdn.salla.network/docs/twilight/6/js-web-tabs-01.png)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<salla-tabs>
  <!-- Tab One -->
  <salla-tab-header slot="header" name="tab_one"
    ><span>Tab One</span></salla-tab-header
  >
  <salla-tab-content slot="content" name="tab_one">
    <p>This is the content of the first tab.</p>
  </salla-tab-content>
  <!-- Tab Two -->
  <salla-tab-header slot="header" name="tab_two"
    ><span>Tab Two</span></salla-tab-header
  >
  <salla-tab-content slot="content" name="tab_two">
    <p>This is the content of the second tab.</p>
  </salla-tab-content>
  <!-- Tab Three -->
  <salla-tab-header slot="header" name="tab_three"
    ><span>Tab Three</span></salla-tab-header
  >
  <salla-tab-content slot="content" name="tab_three">
    <p>Third tab content goes here</p>
  </salla-tab-content>
</salla-tabs>
```

  </Tab>
  <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-tabs` class. Following is a complete source code for customizing this component:

```css
.s-tabs {
  &-selected {
  }

  &-bg-normal {
  }

  &-header {
    /* Hide scrollbar for Chrome, Safari and Opera */
    &::-webkit-scrollbar {
      display: none;
    }
    /* Hide scrollbar for IE, Edge and Firefox */
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
  }
  &-default-background {
  }

  &-content {
  }

  &-content-selected {
  }

  &-transit {
  }
}
```

  </Tab>  
</Tabs>

## Properties

#### salla-tabs

| Property         | Attribute          | Description             | Type      | Default     |
| ---------------- | ------------------ | ----------------------- | --------- | ----------- |
| Background Color | `background-color` | Background color value  | `string`  | `undefined` |
| Vertical         | `vertical`         | Aligns tabs vertically. | `boolean` | `false`     |

#### salla-tab-header

| Property     | Attribute      | Description                                             | Type                 | Default     |
| ------------ | -------------- | ------------------------------------------------------- | -------------------- | ----------- |
| Name         | `name`         | Header identifier name to sync with the content.        | `string`             | `undefined` |
| Active Class | `active-class` | The class applied to the currently active(selected) tab | `string`             | `undefined` |
| Height       | `height`       | Set the height of the tab bar                           | `string` or `number` | `undefined` |
| Centered     | `centered`     | Center tab items in the given flex.                     | `boolean`            | `false`     |

#### salla-tab-content

| Property | Attribute | Description                                                                                               | Type     | Default     |
| -------- | --------- | --------------------------------------------------------------------------------------------------------- | -------- | ----------- |
| Name     | `name`    | Set name of the tab content. Mainly used as a key to synchronize the content with it's respective header. | `string` | `undefined` |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `getChild` which exposes `self` for the parent.


#### salla-tab-header

| Method       | Description                   | Return                                                                             |
| ------------ | ----------------------------- | ---------------------------------------------------------------------------------- |
| `"getChild"` | Expose `self` for the parent. | ```Promise<{selected: `boolean`, unselect: `boolean`, name: `string`, id: `string` }>``` |

#### salla-tab-content

| Method       | Description                   | Return                                                                             |
| ------------ | ----------------------------- | ---------------------------------------------------------------------------------- |
| `"getChild"` | Expose `self` for the parent. | ```Promise<{selected: `boolean`, unselect: `boolean`, name: `string`, id: `string` }>``` |

## Events

#### salla-tab-header

| Event           | Description                                  |
| --------------- | -------------------------------------------- |
| `"tabSelected"` | Emits event object when clicked or selected. |

## Slots

#### salla-tabs

| Slot        | Description                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------- |
| `content` | The current and active tab content section. The `salla-tab-content` component is used here. |
| `header`  | The tab header section. The `salla-tab-header` component is used here.                      |

---

## elements/Salla-map-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Map

The `<salla-map>` web component displays geographical maps from various sources. It supports multiple layers, tiled and full-image sources, adding markers, and interaction through events.



## Example

<!--
focus: false
-->

![Map](https://cdn.salla.network/docs/twilight/6/js-web-map-01.jpeg)

## Usage

<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Salla Map component Usage -->
<salla-map
  api-key="gPAnYXyivuAtzOiE2tYXGpaxxxx"
  theme="light"
  searchable="false">
</salla-map>

<!-- Using the readonly attribute in the Single Order Page -->
<salla-map
  api-key="gPAnYXyivuAtzOiE2tYXGpaxxxx"
  theme="light"
  readonly="false">
</salla-map>

```
  </Tab>      
  <Tab title="SASS">
      

This JS web component can be targeted for styling by its `.s-map-modal-wrapper` class. Following is a complete source code for customizing this component:

```css
.s-map-wrapper {
  .s-map-location-button {
    .s-map-location-icon {
      margin-right: 10px;
    }
  }
}
.s-map-modal-wrapper {
  .s-map-modal-body {
    padding: 0;
  }

  .s-map-title {
    position: relative;
    margin-top: -0.5rem;
    margin-bottom: 1rem;
    padding-left: 1rem;
    padding-right: 1rem;
  }
  .s-map-modal-body {
    overflow: hidden;
    position: relative;
    .s-map-element {
      height: 400px;
      width: 100%;
    }
    .s-map-search-wrapper {
      position: absolute;
      top: 0px;
      z-index: 11;
      z-index: 1;
      margin: 20px;
      width: -webkit-fill-available;
      input {
        width: 100%;
        height: 40px;
        padding: 10px;
      }
      .s-map-search-results {
        height: 100px;
        padding: 10px;
        margin-top: 1px;
        display: flex;
        flex-direction: column;
      }
    }
    .s-loading-container {
      margin: 0;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 5rem;
    }
    .s-map-my-location-icon {
      position: absolute;
      bottom: 1.5rem;
      margin: 10px;
    }
  }
}
```
  
  </Tab>
  
</Tabs>

## Properties

| Property   | Attribute   | Description                     | Type      | Default     |
| ---------- | ----------- | ------------------------------- | --------- | ----------- |
| API Key    | `api-key`   | Valid Google Maps API Key.      | `string`  | `undefined`      |
| Latitude   | `lat`       | Sets the map's latitude.        | `number`  | `undefined` |
| Longitude  | `lng`       | Sets the map's longitude.                                | `number`  | `undefined`  |
| Modal Title | `modal-title` | Modal Title                                             | `string`  | `undefined` |
| Name       | `name`        | File input name for the native formData                 | `string`  | `'location'`              |
| Read Only | `readonly` | Whether or not the actions are disabled or enabled. | `boolean` | `false`     |
| Required   | `required`    | Set if the location input is required or not            | `boolean` | `false`                   |
| Searchable | `seachable` | Whether or not to show the search bar. | `boolean` | `false`     |
| Theme      | `theme`       | Sets map style.                                         | `string`  | `'light'`                 |
| Zoom       | `zoom`      | Sets the inital map zoom.            | `number`  | `10`        |

## Events

| Event                    | Description                                                 | Type               |
| ------------------------ | ----------------------------------------------------------- | ------------------ |
| `currentLocationChanged` | This event will be fired when the current location is selected. | `CustomEvent<any>` |
| `invalidInput` | This event will be fired when the input is invalid. | `CustomEvent<any>` |
| `mapClicked`             | This event will be fired when the map is clicked. | `CustomEvent<any>` |
| `selected`               | This event will be fired when the location is selected. | `CustomEvent<any>` |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `open` which opens the map component.

| Method   | Description             | Return Type            |
| -------- | ----------------------- | ---------------------- |
| `open()` | Open the map component | `Promise<HTMLElement>` |

---

## elements/Salla-modal-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Modal

The `<salla-modal>` web component displays a dialog box or pop-up window on top of the current page. It is positioned above all other components in the application, restricting scrolling of the main page and only allowing scrolling of the modal's content. It consists of a [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component to activate the modal, and that can be customized using the properties, events, methods and slots' parameters available.



## Example

![Modal Example](https://cdn.salla.network/docs/twilight/6/js-web-modal-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Button to Activate the Modal-->
<button onclick="(function(){event.preventDefault();
    document.querySelector('#subscribe-modal').open();
    return false;})();
    "data-modal-id="subscribe-modal">
        Open Modal
</button>
      
<!-- Modal Settings -->
<salla-modal id="subscribe-modal"></salla-modal>
```
      
<!--
<!-- Button to Activate the Modal-->
<salla-button onclick="modal.open()">Click Me!</salla-button>

<!-- Modal Settings -->
<salla-modal
        id="modal"
        title="Title Header"
        sub-title="Title Sub-Header"
        icon="sicon-alert-engine"
        position="middle"
        width="xs"
        is-closable="true">
    
    <!-- Some awesome content within the modal. Custom Slot for the Modal-->
    <div slot="footer">
        <salla-button width="wide" onclick="modal.close()">Close</salla-button>
    </div>
    
</salla-modal>

  
  </Tab>
   

<!--
```js
// Save reference to the Modal Component below
var modal = document.querySelector("salla-modal");

modal.addEventListener("modalVisibilityChanged", function (status) {
  if(status) {
    // Listen for open events
    console.log("Modal Opened");
  } else {
    // Listen for close events
    console.log("Modal Closed");
  }
});
``` 
-->

      <Tab title="SASS">
 
This JS web component can be targeted for styling by its `.s-modal` class. Following is a complete source code for customizing this component:

```js
.s-modal {
  &-container{

  }
  &-wrapper {

  }
  &-close {

  }
  &-header {

  }
  &-header-inner {

  }
  &-header-content {

  }
  &-header-img {

  }
  &-icon {

  }
  &-bg-normal {

  }
  &-bg-success {

  }
  &-bg-error {

  }
  &-bg-primary {

  }
  &-text-success {

  }
  &-text-error {

  }
  &-title {

  }
  &-sub-title {

  }
  &-title-below {

  }
  &-body-slot {

  }
  &-body {

  }
  &-padding {

  }
  &-spacer {

  }
  &-align-middle {

  }
  &-align-top {

  }
  &-align-bottom {

  }
  &-overlay {

  }
  &-overlay-leaving {

  }
  &-entering {

  }
  &-leaving {

  }
  &-is-center {

  }
  // modal sizes
  &-xs {

  }
  &-sm {

  }
  &-md {

  }
  &-lg {

  }
  &-xl {

  }
  &-full {

  }
}
```
     
  </Tab>
</Tabs>

## Properties

| Property        | Attribute         | Description                                          | Type                                             | Default       |
| --------------- | ----------------- | ---------------------------------------------------- | ------------------------------------------------ | ------------- |
| Cenetered       | `cenetered`       | Aligns the modal's content to be in center view      | `boolean`                                        | `'false'`     |
| Has Skeleton    | `has-skeleton`    | Opens the modal on rendering the component           | `boolean`                                        | `'false'`     |
| Icon Style      | `icon-style`      | Sets the modal's header icon style.                  | `"error" \| "success" \|"normal" \| "primary"`   | `'undefined'` |
| Is Closable     | `is-closable`     | Sets the modal to be at the closing state            | `boolean`                                        | `'true'`      |
| Is Loading      | `is-loading`      | Shows the loading state in the modal                 | `boolean`                                        | `'false'`     |
| No Padding      | `no-padding`      | Adds no Padding to the modal                         | `boolean`                                        | `'false'`     |
| Position        | `position`        | Positions the modal in a fixed part of the screen    | `"bottom" \| "middle" \| "top"`                  | `'middle'`    |
| Sub Title       | `sub-title`       | Sets the modal subheader context                     | `string`                                         | `''`          |
| Sub Title First | `sub-title-first` | Whether or not to show the subtitle before the title | `boolean`                                        | `'false'`     |
| Visible         | `visible`         | Shows the modal on rendering the component           | `boolean`                                        | `'false'`     |
| Width           | `width`           | Adjusts the size of the modal                        | `"full" \| "lg" \| "md" \| "sm" \| "xl" \| "xs"` | `'md'`        |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `close` which closes the modal dialog.


| Method                      | Description                        | Return Type            |
| --------------------------- | ---------------------------------- | ---------------------- |
| `close()`                   | Closes the modal dialog            | `Promise<HTMLElement>` |
| `loading()`                 | Loads the modal dialog             | `Promise<HTMLElement>` |
| `setTitle(modalTitle: any)` | Sets the title of the modal dialog | `Promise<HTMLElement>` |
| `open()`                    | Opens the modal dialog             | `Promise<HTMLElement>` |
| `stopLoading()`             | Stops loading the modal dialog     | `Promise<HTMLElement>` |


:::tip[Note]
To use a method, you can for instance use `open` the component via the method:

```html
onclick="salla.event.dispatch('modal::open','modal_id')"
```
and `close` the component via the method:
 ```html
onclick="salla.event.dispatch('modal::close','modal_id')"
```
:::


## Slots
The`slots` makes it customizable to modify certain labels, such as `footer`

| Slot     | Description         |
| -------- | ------------------- |
| `footer` | Footer of the modal |

## Events

| Event                    | Description                                                  | Type                   |
| ------------------------ | ------------------------------------------------------------ | ---------------------- |
| `modalVisibilityChanged` | This event will be fired when the modal visibilty is changed | `CustomEvent<Boolean>` |

<!--

## Tips

Here are some what and what nots for best practises to using the component:

:::tip[Follow]

- When you need to show material that briefly prevents users from interacting with the app's main view.
- When you need to get a user's approval before proceeding.
- When the user must execute a specific activity.
- As a technique to avoid or fix critical problems, for important alerts.

:::

:::danger[Avoid]

For non-essential content that has nothing to do with the present user flow.
To interrupt a purchasing flow in the process of it.
When the modal needs additional information to make a decision that isn't accessible in the modal.

:::

-->

---

