# Settlements

## Table of Contents

- [settlements/Create-Instant-Settlement-Partners-Apps-APIs-Salla-Docs](#settlements-create-instant-settlement-partners-apps-apis-salla-docs)
- [settlements/Instant-Settlement-Details-Partners-Apps-APIs-Salla-Docs](#settlements-instant-settlement-details-partners-apps-apis-salla-docs)
- [settlements/List-Instant-Settlements-Partners-Apps-APIs-Salla-Docs](#settlements-list-instant-settlements-partners-apps-apis-salla-docs)
- [settlements/Update-Instant-Settlement-Partners-Apps-APIs-Salla-Docs](#settlements-update-instant-settlement-partners-apps-apis-salla-docs)

---

## settlements/Create-Instant-Settlement-Partners-Apps-APIs-Salla-Docs

# Create Instant Settlement

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settlements/instant:
    post:
      summary: Create Instant Settlement
      deprecated: false
      description: >+
        This endpoint allows you to temporarily withhold a specific amount of
        money for settlement from the Merchant's wallet.


        :::warning[]

        This endpoint is allowed only for dropshipping applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `settlements.read_write` - Settlements Read & Write

        </Accordion>

      tags:
        - Partner Apps APIs/Settlements
        - Settlements
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                reference_id:
                  type: integer
                  description: >-
                    Order's reference ID. Get a list of Order Reference IDs from
                    [here](https://docs.salla.dev/api-5394146)
                  examples:
                    - 566345
                amount:
                  type: number
                  description: >-
                    The amount to hold. It should be less than or equal to the
                    order total, and up to two decimal points
                  title: ''
                  examples:
                    - 57.32
                    - 120
              x-apidog-orders:
                - reference_id
                - amount
              required:
                - reference_id
                - amount
              x-apidog-ignore-properties: []
            example:
              reference_id: 9363145
              amount: 120.21
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/settlement_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 587246469
                  reference_id: 385748
                  amount: 200
                  status: pending
          headers: {}
          x-apidog-name: Created
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
                    settlements.read
          headers: {}
          x-apidog-name: Unauthorized
        '403':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: Application not have permission to holding money
          headers: {}
          x-apidog-name: Forbidden
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: error_notFound_404
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
                    reference_id:
                      - Order not use Salla Gateway or money transfered to store
                      - No order passed
                    amount:
                      - No order passed
          headers: {}
          x-apidog-name: error_validation
      security:
        - bearer: []
      x-apidog-folder: Partner Apps APIs/Settlements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8548925-run
components:
  schemas:
    settlement_response_body:
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
          $ref: '#/components/schemas/Settlement'
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
    Settlement:
      type: object
      properties:
        id:
          type: number
          description: Settlement unique ID
        reference_id:
          type: integer
          description: >-
            Order's reference ID. Get a list of Order Reference IDs from
            [here](https://docs.salla.dev/api-5394146)
          examples:
            - 653443
        amount:
          type: number
          description: The amount held from the Merchant's wallet
          examples:
            - 153.35
            - 120
          format: float
        status:
          type: string
          description: The settlement status
          enum:
            - pending
            - ready
            - settled
            - canceled
          examples:
            - pending
          x-apidog-enum:
            - name: ''
              value: pending
              description: the very first status when creating the holding payment
            - name: ''
              value: ready
              description: 'when the Partner approves the holding payment '
            - name: ''
              value: settled
              description: when money is successfully transfered to the Partner
            - name: ''
              value: canceled
              description: when the Merchant cancels the order
      x-apidog-orders:
        - id
        - reference_id
        - amount
        - status
      required:
        - id
        - reference_id
        - amount
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

## settlements/Instant-Settlement-Details-Partners-Apps-APIs-Salla-Docs

# Instant Settlement Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settlements/instant/{id}:
    get:
      summary: Instant Settlement Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch the details for a specific settlement
        by passing the `id` as a path parameter.


        :::warning[]

        This endpoint is allowed only for dropshipping applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `settlements.read` - Settlements Read Only

        </Accordion>
      tags:
        - Partner Apps APIs/Settlements
        - Settlements
      parameters:
        - name: id
          in: path
          description: >-
            Unique identification number assigned to the Settlement. Get a list
            of Settlement IDs from [here](https://docs.salla.dev/api-8548913)
          required: true
          example: '897542106'
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/settlement_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 587246469
                  reference_id: 385748
                  amount: 200
                  status: pending
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
                    settlements.read
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
                    type: number
                    description: status
                  success:
                    type: boolean
                    default: false
                  error:
                    type: object
                    properties:
                      code:
                        type: string
                        description: Error
                      message:
                        type: string
                        description: Error Message
                    x-apidog-orders:
                      - code
                      - message
                    x-apidog-ignore-properties: []
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
                  message: Application not have permission to holding money
          headers: {}
          x-apidog-name: Forbidden
        '404':
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
                    x-stoplight:
                      id: f4ajks6ba59j4
                    description: >-
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  error:
                    $ref: '#/components/schemas/NotFound'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: Record Not Found
      security:
        - bearer: []
      x-apidog-folder: Partner Apps APIs/Settlements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9798033-run
components:
  schemas:
    settlement_response_body:
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
          $ref: '#/components/schemas/Settlement'
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
    Settlement:
      type: object
      properties:
        id:
          type: number
          description: Settlement unique ID
        reference_id:
          type: integer
          description: >-
            Order's reference ID. Get a list of Order Reference IDs from
            [here](https://docs.salla.dev/api-5394146)
          examples:
            - 653443
        amount:
          type: number
          description: The amount held from the Merchant's wallet
          examples:
            - 153.35
            - 120
          format: float
        status:
          type: string
          description: The settlement status
          enum:
            - pending
            - ready
            - settled
            - canceled
          examples:
            - pending
          x-apidog-enum:
            - name: ''
              value: pending
              description: the very first status when creating the holding payment
            - name: ''
              value: ready
              description: 'when the Partner approves the holding payment '
            - name: ''
              value: settled
              description: when money is successfully transfered to the Partner
            - name: ''
              value: canceled
              description: when the Merchant cancels the order
      x-apidog-orders:
        - id
        - reference_id
        - amount
        - status
      required:
        - id
        - reference_id
        - amount
        - status
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    NotFound:
      type: object
      properties:
        code:
          anyOf:
            - type: string
            - type: number
          description: >-
            Not Found Response error code, a numeric or alphanumeric unique
            identifier used to represent the error.
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when the
            response is not found or explain the error.
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

## settlements/List-Instant-Settlements-Partners-Apps-APIs-Salla-Docs

# List Instant Settlements

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settlements/instant:
    get:
      summary: List Instant Settlements
      deprecated: false
      description: >-
        This endpoint lists all the instant settlements including details such
        as amount and status that are associated with the store.


        :::warning[]

        This endpoint is allowed only for dropshipping applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `settlements.read` - Settlements Read Only

        </Accordion>
      tags:
        - Partner Apps APIs/Settlements
        - Settlements
      parameters:
        - name: reference_id
          in: query
          description: >-
            Filter by order's reference ID. Get a list of Order Reference IDs
            from [here](https://docs.salla.dev/api-5394146)
          required: false
          schema:
            type: integer
        - name: page
          in: query
          description: 'Filter by page number '
          required: false
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/settlements_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 40643814
                    reference_id: 1444968
                    amount: 56.21
                    status: settled
                  - id: 814209365
                    reference_id: 913456
                    amount: 50
                    status: ready
                  - id: 172398348
                    reference_id: 324144
                    amount: 100
                    status: pending
                  - id: 3499435415
                    reference_id: 694175
                    amount: 37.41
                    status: pending
                  - id: 989289633
                    reference_id: 360174
                    amount: 469.7
                    status: pending
                  - id: 1749842897
                    reference_id: 460169
                    amount: 85.36
                    status: ready
                  - id: 52596436
                    reference_id: 4016556
                    amount: 1000
                    status: pending
                  - id: 1298194523
                    reference_id: 4034135
                    amount: 11.2
                    status: pending
                  - id: 1939592358
                    reference_id: 3879624
                    amount: 118
                    status: pending
                  - id: 566146469
                    reference_id: 3879628
                    amount: 200
                    status: pending
                pagination:
                  count: 10
                  total: 10
                  perPage: 15
                  currentPage: 1
                  totalPages: 1
                  links:
                    previous: http://api.salla.dev/admin/v2/setllements/instant?page=3
                    next: http://api.salla.dev/admin/v2/setllements/instant?page=2
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
                    settlements.read
          headers: {}
          x-apidog-name: Unauthorized
        '403':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: Application not have permission to holding money
          headers: {}
          x-apidog-name: Forbidden
      security:
        - bearer: []
      x-apidog-folder: Partner Apps APIs/Settlements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8548913-run
components:
  schemas:
    settlements_response_body:
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
            $ref: '#/components/schemas/Settlement'
        pagination:
          $ref: '#/components/schemas/Pagination'
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      x-apidog-refs: {}
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
    Settlement:
      type: object
      properties:
        id:
          type: number
          description: Settlement unique ID
        reference_id:
          type: integer
          description: >-
            Order's reference ID. Get a list of Order Reference IDs from
            [here](https://docs.salla.dev/api-5394146)
          examples:
            - 653443
        amount:
          type: number
          description: The amount held from the Merchant's wallet
          examples:
            - 153.35
            - 120
          format: float
        status:
          type: string
          description: The settlement status
          enum:
            - pending
            - ready
            - settled
            - canceled
          examples:
            - pending
          x-apidog-enum:
            - name: ''
              value: pending
              description: the very first status when creating the holding payment
            - name: ''
              value: ready
              description: 'when the Partner approves the holding payment '
            - name: ''
              value: settled
              description: when money is successfully transfered to the Partner
            - name: ''
              value: canceled
              description: when the Merchant cancels the order
      x-apidog-orders:
        - id
        - reference_id
        - amount
        - status
      required:
        - id
        - reference_id
        - amount
        - status
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
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

## settlements/Update-Instant-Settlement-Partners-Apps-APIs-Salla-Docs

# Update Instant Settlement

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settlements/instant/{id}:
    put:
      summary: Update Instant Settlement
      deprecated: false
      description: >-
        This endpoint allows you to update the status and the amount of a
        specific settlment by by passing the `id` as a path parameter.


        :::warning[]

        This endpoint is allowed only for dropshipping applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `settlements.read_write` - Settlements Read & Write

        </Accordion>
      tags:
        - Partner Apps APIs/Settlements
        - Settlements
      parameters:
        - name: id
          in: path
          description: >-
            Unique identification number assigned to the Settlement. Get a list
            of Settlement IDs from [here](https://docs.salla.dev/api-8548913)
          required: true
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                amount:
                  type: number
                  description: >-
                    The amount to hold. It should be <= the order total, and up
                    to two decimal points
                status:
                  type: string
                  description: The settlement status
                  enum:
                    - pending
                    - ready
                  examples:
                    - pending
                    - ready
                  x-apidog-enum:
                    - value: pending
                      name: ''
                      description: pending
                    - value: ready
                      name: ''
                      description: ready
              x-apidog-orders:
                - amount
                - status
              x-apidog-ignore-properties: []
            example:
              amount: 9823743
              status: ready
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/settlement_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 33787469
                  reference_id: 685748
                  amount: 200
                  status: ready
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
                    settlements.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '403':
          description: ''
          content:
            application/json:
              schema:
                description: >-
                  Response status code, a numeric or alphanumeric identifier
                  used to convey the outcome or status of a request, operation,
                  or transaction in various systems and applications, typically
                  indicating whether the action was successful, encountered an
                  error, or resulted in a specific condition.
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: Application not have permission to holding money
          headers: {}
          x-apidog-name: Forbidden
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: Record Not Found
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_validation_422'
              examples:
                '2':
                  summary: 422 validation error
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        amount:
                          - Amount must not exceed two decimal points
                        status:
                          - Allowed status values should be ready or pending
                '6':
                  summary: Amount is <= 0
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        amount:
                          - The Amount must be at least 1.
          headers: {}
          x-apidog-name: Parameter Error
      security:
        - bearer: []
      x-apidog-folder: Partner Apps APIs/Settlements
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8549773-run
components:
  schemas:
    settlement_response_body:
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
          $ref: '#/components/schemas/Settlement'
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
    Settlement:
      type: object
      properties:
        id:
          type: number
          description: Settlement unique ID
        reference_id:
          type: integer
          description: >-
            Order's reference ID. Get a list of Order Reference IDs from
            [here](https://docs.salla.dev/api-5394146)
          examples:
            - 653443
        amount:
          type: number
          description: The amount held from the Merchant's wallet
          examples:
            - 153.35
            - 120
          format: float
        status:
          type: string
          description: The settlement status
          enum:
            - pending
            - ready
            - settled
            - canceled
          examples:
            - pending
          x-apidog-enum:
            - name: ''
              value: pending
              description: the very first status when creating the holding payment
            - name: ''
              value: ready
              description: 'when the Partner approves the holding payment '
            - name: ''
              value: settled
              description: when money is successfully transfered to the Partner
            - name: ''
              value: canceled
              description: when the Merchant cancels the order
      x-apidog-orders:
        - id
        - reference_id
        - amount
        - status
      required:
        - id
        - reference_id
        - amount
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

