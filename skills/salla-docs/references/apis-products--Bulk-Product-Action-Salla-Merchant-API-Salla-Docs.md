# Apis Products  Bulk Product Action Salla Merchant Api Salla Docs

## Table of Contents

- [apis-products/Bulk-Product-Action-Salla-Merchant-API-Salla-Docs](#apis-products-bulk-product-action-salla-merchant-api-salla-docs)
- [apis-products/Change-Product-Status-Salla-Merchant-API-Salla-Docs](#apis-products-change-product-status-salla-merchant-api-salla-docs)

---

## apis-products/Bulk-Product-Action-Salla-Merchant-API-Salla-Docs

# Bulk Product Actions

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/actions:
    post:
      summary: Bulk Product Actions
      deprecated: false
      description: >-
        This endpoint allows you update multiple products with various actions.


        :::check[]

        If only one product is specified, the update will be applied
        immediately. For multiple products, the updates will be processed
        through a queue.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: post-bulk-product-actions
      tags:
        - Default module/Merchant API/APIs/Products
        - Products
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/bulkProductActions_request_body'
            example:
              operations:
                - action_name: duplicate
                - action_name: sale-channels
                  value:
                    channels:
                      - web
                      - app
                - action_name: features
                  value:
                    mahly_category_id: 5670235101
                    categories:
                      - 537348185
                    brand_id: 959852531
                    tags:
                      - 1982584825
                - action_name: notify-quantity
                  value:
                    notify_quantity: 10
                    minimum_notify_quantity: 20
                    subscribers_percentage: 5
                - action_name: pricing
                  value:
                    column: price
                    formula: price - (price * amount /100 )
                    amount: 50
                    apply_on: product
              filters:
                select_all: false
                unselected_ids: []
                ids:
                  - 1661028235
                  - 388819608
                categories:
                  - 48702356
                  - 12857436
                brands:
                  - 716569785
                  - 125713981
                wholesale: false
                mahly: unlinked
                status:
                  - sale
                types:
                  - product
                  - digital
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/bulkProductActions_response_body'
              example:
                status: 200
                success: true
                data:
                  - operation_id: 9cde43d8-dbac-40f4-8d39-74a9443846b9
                    action_name: notify-quantity
                    status: in_progress
                  - operation_id: 9cde43d8-dbba-47cd-98ed-23bb3aeee142
                    action_name: mahly-category
                    status: in_progress
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
                    products.read_write
          headers: {}
          x-apidog-name: unauthorized
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_validation_422'
              examples:
                '2':
                  summary: Invalid Action Name
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        operations.0.action_name:
                          - The selected operations.0.action_name is invalid.
                '4':
                  summary: Required Fields
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        operations:
                          - حقل operations مطلوب.
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Products
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9613153-run
components:
  schemas:
    bulkProductActions_request_body:
      type: object
      properties:
        operations:
          type: array
          items:
            type: object
            properties:
              action_name:
                type: string
                description: >-
                  Product's action name signifying the action to perform based
                  on the filters.
                enum:
                  - duplicate
                  - sale-channels
                  - features
                  - notify-quantity
                  - pricing
                  - restore
                x-apidog-enum:
                  - name: ''
                    value: duplicate
                    description: Duplicate a product
                  - name: ''
                    value: sale-channels
                    description: Change the sales channels
                  - name: ''
                    value: features
                    description: ''
                  - name: ''
                    value: notify-quantity
                    description: Sets a minimum quantity to notify the customer
                  - name: ''
                    value: pricing
                    description: Change the pricing formual
                  - value: restore
                    name: ''
                    description: Restore Trashed Products
              value:
                type: object
                properties:
                  channels:
                    type: array
                    items:
                      type: string
                      enum:
                        - app
                        - web
                      x-apidog-enum:
                        - name: ''
                          value: app
                          description: ''
                        - name: ''
                          value: web
                          description: ''
                    description: >-
                      Channels where the product is published. Works with
                      `sale-channels` action
                  mahly_category_id:
                    type: integer
                    description: Mahally category ID. Works with the `features` action
                  categories:
                    type: array
                    items:
                      type: integer
                    description: >-
                      Array of category IDs that you wish to associate the
                      product with. Works with the `features` action
                  brand_id:
                    type: integer
                    description: >-
                      The brand ID that you wish to associate the product with.
                      Works with the `features` action
                  tags:
                    type: array
                    items:
                      type: integer
                    description: >-
                      Array of tag IDs that you wish to associate with the
                      product
                  notify_quantity:
                    type: integer
                    description: >-
                      Quantity to be notified with. Works with `notify-quantity`
                      action
                  minimum_notify_quantity:
                    type: integer
                    description: >-
                      Minimum quantity to be notified with. Works with
                      `notify-quantity` action
                  subscribers_percentage:
                    type: integer
                    description: Works with `notify-quantity` action
                  column:
                    type: string
                    enum:
                      - cost_price
                      - sale_price
                      - price
                    description: Desired coumn to edit. works with the pricing action.
                    x-apidog-enum:
                      - name: ''
                        value: cost_price
                        description: ''
                      - name: ''
                        value: sale_price
                        description: ''
                      - name: ''
                        value: price
                        description: ''
                  formula:
                    type: string
                    description: >
                      A formula can be added to edit the pricing of one or
                      multiple product.  works with the pricing action.

                      Fixed formulas can be passed as shown in the below table:

                      if column type is `cost_price`

                      |       Description        
                      |Formula                          

                      |----------------|-------------------------------

                      |Adding fixed amount to cost|`cost_price + amount`     

                      |adding profit percentage to cost|`cost_price +
                      (cost_price * amount /100 )`            

                      |new cost price |`amount`


                      if column type is `sale_price`

                      |       Description        
                      |Formula                          

                      |----------------|-------------------------------

                      |Adding fixed amount to cost|`cost_price + amount`

                      |adding profit percentage to cost|`cost_price +
                      (cost_price * amount /100 )`  

                      |subtracting fixed amount from cost| `price - amount`

                      |discount percentage on price|`price - (price * amount
                      /100 )`

                      |fixed discount on sale price|`sale_price - amount`

                      |discount percentage on sale price|`sale_price -
                      (sale_price * amount /100 )`

                      |New sale price | `amount`


                      if column type is `price`

                      |       Description        
                      |Formula                          

                      |----------------|-------------------------------

                      |Adding fixed amount to cost|`cost_price + amount`  

                      |adding profit percentage to cost|`cost_price +
                      (cost_price * amount /100 )`  

                      |adding fixed amount to price|`price + amount`

                      |adding profit percentage on price|`price + (price *
                      amount /100 )`

                      |new price|`amount`
                  amount:
                    type: number
                    description: ' the amount to be used in the `formula` field. works with the pricing action.'
                  apply_on:
                    type: string
                    enum:
                      - product
                      - product_and_variants
                      - variants
                    description: >-
                      options to apply the pricing on. works with the pricing
                      action.
                    x-apidog-enum:
                      - name: ''
                        value: product
                        description: ''
                      - name: ''
                        value: product_and_variants
                        description: ''
                      - name: ''
                        value: variants
                        description: ''
                x-apidog-orders:
                  - channels
                  - mahly_category_id
                  - categories
                  - brand_id
                  - tags
                  - notify_quantity
                  - minimum_notify_quantity
                  - subscribers_percentage
                  - column
                  - formula
                  - amount
                  - apply_on
                description: An array that will hold information based on the action type.
                x-apidog-ignore-properties: []
            x-apidog-orders:
              - action_name
              - value
            x-apidog-ignore-properties: []
        filters:
          type: object
          properties:
            select_all:
              type: boolean
              description: Whether ot not to select all products
            unselected_ids:
              type: array
              items:
                type: string
              description: Exclude IDs from selections
            ids:
              type: array
              items:
                type: integer
              description: >-
                List of product IDs that you wish to apply the actions on. List
                of products IDs can be found
                [here](https://docs.salla.dev/api-5394168).
            categories:
              type: array
              items:
                type: string
              description: Filter using the categories that you wish to update product in.
            brands:
              type: array
              items:
                type: string
              description: >-
                Filter using brand ID(s) that you with to update products in.
                List of brands IDs can be found
                [here](https://docs.salla.dev/api-5394213).
            wholesale:
              type: boolean
            mahly:
              type: string
              enum:
                - linked
                - unlinked
              x-apidog-enum:
                - value: linked
                  name: ''
                  description: ''
                - value: unlinked
                  name: ''
                  description: ''
            status:
              type: array
              items:
                type: string
                enum:
                  - hidden
                  - out
                  - sale
                  - none
                x-apidog-enum:
                  - value: hidden
                    name: ''
                    description: ''
                  - value: out
                    name: ''
                    description: ''
                  - value: sale
                    name: ''
                    description: ''
                  - value: none
                    name: ''
                    description: ''
              description: 'Filter using product status. '
            types:
              type: array
              items:
                type: string
                enum:
                  - product
                  - service
                  - group_products
                  - financial_support
                  - codes
                  - digital
                  - food
                  - donating
                  - booking
                x-apidog-enum:
                  - value: product
                    name: ''
                    description: ''
                  - value: service
                    name: ''
                    description: ''
                  - value: group_products
                    name: ''
                    description: ''
                  - value: financial_support
                    name: ''
                    description: ''
                  - value: codes
                    name: ''
                    description: ''
                  - value: digital
                    name: ''
                    description: ''
                  - value: food
                    name: ''
                    description: ''
                  - value: donating
                    name: ''
                    description: ''
                  - value: booking
                    name: ''
                    description: ''
              description: Filter using product type
          x-apidog-orders:
            - select_all
            - unselected_ids
            - ids
            - categories
            - brands
            - wholesale
            - mahly
            - status
            - types
          x-apidog-ignore-properties: []
      required:
        - operations
        - filters
      x-apidog-orders:
        - operations
        - filters
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    bulkProductActions_response_body:
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
          items:
            $ref: '#/components/schemas/BulkProductActions'
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
    BulkProductActions:
      type: object
      properties:
        operation_id:
          type: string
          description: Product operation unique identification.
        action_name:
          type: string
          description: Bulk operation name.
        status:
          type: string
          description: Operation status.
      x-apidog-orders:
        - operation_id
        - action_name
        - status
      required:
        - operation_id
        - action_name
        - status
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

## apis-products/Change-Product-Status-Salla-Merchant-API-Salla-Docs

# Change Product Status

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/{product}/status:
    post:
      summary: Change Product Status
      deprecated: false
      description: >-
        This endpoint allows you to update specific product status by passing
        the `product` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Change-Product-Status
      tags:
        - Default module/Merchant API/APIs/Products
        - Products
      parameters:
        - name: product
          in: path
          description: >-
            Unique identification number assigned to a product. List of products
            IDs can be found [here](https://docs.salla.dev/422719m0).
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
                status:
                  type: string
                  description: The new status of the prodcut.
                  enum:
                    - out
                    - sale
                    - hidden
              x-apidog-orders:
                - status
              required:
                - status
              x-apidog-ignore-properties: []
            example:
              status: sale
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
                    status:
                      - حقل status غير صالح
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: changeStatus
      x-apidog-folder: Default module/Merchant API/APIs/Products
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394172-run
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

