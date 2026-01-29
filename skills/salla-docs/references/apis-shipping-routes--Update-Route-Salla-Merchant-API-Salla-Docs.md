# Apis Shipping Routes  Update Route Salla Merchant Api Salla Docs

## Table of Contents

- [apis-shipping-routes/Update-Route-Salla-Merchant-API-Salla-Docs](#apis-shipping-routes-update-route-salla-merchant-api-salla-docs)

---

## apis-shipping-routes/Update-Route-Salla-Merchant-API-Salla-Docs

# Update Route

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/routes/{id}:
    patch:
      summary: Update Route
      deprecated: false
      description: >-
        This endpoint allows you to update the details of an existing shipping
        route by passing its `id` as a path parameter.

        You can change the route name, type, status, and priority, and also
        update the list of companies, branded settings, conditions, and
        strategy.

        This helps control how the route works and appears during checkout.


        :::warning[]

        This endpoint is accessable only for allowed applications.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read_write` - Shipping Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Shipping Routes
        - Shipping Routes
      parameters:
        - name: id
          in: path
          description: >-
            Route ID. Get a list of Route IDs from
            [here](https://docs.salla.dev/api-19357016)
          required: true
          example: 8273468
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                name:
                  type: string
                  description: The name of the shipping route
                type:
                  type: string
                  description: >-
                    The route type used to determine how the shipping method is
                    displayed and applied
                  enum:
                    - normal
                    - auto
                    - branded
                  x-apidog-enum:
                    - value: normal
                      name: Selected companies
                      description: >-
                        Lists specific shipping companies available to customers
                        at checkout
                    - value: auto
                      name: Auto assign
                      description: >-
                        Automatically selects a shipping company for the
                        customer at checkout
                    - value: branded
                      name: Special name
                      description: >-
                        Groups multiple companies under a single brand name with
                        unified pricing
                status:
                  type: integer
                  description: Whether the route is active (1) or inactive (0)
                priority:
                  type: integer
                  description: >-
                    Determines the selection priority for the route; lower
                    numbers have higher priority
                branded:
                  type: object
                  description: Details specific to branded routes
                  properties:
                    name:
                      type: string
                      description: Display name for the branded delivery service
                    description:
                      type: string
                      description: Optional description shown to customers
                    logo_url:
                      type: string
                      description: URL of the brand logo displayed during checkout
                    combinable:
                      type: boolean
                      description: >-
                        Whether this route can be used with other applicable
                        routes
                    pricing:
                      type: object
                      description: Pricing configuration for the branded route
                      properties:
                        type:
                          type: string
                          description: Type of pricing applied
                          enum:
                            - rate
                            - fixed
                          x-apidog-enum:
                            - value: rate
                              name: Rate
                              description: Price based on product weight
                            - value: fixed
                              name: Fixed
                              description: Flat price regardless of weight
                        cost:
                          type: integer
                          description: Base shipping cost
                        amount_per_unit:
                          type: integer
                          description: >-
                            Extra charge per weight unit (required if pricing
                            type is 'rate')
                        up_to_weight:
                          type: integer
                          description: >-
                            Maximum weight covered by the base cost (required if
                            pricing type is 'rate')
                        per_unit:
                          type: integer
                          description: >-
                            Charge for each unit above the base weight (required
                            if pricing type is 'rate')
                      x-apidog-orders:
                        - type
                        - cost
                        - amount_per_unit
                        - up_to_weight
                        - per_unit
                      x-apidog-ignore-properties: []
                  x-apidog-orders:
                    - name
                    - description
                    - logo_url
                    - combinable
                    - pricing
                  x-apidog-ignore-properties: []
                companies: &ref_0
                  $ref: '#/components/schemas/ShippingRouteCompany'
                condition_match:
                  type: string
                  description: >-
                    Defines whether all conditions must be met ('all') or any
                    condition is sufficient ('any')
                  enum:
                    - all
                    - any
                  x-apidog-enum:
                    - value: all
                      name: Match all
                      description: All listed conditions must be satisfied
                    - value: any
                      name: Match any
                      description: Only one of the listed conditions must be satisfied
                conditions: &ref_1
                  $ref: '#/components/schemas/ShippingRouteCondition'
                strategy: &ref_2
                  $ref: '#/components/schemas/ShippingRouteStrategy'
              x-apidog-orders:
                - 01K0Q7QGJZ1HHPXD3TFQB7MR71
              x-apidog-refs:
                01K0Q7QGJZ1HHPXD3TFQB7MR71:
                  $ref: '#/components/schemas/UpdateRoute_request_body'
              x-apidog-ignore-properties:
                - name
                - type
                - status
                - priority
                - branded
                - companies
                - condition_match
                - conditions
                - strategy
            example:
              status: false
              name: New Route v1
              strategy:
                type: default
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
                      branded: &ref_3
                        $ref: '#/components/schemas/BrandedRoute'
                      companies: *ref_0
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
                      conditions: *ref_1
                      strategy: *ref_2
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
                  - 01K0Q6PRCBT5W8MT36NPRBKNY4
                required:
                  - status
                  - success
                  - data
                x-apidog-refs:
                  01K0Q6PRCBT5W8MT36NPRBKNY4:
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
                    condition_match:
                      - حقل condition match مطلوب.
                    conditions.0.value:
                      - >-
                        يجب أن تحتوي كل مجموعة مناطق على نوع صالح ومصفوفة من
                        المناطق
                    conditions.0.value.min.type:
                      - حقل conditions.0.value.min.type مطلوب.
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Routes
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-19370925-run
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
    UpdateRoute_request_body:
      type: object
      properties:
        name:
          type: string
          description: The name of the shipping route
        type:
          type: string
          description: >-
            The route type used to determine how the shipping method is
            displayed and applied
          enum:
            - normal
            - auto
            - branded
          x-apidog-enum:
            - value: normal
              name: Selected companies
              description: >-
                Lists specific shipping companies available to customers at
                checkout
            - value: auto
              name: Auto assign
              description: >-
                Automatically selects a shipping company for the customer at
                checkout
            - value: branded
              name: Special name
              description: >-
                Groups multiple companies under a single brand name with unified
                pricing
        status:
          type: integer
          description: Whether the route is active (1) or inactive (0)
        priority:
          type: integer
          description: >-
            Determines the selection priority for the route; lower numbers have
            higher priority
        branded:
          type: object
          description: Details specific to branded routes
          properties:
            name:
              type: string
              description: Display name for the branded delivery service
            description:
              type: string
              description: Optional description shown to customers
            logo_url:
              type: string
              description: URL of the brand logo displayed during checkout
            combinable:
              type: boolean
              description: Whether this route can be used with other applicable routes
            pricing:
              type: object
              description: Pricing configuration for the branded route
              properties:
                type:
                  type: string
                  description: Type of pricing applied
                  enum:
                    - rate
                    - fixed
                  x-apidog-enum:
                    - value: rate
                      name: Rate
                      description: Price based on product weight
                    - value: fixed
                      name: Fixed
                      description: Flat price regardless of weight
                cost:
                  type: integer
                  description: Base shipping cost
                amount_per_unit:
                  type: integer
                  description: >-
                    Extra charge per weight unit (required if pricing type is
                    'rate')
                up_to_weight:
                  type: integer
                  description: >-
                    Maximum weight covered by the base cost (required if pricing
                    type is 'rate')
                per_unit:
                  type: integer
                  description: >-
                    Charge for each unit above the base weight (required if
                    pricing type is 'rate')
              x-apidog-orders:
                - type
                - cost
                - amount_per_unit
                - up_to_weight
                - per_unit
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - name
            - description
            - logo_url
            - combinable
            - pricing
          x-apidog-ignore-properties: []
        companies: *ref_0
        condition_match:
          type: string
          description: >-
            Defines whether all conditions must be met ('all') or any condition
            is sufficient ('any')
          enum:
            - all
            - any
          x-apidog-enum:
            - value: all
              name: Match all
              description: All listed conditions must be satisfied
            - value: any
              name: Match any
              description: Only one of the listed conditions must be satisfied
        conditions: *ref_1
        strategy: *ref_2
      x-apidog-orders:
        - name
        - type
        - status
        - priority
        - branded
        - companies
        - condition_match
        - conditions
        - strategy
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
            branded: *ref_3
            companies: *ref_0
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
            conditions: *ref_1
            strategy: *ref_2
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

