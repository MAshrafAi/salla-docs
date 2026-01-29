# Apis Customer Groups  Add Customers To Group Customer Salla Merchant Api Salla Docs

## Table of Contents

- [apis-customer-groups/Add-Customers-To-Group-Customer-Salla-Merchant-API-Salla-Docs](#apis-customer-groups-add-customers-to-group-customer-salla-merchant-api-salla-docs)
- [apis-customer-groups/Create-Customer-Group-Salla-Merchant-API-Salla-Docs](#apis-customer-groups-create-customer-group-salla-merchant-api-salla-docs)
- [apis-customer-groups/Delete-Customer-Group-Salla-Merchant-API-Salla-Docs](#apis-customer-groups-delete-customer-group-salla-merchant-api-salla-docs)
- [apis-customer-groups/List-Customer-Groups-Salla-Merchant-API-Salla-Docs](#apis-customer-groups-list-customer-groups-salla-merchant-api-salla-docs)
- [apis-customer-groups/Update-Customer-Group-Salla-Merchant-API-Salla-Docs](#apis-customer-groups-update-customer-group-salla-merchant-api-salla-docs)

---

## apis-customer-groups/Add-Customers-To-Group-Customer-Salla-Merchant-API-Salla-Docs

# Add Customers To Group Customer

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/groups/add_customers:
    post:
      summary: Add Customers To Group Customer
      deprecated: false
      description: |-
        This endpoint allows you to add customers to a specific customer groups.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `customers.read_write`- Customers Read & Write
        </Accordion>
      operationId: post-customers-groups-add_customers
      tags:
        - Default module/Merchant API/APIs/Customer Groups
        - Customer Groups
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/addCustomerGroup_request_body'
            example:
              group_id: 667738032
              customers:
                - 447121768
                - 1761729493
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/addCustomerToGroupCustomers_response_body'
              example:
                status: 200
                success: true
                data:
                  - The customers has been added to group successfully
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
                    customers.read_write
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
                        group_id:
                          - حقل group id مطلوب.
                        customers:
                          - حقل customers مطلوب.
                '4':
                  summary: Example 2
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        group_id:
                          - يجب أن يكون حقل group id عددًا صحيحًا
                        customers.0:
                          - حقل customers.0 غير صالح
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: addToGroup
      x-apidog-folder: Default module/Merchant API/APIs/Customer Groups
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394130-run
components:
  schemas:
    addCustomerGroup_request_body:
      type: object
      properties:
        group_id:
          type: integer
          description: >-
            Customer Group ID. List of Customer Group ID can be found
            [here](https://docs.salla.dev/api-5394129).
          examples:
            - 667738032
        customers:
          type: array
          description: >-
            Customer IDs. List of Customer ID can be found
            [here](https://docs.salla.dev/api-5394121)
          items:
            type: integer
            examples:
              - ''
      x-apidog-orders:
        - group_id
        - customers
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    addCustomerToGroupCustomers_response_body:
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
          x-stoplight:
            id: f4ajks6ba59j4
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          type: array
          description: Data Response
          items:
            type: string
            examples:
              - The customers has been added to group successfully
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

## apis-customer-groups/Create-Customer-Group-Salla-Merchant-API-Salla-Docs

# Create Customer Group

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/groups:
    post:
      summary: Create Customer Group
      deprecated: false
      description: >-
        This endpoint allows you to create a customer group by providing a
        required group name, along with conditions *(shared traits among
        members)* and the features that will apply to the group.


        :::tip[Note]


        The **type** variable may be one of the following options:


        | |

        | - |

        | `"total_sales"` |

        | `"total_orders"` |

        | `"store_rating"` |

        | `"doesnt_have_orders"` |



        And the **symbols** may be one of the following options:


        | |

        | - |

        | `>` |

        | `<` |

        | `between` |


        :::


        :::info[Information]

        To add the payment methods you will need to get the payment methods list
        from the [Available Payment Methods](https://docs.salla.dev/api-5394164)
        endpoint

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Create-Group
      tags:
        - Default module/Merchant API/APIs/Customer Groups
        - Customer Groups
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/customerGroup_request_body'
            example:
              name: VIPCustomers
              conditions:
                - type: total_sales
                  symbol: '>'
                  value: 100
              features:
                payment_method:
                  - credit_card
                  - mada
                  - bank
                  - cod
                  - apple_pay
                  - stc_pay
                shipping:
                  - all
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/customerGroup_response_body'
              examples:
                '1':
                  summary: Example
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1394760126
                      name: VIPCustomers
                '3':
                  summary: Example 1
                  value:
                    status: 200
                    success: true
                    data:
                      id: 21314237
                      name: users with no orders
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
                  code: validation_failed
                  message: Validation is not successful
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: createGroup
      x-salla-php-return-type: CustomerGroup
      x-apidog-folder: Default module/Merchant API/APIs/Customer Groups
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394128-run
components:
  schemas:
    customerGroup_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            A unique title or label assigned to a collection of items,
            individuals, or entities that share common characteristics, serving
            as a means of categorization or identification within a broader
            context or organization. List of customers can be found
            [here](https://docs.salla.dev/api-5394121).
        conditions:
          type: array
          description: >-
            An array of conditions to consider when automatically assigning
            customers to a group.
          items:
            type: object
            properties:
              type:
                type: string
                description: The type of the condition.
              symbol:
                type: string
                description: A condition operator.
                enum:
                  - '>'
                  - <
                  - between
              value:
                type: number
                description: A condition value (value to be after the operator).
              min_value:
                type: number
                description: >-
                  Refers to the minimum possible value. <b>Required</b> if
                  `symbol` equals `between`.
              max_value:
                type: number
                description: >-
                  Refers to the maximum possible value. <b>Required</b> if
                  `symbol` equals `between`
            x-apidog-orders:
              - type
              - symbol
              - value
              - min_value
              - max_value
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - name
        - conditions
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    customerGroup_response_body:
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
          $ref: '#/components/schemas/CustomerGroup'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    CustomerGroup:
      description: >-
        Detailed structure of the customer group model object showing its fields
        and data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: CustomerGroup
      properties:
        id:
          type: number
          description: The unique identifier assigned to a specific group of customers.
        name:
          type: string
          description: The name or label for a the Customer Group.
        conditions:
          type: object
          description: >-
            Conditions for group membership, such as `total_sales > 100`,
            determine auto-assignment. For example, customers with sales
            exceeding 100 are added to the group automatically.
          properties:
            type:
              type: string
              description: "The type of the condition.\r\n"
            symbol:
              type: string
              description: >-
                A symbol or function defining relationships between values, used
                in conditional logic.
            value:
              type: number
              description: The condition after the operator.
          x-apidog-orders:
            - type
            - symbol
            - value
          required:
            - type
            - symbol
            - value
          x-apidog-ignore-properties: []
        features:
          type: object
          x-apidog-refs:
            01JJ90T6D94VC68GZZQWCTFJCZ:
              $ref: '#/components/schemas/CustomerGroupFeatures'
              x-apidog-overrides: {}
              required:
                - payment_method
          x-apidog-orders:
            - 01JJ90T6D94VC68GZZQWCTFJCZ
          properties:
            payment_method: &ref_0
              type: array
              description: >-
                The various methods of payment that are offered to a specific
                group of customers. List of payment methods can be found
                [here](https://docs.salla.dev/api-5394164).
              items:
                type: string
            shipping: &ref_1
              type: array
              description: >-
                The various delivery methods that are accessible or offered to a
                specific group of customers.
              items:
                type: string
          required:
            - payment_method
            - shipping
          x-apidog-ignore-properties:
            - payment_method
            - shipping
      x-apidog-orders:
        - id
        - name
        - conditions
        - features
      required:
        - id
        - name
        - conditions
        - features
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    CustomerGroupFeatures:
      title: CustomerGroupFeatures
      type: object
      properties:
        payment_method: *ref_0
        shipping: *ref_1
      x-apidog-orders:
        - payment_method
        - shipping
      deprecated: true
      required:
        - payment_method
        - shipping
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

## apis-customer-groups/Delete-Customer-Group-Salla-Merchant-API-Salla-Docs

# Delete Customer Group

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/groups/{group}:
    delete:
      summary: Delete Customer Group
      deprecated: false
      description: >-
        This endpoint allows you to delete a customer group by passing the
        `group` as a path parameter.


        :::tip[Note]

        Group members will be removed automatically from this group only.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Delete-Group
      tags:
        - Default module/Merchant API/APIs/Customer Groups
        - Customer Groups
      parameters:
        - name: group
          in: path
          description: >-
            Unique identification number assigned to a customer group. List of
            customer group IDs can be found
            [here](https://docs.salla.dev/api-5394129).
          required: true
          example: 0
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/delete_success'
              example:
                status: 202
                success: true
                data:
                  message: The Object has been removed successfully
                  code: 202
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
                    customers.read_write
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
      x-salla-php-method-name: deleteGroup
      x-apidog-folder: Default module/Merchant API/APIs/Customer Groups
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394133-run
components:
  schemas:
    delete_success:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.Response status Code
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/DeleteSuccess'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    DeleteSuccess:
      type: object
      properties:
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when a
            deletion operation is successful.
        code:
          type: number
          description: >-
            A numerical or alphanumeric code that is used in various software
            and web development contexts to convey information about the outcome
            of a request or operation.
      x-apidog-orders:
        - message
        - code
      required:
        - message
        - code
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

## apis-customer-groups/List-Customer-Groups-Salla-Merchant-API-Salla-Docs

# List Customer Groups

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/groups:
    get:
      summary: List Customer Groups
      deprecated: false
      description: >-
        This endpoint allows you to list all the customer groups in your store.


        :::info[Information]

        Customer groups segment your customers into smaller, targeted groups
        rather than a default group. This enables tailored service, better
        understanding of their needs, and personalized treatment for each group.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read`- Customers Read Only

        </Accordion>
      operationId: List-Groups
      tags:
        - Default module/Merchant API/APIs/Customer Groups
        - Customer Groups
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
                $ref: '#/components/schemas/customerGroups_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 2075683582
                    name: VIP Customers
                  - id: 2075683583
                    name: Golden Customers
                pagination:
                  count: 2
                  total: 2
                  perPage: 15
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
                    cutomers.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: listGroups
      x-salla-php-return-type: CustomerGroup
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Customer Groups
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394129-run
components:
  schemas:
    customerGroups_response_body:
      type: object
      properties:
        status:
          type: string
          x-stoplight:
            id: kb8wuu2lgux80
        success:
          type: string
          x-stoplight:
            id: 0llz2yv3myz7r
        data:
          type: array
          x-stoplight:
            id: 6h79afi1xqcxn
          items:
            $ref: '#/components/schemas/CustomerGroup'
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
    CustomerGroup:
      description: >-
        Detailed structure of the customer group model object showing its fields
        and data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: CustomerGroup
      properties:
        id:
          type: number
          description: The unique identifier assigned to a specific group of customers.
        name:
          type: string
          description: The name or label for a the Customer Group.
        conditions:
          type: object
          description: >-
            Conditions for group membership, such as `total_sales > 100`,
            determine auto-assignment. For example, customers with sales
            exceeding 100 are added to the group automatically.
          properties:
            type:
              type: string
              description: "The type of the condition.\r\n"
            symbol:
              type: string
              description: >-
                A symbol or function defining relationships between values, used
                in conditional logic.
            value:
              type: number
              description: The condition after the operator.
          x-apidog-orders:
            - type
            - symbol
            - value
          required:
            - type
            - symbol
            - value
          x-apidog-ignore-properties: []
        features:
          type: object
          x-apidog-refs:
            01JJ90T6D94VC68GZZQWCTFJCZ:
              $ref: '#/components/schemas/CustomerGroupFeatures'
              x-apidog-overrides: {}
              required:
                - payment_method
          x-apidog-orders:
            - 01JJ90T6D94VC68GZZQWCTFJCZ
          properties:
            payment_method: &ref_0
              type: array
              description: >-
                The various methods of payment that are offered to a specific
                group of customers. List of payment methods can be found
                [here](https://docs.salla.dev/api-5394164).
              items:
                type: string
            shipping: &ref_1
              type: array
              description: >-
                The various delivery methods that are accessible or offered to a
                specific group of customers.
              items:
                type: string
          required:
            - payment_method
            - shipping
          x-apidog-ignore-properties:
            - payment_method
            - shipping
      x-apidog-orders:
        - id
        - name
        - conditions
        - features
      required:
        - id
        - name
        - conditions
        - features
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    CustomerGroupFeatures:
      title: CustomerGroupFeatures
      type: object
      properties:
        payment_method: *ref_0
        shipping: *ref_1
      x-apidog-orders:
        - payment_method
        - shipping
      deprecated: true
      required:
        - payment_method
        - shipping
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

## apis-customer-groups/Update-Customer-Group-Salla-Merchant-API-Salla-Docs

# Update Customer Group

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/groups/{group}:
    put:
      summary: Update Customer Group
      deprecated: false
      description: >-
        This endpoint allows you to update a customer group by passing the
        `group` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Update-Group
      tags:
        - Default module/Merchant API/APIs/Customer Groups
        - Customer Groups
      parameters:
        - name: group
          in: path
          description: >-
            Unique identifier assigned to a customer group. List of customer
            group IDs can be found [here](https://docs.salla.dev/api-5394129).
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/customerGroup_request_body'
            example:
              name: VIP
              conditions:
                - type: total_sales
                  symbol: between
                  min_value: 100
                  max_value: 500
              features:
                payment_method:
                  - credit_card
                  - mada
                  - bank
                  - cod
                  - apple_pay
                  - stc_pay
                shipping:
                  - all
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/customerGroup_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 21314237
                  name: VIP
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
                    customers.read_write
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
                  code: validation_failed
                  message: Validation is not successful
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateGroup
      x-salla-php-return-type: CustomerGroup
      x-apidog-folder: Default module/Merchant API/APIs/Customer Groups
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394132-run
components:
  schemas:
    customerGroup_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            A unique title or label assigned to a collection of items,
            individuals, or entities that share common characteristics, serving
            as a means of categorization or identification within a broader
            context or organization. List of customers can be found
            [here](https://docs.salla.dev/api-5394121).
        conditions:
          type: array
          description: >-
            An array of conditions to consider when automatically assigning
            customers to a group.
          items:
            type: object
            properties:
              type:
                type: string
                description: The type of the condition.
              symbol:
                type: string
                description: A condition operator.
                enum:
                  - '>'
                  - <
                  - between
              value:
                type: number
                description: A condition value (value to be after the operator).
              min_value:
                type: number
                description: >-
                  Refers to the minimum possible value. <b>Required</b> if
                  `symbol` equals `between`.
              max_value:
                type: number
                description: >-
                  Refers to the maximum possible value. <b>Required</b> if
                  `symbol` equals `between`
            x-apidog-orders:
              - type
              - symbol
              - value
              - min_value
              - max_value
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - name
        - conditions
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    customerGroup_response_body:
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
          $ref: '#/components/schemas/CustomerGroup'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    CustomerGroup:
      description: >-
        Detailed structure of the customer group model object showing its fields
        and data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: CustomerGroup
      properties:
        id:
          type: number
          description: The unique identifier assigned to a specific group of customers.
        name:
          type: string
          description: The name or label for a the Customer Group.
        conditions:
          type: object
          description: >-
            Conditions for group membership, such as `total_sales > 100`,
            determine auto-assignment. For example, customers with sales
            exceeding 100 are added to the group automatically.
          properties:
            type:
              type: string
              description: "The type of the condition.\r\n"
            symbol:
              type: string
              description: >-
                A symbol or function defining relationships between values, used
                in conditional logic.
            value:
              type: number
              description: The condition after the operator.
          x-apidog-orders:
            - type
            - symbol
            - value
          required:
            - type
            - symbol
            - value
          x-apidog-ignore-properties: []
        features:
          type: object
          x-apidog-refs:
            01JJ90T6D94VC68GZZQWCTFJCZ:
              $ref: '#/components/schemas/CustomerGroupFeatures'
              x-apidog-overrides: {}
              required:
                - payment_method
          x-apidog-orders:
            - 01JJ90T6D94VC68GZZQWCTFJCZ
          properties:
            payment_method: &ref_0
              type: array
              description: >-
                The various methods of payment that are offered to a specific
                group of customers. List of payment methods can be found
                [here](https://docs.salla.dev/api-5394164).
              items:
                type: string
            shipping: &ref_1
              type: array
              description: >-
                The various delivery methods that are accessible or offered to a
                specific group of customers.
              items:
                type: string
          required:
            - payment_method
            - shipping
          x-apidog-ignore-properties:
            - payment_method
            - shipping
      x-apidog-orders:
        - id
        - name
        - conditions
        - features
      required:
        - id
        - name
        - conditions
        - features
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    CustomerGroupFeatures:
      title: CustomerGroupFeatures
      type: object
      properties:
        payment_method: *ref_0
        shipping: *ref_1
      x-apidog-orders:
        - payment_method
        - shipping
      deprecated: true
      required:
        - payment_method
        - shipping
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

