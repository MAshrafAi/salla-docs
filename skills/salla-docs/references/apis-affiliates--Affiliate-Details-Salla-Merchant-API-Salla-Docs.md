# Apis Affiliates  Affiliate Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-affiliates/Affiliate-Details-Salla-Merchant-API-Salla-Docs](#apis-affiliates-affiliate-details-salla-merchant-api-salla-docs)
- [apis-affiliates/Create-Affiliate-Salla-Merchant-API-Salla-Docs](#apis-affiliates-create-affiliate-salla-merchant-api-salla-docs)

---

## apis-affiliates/Affiliate-Details-Salla-Merchant-API-Salla-Docs

# Affiliate Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /affiliates/{affiliates_id}:
    get:
      summary: Affiliate Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch details regarding an affiliate by
        passing the `affiliate_id` as a path parameter.


        :::danger[Deprecation Notice]

        Starting **November 01, 2025**, this endpoint’s response will be
        updated, and the old response body will be deprecated.

        To avoid breaking changes, update your integration to use the new
        schema, which supports the [new Salla affiliate
        system](https://help.salla.sa/article/501443344).

        If the Merchant is still using the old Salla affiliate system, the
        endpoint will still depend on deprecated payloads.

        See the [ChangeLog](https://docs.salla.dev/421127m0) for more details.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read`- Marketing Read Only

        </Accordion>
      operationId: get-affiliates-affiliates.id
      tags:
        - Default module/Merchant API/APIs/Affiliates
        - Affiliates
      parameters:
        - name: affiliates_id
          in: path
          description: >-
            Unique identification number assigned to the Affiliate. List of
            Affiliate IDs can be found
            [here](https://docs.salla.dev/api-5394270).
          required: true
          example: ''
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/affiliate_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 326633404
                  title: this is marketing link
                  type: public
                  apply_to: first-second-order
                  commission:
                    type: percent
                    value: 50
                    minimum_apply: 0
                  discount:
                    type: percent
                    value: 50
                  scopes:
                    - id: 1234567
                      name: salla-store
                      type: store
                      link: https://salla.sa/intend/1234567
                      operation: include
                      thumbnail: >-
                        https://cdn.salla.sa/oEGE/03m2U2cnDGZck7WZNEDJgzMrrtH3MsBmMKXhoIV1.png
                  start_date: ''
                  end_date: ''
                  status: active
                  hide_total_stats: false
                  statistics:
                    visits: 2
                    sales:
                      amount: 21
                      currency: SAR
                    profit:
                      amount: 50
                      currency: SAR
                    orders_count: 1
          headers: {}
          x-apidog-name: Default Response
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
                    marketing.read
          headers: {}
          x-apidog-name: Unauthorized
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
          x-apidog-name: Not Found
        x-200:Deprecated Response:
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/old_affiliate_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 611208326
                  code: afl11
                  marketer_name: User Name
                  marketer_city: Medina
                  commission_type: fixed
                  amount:
                    amount: 300
                    currency: SAR
                  profit:
                    amount: 150
                    currency: SAR
                  links:
                    affiliate: >-
                      https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=aff&utm_campaign=CXNAZ
                    statistics: >-
                      https://salla.sa/dev-wofftr4xsra5xtlv/marketing/statistics/1604086218
                  apply_to: first_order
                  visits_count: 17
                  notes: Notes Here
          headers: {}
          x-apidog-name: Deprecated Response
      security:
        - bearer: []
      x-salla-php-method-name: retrieveretrieve
      x-salla-php-return-type: Affiliate
      x-apidog-folder: Default module/Merchant API/APIs/Affiliates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394271-run
components:
  schemas:
    affiliate_response_body:
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
          x-apidog-refs:
            01K9MGSRF4G8HBPB60TYG2VSPG:
              $ref: '#/components/schemas/NewAffiliate'
              x-apidog-overrides: {}
          x-apidog-orders:
            - 01K9MGSRF4G8HBPB60TYG2VSPG
          properties:
            id: &ref_0
              type: integer
              description: A unique identifier for the affiliate.
              x-apidog-mock: '611208326'
            title: &ref_1
              type: string
              description: The title of the affiliate link.
            type: &ref_2
              type: string
              description: The type of affiliate, either `public` or `private`.
              enum:
                - public
                - private
              x-apidog-enum:
                - value: public
                  name: ''
                  description: A publicly accessible affiliate link.
                - value: private
                  name: ''
                  description: A privately accessible affiliate link.
            apply_to: &ref_3
              type: string
              description: >-
                Specifies where the affiliate link should apply — either to the
                first order or to all orders.
              enum:
                - first-order
                - first-second-order
              x-apidog-enum:
                - value: first-order
                  name: ''
                  description: Applies only to the customer's first order.
                - value: first-second-order
                  name: ''
                  description: Applies to all customer orders.
            commission:
              type: object
              properties:
                type: &ref_4
                  type: string
                  description: >-
                    The type of affiliate commission. If `fixed`, a specific
                    numeric value like `100` is used. If `percent`, a percent
                    value like `15%` is applied.
                  enum:
                    - fixed
                    - percent
                  x-apidog-enum:
                    - value: fixed
                      name: ''
                      description: A fixed commission amount.
                    - value: percent
                      name: ''
                      description: A percentage-based commission.
                value: &ref_5
                  type: number
                  description: >-
                    The value of the commission, depending on the
                    `commission.type` — either a fixed amount or a percentage.
                minimum_apply: &ref_6
                  type: number
                  description: The minimum amount required for the commission to apply.
              x-apidog-orders: &ref_7
                - type
                - value
                - minimum_apply
              required:
                - type
                - value
              description: >-
                Details of the affiliate commission, specifying its type and
                value.
              x-apidog-ignore-properties: []
            discount:
              type: object
              properties:
                type: &ref_8
                  type: string
                  description: >-
                    The type of affiliate discount, either `fixed` or `percent`.
                    If the type is `percent`, the `value` will range from `0` to
                    `100%`.
                  enum:
                    - fixed
                    - percent
                  x-apidog-enum:
                    - value: fixed
                      name: ''
                      description: A fixed discount amount applied to the total price.
                    - value: percent
                      name: ''
                      description: A percentage-based discount applied to the total price.
                  nullable: true
                value: &ref_9
                  type: number
                  description: >-
                    The value of the affiliate discount, which depends on the
                    `discount.type` — either a fixed amount or a percentage.
              x-apidog-orders: &ref_10
                - type
                - value
              description: Details of the discount applied, if any.
              x-apidog-ignore-properties: []
            scopes:
              type: array
              items:
                type: object
                properties:
                  type: &ref_11
                    type: string
                    description: >-
                      The scope to which the affiliate applies, either `store`,
                      `product`, `category`.
                    enum:
                      - store
                      - product
                      - category
                    x-apidog-enum:
                      - value: store
                        name: ''
                        description: Purchases on specific stores
                      - value: product
                        name: ''
                        description: Purchases on specific products
                      - value: category
                        name: ''
                        description: ''
                  id: &ref_12
                    type: integer
                    description: >-
                      A unique identifier representing the scope, based on the
                      selected type.
                  operation: &ref_13
                    type: string
                    enum:
                      - include
                      - exclude
                    x-apidog-enum:
                      - value: include
                        name: ''
                        description: ''
                      - value: exclude
                        name: ''
                        description: ''
                    description: 'Scope operation: `include` or `exclude`'
                  thumbnail: &ref_14
                    type: string
                    description: Product image
                    nullable: true
                x-apidog-orders: &ref_15
                  - type
                  - id
                  - operation
                  - thumbnail
                required:
                  - type
                  - id
                  - operation
                  - thumbnail
                description: >-
                  The specific scope where the affiliate program will be
                  applied.
                x-apidog-ignore-properties: []
              description: The specific scope where the affiliate program will be applied.
            start_date: &ref_16
              type: string
              description: The start date from which the affiliate link becomes active.
            end_date: &ref_17
              type: string
              description: >-
                The end date after which the affiliate link will no longer be
                active.
            status: &ref_18
              type: string
              description: The current status of the affiliate program.
            hide_total_stats: &ref_19
              type: boolean
              description: >-
                Hide aggregate statistics. When this is set to `true`, the sales
                field will report `0` regardless of actual figures.
            statistics: &ref_20
              description: Affiliate statistics in numbers
              $ref: '#/components/schemas/AffiliateStatistics'
          required:
            - id
            - title
            - type
            - apply_to
            - commission
            - discount
            - scopes
            - start_date
            - end_date
            - status
          x-apidog-ignore-properties:
            - id
            - title
            - type
            - apply_to
            - commission
            - discount
            - scopes
            - start_date
            - end_date
            - status
            - hide_total_stats
            - statistics
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AffiliateStatistics:
      type: object
      x-apidog-refs: {}
      properties:
        sales:
          type: object
          properties:
            amount:
              type: number
              description: Marketer's sales amount
            currency:
              type: string
              description: Sales currency value
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        visits:
          type: number
          description: Affiliate's link total visits
        profit:
          type: object
          properties:
            amount:
              type: number
              description: Marketer's profit amount
            currency:
              type: string
              description: Profit currency value
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        orders_count:
          type: number
          description: Total orders count made via the affiliate link
      x-apidog-orders:
        - sales
        - visits
        - profit
        - orders_count
      required:
        - sales
        - profit
        - orders_count
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    NewAffiliate:
      type: object
      x-apidog-refs: {}
      properties:
        id: *ref_0
        title: *ref_1
        type: *ref_2
        apply_to: *ref_3
        commission:
          type: object
          properties:
            type: *ref_4
            value: *ref_5
            minimum_apply: *ref_6
          x-apidog-orders: *ref_7
          required:
            - type
            - value
          description: Details of the affiliate commission, specifying its type and value.
          x-apidog-ignore-properties: []
        discount:
          type: object
          properties:
            type: *ref_8
            value: *ref_9
          x-apidog-orders: *ref_10
          description: Details of the discount applied, if any.
          x-apidog-ignore-properties: []
        scopes:
          type: array
          items:
            type: object
            properties:
              type: *ref_11
              id: *ref_12
              operation: *ref_13
              thumbnail: *ref_14
            x-apidog-orders: *ref_15
            required:
              - type
              - id
              - operation
              - thumbnail
            description: The specific scope where the affiliate program will be applied.
            x-apidog-ignore-properties: []
          description: The specific scope where the affiliate program will be applied.
        start_date: *ref_16
        end_date: *ref_17
        status: *ref_18
        hide_total_stats: *ref_19
        statistics: *ref_20
      required:
        - id
        - title
        - type
        - apply_to
        - commission
        - discount
        - scopes
        - start_date
        - end_date
        - status
      x-apidog-orders:
        - id
        - title
        - type
        - apply_to
        - commission
        - discount
        - scopes
        - start_date
        - end_date
        - status
        - hide_total_stats
        - statistics
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    old_affiliate_response_body:
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
          $ref: '#/components/schemas/OldAffiliate'
      x-apidog-orders:
        - status
        - success
        - data
      required:
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OldAffiliate:
      description: ''
      type: object
      x-examples:
        Example:
          id: 611208326
          code: frm11
          marketer_name: User Name
          marketer_city: Medina
          commission_type: fixed
          amount:
            amount: 300
            currency: SAR
          profit:
            amount: 150
            currency: SAR
          links:
            affiliate: >-
              https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=aff&utm_campaign=CXNAZ
            statistics: >-
              https://salla.sa/dev-wofftr4xsra5xtlv/marketing/statistics/1604086218
          apply_to: first_order
          visits_count: 17
          notes: Notes Here
      title: OldAffiliate
      properties:
        id:
          type: number
          description: >-
            Affiliate unique identifier. Affiliate list can be found
            [here](https://docs.salla.dev/api-5394270).
          examples:
            - 611208326
        code:
          type: string
          description: Affiliate unique code.
          examples:
            - frm11
        marketer_name:
          type: string
          description: Affiliate marketing name
          examples:
            - User Name
        marketer_city:
          type: string
          description: Affiliate marketing city
          examples:
            - Medina
        commission_type:
          type: string
          description: >-
            If `comission_type` is `fixed`, then use a numeric value such as
            `100`. If `comission_type` is `percentage`, then use a percentage
            value such as `15`%. 
          enum:
            - fixed
            - percentage
          examples:
            - fixed
          x-apidog-enum:
            - value: fixed
              name: ''
              description: Fixed commission price
            - value: percentage
              name: ''
              description: Percentage commission price
        amount:
          type: object
          properties:
            amount:
              type: number
              description: Affilate amount value.
              examples:
                - 100
            currency:
              type: string
              description: Affilate amount currency.
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        profit:
          type: object
          properties:
            amount:
              type: number
              description: Profit Amount Value
              examples:
                - 100
            currency:
              type: string
              description: Profit Amount Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        links:
          type: object
          properties:
            affiliate:
              type: string
              description: Affiliate Link
              examples:
                - >-
                  https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=aff&utm_campaign=CXNAZ
            statistics:
              type: string
              description: 'Marketer Statistics Link '
              examples:
                - >-
                  https://salla.sa/dev-wofftr4xsra5xtlv/marketing/statistics/1604086218
          x-apidog-orders:
            - affiliate
            - statistics
          required:
            - affiliate
            - statistics
          x-apidog-ignore-properties: []
        apply_to:
          type: string
          description: >-
            Where the affiliate link should be applied. Available values are
            `all_orders` or `first_order`
          examples:
            - first_order
        visits_count:
          type: number
          description: Link visit counts
          examples:
            - 17
        notes:
          type: string
          description: Additional notes.
          examples:
            - Notes Here
      x-tags:
        - Responses
      x-apidog-orders:
        - id
        - code
        - marketer_name
        - marketer_city
        - commission_type
        - amount
        - profit
        - links
        - apply_to
        - visits_count
        - notes
      required:
        - id
        - code
        - marketer_name
        - marketer_city
        - commission_type
        - amount
        - profit
        - links
        - apply_to
        - visits_count
        - notes
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

## apis-affiliates/Create-Affiliate-Salla-Merchant-API-Salla-Docs

# Create Affiliate

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /affiliates:
    post:
      summary: Create Affiliate
      deprecated: false
      description: >-
        This endpoint allows you to create a marketing affiliate.



        :::danger[Deprecation Notice]

        Starting **November 01, 2025**, this endpoint’s response will be
        updated, and the old response body will be deprecated.

        To avoid breaking changes, update your integration to use the new
        schema, which supports the [new Salla affiliate
        system](https://help.salla.sa/article/501443344).

        If the Merchant is still using the old Salla affiliate system, the
        endpoint will still depend on deprecated payloads.

        See the [ChangeLog](https://docs.salla.dev/421127m0) for more details.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read_write`- Marketing Read & Write

        </Accordion>
      operationId: post-affiliates
      tags:
        - Default module/Merchant API/APIs/Affiliates
        - Affiliates
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              anyOf:
                - description: Deprecated Affiliate Body Request
                  $ref: '#/components/schemas/affiliate_request_body'
                - description: Default Affiliate Body Request
                  $ref: '#/components/schemas/old_affiliate_request_body'
            examples:
              '1':
                value:
                  title: Affiliate name
                  status: active
                  type: public
                  apply_to: first_order
                  commission:
                    type: percent
                    value: 20
                    minimum_apply: null
                  discount:
                    type: percent
                    value: 20
                  scopes:
                    type: store
                  start_date: '2024-09-27'
                  end_date: '2024-07-29'
                summary: New
              '2':
                value:
                  code: afl11
                  marketer_name: User Name
                  marketer_city: Medina
                  commission_type: fixed
                  amount: 20
                  apply_to: first_order
                  notes: Notes Here
                summary: Old
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/affiliate_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 611208326
                  title: Affiliate Test
                  type: public
                  apply_to: first_order
                  commission:
                    type: fix
                    value: 20
                    minimum_apply: 80
                  discount:
                    type: percent
                    value: '10'
                  scopes:
                    id: 1
                    type: product
                  start_date: ''
                  end_date: ''
                  status: ''
                  hide_total_stats: false
                  statistics:
                    visits: 17
                    sales:
                      amount: 300
                      currency: SAR
                    profit:
                      amount: 150
                      currency: SAR
                    orders_count: 9
          headers: {}
          x-apidog-name: Default Response
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
                    marketing.read_write
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
                  code: error
                  message: alert.invalid_fields
                  fields:
                    marketer_name:
                      - حقل اسم المسوق مطلوب.
                    marketer_city:
                      - حقل مدينة المسوق مطلوب.
                    commission_type:
                      - حقل نوع العمولة مطلوب.
                    amount:
                      - حقل مبلغ العمولة مطلوب.
                    apply_to:
                      - حقل تطبيق العمولة على مطلوب.
          headers: {}
          x-apidog-name: Error Validation
        x-200:Deprecated Response:
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/old_affiliate_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 611208326
                  code: afl11
                  marketer_name: User Name
                  marketer_city: Medina
                  commission_type: fixed
                  amount:
                    amount: 300
                    currency: SAR
                  profit:
                    amount: 150
                    currency: SAR
                  links:
                    affiliate: >-
                      https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=aff&utm_campaign=CXNAZ
                    statistics: >-
                      https://salla.sa/dev-wofftr4xsra5xtlv/marketing/statistics/1604086218
                  apply_to: first_order
                  visits_count: 17
                  notes: Notes Here
          headers: {}
          x-apidog-name: Deprecated Response
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: Affiliate
      x-apidog-folder: Default module/Merchant API/APIs/Affiliates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394269-run
components:
  schemas:
    old_affiliate_request_body:
      type: object
      properties:
        code:
          type: string
          description: >
            Affiliate Code. It must be 5 characters, only English letters or
            Numbers are valid.
          examples:
            - frm11
        marketer_name:
          type: string
          description: Marketer name.
          examples:
            - User Name
        marketer_city:
          type: string
          description: Marketer city.
          examples:
            - Medina
        commission_type:
          type: string
          description: >-
            If `comission_type` is `fixed`, then use a numeric value such as
            `100`. If `comission_type` is `percentage`, then use a percentage
            value such as `15`%. 
          enum:
            - fixed
            - percentage
          examples:
            - fixed
          x-apidog-enum:
            - value: fixed
              name: ''
              description: Fixed commission type
            - value: percentage
              name: ''
              description: Precentage commission type
        amount:
          type: number
          description: Marketing amount.
          examples:
            - 100
        apply_to:
          type: string
          description: >-
            Where the affiliatelink should be applied to. Available values are
            `all_orders` or `first_order`.
          enum:
            - first_order
            - all_orders
          examples:
            - first_order
          x-apidog-enum:
            - value: first_order
              name: ''
              description: Apply commission on first order only
            - value: all_orders
              name: ''
              description: Apply commission on all orders
        notes:
          type: string
          description: Additional notes.
          examples:
            - Notes Here
      required:
        - marketer_name
        - marketer_city
        - commission_type
        - amount
        - apply_to
      x-apidog-orders:
        - code
        - marketer_name
        - marketer_city
        - commission_type
        - amount
        - apply_to
        - notes
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    affiliate_request_body:
      type: object
      x-apidog-refs:
        01K9MH3PC5TPJNRQQSMFWKNASS: &ref_17
          $ref: '#/components/schemas/NewAffiliate'
          x-apidog-overrides:
            id: null
            status: null
            hide_total_stats: null
            statistics: null
      x-apidog-orders:
        - 01K9MH3PC5TPJNRQQSMFWKNASS
      properties:
        title: &ref_0
          type: string
          description: The title of the affiliate link.
        type: &ref_1
          type: string
          description: The type of affiliate, either `public` or `private`.
          enum:
            - public
            - private
          x-apidog-enum:
            - value: public
              name: ''
              description: A publicly accessible affiliate link.
            - value: private
              name: ''
              description: A privately accessible affiliate link.
        apply_to: &ref_2
          type: string
          description: >-
            Specifies where the affiliate link should apply — either to the
            first order or to all orders.
          enum:
            - first-order
            - first-second-order
          x-apidog-enum:
            - value: first-order
              name: ''
              description: Applies only to the customer's first order.
            - value: first-second-order
              name: ''
              description: Applies to all customer orders.
        commission:
          type: object
          properties:
            type: &ref_3
              type: string
              description: >-
                The type of affiliate commission. If `fixed`, a specific numeric
                value like `100` is used. If `percent`, a percent value like
                `15%` is applied.
              enum:
                - fixed
                - percent
              x-apidog-enum:
                - value: fixed
                  name: ''
                  description: A fixed commission amount.
                - value: percent
                  name: ''
                  description: A percentage-based commission.
            value: &ref_4
              type: number
              description: >-
                The value of the commission, depending on the `commission.type`
                — either a fixed amount or a percentage.
            minimum_apply: &ref_5
              type: number
              description: The minimum amount required for the commission to apply.
          x-apidog-orders: &ref_6
            - type
            - value
            - minimum_apply
          required:
            - type
            - value
          description: Details of the affiliate commission, specifying its type and value.
          x-apidog-ignore-properties: []
        discount:
          type: object
          properties:
            type: &ref_7
              type: string
              description: >-
                The type of affiliate discount, either `fixed` or `percent`. If
                the type is `percent`, the `value` will range from `0` to
                `100%`.
              enum:
                - fixed
                - percent
              x-apidog-enum:
                - value: fixed
                  name: ''
                  description: A fixed discount amount applied to the total price.
                - value: percent
                  name: ''
                  description: A percentage-based discount applied to the total price.
              nullable: true
            value: &ref_8
              type: number
              description: >-
                The value of the affiliate discount, which depends on the
                `discount.type` — either a fixed amount or a percentage.
          x-apidog-orders: &ref_9
            - type
            - value
          description: Details of the discount applied, if any.
          x-apidog-ignore-properties: []
        scopes:
          type: array
          items:
            type: object
            properties:
              type: &ref_10
                type: string
                description: >-
                  The scope to which the affiliate applies, either `store`,
                  `product`, `category`.
                enum:
                  - store
                  - product
                  - category
                x-apidog-enum:
                  - value: store
                    name: ''
                    description: Purchases on specific stores
                  - value: product
                    name: ''
                    description: Purchases on specific products
                  - value: category
                    name: ''
                    description: ''
              id: &ref_11
                type: integer
                description: >-
                  A unique identifier representing the scope, based on the
                  selected type.
              operation: &ref_12
                type: string
                enum:
                  - include
                  - exclude
                x-apidog-enum:
                  - value: include
                    name: ''
                    description: ''
                  - value: exclude
                    name: ''
                    description: ''
                description: 'Scope operation: `include` or `exclude`'
              thumbnail: &ref_13
                type: string
                description: Product image
                nullable: true
            x-apidog-orders: &ref_14
              - type
              - id
              - operation
              - thumbnail
            required:
              - type
              - id
              - operation
              - thumbnail
            description: The specific scope where the affiliate program will be applied.
            x-apidog-ignore-properties: []
          description: The specific scope where the affiliate program will be applied.
        start_date: &ref_15
          type: string
          description: The start date from which the affiliate link becomes active.
        end_date: &ref_16
          type: string
          description: >-
            The end date after which the affiliate link will no longer be
            active.
      required:
        - title
        - type
        - apply_to
        - commission
        - discount
        - scopes
        - start_date
        - end_date
      x-apidog-ignore-properties:
        - title
        - type
        - apply_to
        - commission
        - discount
        - scopes
        - start_date
        - end_date
      x-apidog-folder: ''
    NewAffiliate:
      type: object
      x-apidog-refs: {}
      properties:
        id: &ref_18
          type: integer
          description: A unique identifier for the affiliate.
          x-apidog-mock: '611208326'
        title: *ref_0
        type: *ref_1
        apply_to: *ref_2
        commission:
          type: object
          properties:
            type: *ref_3
            value: *ref_4
            minimum_apply: *ref_5
          x-apidog-orders: *ref_6
          required:
            - type
            - value
          description: Details of the affiliate commission, specifying its type and value.
          x-apidog-ignore-properties: []
        discount:
          type: object
          properties:
            type: *ref_7
            value: *ref_8
          x-apidog-orders: *ref_9
          description: Details of the discount applied, if any.
          x-apidog-ignore-properties: []
        scopes:
          type: array
          items:
            type: object
            properties:
              type: *ref_10
              id: *ref_11
              operation: *ref_12
              thumbnail: *ref_13
            x-apidog-orders: *ref_14
            required:
              - type
              - id
              - operation
              - thumbnail
            description: The specific scope where the affiliate program will be applied.
            x-apidog-ignore-properties: []
          description: The specific scope where the affiliate program will be applied.
        start_date: *ref_15
        end_date: *ref_16
        status: &ref_19
          type: string
          description: The current status of the affiliate program.
        hide_total_stats: &ref_20
          type: boolean
          description: >-
            Hide aggregate statistics. When this is set to `true`, the sales
            field will report `0` regardless of actual figures.
        statistics: &ref_21
          description: Affiliate statistics in numbers
          $ref: '#/components/schemas/AffiliateStatistics'
      required:
        - id
        - title
        - type
        - apply_to
        - commission
        - discount
        - scopes
        - start_date
        - end_date
        - status
      x-apidog-orders:
        - id
        - title
        - type
        - apply_to
        - commission
        - discount
        - scopes
        - start_date
        - end_date
        - status
        - hide_total_stats
        - statistics
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    AffiliateStatistics:
      type: object
      x-apidog-refs: {}
      properties:
        sales:
          type: object
          properties:
            amount:
              type: number
              description: Marketer's sales amount
            currency:
              type: string
              description: Sales currency value
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        visits:
          type: number
          description: Affiliate's link total visits
        profit:
          type: object
          properties:
            amount:
              type: number
              description: Marketer's profit amount
            currency:
              type: string
              description: Profit currency value
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        orders_count:
          type: number
          description: Total orders count made via the affiliate link
      x-apidog-orders:
        - sales
        - visits
        - profit
        - orders_count
      required:
        - sales
        - profit
        - orders_count
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    affiliate_response_body:
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
          x-apidog-refs:
            01K9MGSRF4G8HBPB60TYG2VSPG: *ref_17
          x-apidog-orders:
            - 01K9MGSRF4G8HBPB60TYG2VSPG
          properties:
            id: *ref_18
            title: *ref_0
            type: *ref_1
            apply_to: *ref_2
            commission:
              type: object
              properties:
                type: *ref_3
                value: *ref_4
                minimum_apply: *ref_5
              x-apidog-orders: *ref_6
              required:
                - type
                - value
              description: >-
                Details of the affiliate commission, specifying its type and
                value.
              x-apidog-ignore-properties: []
            discount:
              type: object
              properties:
                type: *ref_7
                value: *ref_8
              x-apidog-orders: *ref_9
              description: Details of the discount applied, if any.
              x-apidog-ignore-properties: []
            scopes:
              type: array
              items:
                type: object
                properties:
                  type: *ref_10
                  id: *ref_11
                  operation: *ref_12
                  thumbnail: *ref_13
                x-apidog-orders: *ref_14
                required:
                  - type
                  - id
                  - operation
                  - thumbnail
                description: >-
                  The specific scope where the affiliate program will be
                  applied.
                x-apidog-ignore-properties: []
              description: The specific scope where the affiliate program will be applied.
            start_date: *ref_15
            end_date: *ref_16
            status: *ref_19
            hide_total_stats: *ref_20
            statistics: *ref_21
          required:
            - id
            - title
            - type
            - apply_to
            - commission
            - discount
            - scopes
            - start_date
            - end_date
            - status
          x-apidog-ignore-properties:
            - id
            - title
            - type
            - apply_to
            - commission
            - discount
            - scopes
            - start_date
            - end_date
            - status
            - hide_total_stats
            - statistics
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    old_affiliate_response_body:
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
          $ref: '#/components/schemas/OldAffiliate'
      x-apidog-orders:
        - status
        - success
        - data
      required:
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OldAffiliate:
      description: ''
      type: object
      x-examples:
        Example:
          id: 611208326
          code: frm11
          marketer_name: User Name
          marketer_city: Medina
          commission_type: fixed
          amount:
            amount: 300
            currency: SAR
          profit:
            amount: 150
            currency: SAR
          links:
            affiliate: >-
              https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=aff&utm_campaign=CXNAZ
            statistics: >-
              https://salla.sa/dev-wofftr4xsra5xtlv/marketing/statistics/1604086218
          apply_to: first_order
          visits_count: 17
          notes: Notes Here
      title: OldAffiliate
      properties:
        id:
          type: number
          description: >-
            Affiliate unique identifier. Affiliate list can be found
            [here](https://docs.salla.dev/api-5394270).
          examples:
            - 611208326
        code:
          type: string
          description: Affiliate unique code.
          examples:
            - frm11
        marketer_name:
          type: string
          description: Affiliate marketing name
          examples:
            - User Name
        marketer_city:
          type: string
          description: Affiliate marketing city
          examples:
            - Medina
        commission_type:
          type: string
          description: >-
            If `comission_type` is `fixed`, then use a numeric value such as
            `100`. If `comission_type` is `percentage`, then use a percentage
            value such as `15`%. 
          enum:
            - fixed
            - percentage
          examples:
            - fixed
          x-apidog-enum:
            - value: fixed
              name: ''
              description: Fixed commission price
            - value: percentage
              name: ''
              description: Percentage commission price
        amount:
          type: object
          properties:
            amount:
              type: number
              description: Affilate amount value.
              examples:
                - 100
            currency:
              type: string
              description: Affilate amount currency.
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        profit:
          type: object
          properties:
            amount:
              type: number
              description: Profit Amount Value
              examples:
                - 100
            currency:
              type: string
              description: Profit Amount Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        links:
          type: object
          properties:
            affiliate:
              type: string
              description: Affiliate Link
              examples:
                - >-
                  https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=aff&utm_campaign=CXNAZ
            statistics:
              type: string
              description: 'Marketer Statistics Link '
              examples:
                - >-
                  https://salla.sa/dev-wofftr4xsra5xtlv/marketing/statistics/1604086218
          x-apidog-orders:
            - affiliate
            - statistics
          required:
            - affiliate
            - statistics
          x-apidog-ignore-properties: []
        apply_to:
          type: string
          description: >-
            Where the affiliate link should be applied. Available values are
            `all_orders` or `first_order`
          examples:
            - first_order
        visits_count:
          type: number
          description: Link visit counts
          examples:
            - 17
        notes:
          type: string
          description: Additional notes.
          examples:
            - Notes Here
      x-tags:
        - Responses
      x-apidog-orders:
        - id
        - code
        - marketer_name
        - marketer_city
        - commission_type
        - amount
        - profit
        - links
        - apply_to
        - visits_count
        - notes
      required:
        - id
        - code
        - marketer_name
        - marketer_city
        - commission_type
        - amount
        - profit
        - links
        - apply_to
        - visits_count
        - notes
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

