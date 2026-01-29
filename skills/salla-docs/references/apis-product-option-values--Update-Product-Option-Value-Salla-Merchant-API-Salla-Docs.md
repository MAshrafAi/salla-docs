# Apis Product Option Values  Update Product Option Value Salla Merchant Api Salla Docs

## Table of Contents

- [apis-product-option-values/Update-Product-Option-Value-Salla-Merchant-API-Salla-Docs](#apis-product-option-values-update-product-option-value-salla-merchant-api-salla-docs)

---

## apis-product-option-values/Update-Product-Option-Value-Salla-Merchant-API-Salla-Docs

# Update Product Option Value

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/options/values/{value}:
    put:
      summary: Update Product Option Value
      deprecated: false
      description: >-
        This endpoint allows you to update value details in a specific option
        for a specific product by passing the `value` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Update-Value
      tags:
        - Default module/Merchant API/APIs/Product Option Values
        - Product Option Values
      parameters:
        - name: value
          in: path
          description: >-
            Unique identification number assigned to the Option Value. List of
            Product Option Value IDs can be found
            [here](https://docs.salla.dev/api-5394168).
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/productOptionValue_request_body'
            example:
              name: XzL
              price: 121
              display_value: xzzl
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productValue_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 667315336
                  name: salvalueupdated
                  price:
                    amount: 0
                    currency: SAR
                  display_value: ''
                  option_id: 1833119338
                  image_url: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  hashed_display_value: ''
                  skus:
                    - id: 652911549
                      price:
                        amount: 110
                        currency: SAR
                      regular_price:
                        amount: 234
                        currency: SAR
                      sale_price:
                        amount: 100
                        currency: SAR
                      stock_quantity: 13
                      barcode: barcode-ABC
                      sku: sku-variant-1551119600
                      related_option_values:
                        - 667315336
                        - 322122678
                        - 569679762
                        - 1318371393
                    - id: 1966914519
                      price:
                        amount: 9.9
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      sale_price:
                        amount: 100
                        currency: SAR
                      stock_quantity: 20
                      barcode: ''
                      sku: 23-TD23-32
                      related_option_values:
                        - 667315336
                        - 322122678
                        - 1552401892
                        - 1318371393
                    - id: 1799056677
                      price:
                        amount: 9.9
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      sale_price:
                        amount: 100
                        currency: SAR
                      stock_quantity: 20
                      barcode: ''
                      sku: 23-TD23-32
                      related_option_values:
                        - 667315336
                        - 322122678
                        - 1209980149
                        - 1318371393
                    - id: 673658412
                      price:
                        amount: 9.9
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      sale_price:
                        amount: 100
                        currency: SAR
                      stock_quantity: 20
                      barcode: ''
                      sku: 23-TD23-32
                      related_option_values:
                        - 667315336
                        - 322122678
                        - 393917653
                        - 1318371393
          headers: {}
          x-apidog-name: Updated Successfully
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
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_validation_422'
              example:
                status: 422
                success: false
                error:
                  code: validation_failed
                  message: validation have failed
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: ProductValue
      x-apidog-folder: Default module/Merchant API/APIs/Product Option Values
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394200-run
components:
  schemas:
    productOptionValue_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            A descriptive label or title given to a specific attribute, feature,
            or characteristic associated with a product, helping to define and
            differentiate its various qualities or options.
        price:
          type: number
          description: >-
            The additional price which will be added to the product price when
            the customer adds/selects this value. Alternatively the value is set
            0 if there is no additional price.
        quantity:
          type: integer
          description: >-
            The specific quantity or number of units available for a particular
            option or variation of a product.
          examples:
            - 10
        display_value:
          type: string
          description: >-
            The display value in UI based on display type of option, by default
            will use the name of value as display value when the
            'display_value=text', but in case you used 'image' then you need to
            set the image id as value You can upload a new image to product
            using attach image endpoint then use 'image' id from response,
            otherwise when use 'color' as display type you need to pass the
            color for example '#000' for black color
        is_default:
          type: boolean
          description: >-
            The option to indicate if this value is the default value of the
            product option.
      required:
        - name
      x-apidog-orders:
        - name
        - price
        - quantity
        - display_value
        - is_default
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    productValue_response_body:
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
          $ref: '#/components/schemas/ProductValue'
      x-apidog-orders:
        - status
        - success
        - data
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

