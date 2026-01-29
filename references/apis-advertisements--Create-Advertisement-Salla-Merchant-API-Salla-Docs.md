# Apis Advertisements  Create Advertisement Salla Merchant Api Salla Docs

## Table of Contents

- [apis-advertisements/Create-Advertisement-Salla-Merchant-API-Salla-Docs](#apis-advertisements-create-advertisement-salla-merchant-api-salla-docs)
- [apis-advertisements/Delete-Advertisement-Salla-Merchant-API-Salla-Docs](#apis-advertisements-delete-advertisement-salla-merchant-api-salla-docs)
- [apis-advertisements/List-Advertisements-Salla-Merchant-API-Salla-Docs](#apis-advertisements-list-advertisements-salla-merchant-api-salla-docs)
- [apis-advertisements/Update-Advertisement-Salla-Merchant-API-Salla-Docs](#apis-advertisements-update-advertisement-salla-merchant-api-salla-docs)

---

## apis-advertisements/Create-Advertisement-Salla-Merchant-API-Salla-Docs

# Create Advertisement

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /advertisements:
    post:
      summary: Create Advertisement
      deprecated: false
      description: >-
        This endpoint allows you to create an advertisement post of the store on
        its pages.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read_write`- Marketing Read & Write

        </Accordion>
      operationId: post-advertisements
      tags:
        - Default module/Merchant API/APIs/Advertisements
        - Advertisements
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/advertisment_request_body'
            example:
              title: Adv Title
              description: Adv Description
              type:
                name: product
                id: 1261174103
                link: null
              expire_date: '2022-12-31'
              pages:
                - all
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/advertisement_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1549230938
                  title: Adv Title
                  description: Adv Description
                  type:
                    id: 1261174103
                    name: product
                    link: https://productImageLink
                  style:
                    icon: sicon-bell
                    font_color: '#ffffff'
                    background_color: '#9d8383'
                  expire_date:
                    date: '2022-12-12 00:00:00.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  pages:
                    - all
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
                    marketing.read_write
          headers: {}
          x-apidog-name: Unauthorized
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
                    title:
                      - حقل عنوان الإعلان مطلوب.
                    description:
                      - حقل محتوى الإعلان مطلوب.
                    type:
                      - حقل النوع مطلوب.
                    type.id:
                      - id for product is invalid
                    type.name:
                      - حقل اسم الإعلان مطلوب.
                    expire_date:
                      - حقل تاريخ انتهاء الإعلان مطلوب.
                    pages:
                      - حقل صفحات الإعلان مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: Advertisement
      x-apidog-folder: Default module/Merchant API/APIs/Advertisements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394264-run
components:
  schemas:
    advertisment_request_body:
      type: object
      properties:
        title:
          type: string
          description: Advertisement Title.
          examples:
            - Adv Title
        description:
          type: string
          description: >-
            Advertisement Description. 🌐 [Support
            multi-language](https://docs.salla.dev/doc-421122)
          examples:
            - Adv Description
        type:
          type: object
          properties:
            name:
              type: string
              description: Advertisement Type
              enum:
                - category
                - page
                - product
                - offers
                - without_url
                - external_link
              examples:
                - product
              x-apidog-enum:
                - value: category
                  name: ''
                  description: ' Fetch type based on category of the product'
                - value: page
                  name: ''
                  description: Fetch type based on the page
                - value: product
                  name: ''
                  description: Fetch type based on the product
                - value: offers
                  name: ''
                  description: Fetch type based on offers
                - value: without_url
                  name: ''
                  description: Fetch type without url
                - value: external_link
                  name: ''
                  description: Fetch type with external link
            id:
              type: number
              description: >-
                Advertisement ID. The `type.id` variable is `requiredif`
                `type.name` is any of these values: `["category" , "page" ,
                "product"]`
              examples:
                - 1261174103
            link:
              type: string
              description: >-
                Advertisement Link. The `type.link` is `requiredif` `type.name`
                is `external_link`
              nullable: true
          x-apidog-orders:
            - name
            - id
            - link
          x-apidog-ignore-properties: []
        expire_date:
          type: string
          description: Advertisement expiry date.
          examples:
            - '2022-12-31'
        pages:
          type: array
          description: Which pages should the advertisement appear on.
          items:
            type: string
            enum:
              - all
              - cart
              - product
              - payment
              - category
              - home
            examples:
              - all
            x-apidog-enum:
              - value: all
                name: ''
                description: Fetch all pages
              - value: cart
                name: ''
                description: Fetch cart pages
              - value: product
                name: ''
                description: Fetch products pages
              - value: payment
                name: ''
                description: Fetch payment pages
              - value: category
                name: ''
                description: Fetch category pages
              - value: home
                name: ''
                description: Fetch home pages
      required:
        - title
        - description
        - type
        - expire_date
        - pages
      x-apidog-orders:
        - title
        - description
        - type
        - expire_date
        - pages
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    advertisement_response_body:
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
          $ref: '#/components/schemas/Advertisement'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Advertisement:
      type: object
      properties:
        id:
          type: number
          description: Advertisement ID
        title:
          type: string
          description: Advertisement Title
        description:
          type: string
          description: Advertisement Description. 🌐 [Support multi-language](doc-421122)
        type:
          type: object
          properties:
            id:
              type: number
              description: Advertisement Type ID
            name:
              type: string
              description: Advertisement Type Name
            link:
              type: string
              description: Advertisement Type Link
              nullable: true
          x-apidog-orders:
            - id
            - name
            - link
          required:
            - id
            - name
          x-apidog-ignore-properties: []
        style:
          type: object
          properties:
            icon:
              type: string
              description: Advertisement Style Icon
            font_color:
              type: string
              description: Advertisement Style Font Color
            background_color:
              type: string
              description: Advertisement Style Background Color
          x-apidog-orders:
            - icon
            - font_color
            - background_color
          required:
            - icon
            - font_color
            - background_color
          x-apidog-ignore-properties: []
        expire_date:
          type: object
          properties:
            date:
              type: string
              description: Advertisement Expiry Date
            timezone_type:
              type: number
              description: Advertisement Timezone Type
            timezone:
              type: string
              description: Advertisement Timezone
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        pages:
          type: array
          description: Which pages should the advertisement appear on
          items:
            type: string
      x-apidog-orders:
        - id
        - title
        - description
        - type
        - style
        - expire_date
        - pages
      required:
        - id
        - title
        - description
        - type
        - style
        - expire_date
        - pages
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

## apis-advertisements/Delete-Advertisement-Salla-Merchant-API-Salla-Docs

# Delete Advertisement

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /advertisements/{advertisements_id}:
    delete:
      summary: Delete Advertisement
      deprecated: false
      description: >-
        This endpoint allows you to delete an existing advertisement post by
        passing the `advertisement_id` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read_write`- Marketing Read & Write

        </Accordion>
      operationId: delete-advertisements-advertisements_id
      tags:
        - Default module/Merchant API/APIs/Advertisements
        - Advertisements
      parameters:
        - name: advertisements_id
          in: path
          description: ' Unique identification number assigned to the Advertisement. List of Advertisement IDs can be found [here](https://docs.salla.dev/api-5394265).'
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
                  message: The advertisement has been removed successfully
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
                    marketing.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: delete
      x-apidog-folder: Default module/Merchant API/APIs/Advertisements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394268-run
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

## apis-advertisements/List-Advertisements-Salla-Merchant-API-Salla-Docs

# List Advertisements

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /advertisements:
    get:
      summary: List Advertisements
      deprecated: false
      description: >-
        This endpoint allows you to list all of the advertisement posts of the
        store.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read`- Marketing Read Only

        </Accordion>
      operationId: get-advertisements
      tags:
        - Default module/Merchant API/APIs/Advertisements
        - Advertisements
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/advertisements_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 2142305900
                    title: تخفيضات على جميع التيشيرتات
                    description: أعلان لتصنيف التيشيرت
                    type:
                      id: 1032561074
                      name: category
                      link: https://offerLink
                    style:
                      icon: sicon-braille-hand
                      font_color: '#ffffff'
                      background_color: '#9d8383'
                    expire_date:
                      date: '2022-01-21 00:00:00.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    pages:
                      - all
                  - id: 235400060
                    title: جميع المنتجات ستتوفر مرة أخرى بعد العيد
                    description: توفر المنتجات
                    type:
                      id: 132432
                      name: without_url
                      link: https://offerLink
                    style:
                      icon: sicon-bell
                      font_color: '#ffffff'
                      background_color: '#9d8383'
                    expire_date:
                      date: '2022-12-12 00:00:00.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    pages:
                      - cart
                      - product
                pagination:
                  count: 5
                  total: 5
                  perPage: 15
                  currentPage: 1
                  totalPages: 1
                  links: []
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
                    marketing.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Advertisement
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Advertisements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394265-run
components:
  schemas:
    advertisements_response_body:
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
          type: array
          x-stoplight:
            id: 0g0jjeqblwzdt
          items:
            $ref: '#/components/schemas/Advertisement'
        pagination:
          $ref: '#/components/schemas/Pagination'
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
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
    Advertisement:
      type: object
      properties:
        id:
          type: number
          description: Advertisement ID
        title:
          type: string
          description: Advertisement Title
        description:
          type: string
          description: Advertisement Description. 🌐 [Support multi-language](doc-421122)
        type:
          type: object
          properties:
            id:
              type: number
              description: Advertisement Type ID
            name:
              type: string
              description: Advertisement Type Name
            link:
              type: string
              description: Advertisement Type Link
              nullable: true
          x-apidog-orders:
            - id
            - name
            - link
          required:
            - id
            - name
          x-apidog-ignore-properties: []
        style:
          type: object
          properties:
            icon:
              type: string
              description: Advertisement Style Icon
            font_color:
              type: string
              description: Advertisement Style Font Color
            background_color:
              type: string
              description: Advertisement Style Background Color
          x-apidog-orders:
            - icon
            - font_color
            - background_color
          required:
            - icon
            - font_color
            - background_color
          x-apidog-ignore-properties: []
        expire_date:
          type: object
          properties:
            date:
              type: string
              description: Advertisement Expiry Date
            timezone_type:
              type: number
              description: Advertisement Timezone Type
            timezone:
              type: string
              description: Advertisement Timezone
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        pages:
          type: array
          description: Which pages should the advertisement appear on
          items:
            type: string
      x-apidog-orders:
        - id
        - title
        - description
        - type
        - style
        - expire_date
        - pages
      required:
        - id
        - title
        - description
        - type
        - style
        - expire_date
        - pages
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

## apis-advertisements/Update-Advertisement-Salla-Merchant-API-Salla-Docs

# Update Advertisement

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /advertisements/{advertisements_id}:
    put:
      summary: Update Advertisement
      deprecated: false
      description: >-
        This endpoint allows you to update an existing advertisement post by
        passing the `advertisement_id` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read_write`- Marketing Read & Write

        </Accordion>
      operationId: put-advertisements-advertisements_id
      tags:
        - Default module/Merchant API/APIs/Advertisements
        - Advertisements
      parameters:
        - name: advertisements_id
          in: path
          description: ' Unique identification number assigned to the Advertisement. List of Advertisement IDs can be found [here](https://docs.salla.dev/api-5394265).'
          required: true
          example: ''
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/advertisment_request_body'
            example:
              title: Adv Title
              description: Adv Description
              type:
                name: product
                id: 1261174103
                link: null
              expire_date: '2022-12-31'
              pages:
                - all
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/advertisement_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1549230938
                  title: Adv Title
                  description: Adv Description
                  type:
                    id: 1261174103
                    name: product
                    link: https://linkforproduct
                  style:
                    icon: sicon-bell
                    font_color: '#ffffff'
                    background_color: '#9d8383'
                  expire_date:
                    date: '2022-12-12 00:00:00.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  pages:
                    - all
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
                    marketing.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
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
                  code: error
                  message: alert.invalid_fields
                  fields:
                    title:
                      - حقل عنوان الإعلان مطلوب.
                    description:
                      - حقل محتوى الإعلان مطلوب.
                    type:
                      - حقل النوع مطلوب.
                    type.name:
                      - حقل اسم الإعلان مطلوب.
                    expire_date:
                      - حقل تاريخ انتهاء الإعلان مطلوب.
                    pages:
                      - حقل صفحات الإعلان مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: Advertisement
      x-apidog-folder: Default module/Merchant API/APIs/Advertisements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394267-run
components:
  schemas:
    advertisment_request_body:
      type: object
      properties:
        title:
          type: string
          description: Advertisement Title.
          examples:
            - Adv Title
        description:
          type: string
          description: >-
            Advertisement Description. 🌐 [Support
            multi-language](https://docs.salla.dev/doc-421122)
          examples:
            - Adv Description
        type:
          type: object
          properties:
            name:
              type: string
              description: Advertisement Type
              enum:
                - category
                - page
                - product
                - offers
                - without_url
                - external_link
              examples:
                - product
              x-apidog-enum:
                - value: category
                  name: ''
                  description: ' Fetch type based on category of the product'
                - value: page
                  name: ''
                  description: Fetch type based on the page
                - value: product
                  name: ''
                  description: Fetch type based on the product
                - value: offers
                  name: ''
                  description: Fetch type based on offers
                - value: without_url
                  name: ''
                  description: Fetch type without url
                - value: external_link
                  name: ''
                  description: Fetch type with external link
            id:
              type: number
              description: >-
                Advertisement ID. The `type.id` variable is `requiredif`
                `type.name` is any of these values: `["category" , "page" ,
                "product"]`
              examples:
                - 1261174103
            link:
              type: string
              description: >-
                Advertisement Link. The `type.link` is `requiredif` `type.name`
                is `external_link`
              nullable: true
          x-apidog-orders:
            - name
            - id
            - link
          x-apidog-ignore-properties: []
        expire_date:
          type: string
          description: Advertisement expiry date.
          examples:
            - '2022-12-31'
        pages:
          type: array
          description: Which pages should the advertisement appear on.
          items:
            type: string
            enum:
              - all
              - cart
              - product
              - payment
              - category
              - home
            examples:
              - all
            x-apidog-enum:
              - value: all
                name: ''
                description: Fetch all pages
              - value: cart
                name: ''
                description: Fetch cart pages
              - value: product
                name: ''
                description: Fetch products pages
              - value: payment
                name: ''
                description: Fetch payment pages
              - value: category
                name: ''
                description: Fetch category pages
              - value: home
                name: ''
                description: Fetch home pages
      required:
        - title
        - description
        - type
        - expire_date
        - pages
      x-apidog-orders:
        - title
        - description
        - type
        - expire_date
        - pages
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    advertisement_response_body:
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
          $ref: '#/components/schemas/Advertisement'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Advertisement:
      type: object
      properties:
        id:
          type: number
          description: Advertisement ID
        title:
          type: string
          description: Advertisement Title
        description:
          type: string
          description: Advertisement Description. 🌐 [Support multi-language](doc-421122)
        type:
          type: object
          properties:
            id:
              type: number
              description: Advertisement Type ID
            name:
              type: string
              description: Advertisement Type Name
            link:
              type: string
              description: Advertisement Type Link
              nullable: true
          x-apidog-orders:
            - id
            - name
            - link
          required:
            - id
            - name
          x-apidog-ignore-properties: []
        style:
          type: object
          properties:
            icon:
              type: string
              description: Advertisement Style Icon
            font_color:
              type: string
              description: Advertisement Style Font Color
            background_color:
              type: string
              description: Advertisement Style Background Color
          x-apidog-orders:
            - icon
            - font_color
            - background_color
          required:
            - icon
            - font_color
            - background_color
          x-apidog-ignore-properties: []
        expire_date:
          type: object
          properties:
            date:
              type: string
              description: Advertisement Expiry Date
            timezone_type:
              type: number
              description: Advertisement Timezone Type
            timezone:
              type: string
              description: Advertisement Timezone
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        pages:
          type: array
          description: Which pages should the advertisement appear on
          items:
            type: string
      x-apidog-orders:
        - id
        - title
        - description
        - type
        - style
        - expire_date
        - pages
      required:
        - id
        - title
        - description
        - type
        - style
        - expire_date
        - pages
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

