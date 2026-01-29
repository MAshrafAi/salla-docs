# Shipping Routes  Delete Route Salla Merchants Apis Salla Docs

## Table of Contents

- [shipping-routes/Delete-Route-Salla-Merchants-APIs-Salla-Docs](#shipping-routes-delete-route-salla-merchants-apis-salla-docs)
- [shipping-routes/Route-Details-Salla-Merchants-APIs-Salla-Docs](#shipping-routes-route-details-salla-merchants-apis-salla-docs)
- [shipping-routes/Routes-List-Salla-Merchants-APIs-Salla-Docs](#shipping-routes-routes-list-salla-merchants-apis-salla-docs)

---

## shipping-routes/Delete-Route-Salla-Merchants-APIs-Salla-Docs

# Delete Route

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/routes/{id}:
    delete:
      summary: Delete Route
      deprecated: false
      description: >-
        This endpoint allows you to update an existing shipping route by passing
        its `id` as a path paraneter.

        You can change the route’s name, type, status, priority, assigned
        companies, conditions, and pricing strategy.


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read_write` - Shipping Read & Write

        </Accordion>
      tags:
        - Default module/Shipping and Fulfilment API/Shipping Routes
        - Shipping Routes
      parameters:
        - name: id
          in: path
          description: >-
            Route ID. Get a list of Route IDs from
            [here](https://docs.salla.dev/api-19357016)
          required: true
          example: 372846442
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
                  - 01K0Q8GDW3ZB8YGJ8SDMC57SP2
                x-apidog-refs:
                  01K0Q8GDW3ZB8YGJ8SDMC57SP2:
                    $ref: '#/components/schemas/delete_success'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
              example: |
                {
                  "status": 200,
                  "success": true,
                  "data": {
                    "message": "تم حذف المسار بنجاح"
                  }
          headers: {}
          x-apidog-name: Success
        '401':
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
                    $ref: '#/components/schemas/Unauthorized'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: The access token is invalid
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Shipping and Fulfilment API/Shipping Routes
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-19665291-run
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

## shipping-routes/Route-Details-Salla-Merchants-APIs-Salla-Docs

# Route Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/routes/{id}:
    get:
      summary: Route Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch detailed information about a specific
        shipping route, including

        - type

        - priority

        - branded configuration

        - assigned companies

        - shipping conditions

        - selection strategy, and

        - when or where it applies.


        This helps you understand how the route behaves at checkout and under
        which criteria it becomes active.


        :::warning[]

        This endpoint is accessable only for allowed applications.


        :::

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read`- Shipping Read

        </Accordion>
      tags:
        - Default module/Shipping and Fulfilment API/Shipping Routes
        - Shipping Routes
      parameters:
        - name: id
          in: path
          description: >-
            Route ID. Get a list of Route IDs from
            [here](https://docs.salla.dev/api-19357016)
          required: true
          example: 28734623
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
                      Response status code, a numeric or alphanumeric identifier
                      used to convey the outcome or status of a request,
                      operation, or transaction in various systems and
                      applications, typically indicating whether the action was
                      successful, encountered an error, or resulted in a
                      specific condition.
                  data:
                    type: object
                    properties:
                      id:
                        type: integer
                        description: Unique identifier of the route
                      name:
                        type: string
                        description: The name assigned to the shipping route
                      priority:
                        type: integer
                        description: >-
                          Controls route selection order. Lower numbers are
                          given higher priority
                      status:
                        type: boolean
                        description: Indicates whether the route is currently active
                      type:
                        type: string
                        description: Defines the behavior of the route at checkout
                        enum:
                          - normal
                          - auto
                          - branded
                          - default
                        x-apidog-enum:
                          - value: normal
                            name: Selected companies
                            description: >-
                              Used to explicitly list selected shipping
                              companies on checkout
                          - value: auto
                            name: Auto Assign
                            description: >-
                              Automatically assigns one shipping company at
                              checkout without customer input
                          - value: branded
                            name: Special Name
                            description: >-
                              Shows multiple companies under one brand name with
                              a unified price
                          - value: default
                            name: Default
                            description: >-
                              Fallback route that displays all available
                              shipping companies by default
                      branded: &ref_0
                        $ref: '#/components/schemas/BrandedRoute'
                      companies: &ref_1
                        $ref: '#/components/schemas/ShippingRouteCompany'
                      condition_match:
                        type: string
                        enum:
                          - all
                          - any
                        x-apidog-enum:
                          - value: all
                            name: Match all
                            description: >-
                              All specified conditions must be met for the route
                              to be applied
                          - value: any
                            name: Match any
                            description: >-
                              At least one of the specified conditions must be
                              met
                        description: >-
                          Determines whether all or any defined conditions must
                          be satisfied to activate this route
                      conditions: &ref_2
                        $ref: '#/components/schemas/ShippingRouteCondition'
                      strategy: &ref_3
                        description: >-
                          Defines the method used to rank or prioritize shipping
                          companies under this route during checkout
                        $ref: '#/components/schemas/ShippingRouteStrategy'
                    required:
                      - id
                      - name
                      - status
                      - type
                      - strategy
                    x-apidog-orders:
                      - id
                      - name
                      - priority
                      - status
                      - type
                      - branded
                      - companies
                      - condition_match
                      - conditions
                      - strategy
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - 01K0P52HWR8WRPGEV8X5M0Y20Y
                required:
                  - status
                  - success
                  - data
                x-apidog-refs:
                  01K0P52HWR8WRPGEV8X5M0Y20Y:
                    $ref: '#/components/schemas/ShippingRoute_response_body'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
              example:
                status: 200
                success: true
                data:
                  id: 1670414609
                  name: Testing Route 1
                  priority: 1
                  status: true
                  type: branded
                  branded:
                    name: Salla Delivery
                    logo_url: https://example.com/logos/salla.png
                    description: Fast delivery for premium customers
                    combinable: true
                    pricing:
                      type: rate
                      cost: 30
                      amount_per_unit: 2
                      up_to_weight: 15
                      per_unit: 1
                  companies:
                    - id: 989286562
                      priority: 1
                      capacity: 80
                    - id: 1723506348
                      priority: 2
                      capacity: 10
                    - id: 665151403
                      priority: 3
                      capacity: 10
                  condition_match: all
                  conditions:
                    - type: cart_total
                      operator: between
                      value:
                        max: 500
                        min: 200
                    - type: cart_weight
                      operator: '=='
                      value: 3
                    - type: cart_quantity
                      operator: '>='
                      value: 5
                    - type: categories
                      operator: in
                      value:
                        - id: 1975114919
                          name: Perfume
                    - type: areas
                      operator: in
                      value:
                        - type: allowed
                          areas:
                            - country_id:
                                id: 1473353380
                                name: السعودية
                              cities:
                                - id: 1473353380
                                  name: الرياض
                                - id: 1939592358
                                  name: مكة
                                - id: 349994915
                                  name: خميس مشيط
                        - type: excluded
                          areas:
                            - country_id:
                                id: 566146469
                                name: الامارات
                              cities:
                                - id: 2097610897
                                  name: أبو ظبي
                            - country_id:
                                id: 1298199463
                                name: قطر
                              cities:
                                - id: 1008553809
                                  name: الخور
                                - id: 900574300
                                  name: الدوحة
                                - id: 167407186
                                  name: الشمال
                    - type: customer_groups
                      operator: in
                      value:
                        - id: 1237892238
                          name: VIP
                    - type: schedule
                      operator: within_range
                      value:
                        days:
                          - Sunday
                        time_to: '09:00'
                        time_from: '14:30'
                    - type: branches
                      operator: in
                      value:
                        - id: 1937885067
                          name: Main Branch
                        - id: 1299113620
                          name: Jeddah Branch
                    - type: branch_count
                      operator: '>='
                      value: '23'
                    - type: specific_products_quantity
                      operator: in
                      value:
                        quantity: 12
                        products:
                          - id: 1784895147
                            name: Product
                            thumbnail: >-
                              https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/RAQjo5g7fpME4drSj8HD9BLTdnwkGNTdcHyJszRj.jpg
                  strategy:
                    type: ratio
                    capacity_level: route
                    alternative_companies: []
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
                      Response status code, a numeric or alphanumeric identifier
                      used to convey the outcome or status of a request,
                      operation, or transaction in various systems and
                      applications, typically indicating whether the action was
                      successful, encountered an error, or resulted in a
                      specific condition.
                  error:
                    type: object
                    properties:
                      code:
                        type: integer
                        description: >+
                          Not Found Response error code, a numeric or
                          alphanumeric unique identifier used to represent the
                          error.

                      message:
                        type: string
                        description: >-
                          A message or data structure that is generated or
                          returned when the response is not found or explain the
                          error.
                    x-apidog-orders:
                      - code
                      - message
                    required:
                      - code
                      - message
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - status
                  - success
                  - error
                required:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: token is not valid
          headers: {}
          x-apidog-name: Unauthorized
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
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Shipping and Fulfilment API/Shipping Routes
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-19665287-run
components:
  schemas:
    ShippingRouteStrategy:
      type: object
      properties:
        type:
          type: string
          description: Strategy type for selecting companies
          enum:
            - default
            - manual
            - quota
            - ratio
            - lowest_price
          x-apidog-enum:
            - value: default
              name: Salla recommendations
              description: ''
            - value: manual
              name: manual
              description: ''
            - value: quota
              name: Capacity orders count
              description: Available for special plan only
            - value: ratio
              name: Capacity orders ratio
              description: Available for special plan only
            - value: lowest_price
              name: Lowest price
              description: ''
        capacity_level:
          type: string
          description: >-
            the level on which this strategy will be applied, and used with
            `quota` , `ratio`  only
        alternative_companies:
          type: array
          items:
            type: string
          description: >-
            Fallback companies that can be used if primary companies are
            unavailable, and used with `quota`  only
      required:
        - type
      x-apidog-orders:
        - type
        - capacity_level
        - alternative_companies
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ShippingRouteCondition:
      type: array
      items:
        type: object
        properties:
          type:
            type: string
            description: The condition type
            enum:
              - cart_total
              - cart_weight
              - cart_quantity
              - categories
              - areas
              - customer_groups
              - schedule
              - branches
              - branch_count
              - specific_products_quantity
              - excluded
              - allowed
            x-apidog-enum:
              - value: cart_total
                name: ''
                description: ' Based on total cart value'
              - value: cart_weight
                name: ''
                description: Based on total cart weight
              - value: cart_quantity
                name: ''
                description: Number of items in the cart
              - value: categories
                name: ''
                description: Filters by product categories
              - value: areas
                name: ''
                description: Filter by allowed or excluded areas (countries and cities)
              - value: customer_groups
                name: ''
                description: Filter by customer groups
              - value: schedule
                name: ''
                description: Restrict delivery to specific days/times
              - value: branches
                name: ''
                description: >-
                  Route is available only through selected branches (available
                  on special plan only)
              - value: branch_count
                name: ''
                description: >-
                  Based on number of branches in the cart (available on special
                  plan only)
              - value: specific_products_quantity
                name: ''
                description: Quantity of specific products required
              - value: excluded
                name: ''
                description: ''
              - value: allowed
                name: ''
                description: ''
          operator:
            type: string
            description: the condition operator
            enum:
              - '=='
              - '!='
              - '>'
              - '>='
              - <
              - <=
              - between
              - in
              - not_in
              - within_range
            x-apidog-enum:
              - value: '=='
                name: ''
                description: Matches values that are exactly equal to the specified value
              - value: '!='
                name: ''
                description: Matches values that are not equal to the specified value.
              - value: '>'
                name: ''
                description: Matches values that are greater than the specified value.
              - value: '>='
                name: ''
                description: >-
                  Matches values that are greater than or equal to the specified
                  value
              - value: <
                name: ''
                description: Matches values that are less than the specified value
              - value: <=
                name: ''
                description: >-
                  Matches values that are less than or equal to the specified
                  value.
              - value: between
                name: ''
                description: Matches values that fall within a specified range (inclusive)
              - value: in
                name: ''
                description: Matches values that exist in a specified list of values
              - value: not_in
                name: ''
                description: >-
                  Matches values that do not exist in a specified list of
                  values.
              - value: within_range
                name: ''
                description: Matches values that fall within a given numeric or date range.
          value:
            anyOf:
              - type: object
                properties:
                  days:
                    type: array
                    items:
                      type: string
                      description: Days strings
                      examples:
                        - '"Friday"'
                      enum:
                        - Sunday
                        - Monday
                        - Tuesday
                        - Wednesday
                        - Thursday
                        - Friday
                        - Saturday
                      x-apidog-enum:
                        - value: Sunday
                          name: ''
                          description: ''
                        - value: Monday
                          name: ''
                          description: ''
                        - value: Tuesday
                          name: ''
                          description: ''
                        - value: Wednesday
                          name: ''
                          description: ''
                        - value: Thursday
                          name: ''
                          description: ''
                        - value: Friday
                          name: ''
                          description: ''
                        - value: Saturday
                          name: ''
                          description: ''
                    description: >-
                      List of days. Must be written with a first captical letter
                      (ex: "Friday"). required if the type is "scheduale"
                  time_from:
                    type: string
                    examples:
                      - '11:00'
                    description: Time in 24-hour format
                  time_to:
                    type: string
                    examples:
                      - '16:30'
                    description: Time in 24-hour format
                x-apidog-orders:
                  - days
                  - time_from
                  - time_to
                description: required if the type is `scheduale`
                required:
                  - days
                  - time_from
                  - time_to
                x-apidog-ignore-properties: []
              - type: object
                properties:
                  min:
                    type: integer
                    description: >-
                      The minimum amount of the the chosen type. For example,
                      the minimum value of the cart_total
                  max:
                    type: integer
                    description: >-
                      The maximum amount of the the chosen type. For example,
                      the maximum value of the cart_total
                x-apidog-orders:
                  - min
                  - max
                required:
                  - min
                  - max
                description: Required if the operator is set to `between` or `within_range`
                x-apidog-ignore-properties: []
              - type: integer
                description: >-
                  Value can be a single integer if the operator is set to `==`
                  or `>=` or `<=` or `>` or `<` or `!=`
              - type: array
                items:
                  type: integer
                description: >-
                  Required if the type is set to `categories`. Example: [213984,
                  7482390]
              - type: array
                items:
                  type: object
                  properties: {}
                  x-apidog-orders: []
                  x-apidog-ignore-properties: []
                description: >-
                  Required array of objects in case the `type` is set to
                  `allowed` or `excluded`. used to include the allowed/excluded
                  country and cities.
            description: >-
              the value based on the type. This key depends on the `type` and
              the `operator`
        required:
          - type
          - operator
          - value
        x-apidog-orders:
          - type
          - operator
          - value
        x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ShippingRouteCompany:
      type: array
      items:
        type: object
        properties:
          id:
            type: integer
            description: >-
              Shipping company ID. Find a complete list of Shipment companies
              [here](api-5578809/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
          priority:
            type: integer
            description: Manual priority for sorting companies within this route
          capacity:
            type: integer
            description: Manual priority for sorting companies within this route
        required:
          - id
        x-apidog-orders:
          - id
          - priority
          - capacity
        x-apidog-ignore-properties: []
      x-apidog-folder: ''
    BrandedRoute:
      type: object
      properties:
        name:
          type: string
          description: Display name for the branded delivery service
        description:
          type: string
          description: Optional description of the branded service
        logo_url:
          type: string
          description: URL to the branded logo shown in the checkout
        combinable:
          type: boolean
          description: Indicates if this route can be combined with others
        pricing:
          type: object
          properties:
            type:
              type: string
              description: Pricing type
              enum:
                - rate
                - fixed
              x-apidog-enum:
                - value: rate
                  name: Rate
                  description: Based on weight
                - value: fixed
                  name: Fixed
                  description: Fixed price
            cost:
              type: integer
              description: Base cost for shipping
            amount_per_unit:
              type: integer
              description: Additional cost, it is required idf type = rate
            up_to_weight:
              type: integer
              description: Max weight included in base cost, it is required idf type = rate
            per_unit:
              type: integer
              description: Cost per extra weight unit, it is required idf type = rate
          required:
            - type
            - cost
          x-apidog-orders:
            - type
            - cost
            - amount_per_unit
            - up_to_weight
            - per_unit
          description: Pricing details
          x-apidog-ignore-properties: []
      required:
        - name
        - description
        - logo_url
      x-apidog-orders:
        - name
        - description
        - logo_url
        - combinable
        - pricing
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ShippingRoute_response_body:
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
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        data:
          type: object
          properties:
            id:
              type: integer
              description: Unique identifier of the route
            name:
              type: string
              description: The name assigned to the shipping route
            priority:
              type: integer
              description: >-
                Controls route selection order. Lower numbers are given higher
                priority
            status:
              type: boolean
              description: Indicates whether the route is currently active
            type:
              type: string
              description: Defines the behavior of the route at checkout
              enum:
                - normal
                - auto
                - branded
                - default
              x-apidog-enum:
                - value: normal
                  name: Selected companies
                  description: >-
                    Used to explicitly list selected shipping companies on
                    checkout
                - value: auto
                  name: Auto Assign
                  description: >-
                    Automatically assigns one shipping company at checkout
                    without customer input
                - value: branded
                  name: Special Name
                  description: >-
                    Shows multiple companies under one brand name with a unified
                    price
                - value: default
                  name: Default
                  description: >-
                    Fallback route that displays all available shipping
                    companies by default
            branded: *ref_0
            companies: *ref_1
            condition_match:
              type: string
              enum:
                - all
                - any
              x-apidog-enum:
                - value: all
                  name: Match all
                  description: >-
                    All specified conditions must be met for the route to be
                    applied
                - value: any
                  name: Match any
                  description: At least one of the specified conditions must be met
              description: >-
                Determines whether all or any defined conditions must be
                satisfied to activate this route
            conditions: *ref_2
            strategy: *ref_3
          required:
            - id
            - name
            - status
            - type
            - strategy
          x-apidog-orders:
            - id
            - name
            - priority
            - status
            - type
            - branded
            - companies
            - condition_match
            - conditions
            - strategy
          x-apidog-ignore-properties: []
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

## shipping-routes/Routes-List-Salla-Merchants-APIs-Salla-Docs

#   Routes List

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/routes:
    get:
      summary: '  Routes List'
      deprecated: false
      description: >-
        This endpoint allows you to fetch all shipping routes configured for the
        store.

        Each route includes its type (e.g., normal, auto, branded, default),
        status, priority, and combination strategy.

        These routes control how shipping options appear to customers at
        checkout.


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read`- Shipping Read

        </Accordion>
      tags:
        - Default module/Shipping and Fulfilment API/Shipping Routes
        - Shipping Routes
      parameters:
        - name: name
          in: query
          description: The name assigned to the shipping route
          required: false
          example: Branded Route
          schema:
            type: string
      responses:
        '200':
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
                      Response status code, a numeric or alphanumeric identifier
                      used to convey the outcome or status of a request,
                      operation, or transaction in various systems and
                      applications, typically indicating whether the action was
                      successful, encountered an error, or resulted in a
                      specific condition.
                  data:
                    type: array
                    items:
                      type: object
                      properties:
                        id:
                          type: integer
                          description: Unique identifier of the route
                        name:
                          type: string
                          description: The name assigned to the shipping route
                        type:
                          type: string
                          description: The route type
                          enum:
                            - normal
                            - auto
                            - branded
                            - default
                          x-apidog-enum:
                            - value: normal
                              name: Selected companies
                              description: >-
                                Used to explicitly list selected shipping
                                companies on checkout
                            - value: auto
                              name: Auto assign
                              description: >-
                                Automatically assigns one shipping company at
                                checkout without customer input.
                            - value: branded
                              name: Special name
                              description: >-
                                Shows multiple companies under one brand name
                                with a unified price
                            - value: default
                              name: Default
                              description: >-
                                Fallback route that displays all available
                                shipping companies by default
                        status:
                          type: boolean
                          description: Indicates if the route is currently active
                        priority:
                          type: integer
                          description: >-
                            Controls route selection order. Lower numbers are
                            given higher priority
                        strategy:
                          type: string
                          description: >-
                            The internal method used to calculate route
                            applicability or pricing
                        combinable:
                          type: boolean
                          description: >-
                            Whether this route can be combined with other routes
                            during checkout
                      required:
                        - id
                        - name
                        - type
                        - status
                        - priority
                        - strategy
                        - combinable
                      x-apidog-orders:
                        - id
                        - name
                        - type
                        - status
                        - priority
                        - strategy
                        - combinable
                      x-apidog-ignore-properties: []
                  pagination: &ref_0
                    $ref: '#/components/schemas/Pagination'
                x-apidog-orders:
                  - 01K0P4A2MA7Y2VW7T4XYV6TNV4
                required:
                  - status
                  - success
                  - data
                  - pagination
                x-apidog-refs:
                  01K0P4A2MA7Y2VW7T4XYV6TNV4:
                    $ref: '#/components/schemas/ShippingRouteList_response_body'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
                  - pagination
              example:
                status: 200
                success: true
                data:
                  - id: 2087831307
                    name: Branded Route
                    type: branded
                    status: true
                    priority: 1
                    strategy: default
                    combinable: true
                  - id: 580171786
                    name: Selected Route
                    type: default
                    status: true
                    priority: 2
                    strategy: ratio
                    combinable: false
                  - id: 298476048
                    name: Auto assign route
                    type: auto
                    status: true
                    priority: 3
                    strategy: quota
                    combinable: false
                pagination:
                  count: 3
                  total: 3
                  perPage: 15
                  currentPage: 1
                  totalPages: 1
                  links: {}
          headers: {}
          x-apidog-name: Success
        '401':
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
                    $ref: '#/components/schemas/Unauthorized'
                x-apidog-orders:
                  - status
                  - success
                  - error
                x-apidog-ignore-properties: []
              example:
                status: 401
                success: false
                error:
                  code: Unauthorized
                  message: The access token is invalid
          headers: {}
          x-apidog-name: Unauthorized
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
                status: 404
                success: false
                error:
                  code: error
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: Record Not Found
      security:
        - bearer: []
      x-apidog-folder: Default module/Shipping and Fulfilment API/Shipping Routes
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-19665286-run
components:
  schemas:
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
    ShippingRouteList_response_body:
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
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        data:
          type: array
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identifier of the route
              name:
                type: string
                description: The name assigned to the shipping route
              type:
                type: string
                description: The route type
                enum:
                  - normal
                  - auto
                  - branded
                  - default
                x-apidog-enum:
                  - value: normal
                    name: Selected companies
                    description: >-
                      Used to explicitly list selected shipping companies on
                      checkout
                  - value: auto
                    name: Auto assign
                    description: >-
                      Automatically assigns one shipping company at checkout
                      without customer input.
                  - value: branded
                    name: Special name
                    description: >-
                      Shows multiple companies under one brand name with a
                      unified price
                  - value: default
                    name: Default
                    description: >-
                      Fallback route that displays all available shipping
                      companies by default
              status:
                type: boolean
                description: Indicates if the route is currently active
              priority:
                type: integer
                description: >-
                  Controls route selection order. Lower numbers are given higher
                  priority
              strategy:
                type: string
                description: >-
                  The internal method used to calculate route applicability or
                  pricing
              combinable:
                type: boolean
                description: >-
                  Whether this route can be combined with other routes during
                  checkout
            required:
              - id
              - name
              - type
              - status
              - priority
              - strategy
              - combinable
            x-apidog-orders:
              - id
              - name
              - type
              - status
              - priority
              - strategy
              - combinable
            x-apidog-ignore-properties: []
        pagination: *ref_0
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

