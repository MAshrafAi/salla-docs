# Apis Order Status  Update Bulck Orders Statuses Salla Merchant Api Salla Docs

## Table of Contents

- [apis-order-status/Update-Bulck-Orders-Statuses-Salla-Merchant-API-Salla-Docs](#apis-order-status-update-bulck-orders-statuses-salla-merchant-api-salla-docs)
- [apis-order-status/Update-Custom-Order-Status-Salla-Merchant-API-Salla-Docs](#apis-order-status-update-custom-order-status-salla-merchant-api-salla-docs)
- [apis-order-status/Update-Order-Status-Salla-Merchant-API-Salla-Docs](#apis-order-status-update-order-status-salla-merchant-api-salla-docs)

---

## apis-order-status/Update-Bulck-Orders-Statuses-Salla-Merchant-API-Salla-Docs

# Update Bulk Orders Statuses

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/statuses/bulk:
    post:
      summary: Update Bulk Orders Statuses
      deprecated: false
      description: >-
        This endpoint allows you to update orders' statuses in bulk by uploading
        an Excel file with the `xlsx` file extension.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-statuses-bulk
      tags:
        - Default module/Merchant API/APIs/Order Status
        - Order Status
      parameters: []
      requestBody:
        content:
          multipart/form-data:
            schema:
              type: object
              properties:
                file:
                  description: >-
                    The file where the order statuses are retrieved from, to
                    update the order statuses in bulk.
                  example: Salla Order_statuses.xlsx
                  type: string
              required:
                - file
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ordersMessage_response_body'
              example:
                status: 200
                success: true
                data:
                  message: '😍 رائع! يتم حاليا تحديث حالات الطلبات '
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
          x-apidog-name: 'Unauthorised '
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
                    file:
                      - >-
                        صيغة الملف غير مدعوم!<br>في حالة كان ملف إكسل، قد يتطلب
                        أن يكون تعديله عن طريق برنامج مايكروسوفت إكسل، وليس
                        برنامج آخر.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5588886-run
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

## apis-order-status/Update-Custom-Order-Status-Salla-Merchant-API-Salla-Docs

# Update Custom Order Status

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/statuses/{status_id}:
    put:
      summary: Update Custom Order Status
      deprecated: false
      description: >-
        This endpoint allows you to update a custom order status by passing the
        `status_id` as a path parameter.


        :::tip[Note]

        Use available parameters to send as a body request.

        :::


        :::danger[Important]

        All variables in the Update Custom Order Status body request are
        optional. At least one of the variables **must** be in the body request
        payload. Otherwise, an error will be shown if you send an empty body
        request payload.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: put-orders-statuses-status
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
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/put_updateStatuses_request_body'
            example:
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
                  id: 224309239
                  name: حنراجع طلبك
                  type: custom
                  slug: under_review
                  message: حنراجع طلبك وقد تستغرق المراجعة 24 ساعة كحد أقصى
                  color: '#ED696D'
                  icon: sicon-back
                  sort: 5
                  is_active: true
                  original:
                    id: 566146469
                    name: بإنتظار المراجعة
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
                    orders.read_write
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
                    name:
                      - >-
                        حقل عنوان الحالة - اسم الحالة مطلوب إذا لم يتوفّر نص
                        الرسالة الفرعية / الفعالية.
                    message:
                      - >-
                        حقل نص الرسالة الفرعية مطلوب إذا لم يتوفّر عنوان الحالة
                        - اسم الحالة / الفعالية.
                    is_active:
                      - >-
                        حقل الفعالية مطلوب إذا لم يتوفّر نص الرسالة الفرعية /
                        عنوان الحالة - اسم الحالة.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateCustomStatus
      x-salla-php-return-type: OrderStatuses
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394152-run
components:
  schemas:
    put_updateStatuses_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            Order Status Name. List of Order Statuses can be found
            [here](https://docs.salla.dev/api-5394150). 🌐 [Support
            multi-language]([🌐Support
            multi-language](https://docs.salla.dev/doc-421122))
          examples:
            - تبقى 40 دقيقة على الدفع
        message:
          type: string
          description: >-
            Order Status Message. 🌐 [Support multi-language]([🌐Support
            multi-language](https://docs.salla.dev/doc-421122))
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
      x-apidog-orders:
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

## apis-order-status/Update-Order-Status-Salla-Merchant-API-Salla-Docs

# Update Order Status

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/{order_id}/status:
    post:
      summary: Update Order Status
      deprecated: false
      description: >-
        This endpoint allows you to update the status of a specific order by
        passing the `order_id` as a path parameter. 



        :::tip[Note]

        To update an order status, you may use one of the following:

        - `slug`: to update an order with predefined Salla statuses.

        - `status_id`: to update the Custom Order Sub-status.

        :::

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: Update-Order-Status
      tags:
        - Default module/Merchant API/APIs/Order Status
        - Order Status
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
                status_id:
                  type: number
                  description: A unique identifier associated with a specific order status.
                  examples:
                    - 1360188634
                slug:
                  type: string
                  description: >-
                    A user-friendly and URL-friendly text string associated with
                    a specific order status.
                  examples:
                    - restoring
                note:
                  type: string
                  description: >-
                    A written comment or message submitted to request
                    information or updates regarding the status of the order.
                  examples:
                    - Your request has been received
                restore_items:
                  type: boolean
                  description: >-
                    A boolean value indicating whether items should be returned
                    to inventory if the status allows restoration, which can be
                    set from store settings
                  examples:
                    - true
              x-apidog-orders:
                - status_id
                - slug
                - note
                - restore_items
              x-apidog-ignore-properties: []
            example:
              slug: restoring
              restore_items: true
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 201
                success: true
                data:
                  message: The entity has been updated successfully
                  code: 201
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
                    status_id:
                      - حقل الحالة مطلوب إذا لم يتوفّر رمز الحالة.
                    slug:
                      - حقل رمز الحالة مطلوب إذا لم يتوفّر الحالة.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateStatuses
      x-salla-php-return-type: OrderStatuses
      x-apidog-folder: Default module/Merchant API/APIs/Order Status
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394148-run
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

