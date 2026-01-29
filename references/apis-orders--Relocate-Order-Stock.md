# Apis Orders  Relocate Order Stock

## Table of Contents

- [apis-orders/Relocate-Order-Stock](#apis-orders-relocate-order-stock)

---

## apis-orders/Relocate-Order-Stock

# Relocate Order Stock

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/{order_id}/inventory/relocate:
    post:
      summary: Relocate Order Stock
      deprecated: false
      description: >-
        This endpoint allows you to update order stock location associated with
        a spesific order.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Orders
        - Orders
      parameters:
        - name: order_id
          in: path
          description: >-
            Unique identifier associated with an order. Get a list of order id
            [here](https://docs.salla.dev/5394146e0)
          required: true
          example: 3155923424
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/relocateOrderStock_request_body'
            example:
              source: 1923546554
              destination: 495787195
              items:
                - id: 123413414
                  quantity: 2
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/relocateOrderStock_response_body'
              example:
                status: 200
                success: true
                data:
                  message: تم نقل المخزون بنجاح.
          headers: {}
          x-apidog-name: Success
        '403':
          description: 'When the merchant is not activating `multi-shipments` feature '
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
                  - error
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: >-
                    نقل عناصر المخزون بشكل منفصل غير مسموح به عندما تكون ميزة
                    الشحنات المتعددة غير مفعله.
          headers: {}
          x-apidog-name: Forbidden
        '422':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
                    description: HTTP status code
                  success:
                    type: boolean
                    description: Request success indicator
                  error:
                    type: object
                    properties:
                      code:
                        type: string
                        description: Error code
                      message:
                        type: string
                        description: Error message
                      fields:
                        type: object
                        properties:
                          items.0.id:
                            type: array
                            items:
                              type: string
                            description: Validation errors for items.0.id field
                        required:
                          - items.0.id
                        x-apidog-orders:
                          - items.0.id
                        description: Validation error fields
                        x-apidog-ignore-properties: []
                    required:
                      - code
                      - message
                      - fields
                    x-apidog-orders:
                      - code
                      - message
                      - fields
                    description: Error details object
                    x-apidog-ignore-properties: []
                required:
                  - status
                  - success
                  - error
                x-apidog-orders:
                  - status
                  - success
                  - error
                description: Error response schema
                x-apidog-ignore-properties: []
              example:
                status: 422
                success: false
                error:
                  code: error
                  message: alert.invalid_fields
                  fields:
                    items.0.id:
                      - حقل items.0.id غير صالح
          headers: {}
          x-apidog-name: Parameter Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Orders
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-18575329-run
components:
  schemas:
    relocateOrderStock_request_body:
      type: object
      properties:
        source:
          type: number
          x-apidog-mock: '{{$string.numeric}}'
          description: ' Allows specifying the source branch from which stock is deducted.'
        destination:
          type: number
          x-apidog-mock: '{{$string.numeric}}'
          description: ' Allows specifying the source destination from which stock is is added.'
        items:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                x-apidog-mock: '{{$string.numeric}}'
                description: >-
                  The unique identifier for the item being relocated. This is
                  typically a reference to the order item
              quantity:
                type: integer
                x-apidog-mock: '{{$string.numeric}}'
                description: >-
                  The number of units of the item to be relocated. This must be
                  a positive integer.
            x-apidog-orders:
              - id
              - quantity
            required:
              - id
              - quantity
            x-apidog-ignore-properties: []
          description: >-
            A list of order items with their respective quantities to be
            relocated, it is not mandatory, it can be used if there is some
            items or quantities to be reallocated.
      x-apidog-orders:
        - source
        - destination
        - items
      required:
        - source
        - destination
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    relocateOrderStock_response_body:
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
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        data:
          type: object
          properties:
            message:
              type: string
              description: Message content for the order stock relocation.
          x-apidog-orders:
            - message
          required:
            - message
          x-apidog-ignore-properties: []
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

