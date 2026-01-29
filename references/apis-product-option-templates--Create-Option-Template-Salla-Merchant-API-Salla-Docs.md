# Apis Product Option Templates  Create Option Template Salla Merchant Api Salla Docs

## Table of Contents

- [apis-product-option-templates/Create-Option-Template-Salla-Merchant-API-Salla-Docs](#apis-product-option-templates-create-option-template-salla-merchant-api-salla-docs)
- [apis-product-option-templates/Delete-Option-Template-Salla-Merchant-API-Salla-Docs](#apis-product-option-templates-delete-option-template-salla-merchant-api-salla-docs)
- [apis-product-option-templates/List-Options-Template-Salla-Merchant-API-Salla-Docs](#apis-product-option-templates-list-options-template-salla-merchant-api-salla-docs)

---

## apis-product-option-templates/Create-Option-Template-Salla-Merchant-API-Salla-Docs

# Create Option Template

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/options/templates:
    post:
      summary: Create Option Template
      deprecated: false
      description: |-
        This endpoint allows you create a new option template.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `products.read_write` - Products Read and Write 
        </Accordion>
      operationId: create-product-option-templates
      tags:
        - Default module/Merchant API/APIs/Product Option Templates
        - Product Option Templates
      parameters:
        - name: with
          in: query
          description: >-
            Use `with=details` to fetch list of product option templates with
            `details` object.
          required: false
          example: details
          schema:
            type: string
            enum:
              - details
            x-apidog-enum:
              - value: details
                name: ''
                description: >-
                  Used to fetch list of product option templates with `details`
                  object.
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/product_option_template_request_body'
            example:
              name: image url
              display_type: image
              translations:
                en:
                  name: color
                fr:
                  name: couleur
              details:
                - name: profile pic
                  is_default: true
                  display_value: fb.com
                  translations:
                    en:
                      name: pic
                    fr:
                      name: pic
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/product_option_template_response'
              example:
                status: 201
                success: true
                data:
                  - id: 1473353380
                    name: اللون
                    type: radio
                    display_type: color
                    translations:
                      - id: 1473353380
                        name: color
                        locale: en
                      - id: 566146469
                        name: color
                        locale: fr
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
                  message: >-
                    The access token should have access to one of those scopes:
                    products.read_write
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
          headers: {}
          x-apidog-name: Validation
        x-200:With Details:
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/product_option_template_details_response'
              example:
                status: 201
                success: true
                data:
                  - id: 1473353380
                    name: اللون
                    type: radio
                    display_type: color
                    translations:
                      - id: 1473353380
                        name: color
                        locale: en
                      - id: 566146469
                        name: color
                        locale: fr
                    details:
                      - id: 1378987453
                        name: احمر غامق
                        is_default: 0
                        translations:
                          - id: 180625841
                            name: dark red
                            locale: en
                          - id: 1688289458
                            name: dagc red
                            locale: fr
          headers: {}
          x-apidog-name: With Details
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Product Option Templates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9634676-run
components:
  schemas:
    product_option_template_request_body:
      type: object
      properties:
        name:
          type: string
          description: Option name.
        type:
          type: string
          description: Type of product option.
          enum:
            - checkbox
            - radio
          x-apidog-enum:
            - name: ''
              value: checkbox
              description: ''
            - name: ''
              value: radio
              description: ''
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - name: ''
              value: text
              description: ''
            - name: ''
              value: image
              description: ''
            - name: ''
              value: color
              description: ''
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: option name in English
              x-apidog-orders:
                - name
              x-apidog-ignore-properties: []
            fr:
              type: object
              properties:
                name:
                  type: string
                  description: Option Name in French
              x-apidog-orders:
                - name
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
            - fr
          description: Options presented in different languages.
          x-apidog-ignore-properties: []
        details:
          type: object
          properties:
            id:
              type: number
              description: option ID
            name:
              type: string
              description: option value name
            is_default:
              type: boolean
              description: indicates if the value is default or not
            display_value:
              type: string
              description: Option Display value
            translation:
              type: object
              properties:
                ar:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  x-apidog-ignore-properties: []
                en:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  x-apidog-ignore-properties: []
                fr:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - ar
                - en
                - fr
              description: Option display value translations
              required:
                - ar
                - en
                - fr
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - id
            - name
            - is_default
            - display_value
            - translation
          required:
            - id
            - name
            - is_default
            - display_value
            - translation
          description: Option Details. Visible if `with=details` query paramter is passed
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - name
        - type
        - display_type
        - translations
        - details
      required:
        - details
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    product_option_template_response:
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
          description: >+
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.







        data:
          $ref: '#/components/schemas/OptionsTemplate'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OptionsTemplate:
      type: object
      properties:
        id:
          type: string
          description: A unique identifier of the options template.
        name:
          type: string
          description: Option name.
        type:
          type: string
          description: Type of product option.
          enum:
            - checkbox
            - radio
          x-apidog-enum:
            - name: ''
              value: checkbox
              description: Option type of checkbox.
            - name: ''
              value: radio
              description: Option type of radio.
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - name: ''
              value: text
              description: Display the option as text.
            - name: ''
              value: image
              description: Display the option as an image.
            - name: ''
              value: color
              description: Display the option as a color.
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: Option name in English
              x-apidog-orders:
                - name
              description: Options in English langaugae.
              required:
                - name
              x-apidog-ignore-properties: []
            ar:
              type: object
              properties:
                name:
                  type: string
                  description: Option Name in French
              x-apidog-orders:
                - name
              description: Options in Arabic langauge.
              required:
                - name
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
            - ar
          description: >-
            Options presented in different languages based on the store's
            enabled locales.
          required:
            - en
            - ar
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - type
        - display_type
        - translations
      required:
        - id
        - name
        - type
        - display_type
        - translations
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    product_option_template_details_response:
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
          description: >+
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.







        data:
          $ref: '#/components/schemas/OptionsTemplateWithDetails'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OptionsTemplateWithDetails:
      type: object
      properties:
        id:
          type: string
          description: A unique identifier of the options template.
        name:
          type: string
          description: Option template name.
        type:
          type: string
          description: Type of product option.
          enum:
            - checkbox
            - radio
          x-apidog-enum:
            - name: ''
              value: checkbox
              description: Option template type is Checkbox
            - name: ''
              value: radio
              description: Option template type is Radio
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - name: ''
              value: text
              description: Display type is Text
            - name: ''
              value: image
              description: Display type is Image
            - name: ''
              value: color
              description: Display type is Color
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: option name in English
              x-apidog-orders:
                - name
              description: Options in English langaugae.
              required:
                - name
              x-apidog-ignore-properties: []
            ar:
              type: object
              properties:
                name:
                  type: string
                  description: Option Name in French
              x-apidog-orders:
                - name
              description: Options in Arabic langauge.
              required:
                - name
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
            - ar
          description: >-
            Options presented in different languages based on the store's
            enabled locales.
          required:
            - en
            - ar
          x-apidog-ignore-properties: []
        details:
          type: object
          properties:
            id:
              type: number
              description: A unique identifier of the option.
            name:
              type: string
              description: Option value name.
            is_default:
              type: boolean
              description: Whether or not if the value is default.
            display_value:
              type: string
              description: Option display value
            translation:
              type: object
              properties:
                ar:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  required:
                    - name
                  description: Translation in Arabic language.
                  x-apidog-ignore-properties: []
                en:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  required:
                    - name
                  description: Translation in English language.
                  x-apidog-ignore-properties: []
                fr:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  required:
                    - name
                  description: Translation in French language.
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - ar
                - en
                - fr
              required:
                - ar
                - en
                - fr
              description: Option display value translations
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - id
            - name
            - is_default
            - display_value
            - translation
          required:
            - id
            - name
            - is_default
            - display_value
            - translation
          description: Option details. Visible if `with=details` query paramter is passed
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - type
        - display_type
        - translations
        - details
      required:
        - id
        - name
        - type
        - display_type
        - translations
        - details
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

## apis-product-option-templates/Delete-Option-Template-Salla-Merchant-API-Salla-Docs

# Delete Option Template

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/options/templates/{id}:
    delete:
      summary: Delete Option Template
      deprecated: false
      description: >-
        This endpoint allows you to delete a specific product option template by
        passing the `id` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write` - Products Read and Write 

        </Accordion>
      operationId: delete-product-option-templates
      tags:
        - Default module/Merchant API/APIs/Product Option Templates
        - Product Option Templates
      parameters:
        - name: id
          in: path
          description: >-
            A unique identifier of the option template. List of option template
            IDs can be found [here](https://docs.salla.dev/9633869e0)
          required: true
          example: 956236464
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
                  message: تم حذف Option Template بنجاح
                  code: 202
          headers: {}
          x-apidog-name: Deleted
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
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Product Option Templates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9634526-run
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

## apis-product-option-templates/List-Options-Template-Salla-Merchant-API-Salla-Docs

# List Option Templates

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/options/templates:
    get:
      summary: List Option Templates
      deprecated: false
      description: >-
        This endpoint allows you to list all option templates related to the
        product.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read` - Products Read Only

        </Accordion>
      operationId: get-list-product-option-templates
      tags:
        - Default module/Merchant API/APIs/Product Option Templates
        - Product Option Templates
      parameters:
        - name: with
          in: query
          description: >-
            Use `with=details` to fetch list of product option templates with
            `details` object.
          required: false
          example: details
          schema:
            type: string
            x-apidog-enum:
              - name: ''
                value: details
                description: Option template details.
            enum:
              - details
      responses:
        '200':
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
                    description: >+
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.







                  data:
                    type: array
                    items: &ref_0
                      $ref: '#/components/schemas/OptionsTemplate'
                  pagination: &ref_1
                    $ref: '#/components/schemas/Pagination'
                x-apidog-orders:
                  - 01JBH9D5AS3P5CX7HEZGSCXYHN
                x-apidog-refs:
                  01JBH9D5AS3P5CX7HEZGSCXYHN:
                    $ref: '#/components/schemas/product_option_templates_response'
                required:
                  - pagination
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
                  - pagination
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: اللون
                    type: radio
                    display_type: color
                    translations:
                      en:
                        name: color
                      fr:
                        name: color
                pagination:
                  count: 1
                  total: 15
                  perPage: 1
                  currentPage: 1
                  totalPages: 15
                  links:
                    next: https://s.salla.test/admin/v2/options-template?page=2
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
                    products.read
          headers: {}
          x-apidog-name: Unauthorized
        x-200:With Details:
          description: ''
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/product_option_templates_details_response%20
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: اللون
                    type: radio
                    display_type: color
                    translations:
                      en:
                        name: color
                      fr:
                        name: color
                    details:
                      - id: 1378987453
                        name: احمر غامق
                        is_default: 0
                        translations:
                          en:
                            name: dark red
                          fr:
                            name: rouge foncé
                pagination:
                  count: 1
                  total: 15
                  perPage: 1
                  currentPage: 1
                  totalPages: 15
                  links:
                    next: https://s.salla.test/admin/v2/options-template?page=2
          headers: {}
          x-apidog-name: With Details
      security:
        - bearer: []
      x-salla-php-method-name: ''
      x-apidog-folder: Default module/Merchant API/APIs/Product Option Templates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9633869-run
components:
  schemas:
    Pagination:
      type: object
      title: Pagination
      description: >-
        For a better response behavior as well as maintain the best security
        level, All retrieving API endpoints use a mechanism to retrieve data in
        chunks called pagination.  Pagination working by return only a specific
        number of records in each response, and through passing the page number
        you can navigate the different pages.
      properties:
        count:
          type: number
          description: Number of returned results.
        total:
          type: number
          description: Number of all results.
        perPage:
          type: number
          description: Number of results per page.
          maximum: 65
        currentPage:
          type: number
          description: Number of current page.
        totalPages:
          type: number
          description: Number of total pages.
        links:
          type: object
          properties:
            next:
              type: string
              description: Next Page
            previous:
              type: string
              description: Previous Page
          x-apidog-orders:
            - next
            - previous
          description: Array of linkes to next and previous pages.
          required:
            - next
            - previous
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - count
        - total
        - perPage
        - currentPage
        - totalPages
        - links
      required:
        - count
        - total
        - perPage
        - currentPage
        - totalPages
        - links
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OptionsTemplate:
      type: object
      properties:
        id:
          type: string
          description: A unique identifier of the options template.
        name:
          type: string
          description: Option name.
        type:
          type: string
          description: Type of product option.
          enum:
            - checkbox
            - radio
          x-apidog-enum:
            - name: ''
              value: checkbox
              description: Option type of checkbox.
            - name: ''
              value: radio
              description: Option type of radio.
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - name: ''
              value: text
              description: Display the option as text.
            - name: ''
              value: image
              description: Display the option as an image.
            - name: ''
              value: color
              description: Display the option as a color.
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: Option name in English
              x-apidog-orders:
                - name
              description: Options in English langaugae.
              required:
                - name
              x-apidog-ignore-properties: []
            ar:
              type: object
              properties:
                name:
                  type: string
                  description: Option Name in French
              x-apidog-orders:
                - name
              description: Options in Arabic langauge.
              required:
                - name
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
            - ar
          description: >-
            Options presented in different languages based on the store's
            enabled locales.
          required:
            - en
            - ar
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - type
        - display_type
        - translations
      required:
        - id
        - name
        - type
        - display_type
        - translations
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    product_option_templates_response:
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
          description: >+
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.







        data:
          type: array
          items: *ref_0
        pagination: *ref_1
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      required:
        - pagination
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    'product_option_templates_details_response ':
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
          description: >+
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.







        data:
          type: array
          items:
            $ref: '#/components/schemas/OptionsTemplateWithDetails'
        pagination: *ref_1
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      required:
        - pagination
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OptionsTemplateWithDetails:
      type: object
      properties:
        id:
          type: string
          description: A unique identifier of the options template.
        name:
          type: string
          description: Option template name.
        type:
          type: string
          description: Type of product option.
          enum:
            - checkbox
            - radio
          x-apidog-enum:
            - name: ''
              value: checkbox
              description: Option template type is Checkbox
            - name: ''
              value: radio
              description: Option template type is Radio
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - name: ''
              value: text
              description: Display type is Text
            - name: ''
              value: image
              description: Display type is Image
            - name: ''
              value: color
              description: Display type is Color
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: option name in English
              x-apidog-orders:
                - name
              description: Options in English langaugae.
              required:
                - name
              x-apidog-ignore-properties: []
            ar:
              type: object
              properties:
                name:
                  type: string
                  description: Option Name in French
              x-apidog-orders:
                - name
              description: Options in Arabic langauge.
              required:
                - name
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
            - ar
          description: >-
            Options presented in different languages based on the store's
            enabled locales.
          required:
            - en
            - ar
          x-apidog-ignore-properties: []
        details:
          type: object
          properties:
            id:
              type: number
              description: A unique identifier of the option.
            name:
              type: string
              description: Option value name.
            is_default:
              type: boolean
              description: Whether or not if the value is default.
            display_value:
              type: string
              description: Option display value
            translation:
              type: object
              properties:
                ar:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  required:
                    - name
                  description: Translation in Arabic language.
                  x-apidog-ignore-properties: []
                en:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  required:
                    - name
                  description: Translation in English language.
                  x-apidog-ignore-properties: []
                fr:
                  type: object
                  properties:
                    name:
                      type: string
                  x-apidog-orders:
                    - name
                  required:
                    - name
                  description: Translation in French language.
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - ar
                - en
                - fr
              required:
                - ar
                - en
                - fr
              description: Option display value translations
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - id
            - name
            - is_default
            - display_value
            - translation
          required:
            - id
            - name
            - is_default
            - display_value
            - translation
          description: Option details. Visible if `with=details` query paramter is passed
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - type
        - display_type
        - translations
        - details
      required:
        - id
        - name
        - type
        - display_type
        - translations
        - details
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

