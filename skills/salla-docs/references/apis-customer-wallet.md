# Apis Customer Wallet

## Table of Contents

- [apis-customer-wallet/Deposit-to-Wallet](#apis-customer-wallet-deposit-to-wallet)
- [apis-customer-wallet/Withdraw-from-Wallet](#apis-customer-wallet-withdraw-from-wallet)
- [apis-loyalty-points/Customer-Loyalty-Points-Salla-Merchant-API-Salla-Docs](#apis-loyalty-points-customer-loyalty-points-salla-merchant-api-salla-docs)
- [apis-loyalty-points/Update-Customer-Loyalty-Salla-Merchant-API-Salla-Docs](#apis-loyalty-points-update-customer-loyalty-salla-merchant-api-salla-docs)

---

## apis-customer-wallet/Deposit-to-Wallet

# Deposit to Wallet

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/wallets/deposit:
    post:
      summary: Deposit to Wallet
      deprecated: false
      description: >-
        This endpoint allows you to deposit a specific amount in the customer
        wallet.


        :::warning[]

        This endpoint is accessible only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customer-wallets.read_write`- Customer Wallet Read & Write

        </Accordion>


        :::warning[]

        This endpoint will work only if the store has the [Customer
        Wallet](https://apps.salla.sa/en/app/13657422) application installed.

        :::
      operationId: customer-wallet
      tags:
        - Default module/Merchant API/APIs/Customer Wallet
        - Customer Wallet
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/customer_wallet_body_request'
            example:
              customer_id: 1994632444
              amount: 22
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Wallet_response_body'
              example:
                status: 200
                success: true
                data:
                  status: confirmed
                  amount: 12
                  date:
                    date: '2025-11-27 13:45:54.321280'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  wallet:
                    id: 1337429619
                    balance: 468
                    created_at: '2025-11-26 10:28:13'
          headers: {}
          x-apidog-name: Created Successfully
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
                    customer-wallets.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '403':
          description: ''
          content:
            application/json:
              schema:
                title: ''
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
                  error:
                    type: object
                    properties:
                      code:
                        type: integer
                        description: >-
                          Not Found Response error code, a numeric or
                          alphanumeric unique identifier used to represent the
                          error.
                      message:
                        type: string
                        description: >-
                          A message or data structure that is generated or
                          returned when the response is not found or explain the
                          error.
                    required:
                      - code
                      - message
                    x-apidog-orders:
                      - code
                      - message
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - 01KBYYEASNRJA92GHH5XE371TZ
                required:
                  - status
                  - success
                  - error
                x-apidog-refs:
                  01KBYYEASNRJA92GHH5XE371TZ:
                    $ref: '#/components/schemas/error_forbidden_403'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: Application does not have permission to customer wallet
          headers: {}
          x-apidog-name: Forbidden
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
      x-salla-php-method-name: create
      x-salla-php-return-type: Customer
      x-apidog-folder: Default module/Merchant API/APIs/Customer Wallet
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-24839928-run
components:
  schemas:
    customer_wallet_body_request:
      type: object
      properties:
        customer_id:
          type: number
          description: >-
            A unique identifier assigned to a customer. Get a list of customer
            IDs from [here](https://docs.salla.dev/5394121e0)
          examples:
            - 1994632444
        amount:
          type: number
          description: Amount that will be added to the customer wallet.
      x-apidog-refs: {}
      x-apidog-orders:
        - customer_id
        - amount
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Wallet_response_body:
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
          description: >
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/Wallet'
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
    Wallet:
      type: object
      properties:
        status:
          type: string
          description: Status of the deposite/withdraw operation.
          examples:
            - confirmed
        amount:
          type: number
          description: The amount added/deducted from the customer wallet.
        date:
          type: object
          properties:
            date:
              type: string
              description: >-
                A specific point in time, typically expressed in terms of a
                calendar system, including the day, month, year, hour, minutes,
                seconds and nano seconds.
              examples:
                - '2025-11-14 14:28:03.000000'
            timezone_type:
              type: integer
              description: Timezone type of the date, for Middel East = 3
            timezone:
              type: string
              description: |
                Timezone value "Asia/Riyadh"
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        wallet:
          type: object
          properties:
            id:
              type: integer
              description: A unique identifier for the customer wallet.
            balance:
              type: number
              description: The balance available in the customer wallet.
            created_at:
              type: string
              description: The date when the customer wallet was created.
          required:
            - id
            - balance
            - created_at
          x-apidog-orders:
            - id
            - balance
            - created_at
          x-apidog-ignore-properties: []
      required:
        - status
        - amount
        - date
        - wallet
      x-apidog-orders:
        - status
        - amount
        - date
        - wallet
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
    error_forbidden_403:
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

## apis-customer-wallet/Withdraw-from-Wallet

# Withdraw from Wallet

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/wallets/withdraw:
    post:
      summary: Withdraw from Wallet
      deprecated: false
      description: >-
        This endpoint allows you to withdraw a specific amount from the customer
        wallet.


        :::warning[]

        This endpoint is accessible only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customer-wallets.read_write`- Customer Wallet Read & Write

        </Accordion>


        :::warning[]

        This endpoint will work only if the store has the [Customer
        Wallet](https://apps.salla.sa/en/app/13657422) application installed.

        :::
      operationId: customer-wallet
      tags:
        - Default module/Merchant API/APIs/Customer Wallet
        - Customer Wallet
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/customer_wallet_body_request'
            example:
              customer_id: 1994632444
              amount: 22
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Wallet_response_body'
              example:
                status: 200
                success: true
                data:
                  status: confirmed
                  amount_float: -12
                  date:
                    date: '2025-11-27 13:45:54.321280'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  wallet:
                    id: 1337429619
                    balance: 468
                    created_at: '2025-11-26 10:28:13'
          headers: {}
          x-apidog-name: Created Successfully
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
                    customer-wallets.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '403':
          description: ''
          content:
            application/json:
              schema:
                title: ''
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
                  error:
                    type: object
                    properties:
                      code:
                        type: integer
                        description: >-
                          Not Found Response error code, a numeric or
                          alphanumeric unique identifier used to represent the
                          error.
                      message:
                        type: string
                        description: >-
                          A message or data structure that is generated or
                          returned when the response is not found or explain the
                          error.
                    required:
                      - code
                      - message
                    x-apidog-orders:
                      - code
                      - message
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - 01KBYYHYYRW1A5Z3VYP5KYNV0Y
                required:
                  - status
                  - success
                  - error
                x-apidog-refs:
                  01KBYYHYYRW1A5Z3VYP5KYNV0Y:
                    $ref: '#/components/schemas/error_forbidden_403'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: Application does not have permission to customer wallet
          headers: {}
          x-apidog-name: Forbidden
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
      x-salla-php-method-name: create
      x-salla-php-return-type: Customer
      x-apidog-folder: Default module/Merchant API/APIs/Customer Wallet
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-24850516-run
components:
  schemas:
    customer_wallet_body_request:
      type: object
      properties:
        customer_id:
          type: number
          description: >-
            A unique identifier assigned to a customer. Get a list of customer
            IDs from [here](https://docs.salla.dev/5394121e0)
          examples:
            - 1994632444
        amount:
          type: number
          description: Amount that will be added to the customer wallet.
      x-apidog-refs: {}
      x-apidog-orders:
        - customer_id
        - amount
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Wallet_response_body:
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
          description: >
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/Wallet'
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
    Wallet:
      type: object
      properties:
        status:
          type: string
          description: Status of the deposite/withdraw operation.
          examples:
            - confirmed
        amount:
          type: number
          description: The amount added/deducted from the customer wallet.
        date:
          type: object
          properties:
            date:
              type: string
              description: >-
                A specific point in time, typically expressed in terms of a
                calendar system, including the day, month, year, hour, minutes,
                seconds and nano seconds.
              examples:
                - '2025-11-14 14:28:03.000000'
            timezone_type:
              type: integer
              description: Timezone type of the date, for Middel East = 3
            timezone:
              type: string
              description: |
                Timezone value "Asia/Riyadh"
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        wallet:
          type: object
          properties:
            id:
              type: integer
              description: A unique identifier for the customer wallet.
            balance:
              type: number
              description: The balance available in the customer wallet.
            created_at:
              type: string
              description: The date when the customer wallet was created.
          required:
            - id
            - balance
            - created_at
          x-apidog-orders:
            - id
            - balance
            - created_at
          x-apidog-ignore-properties: []
      required:
        - status
        - amount
        - date
        - wallet
      x-apidog-orders:
        - status
        - amount
        - date
        - wallet
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
    error_forbidden_403:
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

## apis-loyalty-points/Customer-Loyalty-Points-Salla-Merchant-API-Salla-Docs

# Customer Loyalty Points

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/loyalty/points:
    get:
      summary: Customer Loyalty Points
      deprecated: false
      description: >-
        This endpoint allows you to fetch the history of a customer's loylty
        points that is assocaited with the store.



        :::info

        This endopint will work only if the store has [Customer
        Loyalty](https://apps.salla.sa/en/app/1178176509) application installed.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read` - Customers Read Only

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Loyalty Points
        - Loyality Points
      parameters:
        - name: customer_id
          in: query
          description: >-
            Unique identification number assigned to the Customer. List of
            Customers IDs can be found
            [here](https://docs.salla.dev/api-5394121).
          required: true
          example: '1257881496'
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/loyality_response_body'
              example:
                status: 200
                success: true
                data:
                  - name: مخصصة
                    points: 900
                    used_points: 0
                    status: مؤكدة
                    created_at:
                      date: '2024-12-17 17:42:14.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    expiry_date: '2029-02-17 17:42:14'
                    order_id: 98787845454
                    used_at: {}
                    notes: reason text
                    reference_id: 3215487
                  - name: مخصصة
                    points: 900
                    used_points: 0
                    status: مؤكدة
                    created_at:
                      date: '2024-12-17 17:15:47.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    expiry_date: '2029-02-17 17:15:47'
                    order_id: 123432
                    used_at: '2025-12-31 23:59:59'
                    notes: sample note
                    reference_id: 1234321
                pagination:
                  count: 30
                  total: 39
                  perPage: 30
                  currentPage: 1
                  totalPages: 2
                  links:
                    next: >-
                      http://api.salla.dev/admin/v2/customers/loyalty/points?customer_id=1227534533&page=2
          headers: {}
          x-apidog-name: OK
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
                  code: Invalid-token
                  message: please provide a valid API Key
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
                    customer_id:
                      - حقل customer id مطلوب.
          headers: {}
          x-apidog-name: Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Loyalty Points
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-12250577-run
components:
  schemas:
    loyality_response_body:
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
            $ref: '#/components/schemas/LoyaltyPoints'
        pagination:
          $ref: '#/components/schemas/Pagination'
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      required:
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
    LoyaltyPoints:
      type: object
      properties:
        name:
          type: string
          description: Description or a reason of the loyalty points increase or decrese
        points:
          type: integer
          description: Amount of loyalty points for the customer
        used_points:
          type: integer
          description: Amount of used points for the customer
        status:
          type: string
          description: Status of the loyalty points
        created_at:
          $ref: '#/components/schemas/Date'
        expiry_date:
          type: string
          description: Date and time of the expirey date
          title: '2029-02-16 14:59:03'
        order_id:
          type: string
          description: >-
            Order unique identifier. Used in case the loyalty points have been
            earned from an order.
          nullable: true
        reference_id:
          type: string
          description: >-
            Order reference unique identifier. Used in case the loyalty points
            have been earned from an order.
          nullable: true
      x-apidog-orders:
        - name
        - points
        - used_points
        - status
        - created_at
        - expiry_date
        - order_id
        - reference_id
      required:
        - name
        - points
        - used_points
        - status
        - created_at
        - expiry_date
        - order_id
        - reference_id
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

## apis-loyalty-points/Update-Customer-Loyalty-Salla-Merchant-API-Salla-Docs

# Update Customer Loyalty Points

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/loyalty/points:
    post:
      summary: Update Customer Loyalty Points
      deprecated: false
      description: >-
        This endpoint enables you to add loyalty points to customers, helping to
        enhance engagement and reward customer loyalty.


        :::info

        This endpoint will work only if the store has [Customer
        Loyalty](https://apps.salla.sa/en/app/1178176509) application installed.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write` - Customers Read & write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Loyalty Points
        - Loyality Points
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                points:
                  type: number
                  description: Loyalty points, required unless rest_point is set to true
                  title: ''
                  minimum: 1
                  maximum: 999999
                  examples:
                    - 100
                reset_points:
                  type: boolean
                  description: Boolean value to reset loyalty points
                type:
                  type: string
                  enum:
                    - plus
                    - minus
                  x-apidog-enum:
                    - name: ''
                      value: plus
                      description: ''
                    - name: ''
                      value: minus
                      description: ''
                  description: >-
                    The type of increasing points or decreasing points "plus" or
                    "minus"
                reason:
                  type: string
                  description: Text for showing the reason for the update
                channel_send:
                  type: array
                  items:
                    type: string
                    enum:
                      - email
                      - sms
                      - mobile
                    x-apidog-enum:
                      - value: email
                        name: ''
                        description: ''
                      - value: sms
                        name: ''
                        description: ''
                      - value: mobile
                        name: ''
                        description: ''
                  description: 'Select which channel to send '
                customers:
                  type: array
                  items:
                    type: number
                    description: >-
                      List of customers to increase or decrease the loyalty
                      points
                  description: Customers list that will receive loyalty points
                select_all:
                  type: boolean
                  description: Selecting all customers
              x-apidog-orders:
                - 01JFAHSWDZYX06SGCA8QMCX6BF
              required:
                - points
                - type
                - reason
                - channel_send
                - customers
              x-apidog-refs:
                01JFAHSWDZYX06SGCA8QMCX6BF:
                  $ref: '#/components/schemas/add_loyalty_points_request'
              x-apidog-ignore-properties:
                - points
                - reset_points
                - type
                - reason
                - channel_send
                - customers
                - select_all
            example:
              points: 900
              reset_point: false
              type: plus
              reason: Valid reason text
              channel_send:
                - email
                - sms
              customers:
                - 748394059
                - 873874834
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
                      message:
                        type: string
                        description: Message indicator of response status
                    x-apidog-orders:
                      - message
                    required:
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
                status: 201
                success: true
                data:
                  code: 201
                  message: تم تحديث نقاط الولاء للعملاء بنجاح
          headers: {}
          x-apidog-name: Created
        '400':
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
                      message:
                        type: string
                        description: Message indicator of response status
                    x-apidog-orders:
                      - message
                    required:
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
                status: 400
                success: false
                error:
                  message: حدث خطأ أثناء تحديث نقاط الولاء للعملاء
          headers: {}
          x-apidog-name: Bad Request
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
                    customers.read_write
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
                    customers:
                      - حقل customers غير صالح
          headers: {}
          x-apidog-name: Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Loyalty Points
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-12250579-run
components:
  schemas:
    add_loyalty_points_request:
      type: object
      properties:
        points:
          type: number
          description: Loyalty points, required unless rest_point is set to true
          title: ''
          minimum: 1
          maximum: 999999
          examples:
            - 100
        reset_points:
          type: boolean
          description: Boolean value to reset loyalty points
        type:
          type: string
          enum:
            - plus
            - minus
          x-apidog-enum:
            - name: ''
              value: plus
              description: ''
            - name: ''
              value: minus
              description: ''
          description: The type of increasing points or decreasing points "plus" or "minus"
        reason:
          type: string
          description: Text for showing the reason for the update
        channel_send:
          type: array
          items:
            type: string
            enum:
              - email
              - sms
              - mobile
            x-apidog-enum:
              - value: email
                name: ''
                description: ''
              - value: sms
                name: ''
                description: ''
              - value: mobile
                name: ''
                description: ''
          description: 'Select which channel to send '
        customers:
          type: array
          items:
            type: number
            description: List of customers to increase or decrease the loyalty points
          description: Customers list that will receive loyalty points
        select_all:
          type: boolean
          description: Selecting all customers
      x-apidog-orders:
        - points
        - reset_points
        - type
        - reason
        - channel_send
        - customers
        - select_all
      required:
        - points
        - type
        - reason
        - channel_send
        - customers
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

