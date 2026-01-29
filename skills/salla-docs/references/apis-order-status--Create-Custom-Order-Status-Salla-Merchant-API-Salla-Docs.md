# Apis Order Status  Create Custom Order Status Salla Merchant Api Salla Docs

## Table of Contents

- [apis-order-status/Create-Custom-Order-Status-Salla-Merchant-API-Salla-Docs](#apis-order-status-create-custom-order-status-salla-merchant-api-salla-docs)
- [apis-order-status/List-Order-Statuses-Salla-Merchant-API-Salla-Docs](#apis-order-status-list-order-statuses-salla-merchant-api-salla-docs)
- [apis-order-status/Order-Status-Details-Salla-Merchant-API-Salla-Docs](#apis-order-status-order-status-details-salla-merchant-api-salla-docs)
- [apis-order-status/Sort-Orders-Statuses-Salla-Merchant-API-Salla-Docs](#apis-order-status-sort-orders-statuses-salla-merchant-api-salla-docs)

---

## apis-order-status/Create-Custom-Order-Status-Salla-Merchant-API-Salla-Docs

# Create Custom Order Status

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/statuses:
    post:
      summary: Create Custom Order Status
      deprecated: false
      description: >-
        This endpoint allows you to create a custom order status using the
        parameters available to be sent as body request.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-statuses-status
      tags:
        - Default module/Merchant API/APIs/Order Status
        - Order Status
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/post_customSubStatus_request_body'
            example:
              parent_id: 863076598
              name: تبقى 40 دقيقة على الدفع
              message: أكمل الدفع الان
              icon: sicon-cup-hot
              sort: 3
              is_active: true
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/orderStatuses_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 120960473
                  name: تبقى 40 دقيقة على الدفع
                  type: custom
                  slug: payment_pending
                  message: أكمل الدفع الان
                  color: '#ffff'
                  icon: sicon-cup-hot
                  sort: 3
                  is_active: true
                  original:
                    id: 1473353380
                    name: بإنتظار الدفع
                  parent:
                    id: 863076598
                    name: في انتظارك تدفع
                  children: []
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
              examples:
                '3':
                  summary: Example 1
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        parent_id:
                          - حقل رقم الحالة الرئيسية - الأب  مطلوب.
                        name:
                          - حقل عنوان الحالة - اسم الحالة مطلوب.
                        message:
                          - حقل نص الرسالة الفرعية مطلوب.
                '4':
                  summary: Example 2
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        parent_id:
                          - >-
                            orders::custom_status.messages.error.you_cant_add_sub_status_for_nun_main_status
                '5':
                  summary: 'Example 3 '
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        name:
                          - يجب أن يكون حقل عنوان الحالة - اسم الحالة نصآ.
                        is_active:
                          - 'يجب أن تكون قيمة حقل الفعالية إما true أو false '
                '6':
                  summary: Example 4
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        parent_id:
                          - 'رقم الحالة الرئيسية - الأب - غير صالح '
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: createCustomStatus
      x-salla-php-return-type: OrderStatuses
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394149-run
components:
  schemas:
    post_customSubStatus_request_body:
      type: object
      properties:
        parent_id:
          type: integer
          description: >-
            Order Status Parent ID. List of Order Statuses can be found
            [here](https://docs.salla.dev/api-5394150)
          examples:
            - 863076598
        name:
          type: string
          description: Order Status Name.
          examples:
            - تبقى 40 دقيقة على الدفع
        message:
          type: string
          description: Order Status Message.
          examples:
            - أكمل الدفع الان
        icon:
          type: string
          description: Order Status Icon.
          examples:
            - sicon-cup-hot
        sort:
          type: integer
          description: Order Status Sort.
          examples:
            - 3
        is_active:
          type: boolean
          description: Whether or not the Order Status is active.
          default: true
      required:
        - parent_id
        - name
        - message
      x-apidog-orders:
        - parent_id
        - name
        - message
        - icon
        - sort
        - is_active
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    orderStatuses_response_body:
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
          $ref: '#/components/schemas/OrderStatuses%20'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    'OrderStatuses ':
      title: OrderStatuses
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific status assigned to an
            order.

            List of order statuses can be found
            [here](https://docs.salla.dev/api-5394150)
          examples:
            - 863076598
        name:
          type: string
          description: >-
            A label or designation given to a specific status assigned to an
            order. [🌐Support multi-language](doc-421122)
          examples:
            - في انتظار الدفع
        type:
          type: string
          description: The categorization or classification of an order.
          enum:
            - original
            - custom
          examples:
            - custom
          x-apidog-enum:
            - value: original
              name: ''
              description: Original order status by Salla.
            - value: custom
              name: ''
              description: Custom order status, made by the Merchant.
        slug:
          type: string
          description: >-
            A user-friendly and URL-friendly text string associated with a
            specific order. __Note__ the parent slug is inherited.
          examples:
            - payment_pending
        message:
          type: string
          description: >-
            A remark that provides information about the current status or
            condition of an order. [🌐Support multi-language](doc-421122)
          examples:
            - '[ {store.name} ] \\n أصبحت حالة طلبك {order.id} {status}'
        color:
          type: string
          description: >-
            A specific color code or indicator assigned to different order
            statuses.
          examples:
            - '#58C9B9'
        icon:
          type: string
          description: >-
            Graphical symbol or image used to represent different order
            statuses.
          examples:
            - sicon-gold-badge
        sort:
          type: number
          description: >-
            The specific numerical or alphanumeric sequence assigned to each
            order status in a list or database.
          examples:
            - 0
        is_active:
          type: boolean
          description: The option to indicate that the order status is active.
          default: true
        original:
          type: object
          properties:
            id:
              type: number
              description: >-
                A unique identifier associated with the initial or default
                status of an order.
              examples:
                - 349994915
            name:
              type: string
              description: >-
                The label assigned to the status of an order when it was first
                placed.
              examples:
                - جاري التوصيل
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          x-apidog-ignore-properties: []
          nullable: true
        parent:
          type: object
          properties:
            id:
              type: number
              description: A unique identifier associated to the parent order.
              examples:
                - 1638621685
            name:
              type: string
              description: The name or label assigned to the parent order.
              examples:
                - تم التنفيذ
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          x-apidog-ignore-properties: []
          nullable: true
        children:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier associated with a specific status assigned
                  to an order.
                examples:
                  - 863076598
              name:
                type: string
                description: The name or label assigned to the order.
                examples:
                  - في انتظار الدفع
              slug:
                type: string
                description: >-
                  A user-friendly and URL-friendly text string associated with a
                  specific order.
                examples:
                  - payment_pending
              type:
                type: string
                description: The classification or categorization of an order.
                enum:
                  - original
                  - custom
                examples:
                  - custom
                x-apidog-enum:
                  - value: original
                    name: ''
                    description: Original order status.
                  - value: custom
                    name: ''
                    description: Custom order status.
              message:
                type: string
                description: >-
                  A notification that provides information about the current
                  status of the order.
                examples:
                  - '[ {store.name} ] \\n أصبحت حالة طلبك {order.id} {status}'
              color:
                type: string
                description: >-
                  A specific color code or indicator assigned to different order
                  statuses.
                examples:
                  - '#58C9B9'
              icon:
                type: string
                description: >-
                  A graphical symbol or image used to represent different order
                  statuses.
                examples:
                  - sicon-shipping
              sort:
                type: number
                description: Order status sort order in a list of order statuses.
                examples:
                  - 0
              is_active:
                type: boolean
                description: "The option to indicate order status is 'Active'.\r\n"
                default: true
            x-apidog-orders:
              - id
              - name
              - slug
              - type
              - message
              - color
              - icon
              - sort
              - is_active
            x-apidog-ignore-properties: []
          nullable: true
      x-apidog-orders:
        - id
        - name
        - type
        - slug
        - message
        - color
        - icon
        - sort
        - is_active
        - original
        - parent
        - children
      required:
        - id
        - name
        - type
        - slug
        - message
        - color
        - icon
        - sort
        - is_active
        - original
        - parent
        - children
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

## apis-order-status/List-Order-Statuses-Salla-Merchant-API-Salla-Docs

# List Order Statuses

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/statuses:
    get:
      summary: List Order Statuses
      deprecated: false
      description: >-
        This endpoint allows you to fetch a list of all order statuses and
        sub-statuses.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read` - Orders Read Only

        </Accordion>
      operationId: List-Order-Statuses
      tags:
        - Default module/Merchant API/APIs/Order Status
        - Order Status
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/get_orderStatuses_response_body'
              examples:
                '1':
                  summary: Example | Custom Status Type
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 863076598
                        name: في انتظار الدفع
                        type: custom
                        slug: payment_pending
                        sort: 0
                        message: >-
                          [ {store.name} ] \n أصبحت حالة طلبك {order.id}
                          {status}
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 1473353380
                          name: بإنتظار الدفع
                      - id: 224309239
                        name: جاري مراجعة طلبك
                        type: custom
                        slug: under_review
                        sort: 1
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 566146469
                          name: بإنتظار المراجعة
                      - id: 1597755120
                        name: بنفذ طلبك
                        type: custom
                        slug: in_progress
                        sort: 2
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 1939592358
                          name: قيد التنفيذ
                      - id: 1638621685
                        name: تم التنفيذ
                        type: custom
                        slug: completed
                        sort: 3
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 1298199463
                          name: تم التنفيذ
                      - id: 1422535667
                        name: جاري التوصيل
                        type: custom
                        slug: delivering
                        sort: 4
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent:
                          id: 1638621685
                          name: تم التنفيذ
                        original:
                          id: 349994915
                          name: جاري التوصيل
                      - id: 647449340
                        name: تم التوصيل
                        type: custom
                        slug: delivered
                        sort: 5
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent:
                          id: 1638621685
                          name: تم التنفيذ
                        original:
                          id: 1723506348
                          name: تم التوصيل
                      - id: 1887201789
                        name: تم الشحن
                        type: custom
                        slug: shipped
                        sort: 6
                        message: ''
                        icon: sicon-trash
                        is_active: false
                        parent:
                          id: 1638621685
                          name: تم التنفيذ
                        original:
                          id: 814202285
                          name: تم الشحن
                      - id: 687926769
                        name: ملغي
                        type: custom
                        slug: canceled
                        sort: 7
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 525144736
                          name: ملغي
                      - id: 2062355698
                        name: مسترجع
                        type: custom
                        slug: restored
                        sort: 8
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 989286562
                          name: مسترجع
                      - id: 1113229566
                        name: قيد الإسترجاع
                        type: custom
                        slug: restoring
                        sort: 9
                        message: ''
                        icon: sicon-trash
                        is_active: true
                        parent: {}
                        original:
                          id: 1548352431
                          name: قيد الإسترجاع
                '3':
                  summary: Example | Original Status Type
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 1473353380
                        name: بإنتظار الدفع
                        type: original
                        slug: payment_pending
                        original: {}
                        parent: {}
                      - id: 566146469
                        name: بإنتظار المراجعة
                        type: original
                        slug: under_review
                        original: {}
                        parent: {}
                      - id: 1939592358
                        name: قيد التنفيذ
                        type: original
                        slug: in_progress
                        original: {}
                        parent: {}
                      - id: 1298199463
                        name: تم التنفيذ
                        type: original
                        slug: completed
                        original: {}
                        parent: {}
                      - id: 349994915
                        name: جاري التوصيل
                        type: original
                        slug: delivering
                        original: {}
                        parent: {}
                      - id: 1723506348
                        name: تم التوصيل
                        type: original
                        slug: delivered
                        original: {}
                        parent: {}
                      - id: 814202285
                        name: تم الشحن
                        type: original
                        slug: shipped
                        original: {}
                        parent: {}
                      - id: 525144736
                        name: ملغي
                        type: original
                        slug: canceled
                        original: {}
                        parent: {}
                      - id: 989286562
                        name: مسترجع
                        type: original
                        slug: restored
                        original: {}
                        parent: {}
                      - id: 1548352431
                        name: قيد الإسترجاع
                        type: original
                        slug: restoring
                        original: {}
                        parent: {}
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
                    orders.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: listStatuses
      x-salla-php-return-type: ListOrderStatuses
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394150-run
components:
  schemas:
    get_orderStatuses_response_body:
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
            id: imhtproefjl6n
          items:
            $ref: '#/components/schemas/ListOrderStatuses'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ListOrderStatuses:
      type: object
      title: ListOrderStatuses
      properties:
        id:
          type: number
          description: >-
            A unique identifier assigned to a specific order. Order status list
            can be found [here](https://docs.salla.dev/api-5394150).
          examples:
            - 863076598
        name:
          type: string
          description: >-
            Descriptive name or label associated with the current status of an
            order. [🌐Support multi-language](doc-421122)
          examples:
            - في انتظار الدفع
        type:
          type: string
          description: The category of a specific order, indicating its purpose or nature.
          enum:
            - original
            - custom
          examples:
            - custom
          x-apidog-enum:
            - value: original
              name: ''
              description: Original order statuses by Salla.
            - value: custom
              name: ''
              description: Custom order statuses, created by the Merchant
        slug:
          type: string
          description: >-
            A unique string or identifier used to represent and access a
            specific order .
          examples:
            - payment_pending
          enum:
            - payment_pending
            - waiting_for_payment_confirmation
            - payment_failed
            - waiting to receive it
            - in_progress
            - under_review
            - completed
            - delivering
            - delivered
            - shipped
            - canceled
            - restored
            - restoring
          x-apidog-enum:
            - value: payment_pending
              name: ''
              description: When the order is payment pending from the Merchant
            - value: waiting_for_payment_confirmation
              name: ''
              description: ' When the order''s payment is done by the customer and the Merchant is '
            - value: payment_failed
              name: ''
              description: '  When the order''s payment is failed to reach the Merchant'
            - value: waiting to receive it
              name: ''
              description: ''
            - value: in_progress
              name: ''
              description: 'When the order is in progress '
            - value: under_review
              name: ''
              description: When the order is  under review by the store owner
            - value: completed
              name: ''
              description: >-
                When the order is completed; aka paid and delivered to the
                customer
            - value: delivering
              name: ''
              description: When the order is being delivered at the moment to the customer
            - value: delivered
              name: ''
              description: When the order has been delievred to the customer
            - value: shipped
              name: ''
              description: When the order is shipped, on its way to the customer
            - value: canceled
              name: ''
              description: 'When the order is  cancelled '
            - value: restored
              name: ''
              description: When the order is restored to the store
            - value: restoring
              name: ''
              description: When the order is being restored to the store at the moment
        sort:
          type: integer
          description: >-
            The specific integer sequence assigned to each order status in a
            list or database, determining the order in which they are displayed
            or sorted. 
        message:
          type: string
          description: Status customized message
        icon:
          type: string
          description: Status Icon.
        is_active:
          type: boolean
          description: Whether or not the status is active
        parent:
          type: object
          properties:
            id:
              type: number
              description: The identifier or reference to the parent status of an order.
              examples:
                - 1638621685
            name:
              type: string
              description: the name or label associated with the parent status.
              examples:
                - تم التنفيذ
          x-apidog-orders:
            - id
            - name
          description: Parent of the order.
          required:
            - id
            - name
          x-apidog-ignore-properties: []
          nullable: true
        original:
          type: object
          properties:
            id:
              type: number
              description: >-
                The initial or original identifier assigned to the status of an
                order.
              examples:
                - 349994915
            name:
              type: string
              description: >-
                The unique identifier assigned to the initial or original status
                of an order.
              examples:
                - جاري التوصيل
          x-apidog-orders:
            - id
            - name
          description: Original order.
          required:
            - id
            - name
          x-apidog-ignore-properties: []
          nullable: true
      x-apidog-orders:
        - id
        - name
        - type
        - slug
        - sort
        - message
        - icon
        - is_active
        - parent
        - original
      required:
        - id
        - name
        - type
        - slug
        - sort
        - message
        - icon
        - is_active
        - parent
        - original
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

## apis-order-status/Order-Status-Details-Salla-Merchant-API-Salla-Docs

# Order Status Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/statuses/{status_id}:
    get:
      summary: Order Status Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch details about specific order status by
        passing the `status_id` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read` - Orders Read Only

        </Accordion>
      operationId: get-orders-statuses-status_id
      tags:
        - Default module/Merchant API/APIs/Order Status
        - Order Status
      parameters:
        - name: status_id
          in: path
          description: >-
            Unique identification number assigned to a status. List of Status
            IDs can be found [here](https://docs.salla.dev/api-5394150)
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
                $ref: '#/components/schemas/orderStatuses_response_body'
              examples:
                '1':
                  summary: Example | Custom Status Type
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1638621685
                      name: تم التنفيذ
                      type: custom
                      slug: completed
                      message: '[ {store.name} ] \n أصبحت حالة طلبك {order.id} {status}'
                      color: '#58C9B9'
                      icon: sicon-gold-badge
                      sort: 0
                      is_active: true
                      original:
                        id: 1298199463
                        name: تم التنفيذ
                      parent: {}
                      children:
                        - id: 1422535667
                          name: جاري التوصيل
                          slug: delivering
                          type: custom
                          message: >-
                            [ {store.name} ] \n أصبحت حالة طلبك {order.id}
                            {status}
                          color: '#58C9B9'
                          icon: sicon-shipping
                          sort: 0
                          is_active: true
                        - id: 647449340
                          name: تم التوصيل
                          slug: delivered
                          type: custom
                          message: >-
                            [ {store.name} ] \n أصبحت حالة طلبك {order.id}
                            {status}
                          color: '#58C9B9'
                          icon: sicon-party-horn
                          sort: 1
                          is_active: true
                        - id: 1887201789
                          name: تم الشحن
                          slug: shipped
                          type: custom
                          message: >-
                            [ {store.name} ] \n أصبحت حالة طلبك {order.id}
                            {status}
                          color: '#58C9B9'
                          icon: sicon-shipping-fast
                          sort: 2
                          is_active: true
                '3':
                  summary: Example | Original Status Type
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1473353380
                      name: بإنتظار الدفع
                      type: original
                      slug: payment_pending
                      message: '[ {store.name} ] \n أصبحت حالة طلبك {order.id} {status}'
                      color: '#f55157'
                      icon: uea77
                      sort: 1
                      is_active: true
                      original: {}
                      parent: {}
                      children: []
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
                    orders.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: retrieveStatuses
      x-salla-php-return-type: OrderStatuses
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394151-run
components:
  schemas:
    orderStatuses_response_body:
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
          $ref: '#/components/schemas/OrderStatuses%20'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    'OrderStatuses ':
      title: OrderStatuses
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific status assigned to an
            order.

            List of order statuses can be found
            [here](https://docs.salla.dev/api-5394150)
          examples:
            - 863076598
        name:
          type: string
          description: >-
            A label or designation given to a specific status assigned to an
            order. [🌐Support multi-language](doc-421122)
          examples:
            - في انتظار الدفع
        type:
          type: string
          description: The categorization or classification of an order.
          enum:
            - original
            - custom
          examples:
            - custom
          x-apidog-enum:
            - value: original
              name: ''
              description: Original order status by Salla.
            - value: custom
              name: ''
              description: Custom order status, made by the Merchant.
        slug:
          type: string
          description: >-
            A user-friendly and URL-friendly text string associated with a
            specific order. __Note__ the parent slug is inherited.
          examples:
            - payment_pending
        message:
          type: string
          description: >-
            A remark that provides information about the current status or
            condition of an order. [🌐Support multi-language](doc-421122)
          examples:
            - '[ {store.name} ] \\n أصبحت حالة طلبك {order.id} {status}'
        color:
          type: string
          description: >-
            A specific color code or indicator assigned to different order
            statuses.
          examples:
            - '#58C9B9'
        icon:
          type: string
          description: >-
            Graphical symbol or image used to represent different order
            statuses.
          examples:
            - sicon-gold-badge
        sort:
          type: number
          description: >-
            The specific numerical or alphanumeric sequence assigned to each
            order status in a list or database.
          examples:
            - 0
        is_active:
          type: boolean
          description: The option to indicate that the order status is active.
          default: true
        original:
          type: object
          properties:
            id:
              type: number
              description: >-
                A unique identifier associated with the initial or default
                status of an order.
              examples:
                - 349994915
            name:
              type: string
              description: >-
                The label assigned to the status of an order when it was first
                placed.
              examples:
                - جاري التوصيل
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          x-apidog-ignore-properties: []
          nullable: true
        parent:
          type: object
          properties:
            id:
              type: number
              description: A unique identifier associated to the parent order.
              examples:
                - 1638621685
            name:
              type: string
              description: The name or label assigned to the parent order.
              examples:
                - تم التنفيذ
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          x-apidog-ignore-properties: []
          nullable: true
        children:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier associated with a specific status assigned
                  to an order.
                examples:
                  - 863076598
              name:
                type: string
                description: The name or label assigned to the order.
                examples:
                  - في انتظار الدفع
              slug:
                type: string
                description: >-
                  A user-friendly and URL-friendly text string associated with a
                  specific order.
                examples:
                  - payment_pending
              type:
                type: string
                description: The classification or categorization of an order.
                enum:
                  - original
                  - custom
                examples:
                  - custom
                x-apidog-enum:
                  - value: original
                    name: ''
                    description: Original order status.
                  - value: custom
                    name: ''
                    description: Custom order status.
              message:
                type: string
                description: >-
                  A notification that provides information about the current
                  status of the order.
                examples:
                  - '[ {store.name} ] \\n أصبحت حالة طلبك {order.id} {status}'
              color:
                type: string
                description: >-
                  A specific color code or indicator assigned to different order
                  statuses.
                examples:
                  - '#58C9B9'
              icon:
                type: string
                description: >-
                  A graphical symbol or image used to represent different order
                  statuses.
                examples:
                  - sicon-shipping
              sort:
                type: number
                description: Order status sort order in a list of order statuses.
                examples:
                  - 0
              is_active:
                type: boolean
                description: "The option to indicate order status is 'Active'.\r\n"
                default: true
            x-apidog-orders:
              - id
              - name
              - slug
              - type
              - message
              - color
              - icon
              - sort
              - is_active
            x-apidog-ignore-properties: []
          nullable: true
      x-apidog-orders:
        - id
        - name
        - type
        - slug
        - message
        - color
        - icon
        - sort
        - is_active
        - original
        - parent
        - children
      required:
        - id
        - name
        - type
        - slug
        - message
        - color
        - icon
        - sort
        - is_active
        - original
        - parent
        - children
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

## apis-order-status/Sort-Orders-Statuses-Salla-Merchant-API-Salla-Docs

# Sort Orders Statuses

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/statuses/sort:
    post:
      summary: Sort Orders Statuses
      deprecated: false
      description: >-
        This endpoint allows you to sort the orders statuses on the Merchant
        dashboard.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-statuses-sort
      tags:
        - Default module/Merchant API/APIs/Order Status
        - Order Status
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/sortOrderStatus_request_body'
            example:
              - status_id: 12345
                sort: 2
              - status_id: 654321
                sort: 1
              - status_id: 98765
                sort: 4
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 200
                success: true
                data:
                  message: The entities has been updated successfully
                  code: 200
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
                    0.status_id:
                      - عذراً، لم يتم العثور على الحالات
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5607770-run
components:
  schemas:
    sortOrderStatus_request_body:
      type: array
      items:
        type: object
        properties:
          status_id:
            type: integer
            description: >-
              Order Status ID, list of Status ID's can be found
              [here](https://docs.salla.dev/api-5394150)
          sort:
            type: integer
            description: The sorting position on the Merchant dashboard.
        x-apidog-orders:
          - status_id
          - sort
        required:
          - status_id
          - sort
        x-apidog-ignore-properties: []
      x-apidog-folder: ''
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

