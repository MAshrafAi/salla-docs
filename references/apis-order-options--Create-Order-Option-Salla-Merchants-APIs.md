# Apis Order Options  Create Order Option Salla Merchants Apis

## Table of Contents

- [apis-order-options/Create-Order-Option-Salla-Merchants-APIs](#apis-order-options-create-order-option-salla-merchants-apis)
- [apis-order-options/Delete-Order-Option-Salla-Merchant-API-Salla-Docs](#apis-order-options-delete-order-option-salla-merchant-api-salla-docs)
- [apis-order-options/List-Order-Options-Salla-Merchant-API-Salla-Docs](#apis-order-options-list-order-options-salla-merchant-api-salla-docs)

---

## apis-order-options/Create-Order-Option-Salla-Merchants-APIs

# Create Order Option

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/options:
    post:
      summary: Create Order Option
      deprecated: false
      description: >-
        This endpoint allows you to create an order option associated with an
        order. 

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: create-order-option
      tags:
        - Default module/Merchant API/APIs/Order Options
        - Order Options
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              description: >-
                Dynamic cart-level options that allow users to make selections
                during checkout
              $ref: '#/components/schemas/orderOptions_request_body'
            example:
              name: Order Option Name
              description: Order Option Description
              is_required: true
              type: text
              length: 80|200
              is_multi_choice: false
              selected_products: true
              categories:
                - 212
                - 223
                - 224
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/orderOptionsDetails_response_body'
              examples:
                '1':
                  summary: Text Option
                  value:
                    status: 200
                    success: true
                    data:
                      id: 123456789
                      name: Order Option Name
                      description: Order Option Description
                      is_required: true
                      type: text
                      status: true
                      length: 80|200
                      is_multi_choice: false
                      selected_products: true
                      categories:
                        - id: 123456788
                          name: category name
                        - id: 123456789
                          name: another category name
                      price: 0
                      currency: SAR
                '2':
                  summary: Number Option
                  value:
                    status: 200
                    success: true
                    data:
                      id: 123456789
                      name: Order Option Name
                      description: Order Option Description
                      is_required: true
                      type: number
                      status: true
                      length: '80'
                      is_multi_choice: false
                      selected_products: true
                      categories:
                        - id: 123456788
                          name: category name
                        - id: 123456789
                          name: another category name
                      price: 0
                      currency: SAR
                '3':
                  summary: Checkbox Option
                  value:
                    status: 200
                    success: true
                    data:
                      id: 123456789
                      name: Order Option Name
                      description: Order Option Description
                      is_required: true
                      type: checkbox
                      status: true
                      length: '80'
                      is_multi_choice: false
                      selected_products: true
                      categories:
                        - id: 123456788
                          name: category name
                        - id: 123456789
                          name: another category name
                      price: 0
                      currency: SAR
                      options:
                        - name: option name
                          price: 10
                          cost: 5
                          weight: 1
                          is_default: true
                        - name: another option name
                          price: null
                          cost: null
                          weight: null
                '4':
                  summary: Days Option
                  value:
                    status: 200
                    success: true
                    data:
                      id: 123456787
                      name: date order option
                      reference_id: 123456786
                      description: some description
                      is_required: false
                      type: date
                      status: true
                      length: '80'
                      is_multi_choice: false
                      selected_products: false
                      categories: []
                      price: 100
                      currency: SAR
                      booking_details:
                        id: 123456788
                        type: date
                        location: here
                        sessions_count: 1
                        time_strict: 1
                        time_strict_type: days
                        maximum_quantity_per_order: 1
                        availabilities:
                          - id: 123456789
                            day: monday
                            is_available: true
                            times:
                              - from: null
                                to: null
                          - id: 123456799
                            day: tuesday
                            is_available: true
                            times:
                              - from: null
                                to: null
                        overrides:
                          - date: '2025-01-30'
                          - date: '2025-01-31'
                '5':
                  summary: Days & Times Option
                  value:
                    status: 200
                    success: true
                    data:
                      id: 123456787
                      name: date order option
                      reference_id: 123456786
                      description: some description
                      is_required: false
                      type: date
                      status: true
                      length: '80'
                      is_multi_choice: false
                      selected_products: false
                      categories: []
                      price: 100
                      currency: SAR
                      booking_details:
                        id: 123456788
                        type: date_time
                        location: here
                        sessions_count: 1
                        time_strict: 1
                        time_strict_type: days
                        maximum_quantity_per_order: 1
                        availabilities:
                          - id: 123456789
                            day: monday
                            is_available: true
                            times:
                              - from: '10:00'
                                to: '16:00'
                          - id: 123456799
                            day: tuesday
                            is_available: true
                            times:
                              - from: '10:00'
                                to: '12:00'
                              - from: '14:00'
                                to: '16:00'
                        overrides:
                          - date: '2025-01-30'
                          - date: '2025-01-31'
                        session_duration: 90
                        session_gap: 10
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
          x-apidog-name: Uauthorized
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
              schema: &ref_0
                $ref: '#/components/schemas/error_validation_422'
              example:
                status: 422
                success: false
                error:
                  code: validation_failed
                  message: 'null'
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
        x-422:Max Number of Options Exceeded:
          description: ''
          content:
            application/json:
              schema: *ref_0
              example:
                status: 422
                success: false
                error:
                  code: error
                  message: لقد تخطيت الحد الاقصي لعدد خيارات الطلب
          headers: {}
          x-apidog-name: Max Number of Options Exceeded
      security:
        - bearer: []
      x-salla-php-method-name: createOrderOption
      x-salla-php-return-type: OrderOption
      x-apidog-folder: Default module/Merchant API/APIs/Order Options
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394153-run
components:
  schemas:
    orderOptions_request_body:
      type: object
      properties:
        name:
          type: string
          description: The label or textual identifier for the checkout field option
        description:
          type:
            - string
            - 'null'
          description: Additional details about this checkout field option
        is_required:
          type: string
          description: Whether this field is mandatory during checkout
        type:
          type: string
          enum:
            - text
            - number
            - checkbox
            - date
          description: The type of input field to render
          x-apidog-enum:
            - name: ''
              value: text
              description: Text input field
            - name: ''
              value: number
              description: Numeric input field
            - name: ''
              value: checkbox
              description: Checkbox selection
            - name: ''
              value: date
              description: Date picker field
        length:
          type: integer
          description: Maximum length for text/number input fields
        is_multi_choice:
          type: boolean
          description: Whether multiple selections are allowed
        selected_products:
          type: boolean
          description: Whether this option applies to specific products
        categories:
          type: array
          items:
            type: integer
            description: ID of a product category
          description: The Product Categories this option applies to
        price:
          type: number
          description: Price adjustment for this option
        options:
          type: object
          description: Configuration for option choices
          properties:
            name:
              type: string
              description: Name of the option choice
            price:
              type:
                - integer
                - 'null'
              description: Price adjustment for this option choiceThe ad
            cost:
              type:
                - integer
                - 'null'
              description: Cost associated with this option choice
            weight:
              type:
                - integer
                - 'null'
              description: Weight adjustment for this option choice
            is_default:
              type: boolean
              default: false
              description: The default choice in the cart
          x-apidog-orders:
            - name
            - price
            - cost
            - weight
            - is_default
          required:
            - name
          x-apidog-ignore-properties: []
        booking_details:
          type: object
          description: Configuration for bookable options
          properties:
            type:
              type: string
              enum:
                - date
                - date_time
              description: Type of booking date selection
              x-apidog-enum:
                - value: date
                  name: ''
                  description: Date only selection
                - value: date_time
                  name: ''
                  description: Date and time selection
            location:
              type: string
              description: Location where the booking takes place
            sessions_count:
              type: integer
              description: Number of sessions included in the booking
            time_strict:
              type: integer
              description: Time restriction value for bookings
            time_strict_type:
              type: string
              description: Type of time restriction for the booking
            maximum_quantity_per_order:
              type: integer
              description: Maximum number of bookings allowed per order
            availabilities:
              type: array
              description: Available booking slots
              items:
                type: object
                properties:
                  day:
                    type: string
                    description: Day of the week or specific date
                  is_available:
                    type: boolean
                    description: Whether bookings are available on this day
                  times:
                    type: array
                    description: Available time slots
                    items:
                      type: object
                      properties:
                        from:
                          type: string
                          description: Start time of the slot
                        to:
                          type: string
                          description: End time of the slot
                      required:
                        - from
                        - to
                      x-apidog-orders:
                        - from
                        - to
                      x-apidog-ignore-properties: []
                required:
                  - day
                  - is_available
                x-apidog-orders:
                  - day
                  - is_available
                  - times
                x-apidog-ignore-properties: []
            overrides:
              type: array
              items:
                type: object
                properties:
                  day:
                    type: string
                x-apidog-orders:
                  - day
                description: Special scheduling override rules
                required:
                  - day
                x-apidog-ignore-properties: []
              description: List of scheduling overrides
          required:
            - type
            - sessions_count
            - time_strict
            - time_strict_type
            - availabilities
          x-apidog-orders:
            - type
            - location
            - sessions_count
            - time_strict
            - time_strict_type
            - maximum_quantity_per_order
            - availabilities
            - overrides
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - name
        - description
        - is_required
        - type
        - length
        - is_multi_choice
        - selected_products
        - categories
        - price
        - options
        - booking_details
      required:
        - name
        - type
      allOf:
        - type: string
        - type: string
        - type: string
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    orderOptionsDetails_response_body:
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
          description: >
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/Order%20Options'
      x-apidog-orders:
        - status
        - success
        - data
      required:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Order Options:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier associated with the order option
        name:
          type: string
          description: Title or lable of the order option
        reference_id:
          type: integer
          description: Unique identifier associated with the refrence
        description:
          type: string
          description: Description of the order options
        status:
          type: boolean
          description: The status of the order options
        is_required:
          type: boolean
          description: 'Whether or not the order option is required '
        type:
          type: string
          description: Type of the order option
          enum:
            - date
            - checkbox
            - text
            - number
            - date_time
          x-apidog-enum:
            - value: date
              name: ''
              description: The date of the booking option
            - value: checkbox
              name: ''
              description: The selected order option type
            - value: text
              name: ''
              description: The selected description of the order option
            - value: number
              name: ''
              description: The selected order option number
            - value: date_time
              name: ''
              description: The selected order option date and time of the order option
        length:
          type: string
          description: Length of order option.
        is_multi_choice:
          type: boolean
          description: Whether or not order option is multi option.
        selected_products:
          type: boolean
          description: Whether or not order options is in the selected products.
        categories:
          type: array
          items:
            type: object
            properties:
              id:
                type: integer
                description: Category unique id number
              name:
                type: string
                description: Category lable or title
            required:
              - id
              - name
            x-apidog-orders:
              - id
              - name
            x-apidog-ignore-properties: []
          description: Order options categories
        price:
          type: integer
          description: Monetary value of the order option.
        currency:
          type: string
          description: Currency of the order option price.
        options:
          type: array
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identification number associated with the option.
              name:
                type: string
                description: Title or lable representing the option
              price:
                type: string
                description: |+
                  Price adjustment for this option choice.

              cost:
                type: string
                description: Cost associated with this option choice
              weight:
                type: string
                description: Weight adjustment for this option choice
              is_default:
                type: boolean
                description: Whether or not option is set as default
            x-apidog-orders:
              - id
              - name
              - price
              - cost
              - weight
              - is_default
            x-apidog-ignore-properties: []
          description: List of options for the order.
        booking_details:
          type: object
          properties:
            id:
              type: integer
              description: Unique identification number associated with the booking
            type:
              type: string
              enum:
                - date
                - date_time
              x-apidog-enum:
                - value: date
                  name: ''
                  description: The date of the booking option
                - value: date_time
                  name: ''
                  description: The period of time and date for the booking option
              description: Type of booking date selection
            location:
              type: string
              description: Location of the booking
            sessions_count:
              type: integer
              description: Number of sessions included in the booking
            time_strict:
              type: integer
              description: Time restriction value for bookings
            time_strict_type:
              type: string
              description: Type of time restriction for the booking
            maximum_quantity_per_order:
              type: integer
              description: |+
                Maximum number of bookings allowed per order

            availabilities:
              type: array
              items:
                type: object
                properties:
                  id:
                    type: integer
                    description: Unique identification associated with the availability
                  day:
                    type: string
                    description: Day of the week or specific date
                  is_available:
                    type: boolean
                    description: |+
                      Whether bookings are available on this day

                  times:
                    type: array
                    items:
                      type: object
                      properties:
                        from:
                          type: string
                          description: Start time of the slot
                        to:
                          type: string
                          description: End time of the slot
                      required:
                        - from
                        - to
                      x-apidog-orders:
                        - from
                        - to
                      x-apidog-ignore-properties: []
                    description: Available time slots
                required:
                  - id
                  - day
                  - is_available
                  - times
                x-apidog-orders:
                  - id
                  - day
                  - is_available
                  - times
                x-apidog-ignore-properties: []
              description: Available booking slots
            overrides:
              type: array
              items:
                type: object
                properties:
                  id:
                    type: integer
                    description: Unique identification number of the overrides
                  date:
                    type: string
                    description: |
                      The date of the overide
                x-apidog-orders:
                  - id
                  - date
                x-apidog-ignore-properties: []
              description: List of scheduling overrides
          x-apidog-orders:
            - id
            - type
            - location
            - sessions_count
            - time_strict
            - time_strict_type
            - maximum_quantity_per_order
            - availabilities
            - overrides
          description: Configuration for bookable options.
          x-apidog-ignore-properties: []
        session_duration:
          type: integer
          description: The duration the session.
        session_gap:
          type: integer
          description: The time between sessions
      x-apidog-orders:
        - id
        - name
        - reference_id
        - description
        - status
        - is_required
        - type
        - length
        - is_multi_choice
        - selected_products
        - categories
        - price
        - currency
        - options
        - booking_details
        - session_duration
        - session_gap
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

## apis-order-options/Delete-Order-Option-Salla-Merchant-API-Salla-Docs

# Delete Order Options

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/options/{id}:
    delete:
      summary: Delete Order Options
      deprecated: false
      description: >-
        This endpoint allows you to delete a particular option from a specific
        order by passing the `id` as a path parameter for the order and the
        `option_id` as a path parameter for the tag. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: delete-order-option
      tags:
        - Default module/Merchant API/APIs/Order Options
        - Order Options
      parameters:
        - name: id
          in: path
          description: Unique identification number associated with and order options
          required: true
          example: 123456787
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
                  data:
                    type: object
                    properties:
                      code:
                        type: string
                      message:
                        type: string
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
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 202
                success: true
                data:
                  code: success
                  message: تم حذف خيار الطلب بنجاح
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
      x-salla-php-method-name: deleteOrderOption
      x-apidog-folder: Default module/Merchant API/APIs/Order Options
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394155-run
components:
  schemas:
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

## apis-order-options/List-Order-Options-Salla-Merchant-API-Salla-Docs

# List Order Options

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/options:
    get:
      summary: List Order Options
      deprecated: false
      description: |-
        This endpoint allows you to list all available order options.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `orders.read` - Orders Read Only
        </Accordion>
      operationId: get-order-options
      tags:
        - Default module/Merchant API/APIs/Order Options
        - Order Options
      parameters:
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
                $ref: '#/components/schemas/orderOptions_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1209602516
                    name: Order option 1
                  - id: 2117923531
                    name: Order option 2
                  - id: 743953354
                    name: Order option 3
                pagination:
                  count: 3
                  total: 3
                  perPage: 5
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
                    orders.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: listOrderOptions
      x-salla-php-return-type: OrderOption
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Order Options
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394154-run
components:
  schemas:
    orderOptions_response_body:
      type: object
      properties:
        status:
          type: integer
          default: 200
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
                x-apidog-mock: id
                default: 802797370
                description: Order option unique identification number.
              name:
                type: string
                description: Order option lable or title.
            required:
              - id
              - name
            x-apidog-orders:
              - id
              - name
            x-apidog-ignore-properties: []
        pagination:
          $ref: '#/components/schemas/Pagination'
      required:
        - status
        - success
        - data
        - pagination
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

