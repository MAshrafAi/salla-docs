# Apis Product Variants  Update Product Variant Salla Merchant Api Salla Docs

## Table of Contents

- [apis-product-variants/Update-Product-Variant-Salla-Merchant-API-Salla-Docs](#apis-product-variants-update-product-variant-salla-merchant-api-salla-docs)

---

## apis-product-variants/Update-Product-Variant-Salla-Merchant-API-Salla-Docs

# Update Product Variant

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/variants/{variant}:
    put:
      summary: Update Product Variant
      deprecated: false
      description: >-
        This endpoint allows you to update variant details by passing the
        `variant` as a path parameter. 



        :::caution[Important]

        - All variables in the update variant body request are optional.

        - Updating one variable at a time is possible, but at least one of the
        variables must be in the body request payload. Otherwise, an error will
        be shown if you send an empty body request payload.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: update-product-variant
      tags:
        - Default module/Merchant API/APIs/Product Variants
        - Product Variants
      parameters:
        - name: variant
          in: path
          description: >-
            Unique identification number assigned to a Product SKU Variant .
            List of Product SKU IDscan be found
            [here](https://docs.salla.dev/api-5394168).
          required: true
          example: ''
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                sku:
                  type: string
                  description: >-
                    Stock Keeping Unit is a unique alphanumeric code used to
                    identify and manage specific product variant within a
                    company's inventory system.
                barcode:
                  type: string
                  description: The barcode value of product variant.
                price:
                  type: number
                  description: The price of the product variant.
                sale_price:
                  type: number
                  description: 'The sale price of the product variant. Example: 90.50'
                cost_price:
                  type: number
                  description: >-
                    The original or purchase price at which a product variant or
                    item was acquired by a business or individual, excluding any
                    additional expenses or markups.
                stock_quantity:
                  type: integer
                  description: >-
                    Amount of the product variant total stock quantity for the
                    default branch, it well ignored if the `quantities` has been
                    used in the body
                weight:
                  type: integer
                  description: Product Variant Weight.
                mpn:
                  type: integer
                  description: Manufacturer Part Number.
                gtin:
                  type: integer
                  description: >-
                    Global Trade Item Number, a unique and standardized
                    identifier used to uniquely represent products, items, or
                    services in the global marketplace, to enable efficient
                    tracking and management across supply chains and retail
                    sector. If `product_type` is set to any of the following:
                    `product`, `group_products`, `codes`, `digital`, `donating`
                    then value can be set. Otherwise, it can be set to `null`
                notify_low:
                  type: integer
                  x-stoplight:
                    id: 5enu780g96fvm
                  description: >-
                    Sets a threshold value to trigger notifications when
                    inventory falls below.
                quantities:
                  type: array
                  items:
                    type: object
                    properties:
                      branch:
                        type: integer
                        description: The branch id where you need to update the quantity
                      quantity:
                        type: integer
                        description: The new quantity
                      reason_id:
                        type: integer
                        description: The reason ID of the quantity change
                    x-apidog-orders:
                      - branch
                      - quantity
                      - reason_id
                    required:
                      - branch
                      - quantity
                    x-apidog-ignore-properties: []
                  description: Optional for manage multi-branch quanaties
              required:
                - sku
                - barcode
                - price
                - sale_price
                - cost_price
                - stock_quantity
                - weight
                - mpn
                - gtin
              x-apidog-orders:
                - sku
                - barcode
                - price
                - sale_price
                - cost_price
                - stock_quantity
                - weight
                - mpn
                - gtin
                - notify_low
                - quantities
              x-apidog-refs: {}
              x-apidog-ignore-properties: []
            example:
              sku: 23-TD23-32
              barcode: abc01
              price: 96.33
              sale_price: 90.5
              cost_price: 100.33
              stock_quantity: 4
              weight: 3
              mpn: 43242342
              gtin: 54353453
              quantities:
                - branch: 863926575
                  quantity: 100
                  reason_id: 303342349
                - branch: 989845784
                  quantity: 89
                  reason_id: 303342349
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productVariant_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 652911549
                  price:
                    amount: 13.5
                    currency: SAR
                  sale_price:
                    amount: 0
                    currency: SAR
                  cost_price:
                    amount: 0
                    currency: SAR
                  stock_quantity: 3000
                  barcode: barcode-ABC
                  sku: sku-variant-1551119600
                  related_option_values:
                    - 667315336
          headers: {}
          x-apidog-name: Updated Successfully
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
                  message: 'null'
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: ProductVariant
      x-apidog-folder: Default module/Merchant API/APIs/Product Variants
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394204-run
components:
  schemas:
    productVariant_response_body:
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
          $ref: '#/components/schemas/ProductVariant'
      x-apidog-orders:
        - status
        - success
        - data
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

