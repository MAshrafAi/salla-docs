# Apis Order Invoice  List Invoices Salla Merchant Api Salla Docs

## Table of Contents

- [apis-order-invoice/List-Invoices-Salla-Merchant-API-Salla-Docs](#apis-order-invoice-list-invoices-salla-merchant-api-salla-docs)
- [apis-order-invoice/Send-Order-Invoice-Salla-Merchant-API-Salla-Docs](#apis-order-invoice-send-order-invoice-salla-merchant-api-salla-docs)

---

## apis-order-invoice/List-Invoices-Salla-Merchant-API-Salla-Docs

# List Invoices

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/invoices:
    get:
      summary: List Invoices
      deprecated: false
      description: |-
        This endpoint allows you to fetch a list of order invoices.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `orders.read` - Orders Read Only
        </Accordion>
      operationId: get-orders-invoices
      tags:
        - Default module/Merchant API/APIs/Order Invoice
        - Order Invoice
      parameters:
        - name: from_date
          in: query
          description: Invoice date start range
          required: false
          schema:
            type: string
        - name: to_date
          in: query
          description: Invoice date end range
          required: false
          schema:
            type: string
        - name: order_id
          in: query
          description: >-
            Unique identification number assigend to an order. Get a list of
            Order IDs from [here](https://docs.salla.dev/api-5394146).
          required: false
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/invoices_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1479538730
                    order_id: 1557892161
                    type: Credit Note
                    sub_total:
                      amount: '1000.00'
                      currency: SAR
                    shipping_cost:
                      amount: '10.00'
                      currency: SAR
                    cod_cost:
                      amount: '0.00'
                      currency: SAR
                    discount:
                      amount: '0.00'
                      currency: SAR
                    tax:
                      percent: '15.00'
                      amount:
                        amount: '151.50'
                        currency: SAR
                    total:
                      amount: 1161.5
                      currency: SAR
                    date: '2021-12-03'
                  - id: 1692688589
                    order_id: 1557892161
                    type: Tax Invoice
                    sub_total:
                      amount: '29.00'
                      currency: SAR
                    shipping_cost:
                      amount: '10.00'
                      currency: SAR
                    cod_cost:
                      amount: '0.00'
                      currency: SAR
                    discount:
                      amount: '0.00'
                      currency: SAR
                    tax:
                      percent: '15.00'
                      amount:
                        amount: '5.85'
                        currency: SAR
                    total:
                      amount: 44.85
                      currency: SAR
                    date: '2021-12-03'
                  - id: 1219192926
                    order_id: 1557892161
                    type: Tax Invoice
                    sub_total:
                      amount: '850.00'
                      currency: SAR
                    shipping_cost:
                      amount: '25.00'
                      currency: SAR
                    cod_cost:
                      amount: '10.00'
                      currency: SAR
                    discount:
                      amount: '0.00'
                      currency: SAR
                    tax:
                      percent: '15.00'
                      amount:
                        amount: '132.75'
                        currency: SAR
                    total:
                      amount: 1017.75
                      currency: SAR
                    date: '2021-12-04'
                pagination:
                  count: 3
                  total: 3
                  perPage: 3
                  currentPage: 1
                  totalPages: 1
                  links:
                    next: https://s.salla.sa/NextPage
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
      x-salla-php-method-name: listInvoices
      x-salla-php-return-type: Invoice
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Order Invoice
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394157-run
components:
  schemas:
    invoices_response_body:
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
            id: 96o79ilej985r
          items:
            $ref: '#/components/schemas/Invoice'
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
    Invoice:
      type: object
      x-examples:
        Example:
          id: 458282634
          order_id: 1557892161
          type: Credit Note
          sub_total:
            amount: '300.00'
            currency: SAR
          shipping_cost:
            amount: '182.50'
            currency: SAR
          cod_cost:
            amount: '0.00'
            currency: SAR
          discount:
            amount: '0.00'
            currency: SAR
          tax:
            percent: '0.00'
            amount:
              amount: '0.00'
              currency: SAR
          total:
            amount: 482.5
            currency: SAR
          date: '2022-01-19'
          items:
            - id: 105272559
              item_id: 1155070869
              name: Nabil
              quantity: 1
              price:
                amount: '300.00'
                currency: SAR
              discount:
                amount: '0.00'
                currency: SAR
              tax:
                percent: '0.00'
                amount:
                  amount: '0.00'
                  currency: SAR
              total:
                amount: 300
                currency: SAR
      title: Invoice
      properties:
        id:
          type: number
          description: >-
            A unique identifier assigned to a specific invoice. Invoice list can
            be found [here](https://docs.salla.dev/api-5394157)
          examples:
            - 458282634
        invoice_number:
          type: string
          description: The invoice number as in the order.
        uuid:
          type: string
          format: uuid
          examples:
            - e7f9e1e3-90d1-487d-afe1-f97e10b80b1d
          description: Another unique identifier of the invoice
        order_id:
          type: integer
          description: A unique identifier assigned to a specific order.
          examples:
            - 1557892161
        invoice_reference_id:
          type: string
          description: >-
            A unique identifier assigned to aninvoice. This is especially used
            if the invoice is issued outside Salla system.
        type:
          type: string
          description: Invoice type.
          examples:
            - Credit Note
        date:
          type: string
          description: Invoice date.
          examples:
            - '2022-01-19'
        qr_code:
          type: string
          description: Invoice QR code.
        payment_method:
          type: string
          description: Invoice payment method.
        sub_total:
          type: object
          properties:
            amount:
              type: string
              description: Subtotal Amount
              examples:
                - '300.00'
            currency:
              type: string
              description: Subtotal Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: Invoice sub total.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        shipping_cost:
          type: object
          properties:
            amount:
              type: string
              description: Shipping Cost Amount
              examples:
                - '182.50'
            currency:
              type: string
              description: Shipping Cost Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: Invoice shipping cost.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        cod_cost:
          type: object
          properties:
            amount:
              type: string
              description: Cash On Delivery Amount
              examples:
                - '0.00'
            currency:
              type: string
              description: Cash On Delivery Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: Cash on delivery cost.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        discount:
          type: object
          properties:
            amount:
              type: string
              description: Discount Amount
              examples:
                - '0.00'
            currency:
              type: string
              description: Discount Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: Discount applied on the invoice.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        tax:
          type: object
          properties:
            percent:
              type: string
              description: Tax Percentage Value
              examples:
                - '0.00'
            amount:
              type: object
              properties:
                amount:
                  type: string
                  description: Tax Amount Value
                  examples:
                    - '0.00'
                currency:
                  type: string
                  description: Tax Amount Value Currency
                  examples:
                    - SAR
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
          description: Tax applied on the invoice.
          required:
            - percent
            - amount
          x-apidog-ignore-properties: []
        total:
          type: object
          properties:
            amount:
              type: number
              description: Total Amount Value
              examples:
                - 482.5
            currency:
              type: string
              description: Total Amount Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: Invoice total.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
      x-tags:
        - Responses
      x-apidog-orders:
        - id
        - invoice_number
        - uuid
        - order_id
        - invoice_reference_id
        - type
        - date
        - qr_code
        - payment_method
        - sub_total
        - shipping_cost
        - cod_cost
        - discount
        - tax
        - total
      required:
        - id
        - invoice_number
        - uuid
        - order_id
        - invoice_reference_id
        - type
        - date
        - qr_code
        - payment_method
        - sub_total
        - shipping_cost
        - cod_cost
        - discount
        - tax
        - total
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

## apis-order-invoice/Send-Order-Invoice-Salla-Merchant-API-Salla-Docs

# Send Order Invoice

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/{order_id}/send-invoice:
    post:
      summary: Send Order Invoice
      deprecated: false
      description: >-
        This endpoint allows you to send the order invoice to the customer's
        email by passing the `order_id` as a path parameter. 


        :::tip[Note]

        To send the invoice, the email address should be recorded on the
        invoice.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-send-orders-order-send-invoice
      tags:
        - Default module/Merchant API/APIs/Order Invoice
        - Order Invoice
      parameters:
        - name: order_id
          in: path
          description: >-
            A unique alphanumeric code or identifier assigned to a specific
            order. List of Order ID can be found
            [here](https://docs.salla.dev/api-5394146)
          required: true
          example: 289032373
          schema:
            type: number
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
                  message: تم ارسال رسالة الفاتورة بنجاح
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
                  message: حصل خطأ غير متوقع يرجى إعادة المُحاولة لاحقاً
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Invoice
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-6336820-run
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

