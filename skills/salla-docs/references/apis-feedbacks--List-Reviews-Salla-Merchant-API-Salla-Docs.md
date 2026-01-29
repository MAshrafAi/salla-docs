# Apis Feedbacks  List Reviews Salla Merchant Api Salla Docs

## Table of Contents

- [apis-reviews/List-Reviews-Salla-Merchant-API-Salla-Docs](#apis-reviews-list-reviews-salla-merchant-api-salla-docs)
- [apis-reviews/Review-Details-Salla-Merchant-API-Salla-Docs](#apis-reviews-review-details-salla-merchant-api-salla-docs)
- [apis-reviews/Update-Review-Salla-Merchant-API-Salla-Docs](#apis-reviews-update-review-salla-merchant-api-salla-docs)

---

## apis-reviews/List-Reviews-Salla-Merchant-API-Salla-Docs

# List Reviews

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /reviews:
    get:
      summary: List Reviews
      deprecated: false
      description: >-
        This endpoint allows you to list product review, general product, and
        shipping ratings as well as Merchant store reviews.


        :::info[Review Types]

        - Product reviews are of type `rating`.

        - General product questions are of type `ask`.

        - Ratings about shipping are of type `shipping`.

        - Merchant store reviews are of type `testimonial`.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read`- Reviews Read Only

        </Accordion>
      operationId: get-feedbacks
      tags:
        - Default module/Merchant API/APIs/Reviews
        - Reviews
      parameters:
        - name: keyword
          in: query
          description: The content of feedback
          required: false
          example: Nice shoes
          schema:
            type: string
        - name: type
          in: query
          description: The type of feedback
          required: false
          example: product
          schema:
            type: string
            enum:
              - rating
              - ask
              - shipping
              - testimonial
            x-apidog-enum:
              - value: rating
                name: ''
                description: Rating  products
              - value: ask
                name: ''
                description: ' General product questions'
              - value: shipping
                name: ''
                description: Rating shipping companies
              - value: testimonial
                name: ''
                description: Merchant store reviews
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
                $ref: '#/components/schemas/reviews_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1989531006
                    type: ask
                    rating: 0
                    content: does it work on MAC machines?
                    order_id: null
                    is_published: false
                    created_at: '2023-09-28 17:17:53'
                    customer:
                      id: 1227534533
                      name: Ahmed Ali
                      mobile: 566666666
                      email: ahmed@mail.com
                      avatar: >-
                        https://cdn.assets.salla.network/admin/cp/assets/images/avatar_male.png
                      country: السعودية
                      city: الخبر
                  - id: 1853140150
                    type: rating
                    rating: 5
                    content: I like this product
                    order_id: 123456789
                    is_published: true
                    created_at: '2023-09-28 17:20:24'
                    customer:
                      id: 1227534533
                      name: Mohammed Ali
                      mobile: 565555555
                      email: mohammed@mail.com
                      avatar: >-
                        https://cdn.assets.salla.network/admin/cp/assets/images/avatar_male.png
                      country: السعودية
                      city: الرياض
                pagination:
                  count: 2
                  total: 2
                  perPage: 15
                  currentPage: 1
                  totalPages: 1
                  links: []
          headers: {}
          x-apidog-name: Success
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Feedbacks
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Reviews
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-16603963-run
components:
  schemas:
    reviews_response_body:
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
            id: fnuvra7dx2r05
          items:
            $ref: '#/components/schemas/Reviews'
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
    Reviews:
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific review. List of
            reviews can be found [here](https://docs.salla.dev/api-5394279).
        type:
          type: string
          description: The type of the review.
          enum:
            - rating
            - ask
            - shipping
            - testimonial
          x-apidog-enum:
            - value: rating
              name: ''
              description: Review for rating.
            - value: ask
              name: ''
              description: Review for asking.
            - value: shipping
              name: ''
              description: Review for shipping.
            - value: testimonial
              name: ''
              description: Review for testimonials.
        rating:
          type: number
          description: Review rating value.
        content:
          type: string
          description: Review content.
        order_id:
          description: >-
            Review order unique identifier. List of orders can be found
            [here](https://docs.salla.dev/api-5394146)
          type: number
          nullable: true
        is_published:
          type: boolean
          description: Whether or not the review is published publicly.
        created_at:
          type: string
          description: String representation of the review original creation date and time.
        customer:
          type: object
          properties:
            id:
              type: number
              description: >-
                Customer's unique identification assigned to an individual
                customer. List of customers can be found
                [here](https://docs.salla.dev/api-5394121).
            name:
              type: string
              description: Customer's given full name.
            mobile:
              type: number
              description: The numerical contact information belonging to a customer.
            email:
              type: string
              description: Email address of the customer used for electronic communication.
            avatar:
              type: string
              description: >-
                Image representing the customer, often a personal photograph or
                avatar.
            country:
              type: string
              description: >-
                The nation of origin or residence of the customer. List of
                countries can be found
                [here](https://docs.salla.dev/api-5394228).
            city:
              type: string
              description: >-
                The city where the customer resides. List of cities can be found
                [here](https://docs.salla.dev/api-5394230).
          x-apidog-orders:
            - id
            - name
            - mobile
            - email
            - avatar
            - country
            - city
          required:
            - id
            - name
            - mobile
            - email
            - avatar
            - country
            - city
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - type
        - rating
        - content
        - order_id
        - is_published
        - created_at
        - customer
      required:
        - id
        - type
        - rating
        - content
        - order_id
        - is_published
        - created_at
        - customer
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

## apis-reviews/Review-Details-Salla-Merchant-API-Salla-Docs

# Review Details 

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /reviews/{id}:
    get:
      summary: 'Review Details '
      deprecated: false
      description: >-
        This endpoint allows you to fetch a specific review by passing the `id`
        as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read`- Reviews Read Only

        </Accordion>
      operationId: get-feedbacks-feedback
      tags:
        - Default module/Merchant API/APIs/Reviews
        - Reviews
      parameters:
        - name: id
          in: path
          description: >-
            Review ID. Get a list of Review IDs from
            [here](https://docs.salla.dev/api-16603963)
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/review_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1096828836
                  type: ask
                  rating: 0
                  content: A question
                  order_id: null
                  is_published: true
                  created_at: '2023-11-01 15:32:31'
                  customer:
                    id: 1227534533
                    name: Ahmed Ali
                    mobile: 565555555
                    email: ahmed@mail.com
                    avatar: >-
                      https://cdn.assets.salla.network/admin/cp/assets/images/avatar_male.png
                    country: السعودية
                    city: الرياض
          headers: {}
          x-apidog-name: Success
      security:
        - bearer: []
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Reviews
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-16603964-run
components:
  schemas:
    review_response_body:
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
          $ref: '#/components/schemas/Reviews'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Reviews:
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific review. List of
            reviews can be found [here](https://docs.salla.dev/api-5394279).
        type:
          type: string
          description: The type of the review.
          enum:
            - rating
            - ask
            - shipping
            - testimonial
          x-apidog-enum:
            - value: rating
              name: ''
              description: Review for rating.
            - value: ask
              name: ''
              description: Review for asking.
            - value: shipping
              name: ''
              description: Review for shipping.
            - value: testimonial
              name: ''
              description: Review for testimonials.
        rating:
          type: number
          description: Review rating value.
        content:
          type: string
          description: Review content.
        order_id:
          description: >-
            Review order unique identifier. List of orders can be found
            [here](https://docs.salla.dev/api-5394146)
          type: number
          nullable: true
        is_published:
          type: boolean
          description: Whether or not the review is published publicly.
        created_at:
          type: string
          description: String representation of the review original creation date and time.
        customer:
          type: object
          properties:
            id:
              type: number
              description: >-
                Customer's unique identification assigned to an individual
                customer. List of customers can be found
                [here](https://docs.salla.dev/api-5394121).
            name:
              type: string
              description: Customer's given full name.
            mobile:
              type: number
              description: The numerical contact information belonging to a customer.
            email:
              type: string
              description: Email address of the customer used for electronic communication.
            avatar:
              type: string
              description: >-
                Image representing the customer, often a personal photograph or
                avatar.
            country:
              type: string
              description: >-
                The nation of origin or residence of the customer. List of
                countries can be found
                [here](https://docs.salla.dev/api-5394228).
            city:
              type: string
              description: >-
                The city where the customer resides. List of cities can be found
                [here](https://docs.salla.dev/api-5394230).
          x-apidog-orders:
            - id
            - name
            - mobile
            - email
            - avatar
            - country
            - city
          required:
            - id
            - name
            - mobile
            - email
            - avatar
            - country
            - city
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - type
        - rating
        - content
        - order_id
        - is_published
        - created_at
        - customer
      required:
        - id
        - type
        - rating
        - content
        - order_id
        - is_published
        - created_at
        - customer
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

## apis-reviews/Update-Review-Salla-Merchant-API-Salla-Docs

# Update Review

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /reviews/{id}:
    put:
      summary: Update Review
      deprecated: false
      description: >-
        This endpoint allows you to update a specific review by passing the `id`
        as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `reviews.read_write`- Reviews Read & Write

        </Accordion>
      operationId: put-feedbacks-review
      tags:
        - Default module/Merchant API/APIs/Reviews
        - Reviews
      parameters:
        - name: id
          in: path
          description: >-
            Review ID. Get a list of Review IDs from
            [here](https://docs.salla.dev/api-16603963)
          required: true
          schema:
            type: integer
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
                $ref: '#/components/schemas/review_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1096828836
                  type: ask
                  rating: 0
                  content: A question
                  order_id: null
                  is_published: true
                  created_at: '2023-11-01 15:32:31'
                  customer:
                    id: 1227534533
                    name: Ahmed Ali
                    mobile: 565555555
                    email: ahmed@mail.com
                    avatar: >-
                      https://cdn.assets.salla.network/admin/cp/assets/images/avatar_male.png
                    country: السعودية
                    city: الرياض
          headers: {}
          x-apidog-name: OK
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: Feedbacks
      x-apidog-folder: Default module/Merchant API/APIs/Reviews
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-16603966-run
components:
  schemas:
    review_response_body:
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
          $ref: '#/components/schemas/Reviews'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Reviews:
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific review. List of
            reviews can be found [here](https://docs.salla.dev/api-5394279).
        type:
          type: string
          description: The type of the review.
          enum:
            - rating
            - ask
            - shipping
            - testimonial
          x-apidog-enum:
            - value: rating
              name: ''
              description: Review for rating.
            - value: ask
              name: ''
              description: Review for asking.
            - value: shipping
              name: ''
              description: Review for shipping.
            - value: testimonial
              name: ''
              description: Review for testimonials.
        rating:
          type: number
          description: Review rating value.
        content:
          type: string
          description: Review content.
        order_id:
          description: >-
            Review order unique identifier. List of orders can be found
            [here](https://docs.salla.dev/api-5394146)
          type: number
          nullable: true
        is_published:
          type: boolean
          description: Whether or not the review is published publicly.
        created_at:
          type: string
          description: String representation of the review original creation date and time.
        customer:
          type: object
          properties:
            id:
              type: number
              description: >-
                Customer's unique identification assigned to an individual
                customer. List of customers can be found
                [here](https://docs.salla.dev/api-5394121).
            name:
              type: string
              description: Customer's given full name.
            mobile:
              type: number
              description: The numerical contact information belonging to a customer.
            email:
              type: string
              description: Email address of the customer used for electronic communication.
            avatar:
              type: string
              description: >-
                Image representing the customer, often a personal photograph or
                avatar.
            country:
              type: string
              description: >-
                The nation of origin or residence of the customer. List of
                countries can be found
                [here](https://docs.salla.dev/api-5394228).
            city:
              type: string
              description: >-
                The city where the customer resides. List of cities can be found
                [here](https://docs.salla.dev/api-5394230).
          x-apidog-orders:
            - id
            - name
            - mobile
            - email
            - avatar
            - country
            - city
          required:
            - id
            - name
            - mobile
            - email
            - avatar
            - country
            - city
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - type
        - rating
        - content
        - order_id
        - is_published
        - created_at
        - customer
      required:
        - id
        - type
        - rating
        - content
        - order_id
        - is_published
        - created_at
        - customer
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

