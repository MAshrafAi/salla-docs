# Apis Order Assignment

## Table of Contents

- [apis-order-assignment/Create-Auto-Assignment-Rules-Salla-Merchant-API-Salla-Docs](#apis-order-assignment-create-auto-assignment-rules-salla-merchant-api-salla-docs)
- [apis-order-assignment/List-Auto-Assignment-Rules-Salla-Merchant-API-Salla-Docs](#apis-order-assignment-list-auto-assignment-rules-salla-merchant-api-salla-docs)
- [apis-order-assignment/Order-Assigned-Employees-Details-Salla-Merchant-API-Salla-Docs](#apis-order-assignment-order-assigned-employees-details-salla-merchant-api-salla-docs)
- [apis-order-assignment/Update-Auto-Assignment-Rule-Salla-Merchant-API-Salla-Docs](#apis-order-assignment-update-auto-assignment-rule-salla-merchant-api-salla-docs)

---

## apis-order-assignment/Create-Auto-Assignment-Rules-Salla-Merchant-API-Salla-Docs

# Create Auto Assignment Rules

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/assignment/rules:
    post:
      summary: Create Auto Assignment Rules
      deprecated: false
      description: |-
        This endpoint allows you to create multiple order auto assignment rules.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `orders.read_write` - Orders Read & Write
        </Accordion>
      operationId: post-orders-assignment-rules
      tags:
        - Default module/Merchant API/APIs/Order Assignment
        - Order Assignment
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/orderAutoAssignment_request_body'
            example:
              user_id: 2897329
              rules:
                - entity: city
                  value: '2097610897'
                - entity: country
                  value: SA
                - entity: status
                  value: '7646469'
                - entity: branch
                  value: '566146469'
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/orderAutoAssignment_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 123123123
                  user_id: 2897329
                  rules:
                    - entity: city
                      value: '2097610897'
                    - entity: country
                      value: SA
                    - entity: status
                      value: '7646469'
                    - entity: branch
                      value: '566146469'
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
                    orders.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Assignment
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5677301-run
components:
  schemas:
    orderAutoAssignment_request_body:
      type: object
      properties:
        user_id:
          type: integer
          description: >-
            Employee User ID. List of Empoloyee can be found
            [here](https://docs.salla.dev/api-5394259)
        rules:
          type: array
          items:
            type: object
            properties:
              entity:
                type: string
                description: Order Rule Entity Name
              value:
                type: string
                description: Order Rule Entity Value
            required:
              - entity
              - value
            x-apidog-orders:
              - entity
              - value
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - user_id
        - rules
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    orderAutoAssignment_response_body:
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
          $ref: '#/components/schemas/OrderAutoAssignment'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OrderAutoAssignment:
      title: OrderAutoAssignment
      type: object
      properties:
        id:
          type: integer
          description: A unique identifier assigned to a specific order.
        user_id:
          type: integer
          description: >-
            A unique identifier assigned to a user of a system, application, or
            website. 
        rules:
          type: array
          items:
            type: object
            properties:
              entity:
                type: string
                description: Name of the intity.
              value:
                type: string
                description: Value of the entity.
            x-apidog-orders:
              - entity
              - value
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - user_id
        - rules
      required:
        - id
        - user_id
        - rules
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

## apis-order-assignment/List-Auto-Assignment-Rules-Salla-Merchant-API-Salla-Docs

# List Auto Assignment Rules

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/assignment/rules:
    get:
      summary: List Auto Assignment Rules
      deprecated: false
      description: >-
        This endpoint allows you to retrieve all the orders auto-assignment
        rules per employee.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read` - Orders Read Only

        </Accordion>
      operationId: get-orders-assignment
      tags:
        - Default module/Merchant API/APIs/Order Assignment
        - Order Assignment
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ordersAutoAssignment_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 219372983
                    user_id: 461258256
                    rules:
                      - entity: city
                        value: '2097610897'
                      - entity: country
                        value: SA
                      - entity: status
                        value: '7646469'
                      - entity: branch
                        value: '566146469'
                  - id: 219372983
                    user_id: 3125825677
                    rules:
                      - entity: status
                        value: '5546369'
                      - entity: branch
                        value: '21654322'
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
                    employee_id:
                      - حقل employee id مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Assignment
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5576999-run
components:
  schemas:
    ordersAutoAssignment_response_body:
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
            $ref: '#/components/schemas/OrderAutoAssignment'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OrderAutoAssignment:
      title: OrderAutoAssignment
      type: object
      properties:
        id:
          type: integer
          description: A unique identifier assigned to a specific order.
        user_id:
          type: integer
          description: >-
            A unique identifier assigned to a user of a system, application, or
            website. 
        rules:
          type: array
          items:
            type: object
            properties:
              entity:
                type: string
                description: Name of the intity.
              value:
                type: string
                description: Value of the entity.
            x-apidog-orders:
              - entity
              - value
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - user_id
        - rules
      required:
        - id
        - user_id
        - rules
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

## apis-order-assignment/Order-Assigned-Employees-Details-Salla-Merchant-API-Salla-Docs

# Order Assigned Employees Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/assignment/{order_id}:
    get:
      summary: Order Assigned Employees Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch the assigned employees' details for a
        specific order by passing the `order_id` as a path parameter. 
      operationId: get-orders-assignment-order
      tags:
        - Default module/Merchant API/APIs/Order Assignment
        - Order Assignment
      parameters:
        - name: order_id
          in: path
          description: >-
            Unique identification number assigend to an order. Get a list of
            Order IDs from [here](https://docs.salla.dev/api-5394146).
          required: true
          example: 525144736
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/orderAssignedEmployees_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 525144736
                    name: Ahmed Mohammed
                    avatar: >-
                      http://www.gravatar.com/avatar/d41d8cd98f00b204e9800998ecf8427e?s=80&d=mm&r=g
          headers: {}
          x-apidog-name: Success
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Assignment
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-6930855-run
components:
  schemas:
    orderAssignedEmployees_response_body:
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
            $ref: '#/components/schemas/OrderAssignedEmployees'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OrderAssignedEmployees:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier assigned to an employee.
        name:
          type: string
          description: Employee name.
        avatar:
          type: string
          description: Employee avatar image
      x-apidog-orders:
        - id
        - name
        - avatar
      required:
        - id
        - name
        - avatar
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

## apis-order-assignment/Update-Auto-Assignment-Rule-Salla-Merchant-API-Salla-Docs

# Update Auto Assignment Rule

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/assignment/rules/{rule_id}:
    put:
      summary: Update Auto Assignment Rule
      deprecated: false
      description: >-
        This endpoint allows you to update the order rules per employee by
        passing the `rule_id` as the path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-assignment-rules
      tags:
        - Default module/Merchant API/APIs/Order Assignment
        - Order Assignment
      parameters:
        - name: rule_id
          in: path
          description: >-
            Unique identifier assigned to an Order Rule. Get a list of order
            rule IDs [here](https://docs.salla.dev/5576999e0).
          required: true
          example: 90828
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              type: array
              items:
                type: object
                properties:
                  entity:
                    type: string
                    description: Order Rule Entity Name
                  value:
                    type: string
                    description: Order Rule Entity Value
                x-apidog-orders:
                  - entity
                  - value
                required:
                  - entity
                  - value
                x-apidog-ignore-properties: []
            example:
              - entity: city
                value: '2097610897'
              - entity: country
                value: SA
              - entity: status
                value: '7646469'
              - entity: branch
                value: '566146469'
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/orderAutoAssignment_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 123123123
                  user_id: 2897329
                  rules:
                    - entity: city
                      value: '2097610897'
                    - entity: country
                      value: SA
                    - entity: status
                      value: '7646469'
                    - entity: branch
                      value: '566146469'
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
                  code: error
                  message: alert.invalid_fields
                  fields:
                    rules.city.0:
                      - حقل المدينة غير صالح
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Order Assignment
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5581833-run
components:
  schemas:
    orderAutoAssignment_response_body:
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
          $ref: '#/components/schemas/OrderAutoAssignment'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OrderAutoAssignment:
      title: OrderAutoAssignment
      type: object
      properties:
        id:
          type: integer
          description: A unique identifier assigned to a specific order.
        user_id:
          type: integer
          description: >-
            A unique identifier assigned to a user of a system, application, or
            website. 
        rules:
          type: array
          items:
            type: object
            properties:
              entity:
                type: string
                description: Name of the intity.
              value:
                type: string
                description: Value of the entity.
            x-apidog-orders:
              - entity
              - value
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - user_id
        - rules
      required:
        - id
        - user_id
        - rules
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

