# Apis Orders  Create Drafted Order Salla Merchant Api Salla Docs

## Table of Contents

- [apis-orders/Create-Drafted-Order-Salla-Merchant-API-Salla-Docs](#apis-orders-create-drafted-order-salla-merchant-api-salla-docs)

---

## apis-orders/Create-Drafted-Order-Salla-Merchant-API-Salla-Docs

# Create Drafted Order

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/draft:
    post:
      summary: Create Drafted Order
      deprecated: false
      description: |-
        This endpoint allows you to create an order in the `Draft` status.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `orders.read_write` - Orders Read & Write
        </Accordion>
      operationId: post-orders-draft
      tags:
        - Default module/Merchant API/APIs/Orders
        - Orders
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/draftedOrder_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 23761823281
                  reference_id: 1527192
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
                  code: Unauthorized
                  message: >-
                    The access token should have access to one of those scopes:
                    orders.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Orders
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5750257-run
components:
  schemas:
    draftedOrder_response_body:
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
            id:
              type: number
              description: >-
                A unique alphanumeric code or identifier assigned to a specific
                order.
            reference_id:
              type: number
              description: >-
                Order refrence ID, a specific alphanumeric code or identifier
                associated with an order, used for easy and precise reference
                and tracking of that particular order, this reference ID appears
                to customers in the store.
          x-apidog-orders:
            - id
            - reference_id
          required:
            - reference_id
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

