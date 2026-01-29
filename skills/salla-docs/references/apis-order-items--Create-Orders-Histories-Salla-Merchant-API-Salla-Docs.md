# Apis Order Items  Create Orders Histories Salla Merchant Api Salla Docs

## Table of Contents

- [apis-order-histories/Create-Orders-Histories-Salla-Merchant-API-Salla-Docs](#apis-order-histories-create-orders-histories-salla-merchant-api-salla-docs)
- [apis-order-histories/List-Orders-Histories-Salla-Merchant-API-Salla-Docs](#apis-order-histories-list-orders-histories-salla-merchant-api-salla-docs)
- [apis-order-items/Create-Order-Item-Salla-Merchant-API-Salla-Docs](#apis-order-items-create-order-item-salla-merchant-api-salla-docs)
- [apis-order-items/Delete-Order-Item-Salla-Merchant-API-Salla-Docs](#apis-order-items-delete-order-item-salla-merchant-api-salla-docs)

---

## apis-order-histories/Create-Orders-Histories-Salla-Merchant-API-Salla-Docs

# Create Order History

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/{order_id}/histories:
    post:
      summary: Create Order History
      deprecated: false
      description: >-
        This endpoint allows you to append a `note` to the Order History, by
        passing the `order_id` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-order_id-histories
      tags:
        - Default module/Merchant API/APIs/Order Histories
        - Order Histories
      parameters:
        - name: order_id
          in: path
          description: >-
            Unique identification number assigend to an order. Get a list of
            Order IDs from [here](https://docs.salla.dev/api-5394146).
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                note:
                  type: string
                  description: Note value
              required:
                - note
              x-apidog-orders:
                - note
              x-apidog-ignore-properties: []
            example: ''
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/post_orderHistories_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1333127585
                  status: مسترجع
                  customized:
                    id: 2062355698
                    name: مسترجع
                    type: custom
                    slug: restored
                    original:
                      id: 989286562
                      name: مسترجع
                    parent: {}
                  note: ملاحظة
                  created_at:
                    date: '2023-02-21 11:09:57.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
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
                    orders.read_write
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
                    note:
                      - نص التعليق مطلوب
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: createHistory
      x-salla-php-return-type: POSTOrderHistory
      x-apidog-folder: Default module/Merchant API/APIs/Order Histories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394163-run
components:
  schemas:
    post_orderHistories_response_body:
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
          $ref: '#/components/schemas/POSTOrderHistory'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    POSTOrderHistory:
      title: POSTOrderHistory
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific entry or record in a
            database containing information about a customer's past order or
            transaction history.
        status:
          type: string
          description: The current state or condition of an order.
        customized:
          type: object
          properties:
            id:
              type: number
              description: >-
                A unique identifier associated with a specific, user-defined
                order status.
            name:
              type: string
              description: User-defined label or name given to a specific order status.
            type:
              type: string
              description: >-
                A user-defined classification or category associated with a
                custom order status.
            slug:
              type: string
              description: >-
                A unique and user-defined text string associated with a custom
                order status.
            original:
              type: object
              properties:
                id:
                  type: number
                  description: >-
                    A customised unique identifier typically associated with the
                    initial status of an order.
                name:
                  type: string
                  description: >-
                    A customised label given to the status of an order when it
                    is first placed in a system.
              x-apidog-orders:
                - id
                - name
              required:
                - id
                - name
              x-apidog-ignore-properties: []
            parent:
              type: string
              description: >-
                Customised status of a higher-level or overarching status to
                which specific order is associated to.
          x-apidog-orders:
            - id
            - name
            - type
            - slug
            - original
            - parent
          required:
            - id
            - name
            - type
            - slug
            - original
            - parent
          x-apidog-ignore-properties: []
        note:
          type: string
          description: A record or comment associated with a specific order.
        created_at:
          $ref: '#/components/schemas/Date'
          description: POST order history date an time of creation.
      x-apidog-orders:
        - id
        - status
        - customized
        - note
        - created_at
      required:
        - id
        - status
        - customized
        - note
        - created_at
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

## apis-order-histories/List-Orders-Histories-Salla-Merchant-API-Salla-Docs

# List Order Histories

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/{order_id}/histories:
    get:
      summary: List Order Histories
      deprecated: false
      description: >
        This endpoint allows you to return the order history of previous and
        current order statuses for a specific order by passing the `order_id` as
        a path parameter. 
      operationId: Order-Histories
      tags:
        - Default module/Merchant API/APIs/Order Histories
        - Order Histories
      parameters:
        - name: order_id
          in: path
          description: >-
            Unique identification number assigend to an order. Get a list of
            Order IDs from [here](https://docs.salla.dev/api-5394146).
          required: true
          example: 3155923424
          schema:
            type: integer
        - name: page
          in: query
          description: The Pagination page number
          required: false
          example: 5
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/get_orderHistories_response_body'
              examples:
                '1':
                  summary: Example
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 213320125
                        status: تم التنفيذ
                        note: تم ارسال الطلب عبر شركة الشحن ارامكس
                        created_at:
                          date: '2020-04-02 18:59:47.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                      - id: 213320122
                        status: قيد التنفيذ
                        note: الطلب قيد التنفيذ
                        created_at:
                          date: '2020-04-02 16:59:47.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                      - id: 213320121
                        status: تحت المراجعة
                        note: الطلب تحت المراجعة
                        created_at:
                          date: '2020-04-02 16:50:47.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                    pagination:
                      count: 3
                      total: 3
                      perPage: 15
                      currentPage: 1
                      totalPages: 1
                      links: []
                '3':
                  summary: Success | With Created_by
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 774142439
                        status: بإنتظار المراجعة
                        customized:
                          id: 1592566197
                          name: استلمنا طلبك وجاري تجهيزه
                          type: custom
                          slug: under_review
                          original:
                            id: 566146469
                            name: بإنتظار المراجعة
                          parent: {}
                        note: ''
                        created_at:
                          date: '2024-02-07 14:06:18.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                        created_by:
                          id: 1473353380
                          name: أحمد Conn
                        type: activity
                    pagination:
                      count: 10
                      total: 10
                      perPage: 15
                      currentPage: 1
                      totalPages: 1
                      links: []
          headers: {}
          x-apidog-name: 'Success '
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
      x-apidog-folder: Default module/Merchant API/APIs/Order Histories
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394162-run
components:
  schemas:
    get_orderHistories_response_body:
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
            id: vu4p3jl2f17ae
          items:
            $ref: '#/components/schemas/ListOrderHistories'
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
    ListOrderHistories:
      title: ListOrderHistories
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific entry or record in a
            database that contains information about a customer's past order or
            transaction history.
        status:
          type: string
          description: >-
            The current state of a specific order in a customer's transaction
            history.
        note:
          type: string
          description: >-
            A written remark, or message associated with an order entry in a
            customer's transaction history.
        created_at:
          $ref: '#/components/schemas/Date'
        created_by:
          type: object
          properties:
            id:
              type: integer
              description: A nique identification of the user who created the offer.
            name:
              type: string
              description: The name of the user who created the offer.
            avatar:
              type: string
              examples:
                - https://www.gravatar.com/avatar/1247a0caa31131ed44f5387
              description: A URL of the order history creator
          x-apidog-orders:
            - id
            - name
            - avatar
          required:
            - id
            - name
            - avatar
          x-apidog-ignore-properties: []
          nullable: true
        type:
          type: string
          description: Type value
          enum:
            - comment
            - activity
          x-apidog-enum:
            - name: ''
              value: comment
              description: 'Order history of type comment '
            - name: ''
              value: activity
              description: Order history of type activity.
      x-apidog-orders:
        - id
        - status
        - note
        - created_at
        - created_by
        - type
      required:
        - id
        - status
        - note
        - created_at
        - created_by
        - type
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

## apis-order-items/Create-Order-Item-Salla-Merchant-API-Salla-Docs

# Create Order Item

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/items:
    post:
      summary: Create Order Item
      deprecated: false
      description: >-
        This endpoint allows you to create an order item for a specific order by
        passing its ID in the body request.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-items
      tags:
        - Default module/Merchant API/APIs/Order Items
        - Order Items
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/orderItem_request_body'
            example:
              order_id: 837293123
              identifier_type: id
              identifier: 123456
              quantity: 1
              branch_id: 12342
              options:
                - id: 789012
                  value:
                    - value1
                    - value2
              name: Custom Product Name
              price: 100
              cost_price: 80
              weight: 150
              weight_type: g
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/orderItem_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 365435777
                    name: SSD
                    sku: sam-ssd-256g
                    quantity: 1
                    currency: SAR
                    weight: 0.51
                    weight_label: ٥١٠ جم
                    amounts:
                      price_without_tax:
                        amount: 150
                        currency: SAR
                      total_discount:
                        amount: 0
                        currency: SAR
                      tax:
                        percent: '15.00'
                        amount:
                          amount: 22.5
                          currency: SAR
                      total:
                        amount: 150
                        currency: SAR
                    notes: ''
                    options:
                      - id: 675638105
                        product_option_id: 1902643925
                        name: size
                        type: radio
                        value:
                          id: 1090448197
                          name: 256G
                          price:
                            amount: 0
                            currency: SAR
                    images: []
                    codes: []
                    files: []
                    reservations: []
                    branches_quantity: []
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
                    orders.read_write
          headers: {}
          x-apidog-name: Unauthorized
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
      x-apidog-folder: Default module/Merchant API/APIs/Order Items
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5751402-run
components:
  schemas:
    orderItem_request_body:
      type: object
      properties:
        order_id:
          type: integer
          description: >-
            Order ID. List of Order ID can be found
            [here](https://docs.salla.dev/api-5394146)
        identifier_type:
          type: string
          description: Product item identifier type
          enum:
            - id
            - sku
          x-apidog-enum:
            - value: id
              name: ''
              description: ''
            - value: sku
              name: ''
              description: ''
        identifier:
          type: integer
          description: >-
            Order Item Identifier ID. List of Order Items can be found
            [here](https://docs.salla.dev/api-5565737)
        quantity:
          type: integer
          description: Order Item Quantity
        branch_id:
          type: integer
          description: >-
            Branch ID. List of Branch ID can be found
            [here](https://docs.salla.dev/api-5394224).
        options:
          type: array
          items:
            type: object
            properties:
              id:
                type: integer
                description: Product Option ID
              value:
                type: array
                items:
                  type: string
            x-apidog-orders:
              - id
              - value
            x-apidog-ignore-properties: []
        name:
          type: string
          description: >-
            Product Name, list of products can be found
            [here](https://docs.salla.dev/api-5394168).
        price:
          type: integer
          description: Product Price.
        cost_price:
          type: integer
          description: Product Cost Price.
        weight:
          type: integer
          description: Product Weight Value.
        weight_type:
          type: string
          description: Product Weight Type.
      x-apidog-orders:
        - order_id
        - identifier_type
        - identifier
        - quantity
        - branch_id
        - options
        - name
        - price
        - cost_price
        - weight
        - weight_type
      required:
        - order_id
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    orderItem_response_body:
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
          x-stoplight:
            id: orurptuq9pvoy
          items:
            $ref: '#/components/schemas/OrderItem'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OrderItem:
      description: >-
        Detailed structure of the Order Item object showing its fields and data
        types.
      type: object
      title: OrderItem
      x-tags:
        - Models
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            A unique identifier, typically numerical or alphanumeric, assigned
            to an individual item or product within an order.
        name:
          type: string
          description: >-
            The name or description of an individual item or product within an
            order.
        sku:
          type: string
          description: >-
            Stock Keeping Unit, and it is a unique code or identifier used to
            track and manage individual products or items in inventory,
            facilitating inventory management, sales tracking, and product
            identification.
        quantity:
          type: integer
          description: >-
            The numerical count of a specific item or product included in an
            order, indicating how many of that particular item have been
            purchased or are part of the order.
        currency:
          type: string
          description: >-
            The specific currency in which the price or value of an individual
            item within an order is expressed, indicating the monetary unit used
            for pricing that particular item.
        weight:
          type: number
          description: >-
            The numerical measurement representing the weight of an individual
            item or product within an order. 
        weight_label:
          type: string
          description: >-
            A textual label or description associated with the weight of an
            individual item within an order, typically used to indicate the unit
            of measurement (e.g., kg, lb) and provide clarity regarding how the
            item's weight is expressed.
        amounts:
          type: object
          properties:
            price_without_tax:
              type: object
              properties:
                amount:
                  type: integer
                  description: 'Order item amounts price without tax '
                currency:
                  type: string
                  description: Order item amounts price without tax currency
              x-apidog-orders:
                - amount
                - currency
              required:
                - amount
                - currency
              x-apidog-ignore-properties: []
            total_discount:
              type: object
              properties:
                amount:
                  type: integer
                  description: Total discount amount of the order item amounts.
                currency:
                  type: string
                  description: Order item amounts total discount currency
              x-apidog-orders:
                - amount
                - currency
              required:
                - amount
                - currency
              x-apidog-ignore-properties: []
            tax:
              type: object
              properties:
                percent:
                  type: string
                  description: Order item amounts tax percent
                amount:
                  type: object
                  properties:
                    amount:
                      type: integer
                      description: Order item amounts tax amount
                    currency:
                      type: string
                      description: Order item amounts tax caurrency
                  x-apidog-orders:
                    - amount
                    - currency
                  required:
                    - amount
                    - currency
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - percent
                - amount
              required:
                - percent
                - amount
              x-apidog-ignore-properties: []
            total:
              type: object
              properties:
                amount:
                  type: integer
                  description: Order item amounts total amount
                currency:
                  type: string
                  description: Total discount currency of the order item amounts.
              x-apidog-orders:
                - amount
                - currency
              required:
                - amount
                - currency
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - price_without_tax
            - total_discount
            - tax
            - total
          required:
            - price_without_tax
            - total_discount
            - tax
            - total
          x-apidog-ignore-properties: []
        notes:
          type: string
          description: Order items notes
        options:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier, often numerical or alphanumeric, assigned
                  to a specific item.
              product_option_id:
                type: number
                description: >-
                  A unique identifier, often numerical or alphanumeric, assigned
                  to a specific product option , enabling easy tracking and
                  management of various product configurations, such as size,
                  color, or other customizable features.
              name:
                type: string
                description: A label for a product variation or choice, like size or color.
              type:
                type: string
                description: Type of the product option.
                enum:
                  - radio
                  - date
                  - datetime
                  - image
                  - text
                  - text area
                  - number
                  - checkbox
                  - splitter
                x-apidog-enum:
                  - value: radio
                    name: ''
                    description: Option type of radio
                  - value: date
                    name: ''
                    description: Option type of date
                  - value: datetime
                    name: ''
                    description: Option type of date and time
                  - value: image
                    name: ''
                    description: Option type of image
                  - value: text
                    name: ''
                    description: Option type of text
                  - value: text area
                    name: ''
                    description: Option type of text area
                  - value: number
                    name: ''
                    description: Option type of number
                  - value: checkbox
                    name: ''
                    description: Option type of checkbox
                  - value: splitter
                    name: ''
                    description: Option type of splitter
              value:
                type: array
                description: >-
                  If `type` value is set to `radio` or `checkbox`, the returned
                  response is an object. Otherwise, a string is returned in all
                  other available `type` values.
                items:
                  type: object
                  properties:
                    id:
                      type: number
                      description: >-
                        A unique identifier, typically numerical or
                        alphanumeric, associated with a specific value or choice
                        within a product option.
                    name:
                      type: string
                      description: >-
                        The descriptive label or text representing a specific
                        choice or value within a product option.
                    price:
                      type: object
                      properties:
                        amount:
                          type: integer
                          description: Option value amount.
                        currency:
                          type: string
                          description: Option value currency.
                      x-apidog-orders:
                        - amount
                        - currency
                      x-apidog-ignore-properties: []
                  x-apidog-orders:
                    - id
                    - name
                    - price
                  x-apidog-ignore-properties: []
            x-apidog-orders:
              - id
              - product_option_id
              - name
              - type
              - value
            x-apidog-ignore-properties: []
        images:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier, typically numerical or alphanumeric,
                  associated with a specific product image in a database or
                  system, enabling easy tracking and referencing of images used
                  for a product.
              image:
                type: string
                description: >-
                  Textual reference, such as a file path or URL link, that
                  points to the location of an image file representing a
                  product. 
              type:
                type: string
                description: Type of the product image.
            x-apidog-orders:
              - id
              - image
              - type
            x-apidog-ignore-properties: []
        codes:
          type: array
          items:
            type: object
            properties:
              code:
                type: string
                description: Product codes value
              status:
                type: string
                description: Product codes status
            x-apidog-orders:
              - code
              - status
            x-apidog-ignore-properties: []
        files:
          type: array
          items:
            type: object
            properties:
              url:
                type: string
                description: >-
                  A web address (URL) that provides access to a file associated
                  with a product.
              name:
                type: string
                description: the name or title of a file associated with a product.
              size:
                type: number
                description: >-
                  The numerical measurement that represents the size of a file
                  associated with a product.
            x-apidog-orders:
              - url
              - name
              - size
            x-apidog-ignore-properties: []
        reservations:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: Product reservations unique identification.
              from:
                type: string
                description: >-
                  Product reservation starting time expressed in 24 hours
                  format.
                examples:
                  - '14:30'
              to:
                type: string
                description: Product reservation e time expressed in 24 hours format.
                examples:
                  - '17:30'
              date:
                type: string
                description: Prodcut reservation date.
                examples:
                  - '2022-01-10'
            x-apidog-orders:
              - id
              - from
              - to
              - date
            x-apidog-ignore-properties: []
        branches_quantity:
          type: array
          items:
            type: integer
            description: Quantity existing in branches
      x-apidog-orders:
        - id
        - name
        - sku
        - quantity
        - currency
        - weight
        - weight_label
        - amounts
        - notes
        - options
        - images
        - codes
        - files
        - reservations
        - branches_quantity
      required:
        - id
        - name
        - sku
        - quantity
        - currency
        - weight
        - weight_label
        - amounts
        - notes
        - options
        - images
        - codes
        - files
        - reservations
        - branches_quantity
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
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

## apis-order-items/Delete-Order-Item-Salla-Merchant-API-Salla-Docs

# Delete Order Item

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/items/{item_id}:
    delete:
      summary: Delete Order Item
      deprecated: false
      description: >-
        This endpoint allows you to delete an order item by passing the
        `item_id` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: delete-orders-items
      tags:
        - Default module/Merchant API/APIs/Order Items
        - Order Items
      parameters:
        - name: item_id
          in: path
          description: >-
            Unique identification number assigned to an item. List of Order Item
            can be found [here](https://docs.salla.dev/api-5565737).
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
                    orders.read_write
          headers: {}
          x-apidog-name: Unauthorized
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
      x-apidog-folder: Default module/Merchant API/APIs/Order Items
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5751557-run
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

