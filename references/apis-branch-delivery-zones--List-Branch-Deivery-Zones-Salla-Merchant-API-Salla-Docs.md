# Apis Branch Delivery Zones  List Branch Deivery Zones Salla Merchant Api Salla Docs

## Table of Contents

- [apis-branch-delivery-zones/List-Branch-Deivery-Zones-Salla-Merchant-API-Salla-Docs](#apis-branch-delivery-zones-list-branch-deivery-zones-salla-merchant-api-salla-docs)
- [apis-branch-delivery-zones/Update-Branch-Delivery-Zone-Salla-Merchant-API-Salla-Docs](#apis-branch-delivery-zones-update-branch-delivery-zone-salla-merchant-api-salla-docs)

---

## apis-branch-delivery-zones/List-Branch-Deivery-Zones-Salla-Merchant-API-Salla-Docs

# List Branch Delivery Zones

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/delivery-zones:
    get:
      summary: List Branch Delivery Zones
      deprecated: false
      description: >-
        This endpoint is used to retrieve delivery zone configurations for
        specific branches. It helps determine which geographical areas (zones)
        each branch can serve for deliveries


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `branches.read`- Branchs Read

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Branch Delivery Zones
        - Branch Delivery Zones
      parameters:
        - name: branch_id
          in: query
          description: ID of the specific branch for which to retrieve delivery zones.
          required: false
          example: 566146469
          schema:
            type: integer
        - name: per_page
          in: query
          description: Delivery zonses limit per page
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
                $ref: '#/components/schemas/BranchDeliveryZones_response_body'
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
                  - 01K6SQGX0T3T8315S7H95QRNW9
                x-apidog-refs:
                  01K6SQGX0T3T8315S7H95QRNW9:
                    $ref: '#/components/schemas/error_unauthorized_401'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
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
                  - 01K6SQ8ZQPYFTYQ0Y0G18A9F20
                required:
                  - status
                  - success
                  - error
                x-apidog-refs:
                  01K6SQ8ZQPYFTYQ0Y0G18A9F20:
                    $ref: '#/components/schemas/error_forbidden_403'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
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
                  - 01K6SQDNH9FSK0QRP31QRKDC6H
                x-apidog-refs:
                  01K6SQDNH9FSK0QRP31QRKDC6H:
                    $ref: '#/components/schemas/error_validation_422'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
          headers: {}
          x-apidog-name: Parameter Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branch Delivery Zones
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-22300545-run
components:
  schemas:
    BranchDeliveryZones_response_body:
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
            $ref: '#/components/schemas/BranchDeliveryZone'
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
    BranchDeliveryZone:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier of the delivery zone configuration
        branch_id:
          type: integer
          description: >-
            The branch to which this delivery zone belongs, list of branches can
            be found [here](https://docs.salla.dev/api-5394224)
        status:
          type: boolean
          description: >-
            Indicates whether the delivery zone is active `(true)` or inactive
            `(false)`
        rules:
          type: object
          properties:
            coverage:
              type: object
              properties:
                enabled:
                  type: boolean
                  description: >-
                    Indicates if the delivery coverage is currently active for
                    this zone
                method:
                  type: string
                  description: |-
                    Specifies the method used to define the delivery area:
                    •`radius`  circular zone based on a center point.
                    •`polygon`  custom geofenced area defined by coordinates.
                radius_meters:
                  type: 'null'
                  description: >-
                    Required when `method` is `radius`; specifies the radius (in
                    meters) of the delivery area.
                coordinates:
                  type: array
                  items:
                    type: object
                    properties:
                      lat:
                        type: number
                        description: Latitude of the polygon point.
                      lng:
                        type: number
                        description: Longitude of the polygon point.
                    required:
                      - lat
                      - lng
                    x-apidog-orders:
                      - lat
                      - lng
                    x-apidog-ignore-properties: []
                  description: >-
                    List of geographic points (`lat`/`lng`) defining the
                    polygonal delivery zone. Required when`method` is `polygon`
                  nullable: true
              required:
                - enabled
                - method
                - radius_meters
                - coordinates
              x-apidog-orders:
                - enabled
                - method
                - radius_meters
                - coordinates
              x-apidog-ignore-properties: []
            working_hours:
              type: array
              items:
                type: object
                properties:
                  name:
                    type: string
                    description: Represents the day of the week
                  times:
                    type: array
                    items:
                      type: object
                      properties:
                        from:
                          type: string
                          description: The start time of the working interval
                        to:
                          type: string
                          description: The end time of the working interval
                      x-apidog-orders:
                        - from
                        - to
                      required:
                        - from
                        - to
                      x-apidog-ignore-properties: []
                    description: >-
                      List of start and end times for working intervals on that
                      day.
                x-apidog-orders:
                  - name
                  - times
                required:
                  - name
                  - times
                x-apidog-ignore-properties: []
              description: >-
                Defines the operating schedule (opening and closing times) for
                each day of the week for a specific delivery zone or route
          required:
            - coverage
          x-apidog-orders:
            - coverage
            - working_hours
          description: Contains configuration rules for delivery coverage
          x-apidog-ignore-properties: []
      required:
        - id
        - branch_id
        - status
        - rules
      x-apidog-orders:
        - id
        - branch_id
        - status
        - rules
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

## apis-branch-delivery-zones/Update-Branch-Delivery-Zone-Salla-Merchant-API-Salla-Docs

# Update Branch Delivery Zone

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/delivery-zones/{zone_id}:
    put:
      summary: Update Branch Delivery Zone
      deprecated: false
      description: >-
        This endpoint allows modifying an existing branch’s delivery coverage,
        such as changing its status, adjusting the radius, or updating polygon
        coordinates to keep the service area accurate and up to date



        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `branches.read_write `- Branchs Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Branch Delivery Zones
        - Branch Delivery Zones
      parameters:
        - name: zone_id
          in: path
          description: Unique identifier of the delivery zone
          required: true
          example: 2079537577
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UpdateBranchDeliveryZones_request_body'
            example:
              status: true
              branch_id: 525010325
              rules:
                coverage:
                  enabled: true
                  method: radius
                  radius_meters: 500
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/BranchDeliveryZoneDetails_response_body'
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
                  - 01K0KYW1VNPP1HB32ND6Y18EV8
                x-apidog-refs:
                  01K0KYW1VNPP1HB32ND6Y18EV8:
                    $ref: '#/components/schemas/error_unauthorized_401'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
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
                  - 01K0KSH3SEZ836R438H4V229EM
                x-apidog-refs:
                  01K0KSH3SEZ836R438H4V229EM:
                    $ref: '#/components/schemas/error_forbidden_403'
                required:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
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
                x-apidog-refs:
                  01K0KTQKVDQ8K9DDZ3BTRX9CRM:
                    $ref: '#/components/schemas/Object%20Not%20Found(404)'
                required:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
          headers: {}
          x-apidog-name: Record Not Found
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
                  - 01K0KTS9JAWN9BK5ZZA1AA27KF
                x-apidog-refs:
                  01K0KTS9JAWN9BK5ZZA1AA27KF:
                    $ref: '#/components/schemas/error_validation_422'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - error
          headers: {}
          x-apidog-name: Parameter Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branch Delivery Zones
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-22300548-run
components:
  schemas:
    UpdateBranchDeliveryZones_request_body:
      type: object
      properties:
        status:
          type: integer
          description: >-
            Indicates whether the delivery zone is active `(true)` or inactive
            `(false)`
          nullable: true
        branch_id:
          type: integer
          description: >-
            The branch to which this delivery zone belongs, list of branches can
            be found [here](https://docs.salla.dev/api-5394224)
          nullable: true
        rules:
          type: object
          properties:
            coverage:
              type: object
              properties:
                enabled:
                  type: boolean
                  description: >-
                    Indicates if the delivery coverage is currently active for
                    this zone
                  nullable: true
                method:
                  type: string
                  description: |-
                    Specifies the method used to define the delivery area:
                    •`radius`  circular zone based on a center point.
                    •`polygon`  custom geofenced area defined by coordinates.
                  nullable: true
                radius_meters:
                  type: integer
                  description: >-
                    Required when `method` is `radius`; specifies the radius (in
                    meters) of the delivery area.
                coordinates:
                  type: array
                  items:
                    type: object
                    properties:
                      lat:
                        type: number
                        description: Latitude of the polygon point.
                      lng:
                        type: number
                        description: Longitude of the polygon point.
                    required:
                      - lat
                      - lng
                    x-apidog-orders:
                      - lat
                      - lng
                    x-apidog-ignore-properties: []
                  description: >-
                    List of geographic points (`lat`/`lng`) defining the
                    polygonal delivery zone. Required when`method` is `polygon`
                  nullable: true
              x-apidog-orders:
                - enabled
                - method
                - radius_meters
                - coordinates
              x-apidog-ignore-properties: []
              nullable: true
            working_hours:
              type: object
              properties:
                day:
                  type: object
                  properties:
                    enabled:
                      type: string
                      description: Indicates whether the delivery is active on that day.
                    from:
                      type: array
                      items:
                        type: string
                      description: List of start times for working intervals on that day.
                    to:
                      type: array
                      items:
                        type: string
                      description: List of end times matching each from time.
                  required:
                    - enabled
                    - from
                    - to
                  x-apidog-orders:
                    - enabled
                    - from
                    - to
                  description: >-
                    Specifies the delivery or service availability for each day
                    of the week.

                    Each key represents a day
                    (`sunday`,`monday`,`tuesday`,`wednesday`,`thursday`,`friday`,`saturday`)
                  x-apidog-ignore-properties: []
              required:
                - day
              x-apidog-orders:
                - day
              description: >-
                Defines the operating schedule (opening and closing times) for
                each day of the week for a specific delivery zone or route
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - coverage
            - working_hours
          description: Contains configuration rules for delivery coverage
          x-apidog-ignore-properties: []
          nullable: true
      x-apidog-orders:
        - status
        - branch_id
        - rules
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    BranchDeliveryZoneDetails_response_body:
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
          $ref: '#/components/schemas/BranchDeliveryZone'
      required:
        - status
        - success
        - data
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    BranchDeliveryZone:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier of the delivery zone configuration
        branch_id:
          type: integer
          description: >-
            The branch to which this delivery zone belongs, list of branches can
            be found [here](https://docs.salla.dev/api-5394224)
        status:
          type: boolean
          description: >-
            Indicates whether the delivery zone is active `(true)` or inactive
            `(false)`
        rules:
          type: object
          properties:
            coverage:
              type: object
              properties:
                enabled:
                  type: boolean
                  description: >-
                    Indicates if the delivery coverage is currently active for
                    this zone
                method:
                  type: string
                  description: |-
                    Specifies the method used to define the delivery area:
                    •`radius`  circular zone based on a center point.
                    •`polygon`  custom geofenced area defined by coordinates.
                radius_meters:
                  type: 'null'
                  description: >-
                    Required when `method` is `radius`; specifies the radius (in
                    meters) of the delivery area.
                coordinates:
                  type: array
                  items:
                    type: object
                    properties:
                      lat:
                        type: number
                        description: Latitude of the polygon point.
                      lng:
                        type: number
                        description: Longitude of the polygon point.
                    required:
                      - lat
                      - lng
                    x-apidog-orders:
                      - lat
                      - lng
                    x-apidog-ignore-properties: []
                  description: >-
                    List of geographic points (`lat`/`lng`) defining the
                    polygonal delivery zone. Required when`method` is `polygon`
                  nullable: true
              required:
                - enabled
                - method
                - radius_meters
                - coordinates
              x-apidog-orders:
                - enabled
                - method
                - radius_meters
                - coordinates
              x-apidog-ignore-properties: []
            working_hours:
              type: array
              items:
                type: object
                properties:
                  name:
                    type: string
                    description: Represents the day of the week
                  times:
                    type: array
                    items:
                      type: object
                      properties:
                        from:
                          type: string
                          description: The start time of the working interval
                        to:
                          type: string
                          description: The end time of the working interval
                      x-apidog-orders:
                        - from
                        - to
                      required:
                        - from
                        - to
                      x-apidog-ignore-properties: []
                    description: >-
                      List of start and end times for working intervals on that
                      day.
                x-apidog-orders:
                  - name
                  - times
                required:
                  - name
                  - times
                x-apidog-ignore-properties: []
              description: >-
                Defines the operating schedule (opening and closing times) for
                each day of the week for a specific delivery zone or route
          required:
            - coverage
          x-apidog-orders:
            - coverage
            - working_hours
          description: Contains configuration rules for delivery coverage
          x-apidog-ignore-properties: []
      required:
        - id
        - branch_id
        - status
        - rules
      x-apidog-orders:
        - id
        - branch_id
        - status
        - rules
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

