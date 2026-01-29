# Apis Transactions  Available Payment Methods Salla Merchant Api Salla Docs

## Table of Contents

- [apis-payments/Available-Payment-Methods-Salla-Merchant-API-Salla-Docs](#apis-payments-available-payment-methods-salla-merchant-api-salla-docs)
- [apis-payments/List-Banks-Salla-Merchant-API-Salla-Docs](#apis-payments-list-banks-salla-merchant-api-salla-docs)
- [apis-payments/Payment-Bank-Details-Salla-Merchant-API-Salla-Docs](#apis-payments-payment-bank-details-salla-merchant-api-salla-docs)
- [apis-transactions/List-Transactions-Salla-Merchant-API-Salla-Docs](#apis-transactions-list-transactions-salla-merchant-api-salla-docs)
- [apis-transactions/Print-Transaction-Invoice-Salla-Merchant-API-Salla-Docs](#apis-transactions-print-transaction-invoice-salla-merchant-api-salla-docs)

---

## apis-payments/Available-Payment-Methods-Salla-Merchant-API-Salla-Docs

# Available Payment Methods

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /payment/methods:
    get:
      summary: Available Payment Methods
      deprecated: false
      description: |-
        This endpoint allows you to list all available payment methods.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `payments.read`- Payments Read Only
        </Accordion>
      operationId: Available-Methods
      tags:
        - Default module/Merchant API/APIs/Payments
        - Payments
      parameters:
        - name: page
          in: query
          description: The Pagination page number
          required: false
          schema:
            type: integer
        - name: status
          in: query
          description: Fetches the payment methods enabled in the store
          required: false
          schema:
            type: string
            enum:
              - enabled
            x-apidog-enum:
              - value: enabled
                name: ''
                description: ''
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/availableMethods_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    slug: credit_card
                    name: creditCard
                  - id: 1939592358
                    slug: paypal
                    name: paypal
                  - id: 1298199463
                    slug: mada
                    name: mada
                  - id: 525144736
                    slug: free
                    name: free
                  - id: 1764372897
                    slug: bank
                    name: BankTransfer
                  - id: 989286562
                    slug: cod
                    name: COD
                  - id: 349994915
                    slug: apple_pay
                    name: ApplePay
                  - id: 1723506348
                    slug: stc_pay
                    name: StcPay
                  - id: 814202285
                    slug: tamara_installment
                    name: TamaraInstallment
                  - id: 40688814
                    slug: tabby_installment
                    name: TabbyInstallment
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
                    payments.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Payment[]
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Payments
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394164-run
components:
  schemas:
    availableMethods_response_body:
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
            id: e0k759pdqsnio
          items:
            $ref: '#/components/schemas/Payment'
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
    Payment:
      description: >-
        Detailed structure of the payment model object showing its fields and
        data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: Payment
      properties:
        id:
          type: number
          description: A unique code assigned to a payment option.
        slug:
          type: string
          description: A short identifier for a payment option.
        name:
          type: string
          description: A brief label for a payment option.
      x-apidog-orders:
        - id
        - slug
        - name
      required:
        - id
        - slug
        - name
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

## apis-payments/List-Banks-Salla-Merchant-API-Salla-Docs

# List Banks

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /payment/banks:
    get:
      summary: List Banks
      deprecated: false
      description: >-
        This endpoint allows you to list all banks associated with the store to
        receive payments.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `payments.read`- Payments Read Only

        </Accordion>
      operationId: get-payment-banks
      tags:
        - Default module/Merchant API/APIs/Payments
        - Payments
      parameters:
        - name: page
          in: query
          description: The Pagination page number
          required: false
          schema:
            type: integer
        - name: status
          in: query
          description: Filter the banks list by either `active` or `inactive`
          required: false
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/banks_response_body'
          headers: {}
          x-apidog-name: Success
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Payments
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394165-run
components:
  schemas:
    banks_response_body:
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
            id: jystbkc6ry3u2
          items:
            $ref: '#/components/schemas/Banks'
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
    Banks:
      title: Banks
      x-stoplight:
        id: 8ju8zo0yzfy79
      type: object
      properties:
        id:
          type: integer
          x-stoplight:
            id: rn8skmtc8j9k3
          description: A unique alphanumeric code or identifier assigned to each bank.
        bank_name:
          type: string
          x-stoplight:
            id: eiyg5pet5eomg
          description: A pre-defined name associated with the bank.
        account_name:
          type: string
          x-stoplight:
            id: fpqf7keq1v5tf
          description: A user defined name associated with the account.
        status:
          type: string
          description: Whether or not the bank is active.
          x-stoplight:
            id: 48p5dzjsg4psp
          enum:
            - active
            - inactive
          x-apidog-enum:
            - value: active
              name: ''
              description: Bank is active
            - value: inactive
              name: ''
              description: Bank is inactive
      x-apidog-orders:
        - id
        - bank_name
        - account_name
        - status
      required:
        - id
        - bank_name
        - account_name
        - status
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

## apis-payments/Payment-Bank-Details-Salla-Merchant-API-Salla-Docs

# Payment Bank Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /payment/banks/{bank_id}:
    get:
      summary: Payment Bank Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch the details of the bank associated
        with the store to recieve payments by passing the `bank_id` as a path
        parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `payments.read`- Payments Read Only

        </Accordion>
      operationId: get-payment-banks-bank_id
      tags:
        - Default module/Merchant API/APIs/Payments
        - Payments
      parameters:
        - name: bank_id
          in: path
          description: >-
            Unique identification number assigned to the Bank. List of Bank IDs
            can be found [here](https://docs.salla.dev/api-5394165)
          required: true
          example: ''
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/bank_response_body'
          headers: {}
          x-apidog-name: Success
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
          headers: {}
          x-apidog-name: 'Unauthorized '
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Payments
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394166-run
components:
  schemas:
    bank_response_body:
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
          $ref: '#/components/schemas/Banks'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Banks:
      title: Banks
      x-stoplight:
        id: 8ju8zo0yzfy79
      type: object
      properties:
        id:
          type: integer
          x-stoplight:
            id: rn8skmtc8j9k3
          description: A unique alphanumeric code or identifier assigned to each bank.
        bank_name:
          type: string
          x-stoplight:
            id: eiyg5pet5eomg
          description: A pre-defined name associated with the bank.
        account_name:
          type: string
          x-stoplight:
            id: fpqf7keq1v5tf
          description: A user defined name associated with the account.
        status:
          type: string
          description: Whether or not the bank is active.
          x-stoplight:
            id: 48p5dzjsg4psp
          enum:
            - active
            - inactive
          x-apidog-enum:
            - value: active
              name: ''
              description: Bank is active
            - value: inactive
              name: ''
              description: Bank is inactive
      x-apidog-orders:
        - id
        - bank_name
        - account_name
        - status
      required:
        - id
        - bank_name
        - account_name
        - status
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

## apis-transactions/List-Transactions-Salla-Merchant-API-Salla-Docs

# List Transactions

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /transactions:
    get:
      summary: List Transactions
      deprecated: false
      description: >-
        This endpoints allows you to list all of the Store Owner's payment
        transactions


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `transactions.read`- Transactions Read Only

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Transactions
        - Transactions
      parameters:
        - name: keyword
          in: query
          description: search by customer details(name, mobile, email)
          required: false
          example: test
          schema:
            type: string
        - name: last_4_digit
          in: query
          description: Account's Last 4 Digits
          required: false
          example: 8490
          schema:
            type: integer
        - name: payment_method
          in: query
          description: array or string
          required: false
          example: credit_card
          schema:
            type: string
            enum:
              - credit_card
              - mada
              - stc_pay
              - free
              - bank
              - cod
              - paypal
              - apple_pay
              - google_pay
            default: all payment method slug
            x-apidog-enum:
              - name: ''
                value: credit_card
                description: Payment with credit card.
              - name: ''
                value: mada
                description: Payment using Mada.
              - name: ''
                value: stc_pay
                description: Payment with STC pay
              - name: ''
                value: free
                description: Free of charge.
              - name: ''
                value: bank
                description: Payment via bank.
              - name: ''
                value: cod
                description: Cash on delivery.
              - name: ''
                value: paypal
                description: Payment with Paypal
              - name: ''
                value: apple_pay
                description: Payment via Apple pay.
              - name: ''
                value: google_pay
                description: Payment with Google pay.
        - name: status
          in: query
          description: Payment Status, as shown in the enum values
          required: false
          example: paid
          schema:
            type: string
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
                description: Transaction is initiated.
              - name: ''
                value: pending
                description: Transaction is pending.
              - name: ''
                value: paid
                description: Transaction is paid.
              - name: ''
                value: canceled
                description: Transaction is canceled.
              - name: ''
                value: refunded
                description: Transaction is refunded.
              - name: ''
                value: partial_refunded
                description: Transaction is partial refunded.
        - name: amount
          in: query
          description: Amount Paid
          required: false
          example: 100
          schema:
            type: number
        - name: order_id
          in: query
          description: >-
            The unqiue ID of the Order. List of Order IDs can be found
            [here](https://docs.salla.dev/api-5394146)
          required: false
          example: 982374933
          schema:
            type: integer
        - name: page
          in: query
          description: Pagination Page
          required: false
          example: 1
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/transactions_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 19940416533
                    customer:
                      id: 48447423
                      email: customer@domain.com
                      mobile: '+966512345678'
                      first_name: Ahmed
                      last_name: Adel
                    references:
                      reference_id: 40497536
                      order_id: 413420930
                      cart_id: 171420334123
                      transaction: 44556293650
                    total:
                      amount: 121
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
                      number: 123123xxxxxx6789
                      country: SA
                    available_actions:
                      - refund
                      - print
                    created_at:
                      date: '2024-07-04 03:33:36.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    notes: Additional Note
                  - id: 7172398767
                    customer:
                      id: 357838499
                      email: customer_email@domain.com
                      mobile: '+966591234567'
                      first_name: Customer
                      last_name: Name
                    references:
                      reference_id: 9387827772
                      order_id: 637894790
                      cart_id: 1044130972
                      transaction: 555984480243
                    total:
                      amount: 121
                      currency: SAR
                    payment_method:
                      payment_provider: salla_pay
                      name: mada
                      slug: mada
                      icon: >-
                        https://cdn.assets.salla.network/prod/admin/cp/assets/images/payment_methods/4.png
                    status:
                      name: ملغية
                      slug: canceled
                    card:
                      brand: mada
                      number: 123123xxxxxx4567
                      country: SA
                    available_actions:
                      - refund
                    created_at:
                      date: '2024-06-30 05:01:13.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    notes: تم رفض العملية من قبل البنك يرجى استخدام وسيلة دفع اخرى
                pagination:
                  count: 4
                  total: 19
                  perPage: 15
                  currentPage: 2
                  totalPages: 2
                  links:
                    next: http://api.salla.dev/admin/v2/payment/transactions?page=2
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
                    status:
                      - The selected status is invalid.
                    last_4_digit:
                      - The last 4 digits must be exactly 4 digits.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Transactions
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8382471-run
components:
  schemas:
    transactions_response_body:
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
            $ref: '#/components/schemas/Transaction'
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

## apis-transactions/Print-Transaction-Invoice-Salla-Merchant-API-Salla-Docs

# Print Transaction Invoice

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /transactions/{transaction_id}/print:
    post:
      summary: Print Transaction Invoice
      deprecated: false
      description: >-
        This endpoint allows you to print the transaction invoice by passing the
        `transaction_id` as a path parameter.


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
            Transaction ID. Get a list of Transaction IDs from
            [here](https://docs.salla.dev/8382471e0)
          required: true
          example: 1924095294
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
                      url:
                        type: string
                        description: Payment Transaction from the store owner
                    required:
                      - url
                    x-apidog-orders:
                      - url
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
              example:
                status: 200
                success: true
                data:
                  url: >-
                    https://cdn.salla.sa/QDqV/downloads/zymawy_ma_17-11-2024-12-51_0_print_transaction_invoice.pdf
          headers: {}
          x-apidog-name: Success
        '404':
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
                  error:
                    type: object
                    properties:
                      code:
                        type: integer
                      message:
                        type: string
                    required:
                      - code
                      - message
                    x-apidog-orders:
                      - code
                      - message
                required:
                  - status
                  - success
                  - error
                x-apidog-orders:
                  - status
                  - success
                  - error
              example:
                status: 404
                success: false
                error:
                  code: 404
                  message: cant print the invoice
          headers: {}
          x-apidog-name: Record Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Transactions
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-11716492-run
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

