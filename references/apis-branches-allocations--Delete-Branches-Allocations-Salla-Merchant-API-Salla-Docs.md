# Apis Branches Allocations  Delete Branches Allocations Salla Merchant Api Salla Docs

## Table of Contents

- [apis-branches-allocations/Delete-Branches-Allocations-Salla-Merchant-API-Salla-Docs](#apis-branches-allocations-delete-branches-allocations-salla-merchant-api-salla-docs)
- [apis-branches-allocations/List-Brnaches-Allocations-Salla-Merchant-API-Salla-Docs](#apis-branches-allocations-list-brnaches-allocations-salla-merchant-api-salla-docs)
- [apis-branches-allocations/Update-Branches-Allocations-Salla-Merchant-API-Salla-Docs](#apis-branches-allocations-update-branches-allocations-salla-merchant-api-salla-docs)

---

## apis-branches-allocations/Delete-Branches-Allocations-Salla-Merchant-API-Salla-Docs

# Delete Branches Allocations

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/allocation/{id}:
    delete:
      summary: Delete Branches Allocations
      deprecated: false
      description: |-
        This endpoint allows you to delete a specific allocation branch.

        :::warning[]
        This endpoint is accessable only for allowed applications.
        :::

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `branches.read_write`- Branchs Read & Write
        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Branches Allocations
        - Branch Allocations
      parameters:
        - name: id
          in: path
          description: >-
            Branch Allocated ID. Get a list of IDs from
            [here](https://docs.salla.dev/api-18495252)
          required: true
          example: 246711701
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
                    type: number
                    description: >-
                      Response status code, a numeric or alphanumeric identifier
                      used to convey the outcome or status of a request,
                      operation, or transaction in various systems and
                      applications, typically indicating whether the action was
                      successful, encountered an error, or resulted in a
                      specific condition.Response status Code
                  success:
                    type: boolean
                    description: >-
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  data: &ref_0
                    $ref: '#/components/schemas/DeleteSuccess'
                x-apidog-orders:
                  - 01JYZVWVR33VWETDT0JS55RZQP
                x-apidog-refs:
                  01JYZVWVR33VWETDT0JS55RZQP:
                    $ref: '#/components/schemas/delete_success'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
              example:
                status: 200
                success: true
                data:
                  message: تم الحذف بنجاح
          headers: {}
          x-apidog-name: Success
        '401':
          description: ''
          content:
            application/json:
              schema:
                title: ''
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
                  error: &ref_1
                    $ref: '#/components/schemas/Unauthorized'
                x-apidog-orders:
                  - 01K0KZ01X7C14QW6S1672BY4MC
                x-apidog-refs:
                  01K0KZ01X7C14QW6S1672BY4MC:
                    $ref: '#/components/schemas/error_unauthorized_401'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: The access token is invalid
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
                  - 01K0KTAFQ8Z6F8B70FXJ3QQPC1
                x-apidog-refs:
                  01K0KTAFQ8Z6F8B70FXJ3QQPC1:
                    $ref: '#/components/schemas/error_forbidden_403'
                required:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: التطبيق لايدعم هذه الميزة
          headers: {}
          x-apidog-name: Forbidden
        '404':
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
                  - 01K0KV00FPM1NWMEC66RZSW8BV
                required:
                  - status
                  - success
                  - error
                x-apidog-refs:
                  01K0KV00FPM1NWMEC66RZSW8BV:
                    $ref: '#/components/schemas/Object%20Not%20Found(404)'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branches Allocations
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-18495551-run
components:
  schemas:
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
        data: *ref_0
      x-apidog-orders:
        - status
        - success
        - data
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
        error: *ref_1
      x-apidog-orders:
        - status
        - success
        - error
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

## apis-branches-allocations/List-Brnaches-Allocations-Salla-Merchant-API-Salla-Docs

# List Branches Allocations

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/allocation:
    get:
      summary: List Branches Allocations
      deprecated: false
      description: >-
        This endpoint allows you to fetch a list of allocated branches with
        their rules, showing which shipping companies are assigned based on
        branch location.


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `branches.read`- Branchs Read

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Branches Allocations
        - Branch Allocations
      parameters:
        - name: per_page
          in: query
          description: Branch allocations limit per page
          required: false
          example: 20
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AllocatedBranches_response_body%20Copy'
              example:
                status: 200
                success: true
                data:
                  - id: 1939592358
                    name: Allocation Rout Name 1
                    company_id: 665151403
                    priority: 1
                    rules:
                      - type: total_items
                        operator: '>='
                        value: '15'
                    action:
                      type: branch
                      strategy: null
                      branch_ids:
                        - '1937885067'
                      single_branch_only: false
                  - id: 1473353380
                    name: Allocation Rout Name 2
                    company_id: 665151403
                    priority: 2
                    rules:
                      - type: total_quantity
                        operator: '>='
                        value: '3'
                    action:
                      type: branches
                      strategy: most_stock
                      branch_ids: []
                      single_branch_only: false
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
                title: ''
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
                  error: &ref_0
                    $ref: '#/components/schemas/Unauthorized'
                x-apidog-orders:
                  - 01K0KY99KQ3X7QTD6KCB4G79C1
                x-apidog-refs:
                  01K0KY99KQ3X7QTD6KCB4G79C1:
                    $ref: '#/components/schemas/error_unauthorized_401'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: token is not valid
          headers: {}
          x-apidog-name: Unauthorized
        '403':
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
                x-apidog-refs:
                  01K0KSG3QM50WD46S0D5SNMKEK:
                    $ref: '#/components/schemas/error_forbidden_403'
                x-apidog-orders:
                  - 01K0KSG3QM50WD46S0D5SNMKEK
                required:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: التطبيق لايدعم هذه الميزة
          headers: {}
          x-apidog-name: Forbidden
        '422':
          description: ''
          content:
            application/json:
              schema:
                title: ''
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
                  error: &ref_1
                    $ref: '#/components/schemas/Validation'
                x-apidog-orders:
                  - 01K0KZ2N73PBJY3G5ZC9KS545P
                x-apidog-refs:
                  01K0KZ2N73PBJY3G5ZC9KS545P:
                    $ref: '#/components/schemas/error_validation_422'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 422
                success: false
                error:
                  code: error
                  message: alert.invalid_fields
                  fields:
                    branch_id:
                      - حقل branch id غير صالح
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branches Allocations
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-18495252-run
components:
  schemas:
    AllocatedBranches_response_body Copy:
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
            $ref: '#/components/schemas/AllocatedBranch'
        pagination:
          $ref: '#/components/schemas/Pagination'
      required:
        - status
        - success
        - data
        - pagination
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
    AllocatedBranch:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier of the allocation route.
        name:
          type: string
          description: Descriptive name of the allocation route for easy identification.
        company_id:
          type: integer
          description: >-
            The ID of the shipping company to which this allocation route
            applies.
          nullable: true
        priority:
          type: integer
          description: The sort
        rules:
          type: array
          items:
            $ref: '#/components/schemas/AllocationRouteRules'
          description: A set of conditions that must be met for this route to be applied.
        action:
          $ref: '#/components/schemas/AllocationRouteAction'
          description: The action to be taken when all the defined rules are satisfied.
      required:
        - id
        - priority
        - rules
        - action
      x-apidog-orders:
        - id
        - name
        - company_id
        - priority
        - rules
        - action
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AllocationRouteAction:
      type: object
      properties:
        type:
          type: string
          description: |-
            Defines the`type` of allocation action:
            -`branch`: allocate to a specific branch.
            -`branches`: allocate using a strategy across multiple branches.
          enum:
            - branch
            - branches
          x-apidog-enum:
            - value: branch
              name: branch
              description: Allocate to branches
            - value: branches
              name: branches
              description: Allocate using a strategy across multiple branches
        branch_ids:
          type: array
          items:
            type: number
          description: The branches ids if `type` is`branch`
          nullable: true
        strategy:
          type: string
          description: The`strategy` slug such as`most_stock` (if `type` is`branches`).
          enum:
            - closest_to_customer
            - most_stock
            - priority
          x-apidog-enum:
            - value: closest_to_customer
              name: ''
              description: Allocation based on being the closest to the customer
            - value: most_stock
              name: ''
              description: Allocation based on the most available inventory stock items
            - value: priority
              name: ''
              description: Allocation based on priority
          nullable: true
        single_branch_only:
          type: boolean
          description: >-
            Determines whether the deduction will be applied to a single branch
            or across multiple branches.
          nullable: true
      required:
        - type
        - branch_ids
        - strategy
        - single_branch_only
      x-apidog-orders:
        - type
        - branch_ids
        - strategy
        - single_branch_only
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AllocationRouteRules:
      type: object
      properties:
        type:
          type: string
          description: |-
            The type of rule to evaluate. Examples:
            `total_items`
          enum:
            - destination_country
            - destination_city
            - total_items
            - total_quantity
            - product_tags
            - skus
            - scope_id
          x-apidog-enum:
            - value: destination_country
              name: destination_country
              description: Matches order based on the shipping destination’s country code.
            - value: destination_city
              name: destination_city
              description: >-
                Matches order based on the shipping destination’s city name or
                code.
            - value: total_items
              name: total_items
              description: Matches order based on the total number of items in the order.
            - value: total_quantity
              name: total_quantity
              description: Matches orders based on the total quantity of products ordered
            - value: product_tags
              name: product_tags
              description: Matches products based on the tags assigned to them
            - value: skus
              name: skus
              description: Matches orders containing products that have specific SKU.
            - value: scope_id
              name: scope_id
              description: >-
                Matches orders based on the origin market/store (e.g., a
                particular marketplace or region).
        operator:
          type: string
          description: >-
            Comparison operator used for the rule condition. Supported
            operators:`==`, ` !=`, `>`, `<`, `>=`, `<=`
          enum:
            - '>'
            - '>='
            - <
            - <=
            - '=='
            - '!='
            - in
            - not_in
            - any_in
          x-apidog-enum:
            - value: '>'
              name: ''
              description: Matches values that are greater than the specified value
            - value: '>='
              name: ''
              description: >-
                Matches values that are greater than or equal to the specified
                value
            - value: <
              name: ''
              description: Matches values that are less than the specified value.
            - value: <=
              name: ''
              description: >-
                Matches values that are less than or equal to the specified
                value.
            - value: '=='
              name: ''
              description: Matches values that are exactly equal to the specified value
            - value: '!='
              name: ''
              description: Matches values that are not equal to the specified value.
            - value: in
              name: ''
              description: ' Matches values that exist in a specified list of values'
            - value: not_in
              name: ''
              description: Matches values that do not exist in a specified list of values.
            - value: any_in
              name: ''
              description: >-
                Matches values that exist in any of the specified list of
                values.
        value:
          type: array
          items:
            type: string
          description: >-
            The value against which the order’s attribute is compared (based on
            the`type`).
      x-apidog-orders:
        - type
        - operator
        - value
      required:
        - type
        - operator
        - value
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
        error: *ref_0
      x-apidog-orders:
        - status
        - success
        - error
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
        error: *ref_1
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

## apis-branches-allocations/Update-Branches-Allocations-Salla-Merchant-API-Salla-Docs

# Update Branches Allocations

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/allocation/{Id}:
    put:
      summary: Update Branches Allocations
      deprecated: false
      description: >-
        This endpoint allows you to update a branch’s configuration by passing
        the `id`of the allocated branch as a path parameter, including its
        courier and area allocation rules.


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `branches.read_write`- Branchs Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Branches Allocations
        - Branch Allocations
      parameters:
        - name: Id
          in: path
          description: >-
            Branch Allocated ID. Get a list of IDs from
            [here](https://docs.salla.dev/api-18495252)
          required: true
          example: 246711701
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UpdateAllocatedBranches_request_body'
            example:
              name: Allocation Rout Name Updated
              company_id: '665151403'
              priority: 1
              rules:
                - type: total_quantity
                  operator: '>='
                  value: '3'
              action:
                type: branch
                branch_ids:
                  - '1937885067'
                  - '876438899'
                single_branch_only: false
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AllocatedBranch_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1939592358
                  name: Allocation Rout Name Updated
                  company_id: 665151403
                  priority: 1
                  rules:
                    - type: total_quantity
                      operator: '>='
                      value: '3'
                  action:
                    type: branch
                    strategy: null
                    branch_ids:
                      - '1937885067'
                      - '876438899'
                    single_branch_only: false
          headers: {}
          x-apidog-name: Success
        '401':
          description: ''
          content:
            application/json:
              schema:
                title: ''
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
                  error: &ref_2
                    $ref: '#/components/schemas/Unauthorized'
                x-apidog-orders:
                  - 01K0KYYEA2M0M336SVJE7A1Y4X
                x-apidog-refs:
                  01K0KYYEA2M0M336SVJE7A1Y4X:
                    $ref: '#/components/schemas/error_unauthorized_401'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: The access token is invalid
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
                  - 01K0KT9YMMK3FJB2ED94QFBD2Q
                x-apidog-refs:
                  01K0KT9YMMK3FJB2ED94QFBD2Q:
                    $ref: '#/components/schemas/error_forbidden_403'
                required:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: التطبيق لايدعم هذه الميزة
          headers: {}
          x-apidog-name: Forbidden
        '404':
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
                  - 01K0KTQKVDQ8K9DDZ3BTRX9CRM
                required:
                  - status
                  - success
                  - error
                x-apidog-refs:
                  01K0KTQKVDQ8K9DDZ3BTRX9CRM:
                    $ref: '#/components/schemas/Object%20Not%20Found(404)'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: Not Found
        '422':
          description: ''
          content:
            application/json:
              schema:
                title: ''
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
                  error: &ref_3
                    $ref: '#/components/schemas/Validation'
                x-apidog-orders:
                  - 01K0KTS9JAWN9BK5ZZA1AA27KF
                x-apidog-refs:
                  01K0KTS9JAWN9BK5ZZA1AA27KF:
                    $ref: '#/components/schemas/error_validation_422'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
              example:
                status: 422
                success: false
                error:
                  code: error
                  message: alert.invalid_fields
                  fields:
                    company_id:
                      - حقل company id غير صالح
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branches Allocations
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-18495548-run
components:
  schemas:
    UpdateAllocatedBranches_request_body:
      type: object
      properties:
        name:
          type: string
          description: Descriptive name of the allocation route for easy identification.
          nullable: true
        company_id:
          type: string
          description: >-
            The ID of the shipping company to which this allocation route
            applies.
          nullable: true
        priority:
          type: integer
          description: The allocation sort
          nullable: true
        rules:
          type: array
          items: &ref_0
            $ref: '#/components/schemas/AllocationRouteRules'
          nullable: true
        action: &ref_1
          $ref: '#/components/schemas/AllocationRouteAction'
      x-apidog-orders:
        - name
        - company_id
        - priority
        - rules
        - action
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AllocationRouteAction:
      type: object
      properties:
        type:
          type: string
          description: |-
            Defines the`type` of allocation action:
            -`branch`: allocate to a specific branch.
            -`branches`: allocate using a strategy across multiple branches.
          enum:
            - branch
            - branches
          x-apidog-enum:
            - value: branch
              name: branch
              description: Allocate to branches
            - value: branches
              name: branches
              description: Allocate using a strategy across multiple branches
        branch_ids:
          type: array
          items:
            type: number
          description: The branches ids if `type` is`branch`
          nullable: true
        strategy:
          type: string
          description: The`strategy` slug such as`most_stock` (if `type` is`branches`).
          enum:
            - closest_to_customer
            - most_stock
            - priority
          x-apidog-enum:
            - value: closest_to_customer
              name: ''
              description: Allocation based on being the closest to the customer
            - value: most_stock
              name: ''
              description: Allocation based on the most available inventory stock items
            - value: priority
              name: ''
              description: Allocation based on priority
          nullable: true
        single_branch_only:
          type: boolean
          description: >-
            Determines whether the deduction will be applied to a single branch
            or across multiple branches.
          nullable: true
      required:
        - type
        - branch_ids
        - strategy
        - single_branch_only
      x-apidog-orders:
        - type
        - branch_ids
        - strategy
        - single_branch_only
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AllocationRouteRules:
      type: object
      properties:
        type:
          type: string
          description: |-
            The type of rule to evaluate. Examples:
            `total_items`
          enum:
            - destination_country
            - destination_city
            - total_items
            - total_quantity
            - product_tags
            - skus
            - scope_id
          x-apidog-enum:
            - value: destination_country
              name: destination_country
              description: Matches order based on the shipping destination’s country code.
            - value: destination_city
              name: destination_city
              description: >-
                Matches order based on the shipping destination’s city name or
                code.
            - value: total_items
              name: total_items
              description: Matches order based on the total number of items in the order.
            - value: total_quantity
              name: total_quantity
              description: Matches orders based on the total quantity of products ordered
            - value: product_tags
              name: product_tags
              description: Matches products based on the tags assigned to them
            - value: skus
              name: skus
              description: Matches orders containing products that have specific SKU.
            - value: scope_id
              name: scope_id
              description: >-
                Matches orders based on the origin market/store (e.g., a
                particular marketplace or region).
        operator:
          type: string
          description: >-
            Comparison operator used for the rule condition. Supported
            operators:`==`, ` !=`, `>`, `<`, `>=`, `<=`
          enum:
            - '>'
            - '>='
            - <
            - <=
            - '=='
            - '!='
            - in
            - not_in
            - any_in
          x-apidog-enum:
            - value: '>'
              name: ''
              description: Matches values that are greater than the specified value
            - value: '>='
              name: ''
              description: >-
                Matches values that are greater than or equal to the specified
                value
            - value: <
              name: ''
              description: Matches values that are less than the specified value.
            - value: <=
              name: ''
              description: >-
                Matches values that are less than or equal to the specified
                value.
            - value: '=='
              name: ''
              description: Matches values that are exactly equal to the specified value
            - value: '!='
              name: ''
              description: Matches values that are not equal to the specified value.
            - value: in
              name: ''
              description: ' Matches values that exist in a specified list of values'
            - value: not_in
              name: ''
              description: Matches values that do not exist in a specified list of values.
            - value: any_in
              name: ''
              description: >-
                Matches values that exist in any of the specified list of
                values.
        value:
          type: array
          items:
            type: string
          description: >-
            The value against which the order’s attribute is compared (based on
            the`type`).
      x-apidog-orders:
        - type
        - operator
        - value
      required:
        - type
        - operator
        - value
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AllocatedBranch_response_body:
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
          $ref: '#/components/schemas/AllocatedBranch'
      required:
        - status
        - success
        - data
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-refs: {}
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AllocatedBranch:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier of the allocation route.
        name:
          type: string
          description: Descriptive name of the allocation route for easy identification.
        company_id:
          type: integer
          description: >-
            The ID of the shipping company to which this allocation route
            applies.
          nullable: true
        priority:
          type: integer
          description: The sort
        rules:
          type: array
          items: *ref_0
          description: A set of conditions that must be met for this route to be applied.
        action: *ref_1
      required:
        - id
        - priority
        - rules
        - action
      x-apidog-orders:
        - id
        - name
        - company_id
        - priority
        - rules
        - action
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
        error: *ref_2
      x-apidog-orders:
        - status
        - success
        - error
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
        error: *ref_3
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

