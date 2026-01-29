# Apis Branch Delivery Zones  Branch Delivery Zone Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-branch-delivery-zones/Branch-Delivery-Zone-Details-Salla-Merchant-API-Salla-Docs](#apis-branch-delivery-zones-branch-delivery-zone-details-salla-merchant-api-salla-docs)
- [apis-branch-delivery-zones/Create-Branch-Delivery-Zone-Salla-Merchant-API-Salla-Docs](#apis-branch-delivery-zones-create-branch-delivery-zone-salla-merchant-api-salla-docs)
- [apis-branch-delivery-zones/Delete-Branch-Delivery-Zone-Salla-Merchant-API-Salla-Docs](#apis-branch-delivery-zones-delete-branch-delivery-zone-salla-merchant-api-salla-docs)

---

## apis-branch-delivery-zones/Branch-Delivery-Zone-Details-Salla-Merchant-API-Salla-Docs

# Branch Delivery Zone Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/delivery-zones/{zone_id}:
    get:
      summary: Branch Delivery Zone Details
      deprecated: false
      description: >-
        This Endpoint is used to show a branch’s delivery zo, including the area
        defined by either a radius or a polygon.


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
        - name: zone_id
          in: path
          description: Unique identifier of the delivery zone
          required: true
          example: 566146469
          schema:
            type: integer
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
                  - 01K0KTDERMRBB8BRTTYW9BMQWC
                x-apidog-refs:
                  01K0KTDERMRBB8BRTTYW9BMQWC:
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
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branch Delivery Zones
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-22300546-run
components:
  schemas:
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

## apis-branch-delivery-zones/Create-Branch-Delivery-Zone-Salla-Merchant-API-Salla-Docs

# Create Branch Delivery Zone

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/delivery-zones:
    post:
      summary: Create Branch Delivery Zone
      deprecated: false
      description: >-
        This endpoint is using for creating a new delivery zone and defining a
        branch’s delivery coverage by specifying its status and setting the area
        using either a radius or polygon coordinates


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `branches.read_write `- Branchs Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Branch Delivery Zones
        - Branch Delivery Zones
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateBranchDeliveryZone_request_body'
            example:
              status: true
              branch_id: 525010325
              rules:
                coverage:
                  enabled: true
                  method: polygon
                  coordinates:
                    - lat: 24.919427692528
                      lng: 46.7360729
                    - lat: 24.840317240711
                      lng: 46.138643243018
                    - lat: 24.506501651095
                      lng: 46.168807580176
                    - lat: 24.407746339329
                      lng: 46.55411184043
                    - lat: 24.608925155159
                      lng: 46.763634850684
                    - lat: 24.766767432571
                      lng: 47.065710808936
                    - lat: 24.919427692528
                      lng: 46.7360729
                working_hours:
                  sunday:
                    enabled: 'on'
                    from:
                      - '08:00'
                      - '19:00'
                    to:
                      - '17:00'
                      - '23:30'
                  monday:
                    enabled: 'on'
                    from:
                      - '08:00'
                      - '19:00'
                    to:
                      - '17:00'
                      - '23:30'
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
                  - 01K6SWYCVQVS166KM44ZMJV8ZC
                x-apidog-refs:
                  01K6SWYCVQVS166KM44ZMJV8ZC:
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
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-22300547-run
components:
  schemas:
    CreateBranchDeliveryZone_request_body:
      type: object
      properties:
        status:
          type: integer
          description: >-
            Indicates whether the delivery zone is active `(true)` or inactive
            `(false)`
        branch_id:
          type: integer
          description: >-
            The branch to which this delivery zone belongs, list of branches can
            be found [here](https://docs.salla.dev/api-5394224)
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
                  type: integer
                  description: >-
                    Required when `method` is `radius`; specifies the radius (in
                    meters) of the delivery area.
                  nullable: true
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
          required:
            - coverage
          x-apidog-orders:
            - coverage
            - working_hours
          description: Contains configuration rules for delivery coverage
          x-apidog-ignore-properties: []
      required:
        - status
        - branch_id
        - rules
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

## apis-branch-delivery-zones/Delete-Branch-Delivery-Zone-Salla-Merchant-API-Salla-Docs

# Delete Branch Delivery Zone

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /branches/delivery-zones/{zone_id}:
    delete:
      summary: Delete Branch Delivery Zone
      deprecated: false
      description: >-
        This endpoint is used for removing an existing delivery coverage
        configuration from a branch


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
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  message:
                    type: string
                    description: >-
                      A message or data structure that is generated or returned
                      when a deletion operation is successful.
                  code:
                    type: number
                    description: >-
                      A numerical or alphanumeric code that is used in various
                      software and web development contexts to convey
                      information about the outcome of a request or operation.
                x-apidog-orders:
                  - 01K6SXMB6KKZG45Z83ZZS9MWJG
                required:
                  - message
                  - code
                x-apidog-refs:
                  01K6SXMB6KKZG45Z83ZZS9MWJG:
                    $ref: '#/components/schemas/DeleteSuccess'
                x-apidog-ignore-properties:
                  - message
                  - code
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
                  - 01K0KTDERMRBB8BRTTYW9BMQWC
                x-apidog-refs:
                  01K0KTDERMRBB8BRTTYW9BMQWC:
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
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Branch Delivery Zones
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-22300549-run
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

