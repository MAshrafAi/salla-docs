# Apis Product Options  Create Product Option Salla Merchant Api Salla Docs

## Table of Contents

- [apis-product-options/Create-Product-Option-Salla-Merchant-API-Salla-Docs](#apis-product-options-create-product-option-salla-merchant-api-salla-docs)
- [apis-product-options/Delete-Product-Option-Salla-Merchant-API-Salla-Docs](#apis-product-options-delete-product-option-salla-merchant-api-salla-docs)

---

## apis-product-options/Create-Product-Option-Salla-Merchant-API-Salla-Docs

# Create Product Option

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/{product}/options:
    post:
      summary: Create Product Option
      deprecated: false
      description: >-
        This endpoint allows you to create a new option for a specific product
        by passing the `product` as a path parameter. 



        :::tip[Note]

        For the `product.type` variable set to `product`, creating a new product
        option will generate a new variant for this option.

        :::


        :::warning[Important]

        If you're creating a new physical product with variants, the price must
        be set after creating options. call the [update product
        SKU](https://docs.salla.dev/5394204e0) to set the price for each
        variant.  Including the price in this case will result on a `422`
        validation error.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Create-Option
      tags:
        - Default module/Merchant API/APIs/Product Options
        - Product Options
      parameters:
        - name: product
          in: path
          description: >-
            Unique identification number assigned to a product. List of products
            IDs can be found [here](https://docs.salla.dev/api-5394168).
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/post_productOption_request_body'
            example:
              name: option name
              required: true
              visibility: on_condition
              visibility_condition_type: '='
              visibility_condition_option: 2134428744
              visibility_condition_value: 306646512
              display_type: image
              values:
                - name: value 3
                  price: '10'
                  is_default: false
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productOption_response_body'
              examples:
                '1':
                  summary: Example
                  value:
                    status: 201
                    success: true
                    data:
                      id: 1130246629
                      name: size
                      description: this product is best seller
                      type: radio
                      required: false
                      associated_with_order_time: 0
                      sort: 0
                      display_type: text
                      visibility: always
                      values:
                        - id: 322122678
                          name: XL
                          price:
                            amount: 180
                            currency: SAR
                          display_value: XL
                          option_id: 1130246629
                          image_url: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                          hashed_display_value: XL
                      skus:
                        - id: 652911549
                          price:
                            amount: 150
                            currency: SAR
                          regular_price:
                            amount: 234
                            currency: SAR
                          stock_quantity: 3000
                          barcode: barcode-ABC
                          sku: sku-variant-1551119600
                          related_option_values:
                            - 667315336
                            - 322122678
                '2':
                  summary: Example
                  value:
                    success: false
                    status: 404
                    error:
                      code: 404
                      message: >-
                        The content you are trying to access is no longer
                        available
                '3':
                  summary: Example
                  value:
                    status: 422
                    success: false
                    error:
                      code: validation_failed
                      message: Alert Validation failed
                      fields:
                        '{field-name}':
                          - The {field-label} field is required.
                '4':
                  summary: Unauthorized
                  value:
                    status: 401
                    success: false
                    error:
                      code: Unauthorized
                      message: >-
                        The access token should have access to one of those
                        scopes: products.read_write
          headers: {}
          x-apidog-name: Created Successfully
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
          headers: {}
          x-apidog-name: Not Found
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_validation_422'
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: ProductOption
      x-apidog-folder: Default module/Merchant API/APIs/Product Options
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394194-run
components:
  schemas:
    post_productOption_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            A distinctive label or title assigned to a specific item or
            commodity, serving as an identifier and often conveying essential
            information about the product.
        type:
          type: string
          x-stoplight:
            id: zaghsz6j3so0p
          enum:
            - radio
            - textarea
            - number
            - checkbox
            - image
            - date
            - time
            - datetime
            - map
            - file
            - color_picker
            - splitter
          description: Product option field type
        display_type:
          type: string
          description: >-
            The various choices or variations of a product are visually
            presented to customers, typically categorized as text, image, or
            color representations.
          default: text
          enum:
            - text
            - image
            - color
        visibility:
          type: string
          x-stoplight:
            id: frqfaaqmqiwvx
          default: always
          enum:
            - always
            - on_condition
          description: Product option field visibilty
        visibility_condition_type:
          type: string
          x-stoplight:
            id: ffyarta6r1fan
          description: >-
            Visibility condition type. Required if the `visibility` variable is
            set to `on_condition`
          enum:
            - '='
            - '!='
            - '>'
            - <
        visibility_condition_option:
          type: string
          x-stoplight:
            id: gy9pos0tn8mkx
          description: "The product option's ID for the condition\t. Required if the variable `visibility` is set to `on_condition`"
        visibility_condition_value:
          type: string
          x-stoplight:
            id: h5z6uezzsirin
          description: >-
            The product option value's ID for the condition. Required if the
            variable `visibility` is set to `on_condition`
        sort:
          type: integer
          x-stoplight:
            id: hdmtzlooik6ur
          description: The sort order of the product option
        advance:
          type: string
          x-stoplight:
            id: fqfyxvn8npl7t
          description: >-
            Whether or not the product has variants. If the product is of type
            `product`, then adding an option to the product will set it to
            `advance`. Default value is `true` when the product type is set to
            `product`
        associated_with_order_time:
          type: boolean
          x-stoplight:
            id: 3y3npfnsilgoy
          description: Only works when the variable `type` is set to `date`
        not_same_day_order:
          type: boolean
          x-stoplight:
            id: 715eduf2lgs9r
          description: Only works when the variable `type` is set to `date`
        values:
          type: array
          x-stoplight:
            id: ev9ebib0gu7ui
          description: >-
            Product Option values. Required if the variable `type` is set to
            either `radio`, `file`, or `checkbox`
          items:
            x-stoplight:
              id: xxzdpjiumkk0d
            type: object
            properties:
              name:
                type: string
                description: >-
                  A descriptive label or title given to a specific attribute,
                  feature, or characteristic associated with a product, helping
                  to define and differentiate its various qualities or options.
              price:
                type: number
                description: >-
                  The additional price which will be added to the product price
                  when the customer adds/selects this value. Alternatively the
                  value is set 0 if there is no additional price. 

                  Note: Cannot be included for phyical products
              display_value:
                type: string
                description: >-
                  The display value in UI based on display type of option, by
                  default will use the name of value as display value when the
                  'display_value=text', but in case you used 'image' then you
                  need to set the image id as value You can upload a new image
                  to product using attach image endpoint then use 'image' id
                  from response, otherwise when use 'color' as display type you
                  need to pass the color for example '#000' for black color.
                  More about attaching an image from [here](api-5394187)
                enum:
                  - image
                  - color
            required:
              - name
            x-apidog-orders:
              - name
              - price
              - display_value
            x-apidog-ignore-properties: []
      required:
        - name
        - type
      x-apidog-orders:
        - name
        - type
        - display_type
        - visibility
        - visibility_condition_type
        - visibility_condition_option
        - visibility_condition_value
        - sort
        - advance
        - associated_with_order_time
        - not_same_day_order
        - values
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    productOption_response_body:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/ProductOption'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductOption:
      description: >-
        Detailed structure of the product option model object showing its fields
        and data types.
      type: object
      title: ProductOption
      x-tags:
        - Models
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            A unique identifier assigned to a specific product configuration or
            variant.
        name:
          type: string
          description: >-
            The label or title used to describe a specific choice or attribute
            associated with a product.
        description:
          type: string
          description: >-
            A text or content that provides detailed information about a
            product.
          nullable: true
        type:
          type: string
          description: Type of the product option, it can be a `radio` button or `checkbox`
          enum:
            - radio
            - checkbox
            - button
          x-apidog-enum:
            - value: radio
              name: ''
              description: Radio button type
            - value: checkbox
              name: ''
              description: Checkbox button type
            - value: button
              name: ''
              description: Button type
        required:
          type: boolean
          description: Whether or not the product option is obligatory.
        associated_with_order_time:
          type: integer
          description: >-
            The product option is only relevant to order receiving time when it
            pertains to date-time selections. **ONLY** for date time options.
        sort:
          type: integer
          description: >-
            Product option sort refers to the method or criteria used to arrange
            or order product options.
          nullable: true
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - value: text
              name: ''
              description: Display as text
            - value: image
              name: ''
              description: Display as image
            - value: color
              name: ''
              description: Display as color
        visibility:
          type: string
          description: >-
            Product option visibility based on condition is applied exclusively
            to products categorized as 'food' or 'service'.
          enum:
            - always
            - on_condition
          x-apidog-enum:
            - value: always
              name: ''
              description: Always display the product on all product types
            - value: on_condition
              name: ''
              description: Show the product option on specific types
        visibility_condition_type:
          type: string
          description: Product option visiblity condition type
          enum:
            - '>'
            - <
            - '='
            - '!='
          x-apidog-enum:
            - value: '>'
              name: ''
              description: Great than value
            - value: <
              name: ''
              description: Less than value
            - value: '='
              name: ''
              description: Equal to value
            - value: '!='
              name: ''
              description: Not equal to value
        visibility_condition_option:
          type: integer
          description: Whether or not Product option is visible.
          nullable: true
        visibility_condition_value:
          type: integer
          description: >-
            A unique identifier associated with a specific value or choice
            within a product option.
          nullable: true
        values:
          type: array
          items:
            $ref: '#/components/schemas/ProductValue'
            description: Product values details.
        skus:
          type: array
          items:
            $ref: '#/components/schemas/ProductVariant'
            description: Product SKUs details.
      x-apidog-orders:
        - id
        - name
        - description
        - type
        - required
        - associated_with_order_time
        - sort
        - display_type
        - visibility
        - visibility_condition_type
        - visibility_condition_option
        - visibility_condition_value
        - values
        - skus
      required:
        - id
        - name
        - description
        - type
        - required
        - associated_with_order_time
        - sort
        - display_type
        - visibility
        - visibility_condition_type
        - visibility_condition_option
        - visibility_condition_value
        - values
        - skus
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductVariant:
      description: >-
        Detailed structure of the product variant model object showing its
        fields and data types.
      type: object
      title: ProductVariant
      x-tags:
        - Models
      x-examples:
        Example:
          id: 1115785385
          price:
            amount: 90.5
            currency: SAR
          regular_price:
            amount: 100.33
            currency: SAR
          sale_price:
            amount: 90.5
            currency: SAR
          stock_quantity: 4
          barcode: abc01
          sku: 23-TD23-32
          mpn: 43242342
          gtin: 54353453
          related_options:
            - 512644768
            - 976327842
          related_option_values:
            - 512644768
            - 976327842
          weight: 3
          weight_type: kg
          weight_label: ٣ كجم
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific variant of a product
            or item.
        price:
          type: object
          description: The price of the product variant.
          properties:
            amount:
              type: number
              description: 'The amount of the product price. Example: 96.33'
              examples:
                - 96.33
            currency:
              type: string
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        regular_price:
          type: object
          x-stoplight:
            id: uub4l1jz09qkf
          description: The regular price of the product variant.
          properties:
            amount:
              type: number
              x-stoplight:
                id: a026eri5g9k4h
            currency:
              type: string
              x-stoplight:
                id: g8gzh6e6ghf4l
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        cost_price:
          type: object
          description: The purchase price excluding any additional expenses.
          x-stoplight:
            id: 687chslg6fdqy
          properties:
            amount:
              type: number
              description: 'The value of the cost price amount. Example: 100.33'
            currency:
              type: string
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        sale_price:
          type: object
          description: The sale price of the product variant.
          properties:
            amount:
              type: number
              description: 'The value of the sale price a Example: 100.33'
            currency:
              type: string
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        has_special_price:
          type: boolean
          readOnly: true
          description: Whether or not the product variant has a special price.
        stock_quantity:
          type: integer
          description: >-
            The amount of the product variant total stock quantity. Only updated
            if the store feature manage product by branches is not activated.
          examples:
            - 4
        unlimited_quantity:
          type: boolean
          x-stoplight:
            id: 62evc4ca3tf7u
          description: Whether or not the product variant is of unlimit quantity.
        notify_low:
          type: integer
          x-stoplight:
            id: j71y502ca9eth
          description: >-
            Sets a threshold value to trigger notifications when inventory falls
            below.
        barcode:
          type: string
          description: The barcode value of product variant.
          examples:
            - abc01
        sku:
          type: string
          description: >-
            A unique Stock Keeping Unit (SKU) identifier assigned to a specific
            variant of a product.
          examples:
            - 23-TD23-32
        mpn:
          type: string
          x-stoplight:
            id: 1xotdb1fnb2p0
          description: >-
            Manufacturer Part Number, a unique identifier assigned by a
            manufacturer to a specific product or component.
        gtin:
          type: string
          x-stoplight:
            id: gp8b5bu8mg5y6
          description: >-
            Global Trade Item Number, a unique and standardized identifier used
            to uniquely represent products, in the global marketplace, to enable
            efficient tracking and management across supply chains and retail
            sectors. If `product_type` is set to any of the following:
            `product`, `group_products`, `codes`, `digital`, `donating` then
            value can be set. Otherwise, it can be set to `null`
        updated_at:
          $ref: '#/components/schemas/Date'
          description: The date and time product variant is updated.
        related_options:
          type: array
          x-stoplight:
            id: gwg4szqmpeyr4
          description: An array for the related options to this variant.
          items:
            x-stoplight:
              id: 2ezv3bfmmwob0
            type: integer
        related_option_values:
          type: array
          x-stoplight:
            id: ruoh1jjr3rjq6
          description: An array for the values of the related options to this variant.
          items:
            x-stoplight:
              id: 78wwfmqiyubcx
            type: integer
        weight:
          type: number
          description: >-
            The numerical value that represents the mass or weight of a specific
            variant of a product.
          examples:
            - 3
        weight_type:
          type: string
          description: Product variant weight type
          examples:
            - kg
        weight_label:
          type: string
          description: Product variant weight label representing the type of the weight.
          examples:
            - ٣ كجم
        is_user_subscribed_to_sku:
          type: boolean
          readOnly: true
          description: Whether or not the user subscribed for the sku.
        is_default:
          type: boolean
          description: >-
            Whether or not enable showing that the product variant is the
            default 
      x-apidog-orders:
        - id
        - price
        - regular_price
        - cost_price
        - sale_price
        - has_special_price
        - stock_quantity
        - unlimited_quantity
        - notify_low
        - barcode
        - sku
        - mpn
        - gtin
        - updated_at
        - related_options
        - related_option_values
        - weight
        - weight_type
        - weight_label
        - is_user_subscribed_to_sku
        - is_default
      required:
        - id
        - price
        - regular_price
        - cost_price
        - sale_price
        - has_special_price
        - stock_quantity
        - unlimited_quantity
        - notify_low
        - barcode
        - sku
        - mpn
        - gtin
        - updated_at
        - related_options
        - related_option_values
        - weight
        - weight_type
        - weight_label
        - is_user_subscribed_to_sku
        - is_default
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Date:
      type: object
      title: Date
      x-examples:
        Example:
          date: '2020-10-14 14:28:03.000000'
          timezone_type: 3
          timezone: Asia/Riyadh
      x-tags:
        - Models
      properties:
        date:
          type: string
          format: date-time
          description: >-
            A specific point in time, typically expressed in terms of a calendar
            system, including the day, month, year, hour, minutes, seconds and
            nano seconds. For example: "2020-10-14 14:28:03.000000"
        timezone_type:
          type: number
          description: 'Timezone type of the date, for Middel East = 3 '
        timezone:
          type: string
          description: Timezone value "Asia/Riyadh"
      x-apidog-orders:
        - date
        - timezone_type
        - timezone
      required:
        - date
        - timezone_type
        - timezone
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductValue:
      description: >-
        Detailed structure of the product value model object showing its fields
        and data types.
      type: object
      title: ProductValue
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: A unique identifier assigned to a value associated with a product.
        name:
          type: string
          description: Identifying label for a product attribute.
        price:
          type: object
          description: The product price.
          properties:
            amount:
              type: number
              description: Amout of the price.
            currency:
              type: string
              description: The currency of the amount.
          x-apidog-orders:
            - amount
            - currency
          x-apidog-ignore-properties: []
        formatted_price:
          type: string
          description: >-
            The extra formatted price added when a customer selects a specific
            value.
        display_value:
          type: string
          description: >-
            The UI displays values based on the option's display type. By
            default, it shows the name when `display_value=text`. For `image`,
            use the image ID (uploaded via the attach image endpoint). For
            `color`, provide a value like `#000` for black.
        advance:
          type: boolean
          description: Is the option value is advanced or not
        option_id:
          description: A unique identifier assigned to a specific choice.
          type: number
        image_url:
          type: string
          description: The web address where the corresponding image is hosted.
        hashed_display_value:
          type: string
          description: >-
            if `option.type` = `image` then hashed display value return `image
            id`. 

            if `option.type` = `text` then hashed display value return value
            `name` 
        translations:
          type: object
          properties:
            ar:
              type: object
              properties:
                option_details_name:
                  type: string
                  readOnly: true
                  description: Option Details Name in Arabic
              x-apidog-orders:
                - option_details_name
              readOnly: true
              description: Translation provided in Arabic language.
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - ar
          readOnly: true
          description: Translation of option values in different languages
          required:
            - ar
          x-apidog-ignore-properties: []
        is_default:
          type: boolean
          description: >-
            This option will be enabled when this particular value is the
            default value.
        is_out_of_stock:
          type: boolean
          description: Whether or not the option value is out of stock.
          readOnly: true
      x-apidog-orders:
        - id
        - name
        - price
        - formatted_price
        - display_value
        - advance
        - option_id
        - image_url
        - hashed_display_value
        - translations
        - is_default
        - is_out_of_stock
      required:
        - id
        - name
        - price
        - formatted_price
        - display_value
        - advance
        - option_id
        - image_url
        - hashed_display_value
        - translations
        - is_default
        - is_out_of_stock
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Object Not Found(404):
      type: object
      properties:
        status:
          type: integer
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        error:
          type: object
          properties:
            code:
              type: integer
              description: >-
                Not Found Response error code, a numeric or alphanumeric unique
                identifier used to represent the error.
            message:
              type: string
              description: >-
                A message or data structure that is generated or returned when
                the response is not found or explain the error.
          required:
            - code
            - message
          x-apidog-orders:
            - code
            - message
          x-apidog-ignore-properties: []
      required:
        - status
        - success
        - error
      x-apidog-orders:
        - status
        - success
        - error
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    error_validation_422:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        error:
          $ref: '#/components/schemas/Validation'
      x-apidog-orders:
        - status
        - success
        - error
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Validation:
      type: object
      properties:
        code:
          type: string
          description: >-
            Response error code,a numeric or alphanumeric unique identifier used
            to represent the error.
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when the
            response is not found or explain the error.
        fields:
          type: object
          description: Validation rules with problems
          properties:
            '{field-name}':
              type: array
              items:
                type: string
          x-apidog-orders:
            - '{field-name}'
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - code
        - message
        - fields
      required:
        - code
        - message
        - fields
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    error_unauthorized_401:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        error:
          $ref: '#/components/schemas/Unauthorized'
      x-apidog-orders:
        - status
        - success
        - error
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Unauthorized:
      type: object
      x-examples: {}
      title: Unauthorized
      properties:
        code:
          type: string
          description: Code Error
        message:
          type: string
          description: Message Error
      x-apidog-orders:
        - code
        - message
      required:
        - code
        - message
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
  securitySchemes:
    bearer:
      type: http
      scheme: bearer
servers:
  - url: ''
    description: Cloud Mock
  - url: https://api.salla.dev/admin/v2
    description: Production
security:
  - bearer: []

```

---

## apis-product-options/Delete-Product-Option-Salla-Merchant-API-Salla-Docs

# Delete Product Option

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/options/{option}:
    delete:
      summary: Delete Product Option
      deprecated: false
      description: >-
        This endpoint allows you to delete a particular option for a specific
        product including its related data (values and variants) by passing the
        `option` as a path parameter. 

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Delete-Option
      tags:
        - Default module/Merchant API/APIs/Product Options
        - Product Options
      parameters:
        - name: option
          in: path
          description: Unique identification number assigned to the product option.
          required: true
          example: 0
          schema:
            type: integer
      responses:
        '202':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/delete_success'
              example:
                status: 202
                success: true
                data:
                  message: The Object has been removed successfully
                  code: 202
          headers: {}
          x-apidog-name: Deleted Successfully
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: >-
                    The access token should have access to one of those scopes:
                    products.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                success: false
                status: 404
                error:
                  code: 404
                  message: The content you are trying to access is no longer available
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: delete
      x-apidog-folder: Default module/Merchant API/APIs/Product Options
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394197-run
components:
  schemas:
    delete_success:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.Response status Code
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/DeleteSuccess'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    DeleteSuccess:
      type: object
      properties:
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when a
            deletion operation is successful.
        code:
          type: number
          description: >-
            A numerical or alphanumeric code that is used in various software
            and web development contexts to convey information about the outcome
            of a request or operation.
      x-apidog-orders:
        - message
        - code
      required:
        - message
        - code
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Object Not Found(404):
      type: object
      properties:
        status:
          type: integer
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        error:
          type: object
          properties:
            code:
              type: integer
              description: >-
                Not Found Response error code, a numeric or alphanumeric unique
                identifier used to represent the error.
            message:
              type: string
              description: >-
                A message or data structure that is generated or returned when
                the response is not found or explain the error.
          required:
            - code
            - message
          x-apidog-orders:
            - code
            - message
          x-apidog-ignore-properties: []
      required:
        - status
        - success
        - error
      x-apidog-orders:
        - status
        - success
        - error
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    error_unauthorized_401:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        error:
          $ref: '#/components/schemas/Unauthorized'
      x-apidog-orders:
        - status
        - success
        - error
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Unauthorized:
      type: object
      x-examples: {}
      title: Unauthorized
      properties:
        code:
          type: string
          description: Code Error
        message:
          type: string
          description: Message Error
      x-apidog-orders:
        - code
        - message
      required:
        - code
        - message
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
  securitySchemes:
    bearer:
      type: http
      scheme: bearer
servers:
  - url: ''
    description: Cloud Mock
  - url: https://api.salla.dev/admin/v2
    description: Production
security:
  - bearer: []

```

---

