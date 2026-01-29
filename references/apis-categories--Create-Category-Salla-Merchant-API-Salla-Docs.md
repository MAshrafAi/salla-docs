# Apis Categories  Create Category Salla Merchant Api Salla Docs

## Table of Contents

- [apis-categories/Create-Category-Salla-Merchant-API-Salla-Docs](#apis-categories-create-category-salla-merchant-api-salla-docs)
- [apis-categories/Delete-Category-Salla-Merchant-API-Salla-Docs](#apis-categories-delete-category-salla-merchant-api-salla-docs)
- [apis-categories/List-Categories-Salla-Merchant-API-Salla-Docs](#apis-categories-list-categories-salla-merchant-api-salla-docs)

---

## apis-categories/Create-Category-Salla-Merchant-API-Salla-Docs

# Create Category

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories:
    post:
      summary: Create Category
      deprecated: false
      description: >-
        This endpoint allows you to create a new category and return the
        category ID and its details.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read_write`- Categories Read & Write

        </Accordion>
      operationId: Create-Category
      tags:
        - Default module/Merchant API/APIs/Categories
        - Categories
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/category_request_body'
            example:
              name: طعام قطط
              status: hidden
              image: >-
                https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/dBmLWHOfKm3tRfQ3Txqs3l96SjI6jdbf6rCsYYQu.jpg
              metadata_title: Dress
              metadata_description: Amazing Dress
              metadata_url: https://dress.com
              show_in:
                app: true
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
                  message: Validation Failed
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: Category
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394206-run
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

## apis-categories/Delete-Category-Salla-Merchant-API-Salla-Docs

# Delete Category

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories/{category}:
    delete:
      summary: Delete Category
      deprecated: false
      description: >-
        This endpoint allows you to delete a specific category by passing the
        `category` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read_write`- Categories Read & Write

        </Accordion>
      operationId: Delete-Category
      tags:
        - Default module/Merchant API/APIs/Categories
        - Categories
      parameters:
        - name: category
          in: path
          description: >-
            Unique identifiers assigned to a Category. List of Category IDs can
            be found [here](https://docs.salla.dev/api-5394207)
          required: true
          example: 0
          schema:
            type: integer
      responses:
        '200':
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
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: delete
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394210-run
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

## apis-categories/List-Categories-Salla-Merchant-API-Salla-Docs

# List Categories

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories:
    get:
      summary: List Categories
      deprecated: false
      description: >-
        This endpoint allows you to list all categories related to your store
        directly from this endpoint. Also, it allows you to filter them using a
        keyword, the endpoint would return any category which name matches this
        keyword.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read`- Categories Read Only

        </Accordion>
      operationId: List-Categories
      tags:
        - Default module/Merchant API/APIs/Categories
        - Categories
      parameters:
        - name: page
          in: query
          description: The Pagination page number
          required: false
          schema:
            type: integer
        - name: keyword
          in: query
          description: A keyword to filter categories by a specific name.
          required: false
          schema:
            type: string
        - name: status
          in: query
          description: >-
            The status of the category, whether or not it is `active` or
            `hidden`
          required: false
          schema:
            type: string
        - name: with
          in: query
          description: >-
            Returns the response with translations or items (or both). Takes
            values with separated comma or array of either items, translations
            or both in this case:

            `with=items` OR `with=translations` OR
            `with[]=items&with[]=translations` OR `with=items,translations`
          required: false
          example: translations
          schema:
            type: array
            items:
              type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/categories_response_body'
              examples:
                '1':
                  summary: Example | Default Response
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 1390018242
                        name: laptops
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/QEFy9wUtKnazAVvm3t3WSYg2z1LTnxUzvrceFo2s.jpg
                        urls:
                          customer: https://store.test/ar/jalal56s/laptops/c1390018242
                          admin: /categories
                        parent_id: 0
                        sort_order: 0
                        status: active
                        show_in:
                          app: true
                          salla_points: true
                        has_hidden_products: true
                        update_at: '2024-10-24 13:24:48'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        sub_categories: []
                      - id: 115638743
                        name: welcome jojo
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/QEFy9wUtKnazAVvm3t3WSYg2z1LTnxUzvrceFo2s.jpg
                        urls:
                          customer: >-
                            https://store.test/ar/jalal56s/welcome-jojo/c115638743
                          admin: /categories
                        parent_id: 0
                        sort_order: 0
                        status: active
                        show_in:
                          app: true
                          salla_points: false
                        has_hidden_products: false
                        update_at: '2024-10-24 14:19:55'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        sub_categories: []
                      - id: 40297589
                        name: قطط
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/QEFy9wUtKnazAVvm3t3WSYg2z1LTnxUzvrceFo2s.jpg
                        urls:
                          customer: https://store.test/ar/jalal56s/قطط/c40297589
                          admin: /categories
                        parent_id: 0
                        sort_order: 1
                        status: active
                        show_in:
                          app: false
                          salla_points: false
                        has_hidden_products: false
                        update_at: '2024-10-21 14:44:57'
                        metadata:
                          title: قطط
                          description: welcome
                          url: قطط
                        sub_categories: []
                      - id: 774382199
                        name: طعام كلاب
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/QEFy9wUtKnazAVvm3t3WSYg2z1LTnxUzvrceFo2s.jpg
                        urls:
                          customer: https://store.test/ar/jalal56s/كلاب/c774382199
                          admin: /categories
                        parent_id: 0
                        sort_order: 2
                        status: hidden
                        show_in:
                          app: false
                          salla_points: false
                        has_hidden_products: false
                        update_at: '2024-10-21 14:45:27'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        sub_categories: []
                      - id: 712043358
                        name: العناية
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/QEFy9wUtKnazAVvm3t3WSYg2z1LTnxUzvrceFo2s.jpg
                        urls:
                          customer: https://store.test/ar/jalal56s/العناية/c712043358
                          admin: /categories
                        parent_id: 0
                        sort_order: 3
                        status: active
                        show_in:
                          app: false
                          salla_points: false
                        has_hidden_products: false
                        update_at: '2024-10-21 14:51:38'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        sub_categories: []
                      - id: 537348185
                        name: جميع الأقسام
                        image: >-
                          https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/QEFy9wUtKnazAVvm3t3WSYg2z1LTnxUzvrceFo2s.jpg
                        urls:
                          customer: >-
                            https://store.test/ar/jalal56s/جميع-الأقسام/c537348185
                          admin: /categories
                        parent_id: 0
                        sort_order: 3
                        status: active
                        show_in:
                          app: true
                          salla_points: false
                        has_hidden_products: false
                        update_at: '2024-09-06 13:01:49'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        sub_categories: []
                      - id: 355378101
                        name: فساتين
                        image: null
                        urls:
                          customer: >-
                            https://store.test/ar/jalal56s/فساتين-سهرة/c355378101
                          admin: /categories
                        parent_id: 0
                        sort_order: 4
                        status: active
                        show_in:
                          app: true
                          salla_points: false
                        has_hidden_products: false
                        update_at: '2024-09-07 14:34:09'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        sub_categories: []
                    pagination:
                      count: 7
                      total: 7
                      perPage: 20
                      currentPage: 1
                      totalPages: 1
                      links: []
                '3':
                  summary: Example | `with=translations` Query Parameter
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 40297589
                        name: قطط
                        urls:
                          customer: https://store.test/ar/jalal56s/قطط/c40297589
                          admin: /categories
                        parent_id: 0
                        status: active
                        sort_order: 1
                        update_at: '2024-08-30 14:19:56'
                        metadata:
                          title: قطط
                          description: welcome
                          url: قطط
                        translations:
                          en:
                            name: cats
                            metadata:
                              title: cats
                              description: welcome
                              url: cats
                      - id: 774382199
                        name: كلاب
                        urls:
                          customer: https://store.test/ar/jalal56s/كلاب/c774382199
                          admin: /categories
                        parent_id: 0
                        status: hidden
                        sort_order: 2
                        update_at: '2024-08-30 14:07:43'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        translations: []
                    pagination:
                      count: 2
                      total: 2
                      perPage: 20
                      currentPage: 1
                      totalPages: 1
                      links: []
                '4':
                  summary: Example | `with=items` Query Parameter
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 40297589
                        name: قطط
                        urls:
                          customer: https://store.test/ar/jalal56s/قطط/c40297589
                          admin: /categories
                        parent_id: 0
                        status: active
                        sort_order: 1
                        update_at: '2024-08-30 14:19:56'
                        metadata:
                          title: قطط
                          description: welcome
                          url: قطط
                        items:
                          - id: 1547895670
                            name: اكل القطط
                            urls:
                              customer: >-
                                https://store.test/ar/jalal56s/اكل-القطط/c1547895670
                              admin: /categories
                            parent_id: 40297589
                            status: hidden
                            sort_order: 1
                            update_at: '2024-08-30 14:04:07'
                            metadata:
                              title: This product is amazing
                              description: >-
                                This Product is one of the amazing things you
                                can buy for yourself
                              url: >-
                                https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                            items: []
                      - id: 774382199
                        name: كلاب
                        urls:
                          customer: https://store.test/ar/jalal56s/كلاب/c774382199
                          admin: /categories
                        parent_id: 0
                        status: hidden
                        sort_order: 2
                        update_at: '2024-08-30 14:07:43'
                        metadata:
                          title: This product is amazing
                          description: >-
                            This Product is one of the amazing things you can
                            buy for yourself
                          url: >-
                            https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                        items:
                          - id: 2079670640
                            name: اكل الكلاب
                            urls:
                              customer: >-
                                https://store.test/ar/jalal56s/اكل-الكلاب/c2079670640
                              admin: /categories
                            parent_id: 774382199
                            status: hidden
                            sort_order: 1
                            update_at: '2024-08-30 14:07:43'
                            metadata:
                              title: This product is amazing
                              description: >-
                                This Product is one of the amazing things you
                                can buy for yourself
                              url: >-
                                https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                            items: []
                    pagination:
                      count: 2
                      total: 2
                      perPage: 20
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
                    categories.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Category
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394207-run
components:
  schemas:
    categories_response_body:
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
            id: nf10n9r82gwro
          items: &ref_0
            $ref: '#/components/schemas/Category'
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

