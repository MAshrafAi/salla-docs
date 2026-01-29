# Apis Coupons  List Coupon Codes Salla Merchant Api Salla Docs

## Table of Contents

- [apis-coupons/List-Coupon-Codes-Salla-Merchant-API-Salla-Docs](#apis-coupons-list-coupon-codes-salla-merchant-api-salla-docs)
- [apis-coupons/List-Coupons-Salla-Merchant-API-Salla-Docs](#apis-coupons-list-coupons-salla-merchant-api-salla-docs)

---

## apis-coupons/List-Coupon-Codes-Salla-Merchant-API-Salla-Docs

# List Coupon Codes

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /coupons/codes:
    get:
      summary: List Coupon Codes
      deprecated: false
      description: >
        This endpoint allows you to return all the child coupons of the parent
        coupon by passing the `coupon_id` as a query parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read` - Marketing Read Only

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Coupons
        - Coupons
      parameters:
        - name: coupon_id
          in: query
          description: ' Unique identification number assigned to the Coupon. List Coupon IDs can be found [here](https://docs.salla.dev/api-5394275).'
          required: true
          example: 1257881496
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/childCouponCode_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 385681437
                    code: coupgmrGA
                  - id: 1622792886
                    code: coupgedkl
                  - id: 847582715
                    code: coupYgPYm
                  - id: 207766776
                    code: coupTyWXg
                  - id: 1582287441
                    code: coupgOuHi
                  - id: 672429890
                    code: coupgKhcv
                  - id: 997861675
                    code: coupgVbU8
                  - id: 1474282764
                    code: coupgPQFE
                  - id: 56440983
                    code: coupgmrEQ
                  - id: 19378402502
                    code: coupggFg9
                  - id: 1299038111
                    code: coupgBzJc
                  - id: 525025974
                    code: coupgUvBh
                  - id: 1762616341
                    code: coupRVtYC
                  - id: 989684078
                    code: coupgyIYy
                  - id: 349932097
                    code: coupgiDru
                pagination:
                  count: 15
                  total: 200
                  perPage: 15
                  currentPage: 3
                  totalPages: 14
                  links:
                    previous: >-
                      http://api.salla.dev/admin/v2/coupons/codes?coupon_id=626791646&page=2
                    next: >-
                      http://api.salla.dev/admin/v2/coupons/codes?coupon_id=626791646&page=4
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
                    marketing.read
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
                    coupon_id:
                      - حقل coupon id مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Coupons
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9185252-run
components:
  schemas:
    childCouponCode_response_body:
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
            $ref: '#/components/schemas/ChildCouponCodes'
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
    ChildCouponCodes:
      type: object
      properties:
        id:
          type: integer
          description: >-
            A unique identifier assigned to a specific coupon code. List of
            coupons cane be found [here](https://docs.salla.dev/api-5394275).
        code:
          type: string
          maxLength: 10
          description: Generated coupon code.
      x-apidog-orders:
        - id
        - code
      required:
        - id
        - code
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

## apis-coupons/List-Coupons-Salla-Merchant-API-Salla-Docs

# List Coupons

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /coupons:
    get:
      summary: List Coupons
      deprecated: false
      description: |-
        This endpoint allows you to return a list of coupons.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `marketing.read`- Marketing Read Only
        </Accordion>
      operationId: get-coupons
      tags:
        - Default module/Merchant API/APIs/Coupons
        - Coupons
      parameters:
        - name: keyword
          in: query
          description: 'Listing the coupons by keywords. '
          required: false
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/coupons_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 6930446
                    code: DEAL
                    type: fixed
                    status: active
                    is_apply_with_offer: true
                    amount:
                      amount: 30
                      currency: SAR
                    minimum_amount: 90
                    maximum_amount:
                      amount: 0
                      currency: SAR
                    show_maximum_amount: false
                    expiry_date: '2024-03-17 00:00:00'
                    start_date: '2025-03-17 00:00:00'
                    free_shipping: true
                    usage_limit: 90
                    usage_limit_per_user: 80
                    include_product_ids: []
                    exclude_product_ids: []
                    is_sale_products_exclude: true
                    include_category_ids: []
                    exclude_category_ids: []
                    include_customer_group_ids: []
                    exclude_customer_group_ids: []
                    exclude_brands_ids: []
                    exclude_shipping_ids: []
                    include_payment_methods: []
                    applied_in: all
                    is_group: true
                    group_name: Deals
                    group_coupons_count: 3
                    group_coupon_suffix: DEAL
                    group_coupons:
                      - code: DEAL5Wsl
                      - code: DEALgaNN
                      - code: DEALFRa7
                    beneficiary_domain: domain.test
                    statistics:
                      num_of_usage: 0
                      num_of_customers: 0
                      coupon_sales:
                        amount: 0
                        currency: SAR
                    created_at:
                      date: '2022-04-06 12:55:06.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    updated_at:
                      date: '2022-04-06 12:55:06.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    marketing_active: false
                    marketing_name: Name of Marketing
                    marketing_type: Percentage
                    marketing_amount: 500
                    marketing_hide_total_sales: false
                    marketing_show_maximum_amount: false
                    marketing_maximum_amount: 10000
                    marketing_info: Additional Notes
                    marketing_visits_count: 80
                    marketing_url: >-
                      https://salla.sa/teststore?utm_source=ref&utm_campaign=QAZCVS
                    marketing_statistics_url: https://mtjr.coupons/VvVMP
                  - id: 1622617640
                    code: QAZCVS
                    type: fixed
                    status: active
                    is_apply_with_offer: true
                    amount:
                      amount: 30
                      currency: SAR
                    minimum_amount: 9000
                    maximum_amount:
                      amount: 0
                      currency: SAR
                    show_maximum_amount: false
                    expiry_date: '2025-02-17 00:00:00'
                    start_date: '2026-03-17 00:00:00'
                    free_shipping: true
                    usage_limit: 600
                    usage_limit_per_user: 8
                    include_product_ids: []
                    exclude_product_ids: []
                    is_sale_products_exclude: true
                    include_category_ids: []
                    exclude_category_ids: []
                    include_customer_group_ids: []
                    exclude_customer_group_ids: []
                    exclude_brands_ids: []
                    exclude_shipping_ids: []
                    include_payment_methods: []
                    applied_in: all
                    is_group: false
                    group_name: Grouping1
                    group_coupons_count: 90
                    group_coupon_suffix: xyz
                    group_coupons: []
                    beneficiary_domain: domain.test
                    statistics:
                      num_of_usage: 0
                      num_of_customers: 0
                      coupon_sales:
                        amount: 0
                        currency: SAR
                    created_at:
                      date: '2022-04-06 12:45:13.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    updated_at:
                      date: '2022-04-06 12:45:13.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    marketing_active: true
                    marketing_name: Nabil
                    marketing_type: percentage
                    marketing_amount:
                      amount: 10
                      currency: SAR
                    marketing_hide_total_sales: false
                    marketing_show_maximum_amount: false
                    marketing_info: ''
                    marketing_visits_count: 0
                    marketing_url: >-
                      https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=ref&utm_campaign=QAZCVS
                    marketing_statistics_url: https://mtjr.coupons/w172T
                  - id: 242399780
                    code: azvfpsv
                    type: fixed
                    status: active
                    is_apply_with_offer: true
                    amount:
                      amount: 30
                      currency: SAR
                    minimum_amount:
                      amount: 100
                      currency: SAR
                    maximum_amount:
                      amount: 50
                      currency: SAR
                    show_maximum_amount: false
                    expiry_date: '2023-03-17 00:00:00'
                    start_date: '2022-04-24 06:00:00'
                    free_shipping: true
                    usage_limit: 10
                    usage_limit_per_user: 1
                    include_product_ids:
                      - 1261174103
                    exclude_product_ids:
                      - 277818017
                    is_sale_products_exclude: true
                    include_category_ids:
                      - 256950451
                      - 2064430530
                    exclude_category_ids:
                      - 307036893
                    include_customer_group_ids:
                      - 667738032
                    exclude_customer_group_ids: []
                    exclude_brands_ids:
                      - 1097509908
                    exclude_shipping_ids:
                      - 1935030040
                    include_payment_methods:
                      - all
                    applied_in: all
                    is_group: false
                    group_name: Grouping1
                    group_coupons_count: 90
                    group_coupon_suffix: bvg
                    group_coupons: []
                    beneficiary_domain: salla.sa
                    statistics:
                      num_of_usage: 0
                      num_of_customers: 0
                      coupon_sales:
                        amount: 0
                        currency: SAR
                    created_at:
                      date: '2022-04-06 12:38:06.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    updated_at:
                      date: '2022-04-06 12:59:14.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    marketing_active: true
                    marketing_name: User Name
                    marketing_type: percentage
                    marketing_amount:
                      amount: 5
                      currency: SAR
                    marketing_hide_total_sales: false
                    marketing_show_maximum_amount: true
                    marketing_maximum_amount: 4000
                    marketing_info: Marketing coupon for User Name
                    marketing_visits_count: 0
                    marketing_url: >-
                      https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=ref&utm_campaign=azvfpsv
                    marketing_statistics_url: https://mtjr.coupons/eqOuz
                pagination:
                  count: 3
                  total: 3
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
                    marketing.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: list Coupon
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Coupons
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394275-run
components:
  schemas:
    coupons_response_body:
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
          x-stoplight:
            id: f5100nxhmn0dp
          items:
            $ref: '#/components/schemas/Coupon'
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
    Coupon:
      description: ''
      type: object
      x-examples:
        Example:
          status: 200
          success: true
          data:
            id: 1622617640
            code: QAZCVS
            type: fixed
            status: active
            amount:
              amount: 30
              currency: SAR
            minimum_amount:
              amount: 2000
              currency: SAR
            maximum_amount:
              amount: 10000
              currency: SAR
            show_maximum_amount: false
            expiry_date: '2022-12-31 12:59:59'
            start_date: '2022-12-28 12:59:59'
            free_shipping: true
            usage_limit: 89
            usage_limit_per_user: 88
            include_product_ids:
              - '23390999'
            exclude_product_ids:
              - '21819432'
            is_sale_products_exclude: true
            include_category_ids:
              - '["1364368", "1364546"]'
            exclude_category_ids:
              - '1187611'
            include_customer_group_ids:
              - '7434'
            exclude_customer_group_ids:
              - '7433'
            exclude_brands_ids:
              - '49250'
            exclude_shipping_ids:
              - '["129390", "131750", "133804"]'
            include_customer_ids:
              - '123987'
            include_payment_methods:
              - all
            applied_in: all
            is_group: true
            group_name: Grouping1
            group_coupons_count: 90
            group_coupon_suffix: xyz
            group_coupons:
              - code: Grouping1xyz
            beneficiary_domain: null
            statistics:
              num_of_usage: 5
              num_of_customers: 10
              coupon_sales:
                amount: 20
                currency: SAR
            created_at:
              date: '2022-04-06 12:45:13.000000'
              timezone_type: 3
              timezone: Asia/Riyadh
            updated_at:
              date: '2022-04-06 12:45:13.000000'
              timezone_type: 3
              timezone: Asia/Riyadh
            marketing_active: true
            marketing_name: Nabil
            marketing_type: percentage
            marketing_amount:
              amount: 10
              currency: SAR
            marketing_hide_total_sales: false
            marketing_show_maximum_amount: false
            marketing_maximum_amount: 4000
            marketing_info: ''
            marketing_visits_count: 55
            marketing_url: >-
              https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=ref&utm_campaign=QAZCVS
            marketing_statistics_url: https://mtjr.coupons/w172T
      title: Coupon
      properties:
        id:
          type: number
          description: >-
            Coupon unique identifier. List of Coupon ID can be found
            [here](https://docs.salla.dev/api-5394275).
          examples:
            - 815296212
        code:
          type: string
          description: Coupon code.
          examples:
            - AAVVC
        type:
          type: string
          description: Coupon type.
          enum:
            - percentage
            - Percentage
            - fixed
            - Fixed
            - f
            - p
          examples:
            - percentage
          x-apidog-enum:
            - value: percentage
              name: ''
              description: Coupon price deducation based on a percentage
            - value: Percentage
              name: ''
              description: Coupon price deducation based on a percentage
            - value: fixed
              name: ''
              description: Coupon price deducation based on a fixed price
            - value: Fixed
              name: ''
              description: Coupon price deducation based on a fixed price
            - value: f
              name: ''
              description: Alias of `fixed` coupon type
            - value: p
              name: ''
              description: Alias of `percentage` coupon type
        status:
          type: string
          description: Coupon status.
          enum:
            - active
            - inactive
            - deleted
          examples:
            - active
          x-apidog-enum:
            - value: active
              name: ''
              description: The coupon is active
            - value: inactive
              name: ''
              description: The coupon is inactive
            - value: deleted
              name: ''
              description: The coupon is deleted
        is_apply_with_offer:
          type: boolean
          description: >-
            In case the variable is set to `true`, the coupon will be applied
            with the created offer that has an apply with coupon option
            activated in the offers; otherwise, it will not be applied.
          nullable: true
        amount:
          type: object
          properties:
            amount:
              type: number
              description: Coupon Amount
              examples:
                - 9000
            currency:
              type: string
              description: Coupon Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: Coupon amount.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        minimum_amount:
          type: object
          properties:
            amount:
              type: number
              description: Minimum Amount Value
              examples:
                - 2000
            currency:
              type: string
              description: Minimum Amount Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: The minimum coupon amount.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        maximum_amount:
          type: object
          properties:
            amount:
              type: number
              description: Maximum Amount Value
              examples:
                - 10000
            currency:
              type: string
              description: Maximum Amount Currency
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          description: The maximum coupon amount.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        show_maximum_amount:
          type: boolean
          description: Whether or not to show the coupon's maximum amount
          default: false
        expiry_date:
          type: string
          description: >-
            Coupon expiry date. Value ***MUST*** be at least one day later than
            today. Supports two formats, either `YYYY-MM-DD` or `YYYY-MM-DD
            HH:MM:SS`
          examples:
            - '2022-12-31 12:59:59'
        start_date:
          type: string
          description: >-
            Coupon start date. Supports two formats, either `YYYY-MM-DD` or
            `YYYY-MM-DD HH:MM:SS`
          examples:
            - '2022-12-28 12:59:59'
        free_shipping:
          type: boolean
          description: Whether or not to the coupon includes free shipping
          default: true
        usage_limit:
          type: number
          description: Coupon's usage limit
          examples:
            - 89
        usage_limit_per_user:
          type: number
          description: Coupon's usage limit per user
          examples:
            - 88
        include_product_ids:
          type: array
          description: >-
            List of included products IDs. List of products can be found
            [here]https://docs.salla.dev/api-5394168).
          items:
            type: string
            examples:
              - '23390999'
        exclude_product_ids:
          type: array
          description: >-
            List of excluded product IDs. List of products ca be found
            [here]https://docs.salla.dev/api-5394168).
          items:
            type: string
            examples:
              - '21819432'
        is_sale_products_exclude:
          type: boolean
          description: Whether or not to exclude On-Sale Products
          default: true
        include_category_ids:
          type: array
          description: >-
            List of included product Category IDs. List of categories can be
            found [here] (https://docs.salla.dev/api-5394207)
          items:
            type: string
            examples:
              - '["1364368", "1364546"]'
        exclude_category_ids:
          type: array
          description: >-
            List of included Category IDs. List of categories can be found
            [here] (https://docs.salla.dev/api-5394207)
          items:
            type: string
            examples:
              - '1187611'
        include_customer_group_ids:
          type: array
          description: >-
            List of included Customer Group IDs. List of customer groups can be
            found [here] (https://docs.salla.dev/api-5394129)
          items:
            type: string
            examples:
              - '7434'
        exclude_customer_group_ids:
          type: array
          description: >-
            List of excluded Customer Group IDs. List of customer groups can be
            found [here] (https://docs.salla.dev/api-5394129)
          items:
            type: string
            examples:
              - '7433'
        exclude_brands_ids:
          type: array
          description: >-
            List of excluded Brand IDs. List of brands can be found [here]
            (https://docs.salla.dev/api-5394213)
          items:
            type: string
            examples:
              - '49250'
        exclude_shipping_ids:
          type: array
          description: >-
            List of excluded Shipment Company IDs. Shipping companies list can
            be found [here](https://docs.salla.dev/api-5394239)
          items:
            type: string
            examples:
              - '["129390", "131750", "133804"]'
        include_customer_ids:
          type: array
          description: >-
            List of excluded Customer IDs. List of customers can be found
            [here](https://docs.salla.dev/api-5394121)
          items:
            type: string
            examples:
              - '123987'
        include_payment_methods:
          type: array
          description: >-
            List of included Payment Methods. List of Available Payment Methods
            can be found [here](https://docs.salla.dev/api-5394164).
          items:
            type: string
            enum:
              - all
              - apple_pay
              - bank
              - cod
              - credit_card
              - knet
              - mada
              - paypal
              - spotii_pay
              - stc_pay
              - tabby_installment
              - tamara_installment
            examples:
              - all
            x-apidog-enum:
              - value: all
                name: ''
                description: Include all available and enabled payment methods
              - value: apple_pay
                name: ''
                description: Apple Pay
              - value: bank
                name: ''
                description: Bank transfer
              - value: cod
                name: ''
                description: Cash On Delivery
              - value: credit_card
                name: ''
                description: Credit Card
              - value: knet
                name: ''
                description: 'KNET '
              - value: mada
                name: ''
                description: Mada
              - value: paypal
                name: ''
                description: PayPal
              - value: spotii_pay
                name: ''
                description: Spotii Pay
              - value: stc_pay
                name: ''
                description: STC Pay
              - value: tabby_installment
                name: ''
                description: Tabby Installment
              - value: tamara_installment
                name: ''
                description: Tamara Installment
        applied_in:
          type: string
          description: Coupon to be applied at. Value can either `all` or `web` or `app`
          enum:
            - all
            - web
            - app
          examples:
            - all
          x-apidog-enum:
            - value: all
              name: ''
              description: Apply the coupon on both the website and application
            - value: web
              name: ''
              description: Apply the coupon only on the website
            - value: app
              name: ''
              description: Apply the coupon only on the application
        is_group:
          type: boolean
          description: Whether or not the Coupon is part of a group of Coupons
          default: true
        group_name:
          type: string
          description: >-
            Coupon Group Name. `requiredif` `is_group` = `true`; otherwise
            returns `null` value
          examples:
            - Grouping1
          nullable: true
        group_coupons_count:
          type: number
          description: >-
            Coupon Group Count.`requiredif` `is_group` = `true`; otherwise
            returns `null` value
          examples:
            - 90
          nullable: true
        group_coupon_suffix:
          type: string
          description: >-
            Coupon Group Suffix. `requiredif` `is_group` = `true`; otherwise
            returns `null` value
          examples:
            - xyz
          nullable: true
        group_coupons:
          description: >-
            Group Coupons. `requiredif` `is_group` = `true`; otherwise returns
            `null` value
          type: array
          items:
            type: object
            properties:
              code:
                type: string
                description: Group Coupon Codes
                examples:
                  - Grouping1xyz
            x-apidog-orders:
              - code
            x-apidog-ignore-properties: []
        beneficiary_domain:
          type: string
          description: Beneficiary’s email domain name
          examples:
            - domain.test
          nullable: true
        statistics:
          type: object
          properties:
            num_of_usage:
              type: number
              description: 'Coupon Number of Usage Statistics '
            num_of_customers:
              type: number
              description: 'Coupon Number of Customers Statistics '
            coupon_sales:
              type: object
              properties:
                amount:
                  type: number
                  description: Coupon Sales Amount
                currency:
                  type: string
                  description: Coupon Sales Currency
              x-apidog-orders:
                - amount
                - currency
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - num_of_usage
            - num_of_customers
            - coupon_sales
          examples:
            - domain.test
          description: Coupon statistics.
          required:
            - num_of_usage
            - num_of_customers
            - coupon_sales
          x-apidog-ignore-properties: []
        created_at:
          type: object
          properties:
            date:
              type: string
              description: Coupon Date Creation
              examples:
                - '2022-12-12 13:50:33.000000'
            timezone_type:
              type: number
              description: Coupon Date Creation Timezone Type
              examples:
                - 3
            timezone:
              type: string
              description: Coupon Date Creation Timezone Value
              examples:
                - Asia/Riyadh
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          description: Date and time of creating the coupon.
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        updated_at:
          type: object
          properties:
            date:
              type: string
              description: Coupon Updated Date Timestamp
              examples:
                - '2022-12-13 14:08:09.000000'
            timezone_type:
              type: number
              description: Coupon Updated Date Timestamp Timezone Type
              examples:
                - 3
            timezone:
              type: string
              description: Coupon Updated Date Timestamp Timezone Value
              examples:
                - Asia/Riyadh
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          description: Date and time of updating the coupon.
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        marketing_active:
          type: boolean
          description: Whether or not the Marketing is active for a certain Coupon
          default: true
        marketing_name:
          type: string
          description: >-
            Marketer name assoicated to the Coupon. `requiredif`
            `marketing_active` = `true`; otherwise returns `null` value 
          examples:
            - User Name
          nullable: true
        marketing_email:
          type: string
          description: >-
            Marketer email assoicated to the Coupon. Value may appear if
            `marketing_acive: true`; otherwise returns `null` value.
          examples:
            - username@test.sa
          nullable: true
        marketing_type:
          type: string
          description: Coupon type.
          enum:
            - percentage
            - Percentage
            - fixed
            - Fixed
            - f
            - p
          examples:
            - percentage
          x-apidog-enum:
            - value: percentage
              name: ''
              description: Coupon price deducation based on a percentage
            - value: Percentage
              name: ''
              description: Coupon price deducation based on a percentage
            - value: fixed
              name: ''
              description: Coupon price deducation based on a fixed price
            - value: Fixed
              name: ''
              description: Coupon price deducation based on a fixed price
            - value: f
              name: ''
              description: Alias of `fixed` coupon type
            - value: p
              name: ''
              description: Alias of `percentage` coupon type
        marketing_amount:
          type: object
          description: >-
            The amount due to the marketer. `requiredif` `marketing_active` =
            `true`; otherwise returns `null` value 
          properties:
            amount:
              type: number
              description: Marketing Amount Value.
              examples:
                - 90
            currency:
              type: string
              description: Marketing Amount Currency.
              examples:
                - SAR
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
          nullable: true
        marketing_hide_total_sales:
          type: boolean
          description: >-
            Whether or not to hide the total sales from the marketer's stastics
            page. Value may appear if `marketing_acive: true`; otherwise returns
            `null` value.
          default: false
          nullable: true
        marketing_show_maximum_amount:
          type: boolean
          description: >-
            Whether or not to show the maximum amount of marketing amount to the
            marketers. Value may appear if `marketing_acive: true`; otherwise
            returns `null` value.
          default: true
          nullable: true
        marketing_maximum_amount:
          type: number
          description: >-
            Marketing maximum amount. Value may appear if `marketing_acive:
            true`; otherwise returns `null` value.
          default: 0
          examples:
            - 4000
          nullable: true
        marketing_info:
          type: string
          description: >-
            Additional notes to the Marketer. Value may appear if
            `marketing_acive: true`; otherwise returns `null` value.
          examples:
            - Additional Notes
          nullable: true
        marketing_visits_count:
          type: number
          description: >-
            Marketing visit counts. Value may appear if `marketing_acive: true`;
            otherwise returns `null` value.
          examples:
            - 33
          nullable: true
        marketing_url:
          type: string
          description: >-
            Marketing URL. Value may appear if `marketing_acive: true`;
            otherwise returns `null` value.
          examples:
            - https://salla.sa/teststore?utm_source=ref&utm_campaign=QAZCVS
          nullable: true
        marketing_statistics_url:
          type: string
          description: >-
            Marketing statistics URL. value may appear if `marketing_acive:
            true`; otherwise returns `null` value.
          examples:
            - https://mtjr.coupons/VvVMP
          nullable: true
      x-tags:
        - Responses
      x-apidog-orders:
        - id
        - code
        - type
        - status
        - is_apply_with_offer
        - amount
        - minimum_amount
        - maximum_amount
        - show_maximum_amount
        - expiry_date
        - start_date
        - free_shipping
        - usage_limit
        - usage_limit_per_user
        - include_product_ids
        - exclude_product_ids
        - is_sale_products_exclude
        - include_category_ids
        - exclude_category_ids
        - include_customer_group_ids
        - exclude_customer_group_ids
        - exclude_brands_ids
        - exclude_shipping_ids
        - include_customer_ids
        - include_payment_methods
        - applied_in
        - is_group
        - group_name
        - group_coupons_count
        - group_coupon_suffix
        - group_coupons
        - beneficiary_domain
        - statistics
        - created_at
        - updated_at
        - marketing_active
        - marketing_name
        - marketing_email
        - marketing_type
        - marketing_amount
        - marketing_hide_total_sales
        - marketing_show_maximum_amount
        - marketing_maximum_amount
        - marketing_info
        - marketing_visits_count
        - marketing_url
        - marketing_statistics_url
      required:
        - id
        - code
        - type
        - status
        - amount
        - minimum_amount
        - maximum_amount
        - show_maximum_amount
        - expiry_date
        - start_date
        - free_shipping
        - usage_limit
        - usage_limit_per_user
        - include_product_ids
        - exclude_product_ids
        - is_sale_products_exclude
        - include_category_ids
        - exclude_category_ids
        - include_customer_group_ids
        - exclude_customer_group_ids
        - exclude_brands_ids
        - exclude_shipping_ids
        - include_customer_ids
        - include_payment_methods
        - applied_in
        - is_group
        - group_name
        - group_coupons_count
        - group_coupon_suffix
        - group_coupons
        - beneficiary_domain
        - statistics
        - created_at
        - updated_at
        - marketing_active
        - marketing_name
        - marketing_email
        - marketing_type
        - marketing_amount
        - marketing_hide_total_sales
        - marketing_show_maximum_amount
        - marketing_maximum_amount
        - marketing_info
        - marketing_visits_count
        - marketing_url
        - marketing_statistics_url
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

