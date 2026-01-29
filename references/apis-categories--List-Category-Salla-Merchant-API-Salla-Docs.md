# Apis Categories  List Category Salla Merchant Api Salla Docs

## Table of Contents

- [apis-categories/List-Category-Salla-Merchant-API-Salla-Docs](#apis-categories-list-category-salla-merchant-api-salla-docs)
- [apis-categories/Update-Category-Salla-Merchant-API-Salla-Docs](#apis-categories-update-category-salla-merchant-api-salla-docs)

---

## apis-categories/List-Category-Salla-Merchant-API-Salla-Docs

# List Category Products

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories/{id}/products:
    get:
      summary: List Category Products
      deprecated: false
      description: >-
        This endpoint allows you to list all the products and their sort order
        that are related in a specified category by passing the `id` as a path
        parameter..


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read` - Categories Read Only

        </Accordion>
      operationId: show-category-products
      tags:
        - Default module/Merchant API/APIs/Categories
        - Categories
      parameters:
        - name: id
          in: path
          description: >-
            Unique identifiers assigned to a Category. List of Category IDs can
            be found [here](https://docs.salla.dev/api-5394207)
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/categoriesProducts_response_body'
              examples:
                '1':
                  summary: Success
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 1616381492
                        name: iPhone 16 Pro
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/1b333d84-4a80-49fc-9fb1-6565aa44045e-500x333.33333333333-omJjjLFh9HqShwJa7O4YD904Q2mfXLqKy0wcLVJE.jpg
                        sort: 1
                      - id: 388819608
                        name: أقراط الياقوت
                        image: >-
                          https://cdn.salla.sa/nzvOE/a2f5abed-2e38-479e-a4ff-4e442508935c-500x500-y5Wuuum0SgGrYfYHbpKPunlapp0BXVXeaT413.jpg
                        sort: 2
                    pagination:
                      count: 2
                      total: 2
                      perPage: 15
                      currentPage: 1
                      totalPages: 1
                      links: []
                '4':
                  summary: Success
                  value:
                    status: 404
                    success: false
                    error:
                      code: error
                      message: المحتوى الذي تحاول الوصول اليه غير متوفر
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
                    categories.read
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
          x-apidog-name: Record Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-11055135-run
components:
  schemas:
    categoriesProducts_response_body:
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
                description: Product ID
              name:
                type: string
                description: Product Name
              image:
                type: string
                description: Product Image in URL format
              sort:
                type: integer
                description: Sort order of the product viewed inside a category
            x-apidog-orders:
              - id
              - name
              - image
              - sort
            x-apidog-ignore-properties: []
        pagination:
          $ref: '#/components/schemas/Pagination'
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      required:
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

## apis-categories/Update-Category-Salla-Merchant-API-Salla-Docs

# Update Category

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories/{category}:
    put:
      summary: Update Category
      deprecated: false
      description: >-
        This endpoint allows you to update category details by passing the
        `category` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read_write`- Categories Read & Write

        </Accordion>
      operationId: Update-Category
      tags:
        - Default module/Merchant API/APIs/Categories
        - Categories
      parameters:
        - name: category
          in: path
          description: >-
            The Category ID. List of Category ID can be found
            [here](https://docs.salla.dev/api-5394207)
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/category_request_body'
            example:
              name: طعام قطط
              image: >-
                https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/dBmLWHOfKm3tRfQ3Txqs3l96SjI6jdbf6rCsYYQu.jpg
              status: hidden
              metadata_title: Dress
              metadata_description: Amazing Dress
              metadata_url: cat-food
              show_in:
                app: true
              products:
                - id: 1212
                  sort: 1
              translations:
                en:
                  name: cat food
                  metadata_title: cat food
                  metadata_description: welcome
                  metadata_url: cat-food
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/category_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 707972603
                  name: Dress 101
                  urls:
                    customer: https://shtara.com/profile
                    admin: https://shtara.com/profiles
                  sort_order: 0
                  items: []
                  parent_id: 516861512
                  status: hidden
                  metadata:
                    title: Dress
                    description: Amazing Dress
                    url: https://dress.com
          headers: {}
          x-apidog-name: Created
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
                    categories.read_write
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
                  code: validation_failed
                  message: Validation is not successfull
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: Category
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394209-run
components:
  schemas:
    category_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            The title or label assigned to a specific grouping or classification
            of items, products, or content, often used to organize and
            categorize them for easier navigation or identification. 🌐 [Support
            multi-language](https://docs.salla.dev/doc-421122)
        status:
          type: string
          description: >-
            The status of the category, whether or not it is `active` or
            `hidden`
          enum:
            - active
            - hidden
          x-apidog-enum:
            - value: active
              name: ''
              description: The category is active and displayed to the customers.
            - value: hidden
              name: ''
              description: The option is hidden and is not displayed to customers.
        image:
          type: string
          description: Category display image
        metadata_title:
          type: string
          description: >-
            Category SEO Metadata Title which is a concise label used to
            optimize search engine results and enhance the visibility of a
            category page.
        metadata_description:
          type: string
          description: >-
            A succinct summary crafted to enhance search engine optimization and
            spotlight a brand's attributes within a category.
        metadata_url:
          type: string
          description: >-
            Metadata URL is a web address that contains information designed to
            improve a webpage's search engine visibility and shareability on
            social platforms.
        shows_in:
          type: object
          properties:
            app:
              type: string
              description: Salla Merchant App
          x-apidog-orders:
            - app
          required:
            - app
          description: Category channels that will be displayed to them
          x-apidog-ignore-properties: []
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: Translated category name
                metadata:
                  type: object
                  properties:
                    title:
                      type: string
                      description: >-
                        Translated Category SEO Metadata Title which is a
                        concise label used to optimize search engine results and
                        enhance the visibility of a category page.
                    description:
                      type: string
                      description: >-
                        A succinct summary crafted to enhance search engine
                        optimization and spotlight a brand's attributes within a
                        Translated category.
                    url:
                      type: string
                      description: >-
                        Translated Metadata URL is a web address that contains
                        information designed to improve a webpage's search
                        engine visibility and shareability on social platforms.
                  x-apidog-orders:
                    - title
                    - description
                    - url
                  required:
                    - title
                    - description
                    - url
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - name
                - metadata
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
          description: >-
            Category translations are based on the store's enabled language
            locale. For instance, if the store supports both Arabic and English,
            the `translations` object will return two entries: `ar` for Arabic
            and `en` for English.
          x-apidog-ignore-properties: []
        parent_id:
          type: number
          description: >-
            A unique identifier that references the parent or higher-level
            category to which a specific category belongs, establishing a
            hierarchical relationship within a categorization system.
        sort_order:
          type: number
          description: >-
            Sort order dictates the sequence or arrangement of categories when
            displayed to users. It determines the order in which categories are
            presented, often using numerical values to assign priority, allowing
            for controlled and organized navigation.
        products:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  Product ID. Get a list of Product IDs from
                  [here](https://docs.salla.dev/api-5394168)
                examples:
                  - 939485452
              sort:
                type: number
                description: >-
                  an Integer number signifying the sort order of the product
                  inside the category
                examples:
                  - 1
                  - 5
                  - 10
            x-apidog-orders:
              - id
              - sort
            x-apidog-ignore-properties: []
          description: Assign products and specify the sort order.
      required:
        - name
      x-apidog-orders:
        - name
        - status
        - image
        - metadata_title
        - metadata_description
        - metadata_url
        - shows_in
        - translations
        - parent_id
        - sort_order
        - products
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    category_response_body:
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
        data: &ref_0
          $ref: '#/components/schemas/Category'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Category:
      type: object
      title: Category
      x-tags:
        - Models
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            Category ID, is a unique identifier assigned to a specific product
            category, facilitating organized classification and efficient
            management of products within a similar group. List of categories
            can be found [here](https://docs.salla.dev/api-5394207).
        name:
          type: string
          description: >-
            Category name is a descriptive label assigned to a product category,
            aiding in clear identification and organization of related products.
            🌐 [Support multi-language](doc-421122)
        image:
          type: string
          description: The category image
        urls:
          $ref: '#/components/schemas/URLs'
        parent_id:
          type: integer
          description: >-
            Category Parent ID refers to the unique identifier assigned to the
            parent category of a subcategory, establishing a hierarchical
            relationship between different levels of product classification.
        sort_order:
          type: integer
          description: 'The sequence or arrangement of categories when displayed to users. '
          nullable: true
        status:
          type: string
          description: >-
            The category status indicates whether the category is currently
            visible and accessible to users `active` or intentionally concealed
            from view `hidden`. It essentially controls whether the category is
            publicly displayed or kept private within the system.
          enum:
            - active
            - hidden
          x-apidog-enum:
            - value: active
              name: ''
              description: The category is active and visible.
            - value: hidden
              name: ''
              description: The category is inactive and invisible.
        show_in:
          type: object
          properties:
            app:
              type: boolean
              description: Whether or not to show the category in the Salla Merchant App
            salla_points:
              type: boolean
              description: Whether or not to show the category in Salla Points
          x-apidog-orders:
            - app
            - salla_points
          required:
            - app
            - salla_points
          x-apidog-ignore-properties: []
        has_hidden_products:
          type: boolean
          description: Whether or not the category has hidden products.
        update_at:
          type: string
          description: The date where the category is updated in.
        metadata:
          type: object
          properties:
            title:
              type: string
              description: >-
                Category SEO Metadata Title which is a concise label used to
                optimize search engine results and enhance the visibility of a
                category page.
            description:
              type: string
              description: >-
                A succinct summary crafted to enhance search engine optimization
                and spotlight a brand's attributes within a category.
            url:
              type: string
              description: >-
                Metadata URL is a web address that contains information designed
                to improve a webpage's search engine visibility and shareability
                on social platforms.
          x-apidog-orders:
            - title
            - description
            - url
          required:
            - title
            - description
            - url
          x-apidog-ignore-properties: []
        sub_categories:
          type: array
          items:
            type: string
          description: The subcategories list of the main category.
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: Translated category name
                metadata:
                  type: object
                  properties:
                    title:
                      type: string
                      description: >-
                        Translated Category SEO Metadata Title which is a
                        concise label used to optimize search engine results and
                        enhance the visibility of a category page.
                    description:
                      type: string
                      description: >-
                        A succinct summary crafted to enhance search engine
                        optimization and spotlight a brand's attributes within a
                        Translated category.
                    url:
                      type: string
                      description: >-
                        Translated Metadata URL is a web address that contains
                        information designed to improve a webpage's search
                        engine visibility and shareability on social platforms.
                  x-apidog-orders:
                    - title
                    - description
                    - url
                  required:
                    - title
                    - description
                    - url
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - name
                - metadata
              required:
                - name
                - metadata
              description: Translation in English language.
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
          required:
            - en
          description: >-
            **You will get this object in the response if you use
            `with=translations` query parameter.** 


            Category translations are based on the store's enabled language
            locale. For instance, if the store supports both Arabic and English,
            the `translations` object will return two entries: `ar` for Arabic
            and `en` for English.
          x-apidog-ignore-properties: []
        items:
          type: array
          items: *ref_0
          description: >-
            **You will get this array in the response if you use `with=items`
            query parameter.**
      x-apidog-orders:
        - id
        - name
        - image
        - urls
        - parent_id
        - sort_order
        - status
        - show_in
        - has_hidden_products
        - update_at
        - metadata
        - sub_categories
        - translations
        - items
      required:
        - id
        - name
        - image
        - urls
        - parent_id
        - sort_order
        - status
        - show_in
        - has_hidden_products
        - update_at
        - metadata
        - sub_categories
        - translations
        - items
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    URLs:
      description: >-
        To help companies and merchants, Salla provides a “urls” attribute that
        has been added to different modules to guide the merchants to have the
        full URL of this module from both scopes, the dashboard scope as a store
        admin, and as a customer.
      type: object
      title: Urls
      x-examples:
        Example:
          customer: https://shtara.com/profile
          admin: https://shtara.com/profiles
      x-tags:
        - Models
      properties:
        customer:
          type: string
          description: Customer link directly to the order.
          examples:
            - https://salla.sa/StoreLink
        admin:
          type: string
          description: Admin dashboard link directly to the order.
          examples:
            - https://s.salla./YourStoreDashboard
        digital_content:
          type: string
          description: >-
            A direct URL link to the digital asset, such as an e-book, image,
            PDF, video, or any downloadable file linked to the order or product.
        rating:
          type: string
          description: >-
            Order Rating Link. <br> Note that the order has to be of either of
            the following statuses: `completed`, `delivered`, or `shipped`. The
            merchant has to allow the product to be rated from the [Store
            Settings](https://s.salla.sa/settings) > Rating Settings
        checkout:
          type: string
          description: >-
            Order Checkout URL. <br>Note that the variable will only be returned
            if the order is unpaid. If the order is already paid, the variable
            will not appear in the response.
      x-apidog-orders:
        - customer
        - admin
        - digital_content
        - rating
        - checkout
      required:
        - customer
        - admin
        - digital_content
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

