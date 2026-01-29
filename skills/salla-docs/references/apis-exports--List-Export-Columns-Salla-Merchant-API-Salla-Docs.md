# Apis Exports  List Export Columns Salla Merchant Api Salla Docs

## Table of Contents

- [apis-exports/List-Export-Columns-Salla-Merchant-API-Salla-Docs](#apis-exports-list-export-columns-salla-merchant-api-salla-docs)
- [apis-exports/List-Export-Templates-Salla-Merchant-API-Salla-Docs](#apis-exports-list-export-templates-salla-merchant-api-salla-docs)
- [apis-exports/Update-Export-Template-Salla-Merchant-API-Salla-Docs](#apis-exports-update-export-template-salla-merchant-api-salla-docs)

---

## apis-exports/List-Export-Columns-Salla-Merchant-API-Salla-Docs

# List Export Columns

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/columns:
    get:
      summary: List Export Columns
      deprecated: false
      description: >-
        This endpoint allows you to retrieve the available fields that you need
        to add into an export template.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read`- Exports Read Only

        </Accordion>
      operationId: get-exports-fields
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters:
        - name: entity
          in: query
          description: The entity to be exported, either `products` or `orders`
          required: true
          example: products
          schema:
            type: string
            enum:
              - products
              - orders
            examples:
              - orders
            x-apidog-enum:
              - name: ''
                value: products
                description: Entity type of product.
              - name: ''
                value: orders
                description: Entity type of orders.
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/exportColumns_response_body'
              example:
                status: 200
                success: true
                data:
                  - title: اسم المنتج
                    name: product_name
                    section: product_info
                  - title: تصنيف المنتج
                    name: product_categories
                    section: product_info
                  - title: صورة المنتج
                    name: product_images
                    section: product_info
                  - title: نوع المنتج
                    name: product_type
                    section: product_info
                  - title: الوصف
                    name: product_desc
                    section: product_info
                  - title: هل يتطلب شحن؟
                    name: required_shipping
                    section: product_info
                  - title: تاريخ نهاية التخفيض
                    name: sale_end_date
                    section: product_info
                  - title: اقصي كمية لكل عميل
                    name: customer_maximum_quantity
                    section: product_info
                  - title: إخفاء خيار تحديد الكمية
                    name: hide_quantity
                    section: product_info
                  - title: اضافة صورة عند الطلب
                    name: enable_upload_image
                    section: product_info
                  - title: الوزن
                    name: product_weight
                    section: product_info
                  - title: وحدة الوزن
                    name: product_weight_unit
                    section: product_info
                  - title: حالة المنتج
                    name: product_status
                    section: product_info
                  - title: الماركة
                    name: product_brand
                    section: product_info
                  - title: العنوان الترويجي
                    name: promotional_title
                    section: product_info
                  - title: تثبيت المنتج
                    name: product_pinned
                    section: product_info
                  - title: السعرات الحرارية
                    name: product_calories
                    section: product_info
                  - title: خاضع للضريبة؟
                    name: with_tax
                    section: product_info
                  - title: غير محدود الكمية
                    name: unlimited_quantity
                    section: product_info
                  - title: خيارات المنتج
                    table: product_options
                    section: product_options
                  - title: السعر
                    name: product_or_option_price
                    section: match_columns
                  - title: الكمية
                    name: product_or_option_quantity
                    section: match_columns
                  - title: رمز المنتج sku
                    name: product_or_option_sku
                    section: match_columns
                  - title: سعر التكلفة
                    name: product_or_option_cost_price
                    section: match_columns
                  - title: سعر التخفيض
                    name: product_or_option_sale_price
                    section: match_columns
                  - title: الباركود
                    name: product_or_option_barcode
                    section: match_columns
                  - title: MPN
                    name: product_or_option_mpn
                    section: match_columns
                  - title: GTIN
                    name: product_or_option_gtin
                    section: match_columns
                  - title: عنوان صفحة المنتج (SEO Page Title)
                    name: meta__title
                    section: seo_improvements
                  - title: رابط مخصص للمنتج (SEO Page URL)
                    name: product_page_url
                    section: seo_improvements
                  - title: وصف صفحة المنتج (SEO Page Description)
                    name: meta_description
                    section: seo_improvements
          headers: {}
          x-apidog-name: Success
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
                    exports.read
          headers: {}
          x-apidog-name: Unauthorized
        '422':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: number
                    description: >-
                      Response status code, a numeric or alphanumeric identifier
                      used to convey the outcome or status of a request,
                      operation, or transaction in various systems and
                      applications, typically indicating whether the action was
                      successful, encountered an error, or resulted in a
                      specific condition.
                  success:
                    type: boolean
                    description: >-
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  error:
                    $ref: '#/components/schemas/Validation'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 422
                success: false
                error:
                  code: error
                  message: alert.invalid_fields
                  fields:
                    entity:
                      - حقل entity غير صالح
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5607986-run
components:
  schemas:
    exportColumns_response_body:
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
        data:
          type: array
          items:
            type: object
            properties:
              title:
                type: string
                description: Column Title
              name:
                type: string
                description: Column Name
              section:
                type: string
                description: Column Section
            x-apidog-orders:
              - title
              - name
              - section
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

## apis-exports/List-Export-Templates-Salla-Merchant-API-Salla-Docs

# List Export Templates

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/templates:
    get:
      summary: List Export Templates
      deprecated: false
      description: >-
        This endpoint allows you to retrieve a list of the current export
        templates of either `orders` or `products` entity.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read`- Exports Read Only

        </Accordion>
      operationId: get-exports-templates
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters:
        - name: entity
          in: query
          description: ''
          required: false
          example: products | customers
          schema:
            type: string
            enum:
              - products
              - orders
            x-apidog-enum:
              - name: ''
                value: products
                description: Entity type of products.
              - name: ''
                value: orders
                description: Entity type of orders.
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/listExportTemplates_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 23424
                    name: مخصص المنتجات ١
                    columns:
                      - title: اسم المنتج
                        name: name
                      - title: السعر
                        name: price
                      - title: الكمية
                        name: quantity
                      - title: صورة المنتج
                        name: image
          headers: {}
          x-apidog-name: Success
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
                    exports.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5593165-run
components:
  schemas:
    listExportTemplates_response_body:
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
        data:
          type: array
          items:
            type: object
            properties:
              id:
                type: integer
                description: Template ID
              name:
                type: string
                description: Template Name
              columns:
                type: array
                items:
                  type: object
                  properties:
                    title:
                      type: string
                      description: Template Column Title
                    name:
                      type: string
                      description: Template Column Name
                  required:
                    - title
                    - name
                  x-apidog-orders:
                    - title
                    - name
                  x-apidog-ignore-properties: []
            x-apidog-orders:
              - id
              - name
              - columns
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

## apis-exports/Update-Export-Template-Salla-Merchant-API-Salla-Docs

# Update Export Template

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/templates/{id}:
    put:
      summary: Update Export Template
      deprecated: false
      description: >-
        This endpoint allows you to update the details of a custom export
        template by passing the `template_id` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read_write`- Exports Read & Write

        </Accordion>
      operationId: post-exports-templates
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters:
        - name: id
          in: path
          description: >-
            Unique identifier assigned to a template. List of Export Templates
            IDs can be found [here](https://docs.salla.dev/api-5593165)
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              x-apidog-refs:
                01HVRFQANYAFMAA06J73PRZCX6:
                  $ref: '#/components/schemas/exportTemplate_request_body'
                  x-apidog-overrides:
                    entity: null
              x-apidog-orders:
                - 01HVRFQANYAFMAA06J73PRZCX6
              properties:
                name:
                  type: string
                  description: Template Name.
                columns:
                  type: array
                  items:
                    type: string
                    description: Column Items .
              required:
                - name
                - columns
              x-apidog-ignore-properties:
                - name
                - columns
            example:
              name: مخصص المنتجات ١
              columns:
                - name: name
                - name: price
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/templates_response_body'
              example:
                status: 200
                success: true
                data:
                  message: تم حفظ القالب بنجاح
          headers: {}
          x-apidog-name: Progress In-Action
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
                    exports.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5593689-run
components:
  schemas:
    exportTemplate_request_body:
      type: object
      properties:
        name:
          type: string
          description: Template Name.
        entity:
          type: string
          description: Entity value, either `orders` or `products`.
          enum:
            - orders
            - products
          x-apidog-enum:
            - name: ''
              value: orders
              description: Entity value
            - name: ''
              value: products
              description: Entity value
        columns:
          type: array
          items:
            type: string
            description: Column Items .
      x-apidog-orders:
        - name
        - entity
        - columns
      required:
        - name
        - entity
        - columns
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    templates_response_body:
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
          type: object
          properties:
            message:
              type: string
              description: >-
                A text or data communication generated by a system or
                application in response to a request.
          x-apidog-orders:
            - message
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

