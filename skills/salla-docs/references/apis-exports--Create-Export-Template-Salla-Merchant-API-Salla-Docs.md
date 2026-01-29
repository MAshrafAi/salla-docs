# Apis Exports  Create Export Template Salla Merchant Api Salla Docs

## Table of Contents

- [apis-exports/Create-Export-Template-Salla-Merchant-API-Salla-Docs](#apis-exports-create-export-template-salla-merchant-api-salla-docs)
- [apis-exports/Delete-Export-Template-Salla-Merchant-API-Salla-Docs](#apis-exports-delete-export-template-salla-merchant-api-salla-docs)
- [apis-exports/Export-Custom-URLs-Salla-Merchant-API-Salla-Docs](#apis-exports-export-custom-urls-salla-merchant-api-salla-docs)
- [apis-exports/Export-Orders-Salla-Merchant-API-Salla-Docs](#apis-exports-export-orders-salla-merchant-api-salla-docs)
- [apis-exports/Export-Products-Salla-Merchant-API-Salla-Docs](#apis-exports-export-products-salla-merchant-api-salla-docs)
- [apis-exports/Exports-Customers-Salla-Merchant-API-Salla-Docs](#apis-exports-exports-customers-salla-merchant-api-salla-docs)
- [apis-exports/Exports-Logs-Salla-Merchant-API-Salla-Docs](#apis-exports-exports-logs-salla-merchant-api-salla-docs)

---

## apis-exports/Create-Export-Template-Salla-Merchant-API-Salla-Docs

# Create Export Template

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/templates:
    post:
      summary: Create Export Template
      deprecated: false
      description: >-
        This endpoint allows you o create a custom export template for either
        `"Orders"` or `"Products"`


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read_write`- Exports Read & Write

        </Accordion>
      operationId: post-exports-templates
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/exportTemplate_request_body'
            example:
              name: first product template
              entity: products
              columns:
                - product_name
                - product_images
                - product_type
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
                    columns.0:
                      - حقل columns.0 غير صالح
                    columns.1:
                      - حقل columns.1 غير صالح
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5593686-run
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

## apis-exports/Delete-Export-Template-Salla-Merchant-API-Salla-Docs

# Delete Export Template

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/templates/{template_id}:
    delete:
      summary: Delete Export Template
      deprecated: false
      description: >-
        This endpoint allows you to delete a custom export template by passing
        the `template_id` as the path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read_write`- Exports Read & Write

        </Accordion>
      operationId: post-exports-templates
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters:
        - name: template_id
          in: path
          description: >-
            Unique identifier assigned to a template. List of Export Templates
            IDs can be found [here](https://docs.salla.dev/api-5593165)
          required: true
          example: 3155923424
          schema:
            type: integer
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
                  message: template deleted successfully
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
                    exports.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5593835-run
components:
  schemas:
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

## apis-exports/Export-Custom-URLs-Salla-Merchant-API-Salla-Docs

# Export Custom URLs

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/custom-urls:
    post:
      summary: Export Custom URLs
      deprecated: false
      description: >+
        This endpoint allows you to export custom URL template in `.xlsx`
        format.


        :::check[Note]

        Once you query the endpoint, the response will be ready to be downloaded
        or saved as content is of type `binary`.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read_write` - Exports Read & write

        </Accordion>

      operationId: post-exports-custom-urls
      tags:
        - Default module/Merchant API/APIs/Exports
        - Custom URLs
      parameters: []
      responses:
        '200':
          description: ''
          content:
            '*/*':
              schema:
                type: object
                properties: {}
                x-apidog-orders: []
                x-apidog-ignore-properties: []
              example: >-
                The response is in `binary` format. Once you query the endpoint,
                the response will be ready to be downloaded / saved
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
                    exports.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10393831-run
components:
  schemas:
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

## apis-exports/Export-Orders-Salla-Merchant-API-Salla-Docs

# Export Orders

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/orders:
    get:
      summary: Export Orders
      deprecated: false
      description: >-
        This endpoint allows you to export orders in excel format (`xlsx` or
        `csv`). 


        :::tip[Note]

        Advance configurations are possible using the available query
        parameters.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `exports.read`- Exports Read Only

        </Accordion>
      operationId: get-exports-orders
      tags:
        - Default module/Merchant API/APIs/Exports
        - Orders
      parameters:
        - name: filter_orders
          in: query
          description: Filter orders by specifying one of the enum values
          required: true
          example: week
          schema:
            type: string
            enum:
              - today
              - week
              - month
              - dates
            x-apidog-enum:
              - name: ''
                value: today
                description: ' Filter by today''s date'
              - name: ''
                value: week
                description: ' Filter by a week''s date'
              - name: ''
                value: month
                description: ' Filter by a month''s date'
              - name: ''
                value: dates
                description: ' Filter by specific dates'
        - name: template_id
          in: query
          description: >-
            Provide the `template_id` if the store has
            [`order-export-templates`](https://help.salla.sa/article/1765308414)
            feature enabled on the store. Query the list of templates from [this
            endpoint](https://docs.salla.dev/api-5593165). Default export
            template_id is set to `-1`
          required: true
          example: -1
          schema:
            type: number
            default: -1
        - name: format
          in: query
          description: >-
            Choose a format from the enum values, either `xlsx` or `csv`, if the
            store has
            [`order-export-templates`](https://help.salla.sa/article/1765308414)
            feature enabled on the store. Recommended format is `xlsx`
          required: true
          example: xlsx
          schema:
            type: string
            enum:
              - xlsx
              - csv
            x-apidog-enum:
              - name: ''
                value: xlsx
                description: File format in XLSX
              - name: ''
                value: csv
                description: File format in CSV
        - name: from_date
          in: query
          description: >-
            Filter from date. Required if the query parameter `filter_orders` is
            set to `dates`
          required: false
          example: '2024-01-01 12:00:00'
          schema:
            type: string
            format: date-time
        - name: to_date
          in: query
          description: >-
            Filter to date. Required if the query parameter `filter_orders` is
            set to `dates`
          required: false
          example: '2024-12-31 23:59:59'
          schema:
            type: string
            format: date-time
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ordersMessage_response_body'
              examples:
                '1':
                  summary: Success
                  value:
                    status: 200
                    success: true
                    data:
                      message: سوف يتم ارسال التقرير علي بريدك الالكتروني بعد قليل
                '4':
                  summary: >-
                    Success Response but no orders found for the selected date
                    range
                  value:
                    status: 200
                    success: true
                    error:
                      code: 404
                      message: لايوجد لديك طلبات في الفترة المختارة
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
              examples:
                '2':
                  summary: Error 1
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        from_date:
                          - حقل من تاريخ مطلوب.
                        to_date:
                          - حقل حتى تاريخ مطلوب.
                '5':
                  summary: Error 2
                  value: |-
                    {
                        "status": 422,
                        "success": false,
                        "error": {
                            "code": "error",
                            "message": "alert.invalid_fields",
                            "fields": {
                                "filter_orders": [ // "today", "week", "month", "dates"
                                    "حقل نوع الفلتر مطلوب."
                                ],
                                "template_id": [ // if store has order-export-templates feature. (-1 for defualt export template)
                                    "حقل template id مطلوب."
                                ],
                                "format": [ // if store has order-export-templates feature. (xlsx,csv)
                                    "حقل format مطلوب."
                                ]
                            }
                        }
                    }
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5590305-run
components:
  schemas:
    ordersMessage_response_body:
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

## apis-exports/Export-Products-Salla-Merchant-API-Salla-Docs

# Export Products

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/products:
    post:
      summary: Export Products
      deprecated: false
      description: >-
        This endpoint allows you to export products into an Excel file in
        specific types. 


        :::info[Info]

        Check the Merchant Help Desk articles
        [here](https://help.salla.sa/article/1082536000) and
        [here](https://help.salla.sa/article/1487653981) for more details.

        :::

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: post-exports-products
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                type:
                  type: string
                  description: >-
                    The type of products to be exported as, only from the
                    allowed enum values
                  enum:
                    - product-sample
                    - category-sample
                    - brand-sample
                    - brand
                    - category
                    - products
                    - quantities
                    - prices
                    - seo
                    - hs-codes
                  x-apidog-enum:
                    - value: product-sample
                      name: ''
                      description: ' A blank template with required columns to help you add new products.'
                    - value: category-sample
                      name: ''
                      description: ' A sample file to guide the structure for adding product categories.'
                    - value: brand-sample
                      name: ''
                      description: ' A sample format for uploading new brands correctly.'
                    - value: brand
                      name: ''
                      description: ' A full export of all existing brands in your store.'
                    - value: category
                      name: ''
                      description: ' An export of all product categories currently available.'
                    - value: products
                      name: ''
                      description: ' A complete list of all your products including names'
                    - value: quantities
                      name: ''
                      description: ' Product quantity data for inventory management or updates.'
                    - value: prices
                      name: ''
                      description: ' A list of all products with their current prices for easy review or updates.'
                    - value: seo
                      name: ''
                      description: ' SEO-related product data including titles'
                    - value: hs-codes
                      name: ''
                      description: ' Harmonized System codes assigned to products for customs and shipping.'
                  examples:
                    - product-sample
                format:
                  type: string
                  description: The format to export the products as, either `csv` or `xlsx`
                  enum:
                    - xlsx
                    - csv
                  x-apidog-enum:
                    - value: xlsx
                      name: ''
                      description: ' Excel file format recommended for most use cases and supports structured editing.'
                    - value: csv
                      name: ''
                      description: ' Comma-separated file format ideal for quick imports'
                  examples:
                    - xlsx
              required:
                - type
                - format
              x-apidog-orders:
                - type
                - format
              x-apidog-refs: {}
              x-apidog-ignore-properties: []
            example:
              type: product-sample
              format: xlsx
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                x-apidog-refs:
                  01J7XFQ5CN73NRG0WKV5J7VJA9:
                    $ref: '#/components/schemas/progress_ActionSuccess'
                    x-apidog-overrides:
                      data: &ref_0
                        type: object
                        properties:
                          message:
                            type: string
                            description: >-
                              A text or data communication generated by a system
                              or application in response to a request.
                        x-apidog-orders:
                          - message
                        x-apidog-ignore-properties: []
                    required: []
                x-apidog-orders:
                  - 01J7XFQ5CN73NRG0WKV5J7VJA9
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
                  data: *ref_0
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
              example:
                status: 200
                success: true
                data:
                  message: سوف يتم ارسال الملف علي بريدك الالكتروني بعد قليل
          headers: {}
          x-apidog-name: OK
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                status: 404
                success: false
                data:
                  message: لايوجد لديك منتجات في الخيارات المحددة
          headers: {}
          x-apidog-name: Record Not Found
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
                  code: error
                  message: alert.invalid_fields
                  fields:
                    type:
                      - حقل النوع غير صالح
                    format:
                      - حقل format غير صالح
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9796006-run
components:
  schemas:
    progress_ActionSuccess:
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
            code:
              type: number
              description: >-
                A numerical or alphanumeric identifier used in various systems
                and protocols to indicate the status or outcome of a specific
                request.
          x-apidog-orders:
            - message
            - code
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

## apis-exports/Exports-Customers-Salla-Merchant-API-Salla-Docs

# Export Customers

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/customers:
    post:
      summary: Export Customers
      deprecated: false
      description: |-
        This endpoint allows you to export customers

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `exports.read_write` - Exports Read & Write
        </Accordion>
      operationId: post-exports-customers
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                type:
                  type: string
                  enum:
                    - customers
                    - customers-sample
                  description: >-
                    Request the exported file by entering `customers` of a
                    sample file using `customers-sample`
                  x-apidog-enum:
                    - value: customers
                      name: ''
                      description: Export Customers
                    - value: customers-sample
                      name: ''
                      description: Export Customers Sample
              x-apidog-orders:
                - type
              required:
                - type
              x-apidog-ignore-properties: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
                    description: >-
                      Response status code, a numeric or alphanumeric identifier
                      used to convey the outcome or status of a request,
                      operation, or transaction in various systems and
                      applications, typically indicating whether the action was
                      successful, encountered an error, or resulted in a
                      specific condition
                  success:
                    type: boolean
                    description: >-
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  data:
                    type: object
                    properties:
                      message:
                        type: string
                        description: The exported file will be sent to the email address
                    x-apidog-orders:
                      - message
                    required:
                      - message
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - status
                  - success
                  - data
                required:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  message: سوف يتم ارسال بيانات العملاء علي بريدك الالكتروني بعد قليل
          headers: {}
          x-apidog-name: Success | customers
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
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10774701-run
components:
  schemas:
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

## apis-exports/Exports-Logs-Salla-Merchant-API-Salla-Docs

# Exports Logs

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /exports/logs:
    get:
      summary: Exports Logs
      deprecated: false
      description: |-
        This endpoint allows you to export store logs

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `exports.read` - Exports Read Only
        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Exports
        - Exports
      parameters:
        - name: event
          in: query
          description: ''
          required: false
          example: ''
          schema:
            type: string
            enum:
              - product.created
              - product.updated
              - product.deleted
              - product.status.changed.hidden
              - product.status.changed.sale
              - customer.created
              - customer.updated
              - customer.banned
              - customer.unbanned
              - customer.add.to.group
              - customer.group.created
              - customer.group.updated
            x-apidog-enum:
              - value: product.created
                name: ''
                description: The event of product creation.
              - value: product.updated
                name: ''
                description: The event od product update
              - value: product.deleted
                name: ''
                description: The event od product is deleted
              - value: product.status.changed.hidden
                name: ''
                description: The event od product status is changed to hidden
              - value: product.status.changed.sale
                name: ''
                description: The event od product status is changed to sale.
              - value: customer.created
                name: ''
                description: The event of customer creation.
              - value: customer.updated
                name: ''
                description: The event of customer update
              - value: customer.banned
                name: ''
                description: The event of customer status is changed to banned.
              - value: customer.unbanned
                name: ''
                description: The event of customer status is changed to unbanned.
              - value: customer.add.to.group
                name: ''
                description: The event of customer is added to group
              - value: customer.group.created
                name: ''
                description: The event of group creation.
              - value: customer.group.updated
                name: ''
                description: The event of group update..
        - name: from
          in: query
          description: Export Logs **from** a specific date
          required: false
          example: ''
          schema:
            type: string
        - name: to
          in: query
          description: Export Logs **to** a specific date
          required: false
          schema:
            type: string
        - name: employee
          in: query
          description: >-
            Unique identifier assigned to an Employee. Get a list of Employee
            IDs from [here](https://docs.salla.dev/api-5394259)
          required: false
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
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
                  data:
                    type: array
                    items:
                      type: object
                      properties:
                        type:
                          type: string
                          enum:
                            - product_prices
                            - orders
                          x-apidog-enum:
                            - value: product_prices
                              name: ''
                              description: ''
                            - value: orders
                              name: ''
                              description: ''
                          description: Event Type
                        user:
                          type: object
                          properties:
                            id:
                              type: string
                              description: User ID
                            name:
                              type: string
                              description: User Name
                          x-apidog-orders:
                            - id
                            - name
                          required:
                            - id
                            - name
                          x-apidog-ignore-properties: []
                        created_at:
                          type: string
                          description: 'Webhook Creation Timestamp '
                        url:
                          type: string
                          description: Event URL
                      x-apidog-orders:
                        - type
                        - user
                        - created_at
                        - url
                      required:
                        - type
                        - user
                        - created_at
                        - url
                      x-apidog-ignore-properties: []
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  - type: product-prices
                    user:
                      id: 46179442
                      name: الامين يوسف
                    created_at: '2024-10-14 11:53:55'
                    url: https://zzzzzzz
                  - type: orders
                    user:
                      id: 46179442
                      name: الامين يوسف
                    created_at: '2024-10-14 11:53:55'
                    url: https://zzzzzzz
          headers: {}
          x-apidog-name: Success
        '401':
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
                    $ref: '#/components/schemas/Unauthorized'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: The access token is invalid
          headers: {}
          x-apidog-name: error_unauthorized_401
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Exports
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10753343-run
components:
  schemas:
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

