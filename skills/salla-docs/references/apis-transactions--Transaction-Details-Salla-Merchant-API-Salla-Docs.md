# Apis Transactions  Transaction Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-transactions/Transaction-Details-Salla-Merchant-API-Salla-Docs](#apis-transactions-transaction-details-salla-merchant-api-salla-docs)
- [apis-transactions/Update-Transaction-Salla-Merchant-API-Salla-Docs](#apis-transactions-update-transaction-salla-merchant-api-salla-docs)

---

## apis-transactions/Transaction-Details-Salla-Merchant-API-Salla-Docs

# Transaction Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /transactions/{transaction_id}:
    get:
      summary: Transaction Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch transaction details by passing the
        `transaction_id` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `transactions.read`- Transactions Read Only

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Transactions
        - Transactions
      parameters:
        - name: transaction_id
          in: path
          description: >-
            Unique identification number assigned to the Transaction. List of
            Transaction IDs can be found
            [here](https://docs.salla.dev/api-8382471)
          required: true
          example: 293485739
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/transaction_response_body'
              examples:
                '1':
                  summary: Success (200)
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1924095294
                      customer:
                        id: 1183285131
                        email: customer@domain.com
                        mobile: '+966567382902'
                        first_name: Ahmed
                        last_name: Saleh
                      references:
                        reference_id: 40497536
                        order_id: 1505493897
                        cart_id: 1649051320
                        transaction: 849383649505
                      total:
                        amount: 129
                        currency: SAR
                      payment_method:
                        payment_provider: salla_pay
                        name: mada
                        slug: mada
                        icon: >-
                          https://cdn.assets.salla.network/prod/admin/cp/assets/images/payment_methods/4.png
                      status:
                        name: مؤكدة
                        slug: paid
                      card:
                        brand: mada
                        number: 987654xxxxxx1234
                        country: SA
                      available_actions:
                        - refund
                        - print
                      created_at:
                        date: '2024-07-02 16:56:21.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      notes: Transaction Notes
                '4':
                  summary: Not Found (404)
                  value:
                    status: 404
                    success: false
                    error:
                      code: 404
                      message: Invoice not found
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
                    transactions.read
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
                  code: 404
                  message: Invoice not found
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Transactions
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8385183-run
components:
  schemas:
    transaction_response_body:
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
          $ref: '#/components/schemas/Transaction'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Transaction:
      type: object
      properties:
        id:
          type: integer
          description: >-
            A unique alphanumeric code assigned to each individual transaction.
            List of transactions can be found
            [here](https://docs.salla.dev/api-8382471).
        customer:
          type: object
          properties:
            id:
              type: integer
              description: >-
                A unique identifier assigned to a customer by a business or
                organization. List of customers can be found
                [here](https://docs.salla.dev/api-5394121)
            email:
              type: string
              description: Customer's email address
              examples:
                - customer@email.com
            mobile:
              type: string
              description: Customer's Phone Number
              examples:
                - '+966567891234'
            first_name:
              type: string
              description: Customer's first name
              examples:
                - Ahmed
            last_name:
              type: string
              description: Customer's last name.
              examples:
                - Ali
          x-apidog-orders:
            - id
            - email
            - mobile
            - first_name
            - last_name
          required:
            - id
            - email
            - mobile
            - first_name
            - last_name
          x-apidog-ignore-properties: []
        references:
          type: object
          properties:
            reference_id:
              type: integer
              description: |
                The unique identification number assigned to the order.
              examples:
                - 205904717
            order_id:
              type: integer
              description: >-
                Order unique identifier. List of Order ID can be found
                [here](https://docs.salla.dev/api-5394146)
              examples:
                - 65239480
            cart_id:
              type: integer
              description: Cart unique identifier.
              title: ''
              examples:
                - 1431851530
            transaction:
              type: integer
              description: >-
                Transaction unique identifire. List of transactions can be found
                [here](https://docs.salla.dev/api-8382471).
              examples:
                - 347825634045
          x-apidog-orders:
            - reference_id
            - order_id
            - cart_id
            - transaction
          required:
            - reference_id
            - order_id
            - cart_id
            - transaction
          x-apidog-ignore-properties: []
        total:
          type: object
          properties:
            amount:
              type: number
              description: Total amount.
              examples:
                - 50
            currency:
              type: string
              description: Currency of the total amount.
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        payment_method:
          type: object
          properties:
            payment_provider:
              type: string
              description: |
                Payment Provider Name
              examples:
                - salla_pay
            name:
              type: string
              description: >-
                Payment method name. List of payment methods can be found
                [here](https://docs.salla.dev/api-5394164)
            slug:
              type: string
              description: Payment method short name.
            icon:
              type: string
              description: 'Icon URL '
          x-apidog-orders:
            - payment_provider
            - name
            - slug
            - icon
          required:
            - payment_provider
            - name
            - slug
            - icon
          x-apidog-ignore-properties: []
        status:
          type: object
          properties:
            name:
              type: string
              description: Transaction status display name in Arabic
              examples:
                - مؤكدة
            slug:
              type: string
              description: Transaction status slug
              enum:
                - initiated
                - pending
                - paid
                - canceled
                - refunded
                - partial_refunded
              examples:
                - paid
              x-apidog-enum:
                - name: ''
                  value: initiated
                  description: Payment is initiated.
                - name: ''
                  value: pending
                  description: Payment is pending.
                - name: ''
                  value: paid
                  description: Payment is paid.
                - name: ''
                  value: canceled
                  description: Payment is canceled.
                - name: ''
                  value: refunded
                  description: Payment is refunded.
                - name: ''
                  value: partial_refunded
                  description: Payment is partial refunded.
          x-apidog-orders:
            - name
            - slug
          required:
            - name
            - slug
          x-apidog-ignore-properties: []
        card:
          type: object
          properties:
            brand:
              type: string
              description: Card brand
              enum:
                - mada
                - visa
                - master_card
                - amex
              examples:
                - mada
              x-apidog-enum:
                - name: ''
                  value: mada
                  description: Card brand is Mada
                - name: ''
                  value: visa
                  description: Card brand is Visa
                - name: ''
                  value: master_card
                  description: Card brand is Master Card
                - name: ''
                  value: amex
                  description: Card brand is Amex
            number:
              type: string
              description: Card number
              examples:
                - 506123xxxxxx8940
            country:
              type: string
              description: Card country
          x-apidog-orders:
            - brand
            - number
            - country
          required:
            - brand
            - number
            - country
          x-apidog-ignore-properties: []
        available_actions:
          type: array
          items:
            type: string
            description: List of available actions strings
            examples:
              - print
            enum:
              - print
              - refund
            x-apidog-enum:
              - name: ''
                value: print
                description: Print the transaction.
              - name: ''
                value: refund
                description: Refund the transaction.
        created_at:
          $ref: '#/components/schemas/Date'
        notes:
          type: string
          description: Transaction notes
          examples:
            - Transaction Notes
          nullable: true
      x-apidog-orders:
        - id
        - customer
        - references
        - total
        - payment_method
        - status
        - card
        - available_actions
        - created_at
        - notes
      required:
        - id
        - customer
        - references
        - total
        - payment_method
        - status
        - card
        - available_actions
        - created_at
        - notes
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

## apis-transactions/Update-Transaction-Salla-Merchant-API-Salla-Docs

# Update Transaction

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /transactions/{transaction_id}:
    put:
      summary: Update Transaction
      deprecated: false
      description: >-
        This endpoint allows you to `refund`, `void`, or `reverse` a transaction
        by passing the `transaction_id` as a path parameter. 

        The endpoint also supports partial refunds.


        :::caution

        The store must have enough balance to process the refund amounts

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `transactions.read_write`- Transactions Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Transactions
        - Transactions
      parameters:
        - name: transaction_id
          in: path
          description: >-
            Unique identification number assigned to the Transaction. List of
            Transaction IDs can be found
            [here](https://docs.salla.dev/api-8382471)
          required: true
          example: 293485739
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                action:
                  type: string
                  enum:
                    - refund
                    - void
                    - reverse
                  examples:
                    - refund
                  description: >-
                    Action to be performed on the transaction; actions from the
                    enum values only are allowed.
                  x-apidog-mock: refund
                  x-apidog-enum:
                    - name: ''
                      value: refund
                      description: ''
                    - name: ''
                      value: void
                      description: ''
                    - name: ''
                      value: reverse
                      description: ''
                amount:
                  type: number
                  description: Transaction Amount value.
                  x-apidog-mock: '90'
                currency:
                  type: string
                  description: Transaction Amount Currency value.
                  x-apidog-mock: SAR
              x-apidog-orders:
                - 01J1YDGVTPGARY7XQF9A3HS2XD
              x-apidog-refs:
                01J1YDGVTPGARY7XQF9A3HS2XD:
                  $ref: '#/components/schemas/updateTransaction_request_body'
              x-apidog-ignore-properties:
                - action
                - amount
                - currency
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
                  message: Invoice Partially Refunded successfully
                  code: 201
          headers: {}
          x-apidog-name: Progress In-Action
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
                    transactions.read_write
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
                  code: 404
                  message: Invoice not found
          headers: {}
          x-apidog-name: Not Found
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
              examples:
                '3':
                  summary: No Funds Available
                  value:
                    status: 422
                    success: false
                    error:
                      code: 422
                      message: >-
                        لايمكن إرجاع العملية بمبلغ 900ر.س لعدم وجود رصيد كافي في
                        رصيد المدفوعات 
                '5':
                  summary: Validation Error
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        action:
                          - >-
                            The selected action is invalid. It must be one of:
                            refund, void, reverse.
                        currency:
                          - The selected currency is invalid.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Transactions
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8385232-run
components:
  schemas:
    updateTransaction_request_body:
      type: object
      properties:
        action:
          type: string
          enum:
            - refund
            - void
            - reverse
          examples:
            - refund
          description: >-
            Action to be performed on the transaction; actions from the enum
            values only are allowed.
          x-apidog-mock: refund
          x-apidog-enum:
            - name: ''
              value: refund
              description: ''
            - name: ''
              value: void
              description: ''
            - name: ''
              value: reverse
              description: ''
        amount:
          type: number
          description: Transaction Amount value.
          x-apidog-mock: '90'
        currency:
          type: string
          description: Transaction Amount Currency value.
          x-apidog-mock: SAR
      x-apidog-orders:
        - action
        - amount
        - currency
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

