# Form

## Table of Contents

- [form/Salla-Botton-Alert-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-botton-alert-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Button-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-button-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Contact-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-contact-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Date-Time-Picker-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-date-time-picker-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-File-upload-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-file-upload-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Menu-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-menu-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Quantity-Input-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-quantity-input-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Select-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-select-salla-storefront-web-components-twilight-documentation-salla-docs)
- [form/Salla-Tel-Input-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs](#form-salla-tel-input-salla-storefront-web-components-twilight-documentation-salla-docs)

---

## form/Salla-Botton-Alert-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Bottom Alert

The `<salla-bottom-alert>` web component displays a message to the Merchant at the bottom of the used component. It blockes interaction with the rest of the screen until they are dismissed


## Example

![Bottom Alert Example](https://cdn.salla.network/docs/twilight/6/js-web-quick-buy-01.gif?v)

## Usage
<Tabs>
  <Tab title="HTML">
      
```html
<!-- Basic Bottom Alert component usage -->
  <salla-bottom-alert
    message="Lorem Ipsum"
    type="banner"
    icon="sicon-anchor">
  </salla-bottom-alert>
```
      
  </Tab>
  
</Tabs>

## Properties

| Property      | Attribute      | Description                                                | Type                            | Default     |
| ------------- | -------------- | ---------------------------------------------------------- | ------------------------------- | ----------- |
| Action Label | `action-label` | Alert's Button label, which is used when the `type` value is either `link` or `popup`            | `string`                        | `undefined` |
| Action URL`   | `action-url`   | Alert's Button URL, which is used when the `type` value is `link`                        | `string`                        | `undefined` |
| Icon        | `icon`         | Alert's Icon class from [Salla Icons library](https://docs.salla.dev/doc-422550) | `string`                        | `undefined` |
| Message     | `message`      | Alert's Message which is a text that appears on the action button                                              | `string`                        | `undefined` |
| Type        | `type`         | Alert Type, which specifies how the alert should look like                                                 | `"banner" \| "link" \| "popup"` | `'popup'`   |

---

## form/Salla-Button-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Button

The `<salla-button>` web component shows a customizable button, in terms of size, color, style, status, position etc ,which can be used with any other web component, and that can be customized using the properties' parameters available.


## Example

<!--
focus: false
-->

![Button Example](https://cdn.salla.network/docs/twilight/6/js-web-button-01.png)


## Usage
<Tabs>
  <Tab title="HTML">

```html
<!-- Basic Default Button-->
<salla-button> Default Button </salla-button>

<!-- Primary Start Loading Wide Button-->
<salla-button width="wide" loader-position="center" color="primary">
    Start Loading
</salla-button>

<!-- Button with loading effect-->
<salla-button fill="outline" loading="true" onclick="button.stop()">
    Stop Loading
</salla-button>

<!-- Solid Disabled Button-->
<salla-button fill="solid" onclick="button.disable()">
    Disable Button!
</salla-button>

<!-- Outlined Enabled Button-->
<salla-button fill="outline" disabled="true" onclick="button.enable())">
    Enable Button!
</salla-button>

<!-- Light Solid Link Button-->
<salla-button href="https://www.salla.sa/" fill="solid" color="light">
    Redirect URL
</salla-button>
```
      
  </Tab>
  <Tab title="JS">

```js
// Save reference to the Button Component below
const button = document.querySelector("salla-button");

// enable loading effect
button.load().then(() => {
  // let's call API request and await for it
  // let stop the loading effect
  setTimeout(() => button.stop(), 40000)
});
```
      
  </Tab> 
    <Tab title="SASS">

This JS web component can be targeted for styling by its `.s-button-*` class. Following is a complete source code for customizing this component:


```js


.s-button{
  &-wrap{
    
  }
  &-element{
    
  }
  &-link{
    
  }
  &-icon{
    
  }
  &-btn{
    
  }
  &-solid{
    
  }
  &-outline{
    
  }
  &-fill-none{
    
  }
  &-large{
    
  }
  &-small{
    
  }
  &-wide{
    
  }
  &-primary{
    
  }
  &-success{
    
  }
  &-warning{
    
  }
  &-danger{
    
  }
  &-light{
    
  }
  &-gray{
    
  }
  &-dark{
    
  }
  &-primary-link{
    
  }
  &-success-link{
    
  }
  &-warning-link{
    
  }
  &-danger-link{
    
  }
  &-light-link{
    
  }
  &-gray-link{
    
  }
  &-dark-link{
    
  }
  &-primary-outline{
    
  }
  &-success-outline{
    
  }
  &-warning-outline{
    
  }
  &-danger-outline{
    
  }
  &-light-outline{
    
  }
  &-gray-outline{
    
  }
  &-dark-outline{
    
  }
  &-disabled{
    
  }
  &-loader{

  }
  &-loader-start{
    
  }
  &-loader-end{
    
  }
  &-loader-center{
    
  }
  &-loader-after{
    
  }
  &-text{

  }
  &-hide{

  }
}
```

      
  </Tab>  
</Tabs>


## Properties

| Property        | Attribute         | Description                             | Type                                                                             | Default     |
| --------------- | ----------------- | --------------------------------------- | -------------------------------------------------------------------------------- | ----------- |
| Color           | `color`           | Customized Button color                            | `"danger" \| "dark" \| "gray" \| "light" \| "primary" \| "success" \| "warning"` | `'primary'` |
| Disabled        | `disabled`        | Button disability status                | `boolean`                                                                        | `'false'`     |
| Fill            | `fill`            | Button fill style                       | `"none" \| "outline" \| "solid"`                                                 | `'solid'`   |
| href            | `href`            | Button with a link capability           | `string`                                                                         | `undefined` |
| Loader Position | `loader-position` | Set the loading animation's position    | `"after" \| "center" \| "end" \| "start"`                                        | `'after'`   |
| Loading         | `loading`         | Activate Button loading                 | `boolean`                                                                        | `'false'`     |
| Shape           | `shape`           | Button type Configs                     | `"btn" \| "icon" \| "link"`                                                      | `'btn'`     |
| Size            | `size`            | Button size Configs                     | `"small" \| "medium" \| "large"`                                                     | `'medium'`  |
| Width           | `width`           | Button extends the full available width | `"normal" \| "wide"`                                                               | `'normal'`    |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `enable` and/or `disable` loading the component.


| Method                  | Description                                                                                              | Return Type            |
| ----------------------- | -------------------------------------------------------------------------------------------------------- | ---------------------- |
| `disable()`             | Inactivates the button by adding `disabled` attribute. Visually, it becomes unclickable and unhoverable. | `Promise<void>`        |
| `enable()`              | Activates the button by removing `disabled` attribute.                                                   | `Promise<void>`        |
| `load()`                | Runs loading animation to notify a user that there is a processing taking place.                           | `Promise<HTMLElement>` |
| `stop()`                | Stops loading animation after a process has completed                                                    | `Promise<HTMLElement>` |
| `setText(html: string)` | Customizes the button's body text                                                                        | `Promise<HTMLElement>` |

---

## form/Salla-Contact-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Contacts

The `<salla-contacts>` web component allows users to display contact items. It is possible to include the [`salla-social`](https://docs.salla.dev/doc-499802?nav=01HNFTE06J4QC24T0D5BPRYKMD) component for icon visual representation. 
## Example

<!--
focus: false
-->

![Alt text](https://cdn.salla.network/docs/twilight/6/js-web-contacts-01.png)

## Usage

<Tabs>

  <Tab title="HTML">

```html
# Basic usage  
<salla-contacts is-header=“false” hide-title=“true”></salla-contacts>
      
# salla-social component included  
 <div>
   <salla-contacts></salla-contacts>
   <div class="lg:hidden contact-social">
      <salla-social></salla-social>
   </div>
</div>
```
      
  </Tab>

  <Tab title="SASS">

This JS web component can be targeted for styling by its `:host` class. Following is a complete source code for
    customizing this component:

```js
    :host {
    display: block;
    }
```
      
  </Tab>


</Tabs>

## Properties

| Property        | Attribute        | Description                                                       | Type     | Default     |
| --------------- | ---------------- | ----------------------------------------------------------------- | -------- | ----------- |
| Contacts Title | `contacts-title` | Title for the social block within the footer section               | `string` | `undefined` |
| Hide Title     | `hide-title`     | Whether or not to toggle the visibility of the title                      | `boolean`| `undefined` |
| Horizontal    | `horizontal`     | Whether or not to switch between vertical and horizontal display of content          | `boolean`| `undefined` |
| Icons Only     | `icons-only`     | Whether or not to display only `icons` or both `icons` and `labels`              | `boolean`| `undefined` |
| Is Header      | `is-header`      | Whether or not the content serves as a header             | `boolean`| `undefined` |



## Slots
The`slots` makes it customizable to modify certain labels, such as `contact`.
| Slot    	| Description                                                   	|
| ----------- | ----------------------------------------------------------------- |
| `contact` | This slot has replaceable properties, which are `icon` and `value`. |

---

## form/Salla-Date-Time-Picker-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Date Time Picker

The `<salla-datetime-picker>` web component is used to allow users to select both date and time with the same control. The date and time can be entered directly in the format of the current locale or through the Date Time Picker’s visible overlay.

## Example

<!--
focus: false
-->

![Date Time Picker](https://cdn.salla.network/docs/twilight/6/js-web-date-time-picker-01.png)

## Usage
<Tabs>
  <Tab title="HTML">

```html
<!-- Basic Ranged Date Time Picker -->
  <salla-datetime-picker mode="range"></salla-datetime-picker>

<!-- Enabled Date Time Picker with Seconds and Formatted Date -->
  <salla-datetime-picker enable-seconds enable-time date-format="Y-m-d H:i">
  </salla-datetime-picker>

<!-- Inline Enabled Date Time Picker with Seconds and Formatted Date -->
  <salla-datetime-picker inline enable-seconds date-format="Y-m-d H:i">
  </salla-datetime-picker>
```   
  </Tab>
  
</Tabs>

## Properties

| Property                 | Attribute                 | Description                                                                                                                                                                                                                                  | Type                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | Default                                                          |
| ------------------------ | ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Allow Input              | `allow-input`             | Allows the user to enter a date directly into the input field.                                                                                                                                                                               | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Allow Invalid Preload    | `allow-invalid-preload`   | Allows the preloading of an invalid date. When disabled, the field will be cleared if the provided date is invalid                                                                                                                           | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Alternative Format               | `alt-format`              | Exactly the same as date format, but for the altInput field.                                                                                                                                                                                 | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `"F j, Y"`                                                       |
| Alternative Input                | `alt-input`               | Displays to the user a readable date (as per `altFormat`), but return something totally different to the server.                                                                                                                             | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Alternative Input Class          | `alt-input-class`         | Adds to the input element created by the `altInput` option. Note that `altInput` already inherits classes from the original input.                                                                                                           | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `undefined`                                                      |
| Append To                | --                        | Appends the calendar to the specified node Instead of body.                                                                                                                                                                                  | `HTMLElement`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | `undefined`                                                      |
| Aria Date Format         | `aria-date-format`        | Defines how the date will be formatted in the `aria-label` for calendar days, using the same tokens as `dateFormat`. If this is changed, choose a value that will make sense when a screen reader reads it out loud.                         | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `"F j, Y"`                                                       |
| Auto Fill Default Time   | `auto-fill-default-time`  | Whether or not the default time should be `auto-filled` when the input is empty and gains / loses focus when entered.                                                                                                                        | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `true`                                                           |
| Click Opens              | `click-opens`             | Whether or not clicking on the input should opens the datetime picker. Set it to false if only opening the calendar programmatically with the [open()] method is needed.                                                                     | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `true`                                                           |
| Close On Select          | `close-on-select`         | Whether or not the calendar should close after date selection.                                                                                                                                                                               | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `true`                                                           |
| Conjunction              | `conjunction`             | Separates dates in the entry field, using Conjunction, as it is used in "multiple" mode.                                                                                                                                                     | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `undefined`                                                      |
| Date Format              | `date-format`             | String of characters which are used to define how the date will be displayed in the input box.                                                                                                                                               | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `"Y-m-d"`                                                        |
| Date Parser              | --                        | Custom `datestring` parser                                                                                                                                                                                                                   | `(date: string, format: string) => Date`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `undefined`                                                      |
| Default Date             | `default-date`            | Sets the initial selected date(s). If using mode: "multiple" or a range calendar supply an Array of Date objects or an Array of date strings which follow the defualt `dateFormat`. Otherwise, supply a single Date object or a date string. | `Date \| DateOption[] \| number \| string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | `undefined`                                                      |
| Default Hour             | `default-hour`            | Initializes value of the `hour` element, when no date is selected.                                                                                                                                                                           | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `12`                                                             |
| Default Minute           | `default-minute`          | Initializes the value of the `minute` element, when no date is selected.                                                                                                                                                                     | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `0`                                                              |
| Default Seconds          | `default-seconds`         | Initializes the value of the `seconds` element, when no date is selected.                                                                                                                                                                    | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `0`                                                              |
| Disable                  | --                        | Disables certain dates, preventing them from being selected.                                                                                                                                                                                 | `DateLimit<DateOption>[]`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `[]`                                                             |
| Disable Mobile           | `disable-mobile`          | Sets this field to `true` in order to always use the non-native picker on mobile devices.                                                                                                                                                    | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Enable                   | --                        | Disables all dates except the specified ones.                                                                                                                                                                                                | `DateLimit<DateOption>[]`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `[(_) => true]`                                                  |
| Enable Seconds           | `enable-seconds`          | Enables seconds selection in the time picker.                                                                                                                                                                                                | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Enable Time              | `enable-time`             | Enables the time picker.                                                                                                                                                                                                                     | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Format Date              | --                        | Allows using a custom date formatting function instead of the built-in handling for date formats using `dateFormat`, `altFormat`, etc.                                                                                                       | `(date: Date, format: string, locale: Object) => string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `undefined`                                                      |
| Hour Increment           | `hour-increment`          | Adjusts the step for the hour input, including scrolling.                                                                                                                                                                                    | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `1`                                                              |
| Inline                   | `inline`                  | Displays the calendar in an inline manner.                                                                                                                                                                                                   | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Locale                   | `locale`                  | The locale, either as a string (e.g. "ar", "en") or as an object.                                                                                                                                                                            | `"ar" \| "at" \| "az" \| "be" \| "bg" \| "bn" \| "bs" \| "ca" \| "cat" \| "ckb" \| "cs" \| "cy" \| "da" \| "de" \| "default" \| "en" \| "eo" \| "es" \| "et" \| "fa" \| "fi" \| "fo" \| "fr" \| "gr" \| "he" \| "hi" \| "hr" \| "hu" \| "hy" \| "id" \| "is" \| "it" \| "ja" \| "ka" \| "ko" \| "km" \| "kz" \| "lt" \| "lv" \| "mk" \| "mn" \| "ms" \| "my" \| "nl" \| "nn" \| "no" \| "pa" \| "pl" \| "pt" \| "ro" \| "ru" \| "si" \| "sk" \| "sl" \| "sq" \| "sr" \| "sv" \| "th" \| "tr" \| "uk" \| "vn" \| "zh" \| "uz" \| "uz_latn" \| "zh_tw"` | `"en"`                                                           |
| Maximum Date             | `max-date`                | The maximum date that a user can pick to.                                                                                                                                                                                                    | `Date \| number \| string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | `null`                                                           |
| Maximum Time             | `max-time`                | The minimum date that a user can start picking from.                                                                                                                                                                                         | `Date \| number \| string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | `null`                                                           |
| Minimum Date             | `min-date`                | The minimum date that a user can start picking from.                                                                                                                                                                                         | `Date \| number \| string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | `null`                                                           |
| Minimum Time             | `min-time`                | The minimum time that a user can start picking from.                                                                                                                                                                                         | `Date \| number \| string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | `null`                                                           |
| Minute Increment         | `minute-increment`        | Adjusts the step for the minute input, including scrolling.                                                                                                                                                                                  | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `5`                                                              |
| Mode                     | `mode`                    | Date selection mode.                                                                                                                                                                                                                         | `"multiple" \| "range" \| "single" \| "time"`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | `"single"`                                                       |
| Month Selector Type      | `month-selector-type`     | How the month should be displayed in the header of the calendar. If `showMonths` has a value greater than `1`, the month is always shown as static.                                                                                          | `"dropdown" \| "static"`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `"dropdown"`                                                     |
| Name               | `name`              | Input name. | `string`      | `undefiend`             |
| Next Arrow               | `next-arrow`              | HTML for the arrow icon, used to switch months.                                                                                                                                                                                              | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `'<span class="sicon-keyboard_arrow_right"></span>'`             |
| No Calendar              | `no-calendar`             | Hides the day selection in calendar. Use it along with `enableTime` to create a time picker.                                                                                                                                                 | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Placeholder              | `placeholder`             | Placeholder text to show on the input element.                                                                                                                                                                                               | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `salla.lang.get('blocks.buy_as_gift.select_send_date_and_time')` |
| Position                 | `position`                | How the calendar should be positioned with regards to the input.                                                                                                                                                                             | `"above center" \| "above left" \| "above right" \| "above" \| "auto center" \| "auto left" \| "auto right" \| "auto" \| "below center" \| "below left" \| "below right" \| "below" \| ((self: any, customElement: HTMLElement) => void)`                                                                                                                                                                                                                                                                                                             | `"auto"`                                                         |
| Position Element         | --                        | The element off, of which the calendar will be positioned.                                                                                                                                                                                   | `HTMLElement`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | `undefined`                                                      |
| Previous Arrow               | `prev-arrow`              | HTML for the left arrow icon, used to switch months.                                                                                                                                                                                         | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `'<span class="sicon-keyboard_arrow_left"></span>'`              |
| Required               | `required`              | Whether or not the input is required. | `boolean` | `false`              |
| Short Hand Current Month | `shorthand-current-month` | Whether or not to display the current month name in shorthand mode, e.g. `"Sep"` instead `"September"`.                                                                                                                                      | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Show Months              | `show-months`             | The number of months to be shown at the same time when displaying the calendar.                                                                                                                                                              | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `1`                                                              |
| Static                   | `static`                  | Positions the calendar inside the wrapper and next to the input element.                                                                                                                                                                     | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Time 24 Hours            | `time_-2-4hr`             | Displays time picker in 24 hour mode without `AM/PM` selection when enabled.                                                                                                                                                                 | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Value                    | `value`                   | Two way data binding to retrieve the selected `datetime` value.                                                                                                                                                                              | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | `null`                                                           |
| Week Numbers              | `week-numbers`            | Enables display of week numbers in calendar.                                                                                                                                                                                                 | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |
| Wrap                     | `wrap`                    | Visit [here](https://chmln.github.io/flatpickr/examples/#flatpickr-external-elements) for more details                                                                                                                                             | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | `false`                                                          |

## Events

| Event    | Description                                                                                               | Type               |
| -------- | --------------------------------------------------------------------------------------------------------- | ------------------ |
| `invalidInput` | This event will be fired when the input is invalid. | `CustomEvent<any>` |
| `picked` | This event will be fired when the file input gets changed by the user, which happens when selecting file(s). | `CustomEvent<any>` |

---

## form/Salla-File-upload-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# File Upload

The `<salla-file-upload>` web component is used to allow the user to allow uploading a file or a number of files is supported by the File Upload web component, with the help of completed and supported parameters.


## Example

<!--
focus: false
-->

![File Upload](https://cdn.salla.network/docs/twilight/6/js-web-file-upload-01.png)

## Usage
<Tabs>
<Tab title="HTML">
 
```html
<!-- Basic File Upload component usage -->
<salla-file-upload 
  profile-image = false
  name = "First File"
  required = false">
</salla-file-upload>
```     
  </Tab>  

</Tabs>


## Properties

| Property                           | Attribute                            | Description                                                                                                                                                                                                                                                                                                                                           | Type                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Default                                                                                                                                       |
| ---------------------------------- | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Accept                       | `accept`                       | Accepted file types.                                                                                                                                                                                                                                                                                                                          | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `image/png, image/jpeg, image/jpg, image/gif, video/*`                                                                                                                                        |
| Allow Browse                       | `allow-browse`                       | Enables or disables browser.                                                                                                                                                                                                                                                                                                                          | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Allow Drop                         | `allow-drop`                         | Enables or disables drag and drop.                                                                                                                                                                                                                                                                                                                    | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Allow Image Preview       | `allow-image-preview`       | Enable or disable preview mode when uploading an image                                                                                                                                                                                                                                                                                                                  | `boolean`                                                               | `true`                                          |
| Allow Multiple                     | `allow-multiple`                     | Enables or disables adding multiple files.                                                                                                                                                                                                                                                                                                            | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Allow Paste                        | `allow-paste`                        | Enables or disables pasting of files. Pasting files is not supported on all browesrs.                                                                                                                                                                                                                                                                 | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Allow Process                      | `allow-process`                      | Enables or disables the process button.                                                                                                                                                                                                                                                                                                               | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Allow Remove                       | `allow-remove`                       | When set to false, the remove button is hidden and disabled.                                                                                                                                                                                                                                                                                          | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Allow Reorder                      | `allow-reorder`                      | Allows users to reorder files with drag and drop interaction. **Note** that this only works in single column mode. It also only works on browsers that support pointer events.                                                                                                                                                                        | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Allow Replace                      | `allow-replace`                      | Allows drop to replace a file, only works when `allowMultiple` is `false`.                                                                                                                                                                                                                                                                            | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Allow Revert                       | `allow-revert`                       | Enables or disables the revert processing button.                                                                                                                                                                                                                                                                                                     | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Cart Item ID                       | `cartItemId`                       | Pass this property to prepare the upload URL automatically, such as uploading an attachement file in the cart item.                                                                                                                                                                                                                                                                                                     | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `undefined`                                                                                                                                        |
| Check Validity                     | `check-validity`                     | Set to `true` to enable custom validity messages. `FilePond` will throw an error when a parent form is submitted and contains invalid files.                                                                                                                                                                                                          | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Chunk Force                        | `chunk-force`                        | Forces chunks, even for files smaller than the set `chunkSize`.                                                                                                                                                                                                                                                                                       | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Chunk Retry Delays                 | --                                   | Amount of times and delayes between re-tried uploading of a chunk.                                                                                                                                                                                                                                                                                    | `number[]`                                                                                                                                                                                                                                                                                                                                                                                                                                                | `[500, 1000, 3000]`                                                                                                                           |
| Chunk Size                         | `chunk-size`                         | The size of a chunk in bytes.                                                                                                                                                                                                                                                                                                                         | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `5000000`                                                                                                                                     |
| Chunk Uploads                      | `chunk-uploads`                      | Enables chunked uploads. When enabled, it will automatically cut up files in `chunkSize` chunks before upload.                                                                                                                                                                                                                                        | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Credits                            | `credits`                            | Shows credits at the bottom of the upload element. Structure is like the following: [{label,url}].                                                                                                                                                                                                                                                    | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Disabled                           | `disabled`                           | Sets the disabled attribute to the output field.                                                                                                                                                                                                                                                                                                      | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Drop On Element                    | `drop-on-element`                    | Requires drop on the element itself to catch the file.                                                                                                                                                                                                                                                                                                | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `true`                                                                                                                                        |
| Drop On Page                       | `drop-on-page`                       | This will catch all files dropped on the webpage.                                                                                                                                                                                                                                                                                                     | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Drop Validation                    | `drop-validation`                    | When enabled, files are validated before they are dropped. A file is not added when it is invalid.                                                                                                                                                                                                                                                    | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| File ID                  | `file-id`                   | If the current file has an ID, pass it here as a property, which is to be passed back in the `removed` event.                                                                                                                                                                                                                                                                  | `number`                                                                | `undefined`                                              |
| Files                   | `files`                     | The uploaded files as json `[{url:"...", id:123}]` for delete possibility.                                                                                                                                                                                                                                                                       | `string`                                                                | `undefined`                                              |
|
| Force Revert                       | `force-revert`                       | Set to `true` to require the file to be successfully reverted before continuing.                                                                                                                                                                                                                                                                      | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Form Data                       | `formData`                       | A JSON form data that is to be injected in the submit request.                                                                                                                                                                                                                                                                      | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `"{}"`                                                                                                                                       |
| Height                       | `height`                       | The original height of the uploader, will be used to reset the height after the image is removed.                                                                                                                                                                                                                                                                      | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `undefined`                                                                                                                                       |
| Icon Process                       | `icon-process`                       | The icon used for processing actions.                                                                                                                                                                                                                                                                                                                 | `string` I                                                                                                                                                                                                                                                                                                                                                                                                                                                | `'<svg>...</svg>'`                                                                                                                            |
| Icon Remove                        | `icon-remove`                        | The icon used for removing actions.                                                                                                                                                                                                                                                                                                                   | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `'<svg>...</svg>'`                                                                                                                            |
| Icon Retry                         | `icon-retry`                         | The icon used for retrying actions.                                                                                                                                                                                                                                                                                                                   | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `'<svg>...</svg>'`                                                                                                                            |
| Icon Undo                          | `icon-undo`                          | The icon used for undoing actions.                                                                                                                                                                                                                                                                                                                    | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `'<svg>...</svg>'`                                                                                                                            |
| Ignored Files                      | --                                   | Ignored file names when handling dropped directories. **Note** that it is not supported on all browsers.                                                                                                                                                                                                                                              | `any[]`                                                                                                                                                                                                                                                                                                                                                                                                                                                   | `['.ds_store', 'thumbs.db', 'desktop.ini']`                                                                                                   |
| Instant Upload                     | `instant-upload`                     | Immediately upload new files to the server.                                                                                                                                                                                                                                                                                                           | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Item Insert Interval               | `item-insert-interval`               | The interval to use before showing each item being added to the list.                                                                                                                                                                                                                                                                                 | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `75`                                                                                                                                          |
| Item Insert Location               | `item-insert-location`               | You can either set the value to `'after'` to add files to end of list, when dropped at the top of the list or added using browse or paste, or set the value to `'before'` to add files at start of list, or set the value to a compare function to automatically sort items when added.                                                               | `"after" \| "before" \| ((a: FilePondFile, b: FilePondFile) => number)`                                                                                                                                                                                                                                                                                                                                                                                   | `'after'`                                                                                                                                     |
| Label Decimal Separator            | `label-decimal-separator`            | The decimal separator used to render numbers.                                                                                                                                                                                                                                                                                                         | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `undefined`                                                                                                                                   |
| Label Idle                         | `label-idle`                         | Default label shown to indicate this is a drop area. It will automatically bind browse file events to the element with CSS class `.filepond--label-action`.                                                                                                                                                                                           | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `${salla.lang.get('common.uploader.drag_and_drop')}<span class="filepond--label-action"> ${salla.lang.get('common.uploader.browse')} </span>` |
| Label Thousands Separator          | `label-thousands-separator`          | The thousdands number separator used to render numbers.                                                                                                                                                                                                                                                                                               | `string`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `undefined`                                                                                                                                   |
| Max Files Size                    | `max-files-size`                    | The maximum size of a file, for instance 3MB or 750KB                                                                                                                                                                                                                                                                                                      | `${number}KB}` \| `${number}MB`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `2MB`                                                                                                                                        |
| Max Files Count                    | `max-files-count`                    | The maximum number of files that can be handled.                                                                                                                                                                                                                                                                                                      | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `null`                                                                                                                                        |
| Max Parallel Uploads               | `max-parallel-uploads`               | The maxmimum number of files that can be uploaded in parallel.                                                                                                                                                                                                                                                                                        | `number`                                                                                                                                                                                                                                                                                                                                                                                                                                                  | `2`                                                                                                                                           |
| Method                  | `method`                    | The submit request method.                                                                                                                                                                                                                                                                                                                      | `string`                                                                | `'POST'`                                                 |
| Name                    | `name`                      | File input name for the native formData                                                                                                                                                                                                                                                                                                         | `string`                                                                | `undefined`                                              |
| Payload Name             | `payload-name`              | File input name in the request payload                                                                                                                                                                                                                                                                                                          | `string`                                                                | `undefined`                                              |
| Profile Image            | `profile-image`             | Set the component to be profile image uploader with a preview and a circular shape                                                                                                                                                                                                                                                              | `boolean`                                                               | `false`                                                  |
| Required                           | `required`                           | Sets the required attribute to the output field.                                                                                                                                                                                                                                                                                                      | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Server Config                      | `server-config`                      | A server configuration object describing how the feature should interact with the server.                                                                                                                                                                                                                                                             | `string \| { url?: string; timeout?: number; headers?: { [key: string]: string \| number \| boolean; }; process?: string \| ServerUrl \| ProcessServerConfigFunction; revert?: string \| ServerUrl \| RevertServerConfigFunction; restore?: string \| ServerUrl \| RestoreServerConfigFunction; load?: string \| ServerUrl \| LoadServerConfigFunction; fetch?: string \| ServerUrl \| FetchServerConfigFunction; remove?: RemoveServerConfigFunction; }` | `null`                                                                                                                                        |
| Store As File                      | `store-as-file`                      | Tells the feature to store files in hidden file input elements, so they can be posted along with normal form post. It only works if the browser supports the [DataTransfer constructor](https://caniuse.com/mdn-api_datatransfer_datatransfer), which is the case on browsers such as Firefox, Chrome, Chromium powered browsers and Safari version 14.1 and higher. | `boolean`                                                                                                                                                                                                                                                                                                                                                                                                                                                 | `false`                                                                                                                                       |
| Uploaded Image                      | `uploadedImage`                      | The uploaded image link or URL. | `string`                                                         | `undefined`                                                                                                                                       |
| URL                     | `url`                       | The url to submit the image into.                                                                                                                                                                                                                                                                                                               | `string`                                                                | `undefined`                                              |
| Value                   | `value`                     | The uploaded image link or URL                                                                                                                                                                                                                                                                                                                  | `string`                                                                | `undefined`                                              |


## Events

| Event    | Description                                                                            | Type               |
| -------- | -------------------------------------------------------------------------------------- | ------------------ |
| `added`    | Event emitted when the file has been added                                                                                  | `CustomEvent<{ error: FilePondErrorDescription; file: FilePondFile; }>` |
| `invalidInput` | This event will be fired when the input is invalid. | `CustomEvent<any>` |
| `remove` | This event will be fired when the file is about to be removed. Returns a `boolean` value. | `CustomEvent<any>` |
| `uploaded` | This event will be fired when the file has been uploaded, and a link to the file has been received from the server. | `CustomEvent<string>` |

## Methods
The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, such as `oppendFile` which appends an initial file.


| Method                                  | Description            | Return Type                     |
| --------------------------------------- | ---------------------- | ------------------------------- |
| `appendFile(file: FilePondInitialFile)` | Appends an intial file | `Promise<FilePondInitialFile[]` |

---

## form/Salla-Menu-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Menu

 
The `<salla-menu>` web component displays a nested list items that either appear on the header section or footer section.

:::tip[API Usage]
Learn more about the Menu API usage from [here](https://docs.salla.dev/doc-705835?nav=01HNFTDZPB31Y2E120R84YXKCX)
:::

## Example 
<!--
focus: false
-->

<Frame caption="Header">
  ![Image](https://cdn.salla.network/docs/twilight/6/js-web-menu-header-01.png)
</Frame>


<Frame caption="Footer">
  ![Image](https://cdn.salla.network/docs/twilight/6/js-web-menu-footer-01.png)
</Frame>

## Usage

<Tabs>
  <Tab title="HTML">

```html
<salla-menu source="footer"></salla-menu>
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

| Property           | Attribute        | Type                               | Default          |
| ------------------ | ---------------- | ---------------------------------- | ---------------- |
| Limit        | `limit`          | Limiting the number of menu items options                                         | `number`                         | `undefined` |
| Source             | `source`        | `Sources.Footer \| Sources.Header` | `Sources.Header` |
| Source Value       | `source-value`  | `string`                           | `undefined`      |
| Top Navigation Bar | `topnav`        | `boolean`                          | `undefined`      |
| Use React Link     | `use-react-link`| `boolean`                          | `false`          |

---

## form/Salla-Quantity-Input-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Quantity Input

The `<salla-quantity-input>` web component is used to allow the customer to use a counter to specify the needed quantity of a specific product, which is framed by a [Button](https://docs.salla.dev/doc-422694?nav=01HNFTE06J4QC24T0D5BPRYKMD) component. The component extends the input number element. For more, read from [Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number).


## Example

<!--
focus: false
-->

![Quantity Input Example](https://cdn.salla.network/docs/twilight/6/js-web-quantity-input-01.gif)

## Usage
<Tabs>
  <Tab title="HTML">
      
 ```html
<!-- Basic Quantity Input component usage -->
<salla-quantity-input
  cart-item-id="12345"
  max="10"
  value="1"
  name="quantity">
</salla-quantity-input>
```     
  </Tab>

 <Tab title="SASS">
        
 This JS web component can be targeted for styling by its `.s-quantity-input` class. Following is a complete source code for customizing this component:

```js
.s-quantity-input{
  &-input{
    
  }
  &-button{

  }
}
```     
  </Tab>  
    
</Tabs>



## Properties

| Property | Attribute  | Description                                                                                                | Type                             | Default     |
| -------- | ---------- | ----------------------- | -------------------------------- | ----------- |
| Cart Item ID            | `cart-item-id`              | Cart Item's ID.                                                                                                         | `any`                                                     | `undefined`         |

## Methods
The pre-defined `methods` allow for calling the function built by Salla which are `increase` to add up quantity by one, `decrease` to reduce quantity by one, and `setValue` which allows for a customizible manner of inputting numbers.


| Method   | Description                | Return Type             |
| -------- | -------------------------- | ----------------------- |
| `increase()` | Increases quantity by one. | `Promise<HTMLElement>` |
| `decrease()` | Decreases quantity by one. | `Promise<HTMLElement>`  |
| `setValue(value: any)` | Sets quantity by custom value. | `Promise<HTMLElement>` |

---

## form/Salla-Select-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Select

The `<salla-select>` web component is used to allow selection from a particular dropdown list, which can be an item's color, size, and so on. The component can be customized using the properties' parameters available.

## Example

<!--
focus: false
-->

![Select](https://cdn.salla.network/docs/twilight/6/js-web-select-01.png)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Basic Select component usage -->
<salla-select
  color="primary"
  autocomplete="true"
  size="large">
</salla-select>
```     
  </Tab>
<Tab title="SASS">
    
```css
.s-select-label {
  display: block;
  margin-bottom: 0.5rem;
  color: #111827;
  font-size: 0.875rem;
  line-height: 1.25rem;
  font-weight: 500;
}

.s-select-underline {
  display: block;
  padding-left: 0;
  padding-right: 0;
  padding-top: 0.625rem;
  padding-bottom: 0.625rem;
  background-color: transparent;
  color: #6B7280;
  font-size: 0.875rem;
  line-height: 1.25rem;
  width: 100%;
  border-width: 0;
  border-bottom-width: 2px;
  border-color: #E5E7EB;
  appearance: none;
}

.s-select-outlined {
  display: block;
  padding: 0.625rem;
  padding-top: 0.75rem;
  padding-bottom: 0.75rem;
  padding-left: 1rem;
  padding-right: 1rem;
  background-color: #F9FAFB;
  color: #111827;
  font-size: 0.875rem;
  line-height: 1.25rem;
  width: 100%;
  border-radius: 0.5rem;
  border-width: 1px;
  border-color: #D1D5DB;
}

.s-select-x-large {
  height: 5rem;
}

.s-select-large {
  height: 4rem;
}

.s-select-normal {
  height: 3rem;
}

.s-select-small {
  height: 3rem;
}

.s-select-x-small {
  height: 2.5rem;
}

.s-select-field {
  padding-top: 0.25rem;
  padding-bottom: 0.25rem;
  padding-right: 0.5rem;
  padding-left: 0.5rem;
  margin: 0;
  font-size: 1.125rem;
  line-height: 1.75rem;
  font-weight: 400;
  line-height: 1.75rem;
  width: 100%;
  border-radius: 0.375rem;
  border-color: #9CA3AF;
  box-shadow: none;
}


.s-select-hint {
  margin-top: 0.25rem;
  color: #374151;
  font-size: 0.875rem;
  line-height: 1.25rem;
  line-height: 1.25rem;
}
```
      
  </Tab>    
</Tabs>

## Properties

| Property      | Attribute       | Description                                                                                                                 | Type                                                                             | Default          |
| ------------- | --------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ---------------- |
| Auto Complete | `autocomplete`  | Enables multiple item selection.                                                                                            | `boolean`                                                                        | `false`          |
| Auto Focus    | `autofocus`     | Enables `autofocus`.                                                                                                        | `boolean`                                                                        | `false`          |
| Chips         | `chips`         | Changes display of selections to `chips`.                                                                                   | `boolean`                                                                        | `false`          |
| Clear Icon    | `clear-icon`    | Applies when using `clearable` and the input is filled.                                                                     | `string`                                                                         | `'sicon-cancel'` |
| Clearable     | `clearable`     | Adds input clear functionality.                                                                                             | `boolean`                                                                        | `false`          |
| Color         | `color`         | Applies specified color to the control.                                                                                     | `"danger" \| "dark" \| "gray" \| "light" \| "primary" \| "success" \| "warning"` | `'primary'`      |
| Disabled      | `disabled`      | Disable the input.                                                                                                          | `boolean`                                                                        | `false`          |
| Flat          | `flat`          | Removes elevation or box shadow.                                                                                            | `boolean`                                                                        | `undefined`      |
| Hide Detail   | `hide-detail`   | Hides `hint` if any.                                                                                                        | `boolean`                                                                        | `false`          |
| Hint          | `hint`          | Adds hint text.                                                                                                             | `string`                                                                         | `undefined`      |
| Item Disabled | `item-disabled` | Sets property of items’s disabled value.                                                                                    | `string`                                                                         | `'disabled'`     |
| Item Text     | `item-text`     | Sets property of items’s text value.                                                                                        | `string`                                                                         | `"text"`         |
| Item Value    | `item-value`    | Sets property of items’s value - must be primitive. Dot notation is supported.                                              | `string`                                                                         | `"value"`        |
| Items         | --              | Can be an array of objects or array of strings. When using objects, it will look for a `text`, `value` and `disabled keys`. | `any[]`                                                                          | `[]`             |
| Label         | `label`         | Sets label value.                                                                                                           | `string`                                                                         | `undefined`      |
| Loading       | `loading`       | Displays linear progress bar.                                                                                               | `boolean`                                                                        | `false`          |
| Loading Color | `loading-color` | Specifies which color is applied to the progress bar.                                                                       | `string`                                                                         | `'primary'`      |
| Multiple      | `multiple`      | Enables multiple item selection.                                                                                            | `boolean`                                                                        | `false`          |
| Persist Hint  | `persist-hint`  | Forces hint to always be visible.                                                                                           | `boolean`                                                                        | `false`          |
| Placeholder   | `placeholder`   | Sets the input’s placeholder text.                                                                                          | `string`                                                                         | `undefined`      |
| Required      | `required`      | Enables multiple item selection.                                                                                            | `boolean`                                                                        | `false`          |
| Return Object | `return-object` | Changes the selection behavior to return the object directly, rather than the value specified with `item-value`.            | `boolean`                                                                        | `false`          |
| Shape         | `shape`         | Defines the appearance of the component.                                                                                    | `"outlined" \| "underline"`                                                      | `'outlined'`     |
| Size          | `size`          | Available sizing options.                                                                                                   | `"large" \| "normal" \| "small" \| "x-large" \| "x-small"`                       | `'normal'`       |
| Value         | `value`         | The selected value.                                                                                                         | `any`                                                                            | `undefined`      |

---

## form/Salla-Tel-Input-Salla-Storefront-Web-Components-Twilight-Documentation-Salla-Docs

# Tel Input

The `<salla-tel-input>` web component is used to show a field for entering a telephone number, with country key/code prefix, and that can be customized using the properties' parameters available.


## Example

<!--
focus: false
-->

![Tel Input Example](https://cdn.salla.network/docs/twilight/6/js-web-tel-input-01.gif)

## Usage

<Tabs>
  <Tab title="HTML">

```html
<!-- Accepting Valid Telephone Input-->
<salla-tel-input
  onclick="telInput.isValid()"
  country-code="sa"
  phone="555555555">
</salla-tel-input>

<!-- getting Inputted Values -->
<salla-button fill="outline" color="primary" onclick="telInput.getValues()">
  Get Values
</salla-button>
```     
  </Tab>
 <Tab title="JS">

```js
// Save reference to the Tel Input Component below
var telInput = document.querySelector("salla-tel-input");

// Listen for the telInput for enterClicked event
telInput.addEventListener("phoneEntered", function (phone) {
  console.log("phone readt!", phone);
});
```      
  </Tab>
    
<Tab title="SASS">

This JS web component can be targeted for styling by its `.s-tel-input` class. Following is a complete source code for customizing this component:

```js
.s-tel-input {
  // the input field
  &-control {

  }
  // field error message
  &-error-msg {

  }
}
```      
  </Tab>  
</Tabs>

<!-- Auto Generated Below -->

## Properties

| Property     | Attribute      | Description          | Type     | Default                                         |
| ------------ | -------------- | -------------------- | -------- | ----------------------------------------------- |
| Country Code | `country-code` | Current country code | `string` | `'salla.config.get('user.country_code', 'SA')'` |
| Name         | `name`         | Input name value     | `string` | ``                                         |
| Phone        | `phone`        | Current phone number | `string` | `undefined`                                     |

## Events

| Event          | Description                                                          | Type               |
| -------------- | -------------------------------------------------------------------- | ------------------ |
| `phoneEntered` | This event will be fired when the user enters the telephone input field | `CustomEvent<Phone>` |

## Methods

The pre-defined `methods` allow for calling functions built by Salla to carry out certain actvities, suh as `getValues` to fetch the inputted values, and `isValid` to determine whether or not the values are valid.


| Method        | Description                                       | Return Type                                             |
| ------------- | ------------------------------------------------- | ------------------------------------------------------- |
| `getValues()` | Gets current inputted values                      | `Promise<{[x: string]: string; countryCode: string; }>` |
| `isValid()`   | Shows the validity of the current inputted values | `Promise<boolean>`                                      |

---

