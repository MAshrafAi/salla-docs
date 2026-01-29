# Apis Categories  Categories Search Salla Merchant Api Salla Docs

## Table of Contents

- [apis-categories/Categories-Search-Salla-Merchant-API-Salla-Docs](#apis-categories-categories-search-salla-merchant-api-salla-docs)
- [apis-categories/Category-Children](#apis-categories-category-children)
- [apis-categories/Category-Details-Salla-Merchant-API-Salla-Docs](#apis-categories-category-details-salla-merchant-api-salla-docs)

---

## apis-categories/Categories-Search-Salla-Merchant-API-Salla-Docs

# Categories Search

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories/search:
    get:
      summary: Categories Search
      deprecated: false
      description: >
        This endpoint allows you to search through existing categories using
        keywords *(a.k.a name of the category)* as well as an array of Category
        IDs


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read` - Categories Read Only

        </Accordion>
      operationId: categories-search
      tags:
        - Default module/Merchant API/APIs/Categories
        - Category
      parameters:
        - name: keyword
          in: query
          description: >-
            Name of the category. Get a list of category names from
            [here](https://docs.salla.dev/api-5394207)
          required: false
          example: phones
          schema:
            type: string
        - name: ids
          in: query
          description: >-
            Unique identifiers assigned to a Category. List of Category IDs can
            be found [here](https://docs.salla.dev/api-5394207)

            :::check[]


            You can use the query parameter like this example.:
            <CopyToClipboard>`?ids[]=451690116&ids[]=451690117`</CopyToClipboard>


            :::
          required: false
          example: ''
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/categories_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 558898595
                    name: الفساتين
                    urls:
                      customer: https://salla.sa/dev-k9dn7fok0vih4p70/category/mENQjb
                      admin: https://s.salla.sa/categories
                    parent_id: 0
                    status: active
                    sort_order: 0
                    update_at: '2024-10-02 13:10:17'
                    metadata:
                      title: dresses
                      description: dresses
                      url: dresses
                  - id: 1181713494
                    name: البلايز
                    urls:
                      customer: https://salla.sa/dev-k9dn7fok0vih4p70/category/NDYwBg
                      admin: https://s.salla.sa/categories
                    parent_id: 0
                    status: hidden
                    sort_order: 2
                    update_at: '2024-02-05 16:33:11'
                    metadata:
                      title: tshirts
                      description: tshirts
                      url: tshirts
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
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10309545-run
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

## apis-categories/Category-Children

# Category Children

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories/{category}/children:
    get:
      summary: Category Children
      deprecated: false
      description: >-
        This endpoint allows you to return specific category children by passing
        the `category` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read`- Categories Read Only

        </Accordion>
      operationId: Category-Children
      tags:
        - Default module/Merchant API/APIs/Categories
        - Categories
      parameters:
        - name: category
          in: path
          description: >-
            Unique identifiers assigned to a Category. List of Category IDs can
            be found [here](https://docs.salla.dev/api-5394207).
          required: true
          example: 0
          schema:
            type: integer
        - name: page
          in: query
          description: The Pagination page number
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
                    description: Response Status Code
                  success:
                    type: boolean
                    description: 'Whether or not the response is successful '
                  data:
                    type: array
                    items:
                      type: object
                      properties:
                        id:
                          type: integer
                          description: Category ID
                        name:
                          type: string
                          description: Category Name
                        urls:
                          type: object
                          properties:
                            customer:
                              type: string
                              description: Category Customer URL
                            admin:
                              type: string
                              description: Category Admin URL
                          required:
                            - customer
                            - admin
                          x-apidog-orders:
                            - customer
                            - admin
                          x-apidog-ignore-properties: []
                        sort_order:
                          type: integer
                          description: Category Sort Order
                        items:
                          type: array
                          items:
                            type: string
                      x-apidog-orders:
                        - id
                        - name
                        - urls
                        - sort_order
                        - items
                      x-apidog-refs: {}
                      x-apidog-ignore-properties: []
                  pagination:
                    $ref: '#/components/schemas/Pagination'
                x-apidog-orders:
                  - status
                  - success
                  - data
                  - pagination
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  - id: 1255216786
                    name: فواكه صيفية
                    urls:
                      customer: https://shtara.com/profile
                      admin: https://shtara.com/profile
                    sort_order: 1
                    items: []
                pagination:
                  count: 1
                  total: 1
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
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: listChildren
      x-salla-php-return-type: Category
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394211-run
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
          description: number of returned results
        total:
          type: number
          description: number of all results
        perPage:
          type: number
          description: number of results per page
          maximum: 65
        currentPage:
          type: number
          description: number of current page
        totalPages:
          type: number
          description: 'number of total pages '
        links:
          type: array
          description: array of linkes to next and previous pages
          items:
            type: string
      x-examples: {}
      x-tags:
        - Responses
      x-apidog-orders:
        - count
        - total
        - perPage
        - currentPage
        - totalPages
        - links
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

## apis-categories/Category-Details-Salla-Merchant-API-Salla-Docs

# Category Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /categories/{category}:
    get:
      summary: Category Details
      deprecated: false
      description: >-
        This endpoint allows you to return the complete details for a specific
        category by passing the `category` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `categories.read`- Categories Read Only

        </Accordion>
      operationId: Category-Details
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
        - name: with
          in: query
          description: >-
            Returns the response with translations or items (or both). Takes
            values with separated comma or array of either items, translations
            or both in this case:

            `with=items` OR `with=translations` OR
            `with[]=items&with[]=translations` OR `with=items,translations`
          required: false
          example:
            - items
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
                $ref: '#/components/schemas/category_response_body'
              examples:
                '1':
                  summary: Example
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1390018242
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
                          This Product is one of the amazing things you can buy
                          for yourself
                        url: >-
                          https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                      sub_categories: []
                '3':
                  summary: Success | `with=translations` Query Parameter
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1390018242
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
                          This Product is one of the amazing things you can buy
                          for yourself
                        url: >-
                          https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                      sub_categories: []
                      translations:
                        en:
                          name: cats
                          metadata:
                            title: cats
                            description: welcome
                            url: cats
                '5':
                  summary: Success | `with=items` Query Parameter
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1390018242
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
                          This Product is one of the amazing things you can buy
                          for yourself
                        url: >-
                          https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672908878
                      sub_categories: []
                      items: []
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
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: Category
      x-apidog-folder: Default module/Merchant API/APIs/Categories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394208-run
components:
  schemas:
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

