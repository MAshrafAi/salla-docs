# Apis Shipping Zones  Update Shipping Zone Salla Merchant Api Salla Docs

## Table of Contents

- [apis-shipping-zones/Update-Shipping-Zone-Salla-Merchant-API-Salla-Docs](#apis-shipping-zones-update-shipping-zone-salla-merchant-api-salla-docs)

---

## apis-shipping-zones/Update-Shipping-Zone-Salla-Merchant-API-Salla-Docs

# Update Shipping Zone

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/zones/{zone_id}:
    put:
      summary: Update Shipping Zone
      deprecated: false
      description: >-
        This endpoint allows you to update a specific __Custom__ Shipping Zone,
        by passing the `zone_id` as a path parameter. 


        :::tip[Note]


        If you ship to all countries and cities, set the `country` and `city`
        IDs to `"-1"`. When set this way, the `code` and `mobile_code` variables
        will be excluded from the response.


        :::



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read_write`- Shipping Read & Write

        </Accordion>
      operationId: update-shipping-zones
      tags:
        - Default module/Merchant API/APIs/Shipping Zones
        - Shipping Zones
      parameters:
        - name: zone_id
          in: path
          description: >-
            Unique identifier assigned to a shipping zone, list of shipping
            companies can be found [here](https://docs.salla.dev/api-5394239).
          required: true
          example: ''
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/shippingZone_request_body'
            example:
              company: 488260393
              shipping:
                country: 1939592358
                city: 1592433390
                cities_excluded:
                  - 257742554
                  - 81998629
                cash_on_delivery:
                  fees: 12
                  status: true
                fees:
                  type: rate
                  amount: 11
                  up_to_weight: 5
                  amount_per_unit: 2
                  per_unit: 3
                duration: 13 days
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/shippingZone_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 488260393
                  zone_code: .SA.riyadh
                  company:
                    id: 1473353380
                    slug: ABU HALIFA
                  country:
                    id: 1473353380
                    name: السعودية
                    name_en: Saudi Arabia
                    code: SA
                    mobile_code: '+966'
                  city:
                    id: 1473353380
                    name: الرياض
                    name_en: Riyadh
                  cities_excluded:
                    - id: 257742554
                      name: أبو حليفة
                      name_en: ABU HALIFA
                  fees:
                    amount: '15.00'
                    currency: SAR
                    type: fixed
                    weight_unit: kg
                    up_to_weight: 5
                    amount_per_unit: 2
                    per_unit: 3
                  cash_on_delivery:
                    status: true
                    fees: '12.00'
                  duration: 3-5
          headers: {}
          x-apidog-name: OK
        '400':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              examples:
                '3':
                  summary: Example
                  value:
                    status: 400
                    success: false
                    error:
                      code: 400
                      message: حقل نوع التسعيرة غير صالحٍ
                '4':
                  summary: Example 2
                  value:
                    status: 400
                    success: false
                    error:
                      code: 400
                      message: يجب أن يكون حقل مدة الشحن نصآ.
          headers: {}
          x-apidog-name: Bad Request
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
                    shipping.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: ShippingZone
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Zones
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394249-run
components:
  schemas:
    shippingZone_request_body:
      type: object
      properties:
        company:
          type: number
          description: >-
            Unique identification number assigned to a zone, list of shipping
            companies can be found [here](https://docs.salla.dev/api-5394239).
        shipping:
          type: object
          properties:
            country:
              type: number
              description: >-
                Unique identification number assigned to Shipping Country. If
                you ship to all countries, ensure that you set the value to
                `-1`.  List of countries can be found
                [here](https://docs.salla.dev/api-5394228).
            city:
              type: number
              description: >-
                Unique identification number assigned to Shipping City. If you
                ship to all cities, ensure that you set the value to `-1`.  List
                of cities can be found
                [here](https://docs.salla.dev/api-5394230).
            cities_excluded:
              type: array
              description: >-
                Excluded Cities from Shipping. List of cities can be found
                [here](https://docs.salla.dev/api-5394230).
              items:
                type: number
            cash_on_delivery:
              type: object
              description: >-
                Excluded City Name in English. List of cities can be found
                [here](https://docs.salla.dev/api-5394230).
              properties:
                fees:
                  type: number
                  description: Cash on Delivery (COD) Fee
                status:
                  type: boolean
                  description: 'Whether or not Cash On Delivery (COD) is activated '
              x-apidog-orders:
                - fees
                - status
              x-apidog-ignore-properties: []
            fees:
              type: object
              properties:
                type:
                  type: string
                  description: Fees Type
                  enum:
                    - rate
                    - fixed
                  examples:
                    - rate
                  x-apidog-enum:
                    - value: rate
                      name: ''
                      description: Shipping fees type is rate.
                    - value: fixed
                      name: ''
                      description: Shipping fees type is fixed.
                amount:
                  type: number
                  description: Fees Amount. `requiredif` `type` is set to `fixed`
                up_to_weight:
                  type: number
                  description: Maximum Allowed Weight. `requiredif` `type` is set to `rate`
                amount_per_unit:
                  type: number
                  description: Amount Per Unit. `requiredif` `type` is set to `rate`
                per_unit:
                  type: number
                  description: Per Unit Value. `requiredif` `type` is set to `rate`
              x-apidog-orders:
                - type
                - amount
                - up_to_weight
                - amount_per_unit
                - per_unit
              description: Fees details.
              x-apidog-ignore-properties: []
            duration:
              type: string
              description: Shipping duration in days
          required:
            - country
            - city
            - fees
            - duration
          x-apidog-orders:
            - country
            - city
            - cities_excluded
            - cash_on_delivery
            - fees
            - duration
          description: Shipping details.
          x-apidog-ignore-properties: []
      required:
        - company
      x-apidog-orders:
        - company
        - shipping
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    shippingZone_response_body:
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
          $ref: '#/components/schemas/ShippingZone'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ShippingZone:
      title: ShippingZone
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a certain shipping zone. List of
            shipping zons can be found
            [here](https://docs.salla.dev/api-5394247)
          examples:
            - 488260393
        zone_code:
          type: string
          description: A short alphanumeric identification code for a zone.
          examples:
            - .SA.riyadh
        company:
          type: object
          properties:
            id:
              type: number
              description: >-
                A unique identifier associated with a company. List of shipping
                companies can be found
                [here](https://docs.salla.dev/api-5394239)
              examples:
                - 1473353380
            slug:
              type: string
              description: Shipping company lable or short title.
              nullable: true
          x-apidog-orders:
            - id
            - slug
          required:
            - id
            - slug
          x-apidog-ignore-properties: []
        country:
          type: object
          properties:
            id:
              type: number
              description: >-
                The unique identifier of a country. List of countries can be
                found [here](https://docs.salla.dev/api-5394228)
              examples:
                - 1473353380
            name:
              type: string
              description: Country name
              examples:
                - السعودية
            name_en:
              type: string
              description: Country name in English
              examples:
                - Saudi Arabia
            code:
              type: string
              description: >-
                A short alphanumeric identification code for countries and
                dependent areas.
              examples:
                - SA
            mobile_code:
              type: string
              description: Country mobile code.
              examples:
                - '+966'
          x-apidog-orders:
            - id
            - name
            - name_en
            - code
            - mobile_code
          required:
            - id
            - name
            - name_en
            - code
            - mobile_code
          x-apidog-ignore-properties: []
        city:
          type: object
          properties:
            id:
              type: number
              description: >-
                The unique identifier of a city. List of cities can be found
                [here](https://docs.salla.dev/api-5394230)
              examples:
                - 1473353380
            name:
              type: string
              description: A label given to a significant urban area.
              examples:
                - الرياض
            name_en:
              type: string
              description: City name in English.
              examples:
                - Riyadh
          x-apidog-orders:
            - id
            - name
            - name_en
          required:
            - id
            - name
            - name_en
          x-apidog-ignore-properties: []
        cities_excluded:
          type: array
          description: The cities excluded from Shipping zone.
          items:
            type: object
            properties:
              id:
                type: number
                description: Unique identufiers for excluded cities.
                examples:
                  - 257742554
              name:
                type: string
                description: Excluded city name.
                examples:
                  - أبو حليفة
              name_en:
                type: string
                description: Excluded vity name in English
                examples:
                  - ABU HALIFA
            x-apidog-orders:
              - id
              - name
              - name_en
            x-apidog-ignore-properties: []
        fees:
          type: object
          properties:
            amount:
              type: string
              description: Amount due for shipping services.
              examples:
                - '15.00'
            currency:
              type: string
              description: Fee currency.
              examples:
                - SAR
            type:
              type: string
              description: Type of fee applies for shipping.
              examples:
                - fixed
            weight_unit:
              type: string
              description: 'The unit used to describe the weight '
              examples:
                - kg
            up_to_weight:
              type: number
              description: Maximum weight allowed for shipping.
              examples:
                - 5
            amount_per_unit:
              type: number
              description: Amount per unit
              examples:
                - 2
            per_unit:
              type: number
              description: Fees applies per unit.
              examples:
                - 3
          x-apidog-orders:
            - amount
            - currency
            - type
            - weight_unit
            - up_to_weight
            - amount_per_unit
            - per_unit
          required:
            - amount
            - currency
            - type
            - weight_unit
            - up_to_weight
            - amount_per_unit
            - per_unit
          x-apidog-ignore-properties: []
        cash_on_delivery:
          type: object
          properties:
            status:
              type: boolean
              default: true
              description: 'Whether or not the Shipment supports Cash On Delivery (COD) '
            fees:
              type: string
              description: Cash On Delivery (COD) Fee
              examples:
                - '12.00'
          x-apidog-orders:
            - status
            - fees
          required:
            - status
            - fees
          x-apidog-ignore-properties: []
        duration:
          type: string
          description: Shipping duration in days
          examples:
            - 3-5
      x-apidog-orders:
        - id
        - zone_code
        - company
        - country
        - city
        - cities_excluded
        - fees
        - cash_on_delivery
        - duration
      required:
        - id
        - zone_code
        - company
        - country
        - city
        - cities_excluded
        - fees
        - cash_on_delivery
        - duration
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

