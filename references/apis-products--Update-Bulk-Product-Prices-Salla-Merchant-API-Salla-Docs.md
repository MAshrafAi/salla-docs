# Apis Products  Update Bulk Product Prices Salla Merchant Api Salla Docs

## Table of Contents

- [apis-products/Update-Bulk-Product-Prices-Salla-Merchant-API-Salla-Docs](#apis-products-update-bulk-product-prices-salla-merchant-api-salla-docs)

---

## apis-products/Update-Bulk-Product-Prices-Salla-Merchant-API-Salla-Docs

# Update Bulk Product Prices

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/prices/bulkPrice:
    post:
      summary: Update Bulk Product Prices
      deprecated: false
      description: >-
        This endpoint allows you to update unlimited **bulk** products' prices
        by providing the IDs of the products and the price amounts to be
        updated. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: post-products-prices-bulkPrice
      tags:
        - Default module/Merchant API/APIs/Products
        - Products
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              description: ''
              type: object
              x-examples:
                example-1:
                  products:
                    - id: 1078784557
                      price: 300
              properties:
                products:
                  type: array
                  minItems: 1
                  items:
                    type: object
                    properties:
                      id:
                        type: number
                        description: >-
                          Product ID. List of Product ID can be found
                          [here](https://docs.salla.dev/api-5394168).
                        examples:
                          - 784769282
                      price:
                        type: number
                        description: Product Price
                        examples:
                          - 500
                      cost_price:
                        type: number
                        description: Cost Price
                        examples:
                          - 550
                      sale_price:
                        type: number
                        description: Sale Price
                        examples:
                          - 600
                      sale_end:
                        type: string
                        description: Sale price end
                        examples:
                          - '2022-07-30'
                    required:
                      - id
                      - price
                    x-apidog-orders:
                      - id
                      - price
                      - cost_price
                      - sale_price
                      - sale_end
                    x-apidog-ignore-properties: []
              required:
                - products
              x-apidog-orders:
                - products
              x-apidog-ignore-properties: []
            example:
              products:
                - id: 784769282
                  price: 500
                  cost_price: 550
                  sale_price: 600
                  sale_end: '2022-07-30'
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
                  message: >-
                    The details has been queued to update, it may take several
                    minutes to finish the process.
                  code: 201
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
                    products.read_write
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
                        products:
                          - حقل products مطلوب.
                '4':
                  summary: Example 2
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        products.0.id:
                          - حقل products.0.id مطلوب.
                        products.0.price:
                          - حقل products.0.price مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateBulkPricesBySKU
      x-apidog-folder: Default module/Merchant API/APIs/Products
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394177-run
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

