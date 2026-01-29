# Apis Feedbacks  Feedback Reply

## Table of Contents

- [apis-feedbacks/Feedback-Reply](#apis-feedbacks-feedback-reply)
- [apis-feedbacks/List-Reviews-Salla-Merchants-APIs](#apis-feedbacks-list-reviews-salla-merchants-apis)
- [apis-feedbacks/Review-Details-Salla-Merchants-APIs](#apis-feedbacks-review-details-salla-merchants-apis)
- [apis-feedbacks/Store-Feedback](#apis-feedbacks-store-feedback)
- [apis-feedbacks/Update-Feedback-Reply](#apis-feedbacks-update-feedback-reply)
- [apis-feedbacks/Update-Review-Salla-Merchants-APIs](#apis-feedbacks-update-review-salla-merchants-apis)

---

## apis-feedbacks/Feedback-Reply

# Feedback Reply

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /feedbacks/{feedback_id}/reply:
    post:
      summary: Feedback Reply
      deprecated: false
      description: >-
        This endpoint allows you to add a specific reply feedback by passing the
        `feedback_id` as a path parameter. 


        :::warning[]

        This endpoint will be accessible only for allowed applications and
        requires approval

        :::

        This endpoint allows you to Store feedbacks


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read_write`- Questions & Reviews Read & Write

        </Accordion>
      operationId: put-feedbacks-review
      tags:
        - Default module/Merchant API/APIs/Feedbacks
        - Feedbacks
      parameters:
        - name: feedback_id
          in: path
          description: ''
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                comment:
                  type: string
              required:
                - comment
              x-apidog-orders:
                - comment
            example:
              comment: test
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
                  success:
                    type: boolean
                  data:
                    type: object
                    properties:
                      reply:
                        type: integer
                    required:
                      - reply
                    x-apidog-orders:
                      - reply
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
          headers: {}
          x-apidog-name: Created Successfully
      security:
        - bearer: []
      x-salla-php-method-name: add-reply
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Feedbacks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-11160591-run
components:
  schemas: {}
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

## apis-feedbacks/List-Reviews-Salla-Merchants-APIs

# List Feedbacks

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /feedbacks:
    get:
      summary: List Feedbacks
      deprecated: false
      description: >-
        This endpoint allows you to list product feedbacks, general product,
        blog,and shipping ratings as well as Merchant store feedbacks.


        :::info[Feedback Types]

        - Product reviews are of type ```product```. 

        - General product questions are of type ```ask```.

        - Ratings about shipping are of type ```shipping```.

        - Merchant store feedbacks are of type ```store```.

        - Merchant blog feedbacks are of type ```blog```.

        - Merchant reported feedbacks are of type ```reported```.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read`- Questions & Reviews Read Only

        </Accordion>
      operationId: get-feedbacks
      tags:
        - Default module/Merchant API/APIs/Feedbacks
        - Feedbacks
      parameters:
        - name: keyword
          in: query
          description: The content of feedback
          required: false
          example: blah
          schema:
            type: string
        - name: type
          in: query
          description: The type of feedback
          required: false
          example: product
          schema:
            type: string
        - name: start_date
          in: query
          description: Start date filter in 'YYYY-MM-DD' format.
          required: false
          example: '2020-01-02'
          schema:
            type: string
        - name: end_date
          in: query
          description: End date filter in 'YYYY-MM-DD' format.
          required: false
          example: '2024-10-02'
          schema:
            type: string
        - name: products
          in: query
          description: List of product IDs to filter feedbacks.
          required: false
          example:
            - '2345231543'
          schema:
            type: array
            items:
              type: string
        - name: blogs
          in: query
          description: List of blog IDs to filter feedbacks.
          required: false
          example:
            - '2345231543'
          schema:
            type: array
            items:
              type: string
        - name: customers
          in: query
          description: List of customer IDs to filter feedbacks.
          required: false
          example:
            - 2345231543
          schema:
            type: array
            items:
              type: string
        - name: reply
          in: query
          description: Indicates if a feedbacks that have reply.
          required: false
          example: 'true'
          schema:
            type: boolean
        - name: stars
          in: query
          description: Star rating filter (e.g.)
          required: false
          example:
            - '2'
          schema:
            type: array
            items:
              type: string
        - name: publish
          in: query
          description: Indicates if a feedbacks published or not.
          required: false
          example: 'true'
          schema:
            type: boolean
        - name: page
          in: query
          description: The Pagination page number
          required: false
          example: 0
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
                  success:
                    type: boolean
                  data:
                    type: array
                    items:
                      type: object
                      properties:
                        id:
                          type: integer
                          description: Feedback unique identifer
                        type:
                          type: string
                          description: The type of feedback
                          enum:
                            - testimonial
                            - rating
                            - store
                            - ask
                            - page
                            - shipping
                          x-apidog-enum:
                            - value: testimonial
                              name: ''
                              description: ''
                            - value: rating
                              name: ''
                              description: ''
                            - value: store
                              name: ''
                              description: ''
                            - value: ask
                              name: ''
                              description: ''
                            - value: page
                              name: ''
                              description: ''
                            - value: shipping
                              name: ''
                              description: ''
                        rating:
                          type: integer
                          minimum: 1
                          maximum: 5
                          enum:
                            - 1
                            - 2
                            - 3
                            - 4
                            - 5
                          x-apidog-enum:
                            - value: 1
                              name: ''
                              description: ''
                            - value: 2
                              name: ''
                              description: ''
                            - value: 3
                              name: ''
                              description: ''
                            - value: 4
                              name: ''
                              description: ''
                            - value: 5
                              name: ''
                              description: ''
                          examples:
                            - 5
                          description: Rating our of five
                        content:
                          type: string
                          description: The content of the feedback.
                          examples:
                            - Great Product
                        order_id:
                          type: integer
                          description: 'Order unique identifier '
                          nullable: true
                        reference_id:
                          type: integer
                          description: Order reference_id
                          nullable: true
                        is_published:
                          type: boolean
                          description: >-
                            Wheather the feedback is published and visible or
                            not
                        created_at:
                          type: string
                          description: Timestamp of the feedback creation date
                        likes_count:
                          type: integer
                        images:
                          type: array
                          items:
                            type: string
                          description: List of images attached to the rating
                        customer:
                          type: object
                          properties:
                            id:
                              type: integer
                              description: 'Customer unique identifier '
                              nullable: true
                            name:
                              type: string
                              description: Customer name
                              nullable: true
                            mobile:
                              type: integer
                              description: Customer mobile number
                              nullable: true
                            email:
                              type: string
                              description: Customer Email
                              nullable: true
                            avatar:
                              type: string
                              description: Custoemr avatar URL
                              nullable: true
                            country:
                              type: string
                              description: Custoemr country
                              nullable: true
                            city:
                              type: string
                              description: Customer city
                              nullable: true
                          x-apidog-orders:
                            - id
                            - name
                            - mobile
                            - email
                            - avatar
                            - country
                            - city
                          x-apidog-ignore-properties: []
                        reply:
                          type: object
                          properties:
                            id:
                              type: integer
                              description: 'Reply unique identifier '
                              nullable: true
                            content:
                              type: string
                              description: The text content of the reply
                              nullable: true
                          x-apidog-orders:
                            - id
                            - content
                          description: Reply information
                          x-apidog-ignore-properties: []
                        shipping_company:
                          type: object
                          properties:
                            id:
                              type: integer
                              description: 'Shipping company unique identifier '
                              nullable: true
                            name:
                              type: string
                              description: Shipping company name
                            thumbnail:
                              type: string
                          x-apidog-orders:
                            - id
                            - name
                            - thumbnail
                          description: Shipping company information
                          x-apidog-ignore-properties: []
                        product:
                          type: object
                          properties:
                            id:
                              type: integer
                              description: 'Product unique identifier '
                              nullable: true
                            name:
                              type: string
                              description: Product name
                            thumbnail:
                              type: string
                          x-apidog-orders:
                            - id
                            - name
                            - thumbnail
                          description: Product information
                          x-apidog-ignore-properties: []
                        page:
                          type: object
                          properties:
                            id:
                              type: 'null'
                              description: 'Page unique identifier '
                            name:
                              type: string
                              description: Page name
                            thumbnail:
                              type: string
                          x-apidog-orders:
                            - id
                            - name
                            - thumbnail
                          x-apidog-ignore-properties: []
                        blog:
                          type: object
                          properties:
                            id:
                              type: integer
                              description: 'Blog unique identifier '
                              nullable: true
                            name:
                              type: string
                              description: Blog name
                            thumbnail:
                              type: string
                          x-apidog-orders:
                            - id
                            - name
                            - thumbnail
                          x-apidog-ignore-properties: []
                      x-apidog-orders:
                        - id
                        - type
                        - rating
                        - content
                        - order_id
                        - reference_id
                        - is_published
                        - created_at
                        - likes_count
                        - images
                        - customer
                        - reply
                        - shipping_company
                        - product
                        - page
                        - blog
                      x-apidog-ignore-properties: []
                  pagination:
                    type: object
                    properties:
                      count:
                        type: integer
                      total:
                        type: integer
                      perPage:
                        type: integer
                      currentPage:
                        type: integer
                      totalPages:
                        type: integer
                      links:
                        type: object
                        properties:
                          next:
                            type: string
                        required:
                          - next
                        x-apidog-orders:
                          - next
                        x-apidog-ignore-properties: []
                    required:
                      - count
                      - total
                      - perPage
                      - currentPage
                      - totalPages
                      - links
                    x-apidog-orders:
                      - count
                      - total
                      - perPage
                      - currentPage
                      - totalPages
                      - links
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - status
                  - success
                  - data
                  - pagination
                x-apidog-ignore-properties: []
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
          headers: {}
          x-apidog-name: error_unauthorized_401
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Feedbacks
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Feedbacks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394279-run
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

## apis-feedbacks/Review-Details-Salla-Merchants-APIs

# Feedback Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /feedbacks/{feedback_id}:
    get:
      summary: Feedback Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch a specific review by passing the
        `feedback_id` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read`- Questions & Reviews Read Only

        </Accordion>
      operationId: get-feedbacks-feedback
      tags:
        - Default module/Merchant API/APIs/Feedbacks
        - Feedbacks
      parameters:
        - name: feedback_id
          in: path
          description: ''
          required: true
          schema:
            type: string
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
                  success:
                    type: boolean
                  data:
                    type: object
                    properties:
                      id:
                        type: integer
                        description: Feedback unique identifer
                      type:
                        type: string
                        description: The type of feedback
                        enum:
                          - testimonial
                          - rating
                          - store
                          - ask
                          - page
                          - shipping
                        x-apidog-enum:
                          - value: testimonial
                            name: ''
                            description: ''
                          - value: rating
                            name: ''
                            description: ''
                          - value: store
                            name: ''
                            description: ''
                          - value: ask
                            name: ''
                            description: ''
                          - value: page
                            name: ''
                            description: ''
                          - value: shipping
                            name: ''
                            description: ''
                      rating:
                        type: integer
                        minimum: 1
                        maximum: 5
                        enum:
                          - 1
                          - 2
                          - 3
                          - 4
                          - 5
                        x-apidog-enum:
                          - value: 1
                            name: ''
                            description: ''
                          - value: 2
                            name: ''
                            description: ''
                          - value: 3
                            name: ''
                            description: ''
                          - value: 4
                            name: ''
                            description: ''
                          - value: 5
                            name: ''
                            description: ''
                        examples:
                          - 5
                        description: Rating our of five
                      content:
                        type: string
                        description: The content of the feedback.
                        examples:
                          - Great Product
                      order_id:
                        type: integer
                        description: 'Order unique identifier '
                        nullable: true
                      reference_id:
                        type: integer
                        description: Order reference_id
                        nullable: true
                      is_published:
                        type: boolean
                        description: Wheather the feedback is published and visible or not
                      created_at:
                        type: string
                        description: Timestamp of the feedback creation date
                      likes_count:
                        type: integer
                      images:
                        type: array
                        items:
                          type: string
                        description: List of images attached to the rating
                      customer:
                        type: object
                        properties:
                          id:
                            type: integer
                            description: 'Customer unique identifier '
                            nullable: true
                          name:
                            type: string
                            description: Customer name
                            nullable: true
                          mobile:
                            type: integer
                            description: Customer mobile number
                            nullable: true
                          email:
                            type: string
                            description: Customer Email
                            nullable: true
                          avatar:
                            type: string
                            description: Custoemr avatar URL
                            nullable: true
                          country:
                            type: string
                            description: Custoemr country
                            nullable: true
                          city:
                            type: string
                            description: Customer city
                            nullable: true
                        x-apidog-orders:
                          - id
                          - name
                          - mobile
                          - email
                          - avatar
                          - country
                          - city
                        x-apidog-ignore-properties: []
                      reply:
                        type: object
                        properties:
                          id:
                            type: integer
                            description: 'Reply unique identifier '
                            nullable: true
                          content:
                            type: string
                            description: The text content of the reply
                            nullable: true
                        x-apidog-orders:
                          - id
                          - content
                        description: Reply information
                        x-apidog-ignore-properties: []
                      shipping_company:
                        type: object
                        properties:
                          id:
                            type: integer
                            description: 'Shipping company unique identifier '
                            nullable: true
                          name:
                            type: string
                            description: Shipping company name
                          thumbnail:
                            type: string
                        x-apidog-orders:
                          - id
                          - name
                          - thumbnail
                        description: Shipping company information
                        x-apidog-ignore-properties: []
                      product:
                        type: object
                        properties:
                          id:
                            type: integer
                            description: 'Product unique identifier '
                            nullable: true
                          name:
                            type: string
                            description: Product name
                          thumbnail:
                            type: string
                        x-apidog-orders:
                          - id
                          - name
                          - thumbnail
                        description: Product information
                        x-apidog-ignore-properties: []
                      page:
                        type: object
                        properties:
                          id:
                            type: 'null'
                            description: 'Page unique identifier '
                          name:
                            type: string
                            description: Page name
                          thumbnail:
                            type: string
                        x-apidog-orders:
                          - id
                          - name
                          - thumbnail
                        x-apidog-ignore-properties: []
                      blog:
                        type: object
                        properties:
                          id:
                            type: integer
                            description: 'Blog unique identifier '
                            nullable: true
                          name:
                            type: string
                            description: Blog name
                          thumbnail:
                            type: string
                        x-apidog-orders:
                          - id
                          - name
                          - thumbnail
                        x-apidog-ignore-properties: []
                    x-apidog-orders:
                      - id
                      - type
                      - rating
                      - content
                      - order_id
                      - reference_id
                      - is_published
                      - created_at
                      - likes_count
                      - images
                      - customer
                      - reply
                      - shipping_company
                      - product
                      - page
                      - blog
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
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
          headers: {}
          x-apidog-name: error_unauthorized_401
        '404':
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
                    x-stoplight:
                      id: f4ajks6ba59j4
                    description: >-
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  error:
                    $ref: '#/components/schemas/NotFound'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
          headers: {}
          x-apidog-name: error_notFound_404
      security:
        - bearer: []
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Feedbacks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394280-run
components:
  schemas:
    NotFound:
      type: object
      properties:
        code:
          anyOf:
            - type: string
            - type: number
          description: >-
            Not Found Response error code, a numeric or alphanumeric unique
            identifier used to represent the error.
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when the
            response is not found or explain the error.
      x-apidog-orders:
        - code
        - message
      required:
        - code
        - message
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

## apis-feedbacks/Store-Feedback

# Store Feedback

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /feedbacks:
    post:
      summary: Store Feedback
      deprecated: false
      description: >-

        :::warning[]

        This endpoint will be accessible only for allowed applications and
        requires approval

        :::

        This endpoint allows you to Store feedbacks


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read_write`- Questions & Reviews Read & Write

        </Accordion>
      operationId: put-feedbacks-review
      tags:
        - Default module/Merchant API/APIs/Feedbacks
        - Feedbacks
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                type:
                  type: string
                  description: The type of the feedback
                  examples:
                    - rating
                  enum:
                    - testimonial
                    - rating
                    - store
                    - ask
                    - page
                    - shipping
                  x-apidog-enum:
                    - value: testimonial
                      name: ''
                      description: ''
                    - value: rating
                      name: ''
                      description: ''
                    - value: store
                      name: ''
                      description: ''
                    - value: ask
                      name: ''
                      description: ''
                    - value: page
                      name: ''
                      description: ''
                    - value: shipping
                      name: ''
                      description: ''
                order_id:
                  type: integer
                  description: >-
                    Customer order's ID. required if feedback_type is
                    testimonial,shipping or rating
                  examples:
                    - 99747126
                customer_id:
                  type: integer
                  description: Customer unique identifier.
                  examples:
                    - 36547883
                page_id:
                  type: integer
                  description: Page unique identifier. required if type is page
                  examples:
                    - 274126897
                shipping_company_id:
                  type: integer
                  description: >-
                    Shipping company unique identifier. Required if the `type`
                    is `shipping`
                product_id:
                  type: integer
                  description: Product unique identifier. Required if `type` is `rating`
                  examples:
                    - 823654778
                content:
                  type: string
                  description: >-
                    The content of the feedback or "review". Required if
                    feedback_type is ask
                  maxLength: 255
                  examples:
                    - Fantastic product
                    - Do you shipt to UAE?
                  nullable: true
                rating:
                  type: integer
                  description: >-
                    values from 1 to 5 "stars". Required if feedback_type is
                    testimonial,shipping or rating
                  enum:
                    - 1
                    - 2
                    - 3
                    - 4
                    - 5
                  x-apidog-enum:
                    - value: 1
                      name: ''
                      description: ''
                    - value: 2
                      name: ''
                      description: ''
                    - value: 3
                      name: ''
                      description: ''
                    - value: 4
                      name: ''
                      description: ''
                    - value: 5
                      name: ''
                      description: ''
                  minimum: 1
                  maximum: 5
                  examples:
                    - 5
                images:
                  type: array
                  items:
                    type: string
                    description: Valid image URL
                  description: Array of image URLs
              x-apidog-orders:
                - 01KDST3YZPKE14BD68XBTRTDZJ
              required:
                - type
                - customer_id
              x-apidog-refs:
                01KDST3YZPKE14BD68XBTRTDZJ:
                  $ref: '#/components/schemas/Feedback'
              x-apidog-ignore-properties:
                - type
                - order_id
                - customer_id
                - page_id
                - shipping_company_id
                - product_id
                - content
                - rating
                - images
            example:
              type: rating
              order_id: 75895308
              customer_id: 83854628
              page_id: 21931877
              shipping_company_id: 26093455
              product_id: 919068012
              content: Product Rating
              images:
                - https://loremflickr.com/640/480/animals
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
                  success:
                    type: boolean
                  data:
                    type: object
                    properties:
                      id:
                        type: integer
                      type:
                        type: string
                      rating:
                        type: integer
                      content:
                        type: string
                      order_id:
                        type: integer
                      is_published:
                        type: boolean
                      created_at:
                        type: string
                      likes_count:
                        type: integer
                      images:
                        type: 'null'
                    required:
                      - id
                      - type
                      - rating
                      - content
                      - order_id
                      - is_published
                      - created_at
                      - likes_count
                      - images
                    x-apidog-orders:
                      - id
                      - type
                      - rating
                      - content
                      - order_id
                      - is_published
                      - created_at
                      - likes_count
                      - images
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
          headers: {}
          x-apidog-name: OK
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
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Feedbacks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-12250711-run
components:
  schemas:
    Feedback:
      type: object
      properties:
        type:
          type: string
          description: The type of the feedback
          examples:
            - rating
          enum:
            - testimonial
            - rating
            - store
            - ask
            - page
            - shipping
          x-apidog-enum:
            - value: testimonial
              name: ''
              description: ''
            - value: rating
              name: ''
              description: ''
            - value: store
              name: ''
              description: ''
            - value: ask
              name: ''
              description: ''
            - value: page
              name: ''
              description: ''
            - value: shipping
              name: ''
              description: ''
        order_id:
          type: integer
          description: >-
            Customer order's ID. required if feedback_type is
            testimonial,shipping or rating
          examples:
            - 99747126
        customer_id:
          type: integer
          description: Customer unique identifier.
          examples:
            - 36547883
        page_id:
          type: integer
          description: Page unique identifier. required if type is page
          examples:
            - 274126897
        shipping_company_id:
          type: integer
          description: >-
            Shipping company unique identifier. Required if the `type` is
            `shipping`
        product_id:
          type: integer
          description: Product unique identifier. Required if `type` is `rating`
          examples:
            - 823654778
        content:
          type: string
          description: >-
            The content of the feedback or "review". Required if feedback_type
            is ask
          maxLength: 255
          examples:
            - Fantastic product
            - Do you shipt to UAE?
          nullable: true
        rating:
          type: integer
          description: >-
            values from 1 to 5 "stars". Required if feedback_type is
            testimonial,shipping or rating
          enum:
            - 1
            - 2
            - 3
            - 4
            - 5
          x-apidog-enum:
            - value: 1
              name: ''
              description: ''
            - value: 2
              name: ''
              description: ''
            - value: 3
              name: ''
              description: ''
            - value: 4
              name: ''
              description: ''
            - value: 5
              name: ''
              description: ''
          minimum: 1
          maximum: 5
          examples:
            - 5
        images:
          type: array
          items:
            type: string
            description: Valid image URL
          description: Array of image URLs
      x-apidog-orders:
        - type
        - order_id
        - customer_id
        - page_id
        - shipping_company_id
        - product_id
        - content
        - rating
        - images
      required:
        - type
        - customer_id
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

## apis-feedbacks/Update-Feedback-Reply

# Update Feedback Reply

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /feedbacks/{feedback_reply_id}/reply:
    put:
      summary: Update Feedback Reply
      deprecated: false
      description: >-
        This endpoint allows you to update a specific reply feedback by passing
        the `feedback_reply_id` as a path parameter. 


        :::warning[]

        This endpoint will be accessible only for allowed applications and
        requires approval

        :::

        This endpoint allows you to Store feedbacks


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read_write`- Questions & Reviews Read & Write

        </Accordion>
      operationId: put-feedbacks-review
      tags:
        - Default module/Merchant API/APIs/Feedbacks
        - Feedbacks
      parameters:
        - name: feedback_reply_id
          in: path
          description: ''
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                comment:
                  type: string
              required:
                - comment
              x-apidog-orders:
                - comment
            example:
              comment: test
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
                  success:
                    type: boolean
                  data:
                    type: object
                    properties:
                      reply:
                        type: integer
                    required:
                      - reply
                    x-apidog-orders:
                      - reply
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
          headers: {}
          x-apidog-name: OK
      security:
        - bearer: []
      x-salla-php-method-name: add-reply
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Feedbacks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-11160744-run
components:
  schemas: {}
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

## apis-feedbacks/Update-Review-Salla-Merchants-APIs

# Update Feedback

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /feedbacks/{feedback_id}:
    put:
      summary: Update Feedback
      deprecated: false
      description: >-
        This endpoint allows you to update a specific feedback by passing the
        `feedback_id` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read_write`- Questions & Reviews Read & Write

        </Accordion>
      operationId: put-feedbacks-review
      tags:
        - Default module/Merchant API/APIs/Feedbacks
        - Feedbacks
      parameters:
        - name: feedback_id
          in: path
          description: ''
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                is_published:
                  type: boolean
                  x-stoplight:
                    id: 19iy4bagx3zqk
                  description: >-
                    Indicates whether the review is published publicly and seen
                    on the Merchant store front
              x-apidog-orders:
                - is_published
              x-apidog-ignore-properties: []
            example:
              is_published: true
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
                  success:
                    type: boolean
                  data:
                    type: object
                    properties:
                      id:
                        type: integer
                      type:
                        type: string
                      rating:
                        type: integer
                      content:
                        type: string
                      order_id:
                        type: integer
                      is_published:
                        type: boolean
                      created_at:
                        type: string
                      likes_count:
                        type: integer
                      images:
                        type: 'null'
                    required:
                      - id
                      - type
                      - rating
                      - content
                      - order_id
                      - is_published
                      - created_at
                      - likes_count
                      - images
                    x-apidog-orders:
                      - id
                      - type
                      - rating
                      - content
                      - order_id
                      - is_published
                      - created_at
                      - likes_count
                      - images
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
          headers: {}
          x-apidog-name: OK
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
          headers: {}
          x-apidog-name: error_unauthorized_401
        '404':
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
                    x-stoplight:
                      id: f4ajks6ba59j4
                    description: >-
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  error:
                    $ref: '#/components/schemas/NotFound'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
          headers: {}
          x-apidog-name: error_notFound_404
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
          x-apidog-name: error_validation_422
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Feedbacks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394281-run
components:
  schemas:
    NotFound:
      type: object
      properties:
        code:
          anyOf:
            - type: string
            - type: number
          description: >-
            Not Found Response error code, a numeric or alphanumeric unique
            identifier used to represent the error.
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when the
            response is not found or explain the error.
      x-apidog-orders:
        - code
        - message
      required:
        - code
        - message
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

