# Apis Coupons  Create Coupon Salla Merchant Api Salla Docs

## Table of Contents

- [apis-coupons/Create-Coupon-Salla-Merchant-API-Salla-Docs](#apis-coupons-create-coupon-salla-merchant-api-salla-docs)
- [apis-coupons/Delete-Coupon-Salla-Merchant-API-Salla-Docs](#apis-coupons-delete-coupon-salla-merchant-api-salla-docs)

---

## apis-coupons/Create-Coupon-Salla-Merchant-API-Salla-Docs

# Create Coupon

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /coupons:
    post:
      summary: Create Coupon
      deprecated: false
      description: >-

        This endpoint allows you to create Single Coupon, and Group Coupons.


        :::info[Information]

        Although the response payload you will be receiving of the two coupon
        types at once, each has its own required Body Requests.

        :::

        <Card>


        <Tabs>
          <Tab title="Single Coupon">
                                    
        When creating a `Single Coupon`, ensure that you are sending the
        following required variables:

            | Attribute               | Type    | Is Required |
            | ----------------------- | ------- | ----------- |
            | `code`                  | string  | Yes         |
            | `type`                  | string  | Yes         |
            | `amount`                | number  | Yes         |
            | `free_shipping`         | boolean | Yes         |
            | `expiry_date`           | string  | Yes         |
            | `exclude_sale_products` | boolean | Yes         |

            If `marketing_active` is valued as `true`, then when creating `Marketing Coupons`, ensure that you are sending the
            following required variables:

            | Attribute          | Type    | Is Required |
            | ------------------ | ------- | ----------- |
            | `marketing_active` | boolean | Yes         |
            | `marketing_name`   | string  | Yes         |
            | `marketing_type`   | string  | Yes         |
            | `marketing_amount` | number  | Yes         |

          </Tab>
          
        <Tab title="Group Coupons">
              
        If `is_group` is valued as `true`, then when creating `Group Coupons`,
        ensure that you are sending the following required variables:

            | Attribute               | Type    | Is Required |
            | ----------------------- | ------- | ----------- |
            | `is_group`              | boolean | Yes         |
            | `group_coupons_count`   | number  | Yes         |
            | `group_suffix`          | string  | Yes         |
            | `group_name`            | string  | Yes         |
            | `type`                  | string  | Yes         |
            | `amount`                | number  | Yes         |
            | `free_shipping`         | boolean | Yes         |
            | `expiry_date`           | string  | Yes         |
            | `exclude_sale_products` | boolean | Yes         |

            If `marketing_active` is valued as `true`, then when creating `Marketing Coupons`, ensure that you are sending the following required variables:

            | Attribute          | Type    | Is Required |
            | ------------------ | ------- | ----------- |
            | `marketing_active` | boolean | Yes         |
            | `marketing_name`   | string  | Yes         |
            | `marketing_type`   | string  | Yes         |
            | `marketing_amount` | number  | Yes         |

        </Tab>

        </Tabs>

        </Card>

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
          `marketing.read_write`- Marketing Read & Write
        </Accordion>
      operationId: post-coupons
      tags:
        - Default module/Merchant API/APIs/Coupons
        - Coupons
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/post_coupon_request_body'
            example:
              code: discount10
              type: percentage
              amount: 10
              maximum_amount: 50
              free_shipping: true
              start_date: '2022-08-02'
              expiry_date: '2022-12-12'
              exclude_sale_products: false
              is_apply_with_offer: true
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/coupon_response_body'
              examples:
                '1':
                  summary: Example | Single Coupon Response
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1622617640
                      code: QAZCVS
                      type: fixed
                      status: active
                      is_apply_with_offer: true
                      amount:
                        amount: 30
                        currency: SAR
                      minimum_amount: null
                      maximum_amount:
                        amount: 0
                        currency: SAR
                      show_maximum_amount: false
                      expiry_date: '2023-03-17 00:00:00'
                      start_date: null
                      free_shipping: true
                      usage_limit: null
                      usage_limit_per_user: null
                      include_product_ids:
                        - '1626467363'
                      exclude_product_ids:
                        - '213592621'
                      is_sale_products_exclude: true
                      include_category_ids:
                        - '676928739'
                      exclude_category_ids:
                        - '1585249762'
                      include_customer_group_ids:
                        - '322729604'
                      exclude_customer_group_ids:
                        - '1830458757'
                      exclude_brands_ids:
                        - '1939592358'
                      exclude_shipping_ids:
                        - '1345871747'
                      include_customer_ids: []
                      include_payment_methods:
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
                      applied_in: all
                      is_group: false
                      group_name: null
                      group_coupons_count: null
                      group_coupon_suffix: null
                      group_coupons: null
                      beneficiary_domain: null
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
                      marketing_maximum_amount: 4000
                      marketing_info: ''
                      marketing_visits_count: 0
                      marketing_url: >-
                        https://salla.sa/dev-wofftr4xsra5xtlv?utm_source=ref&utm_campaign=QAZCVS
                      marketing_statistics_url: https://mtjr.coupons/w172T
                '3':
                  summary: Example | Group Coupon Response
                  value:
                    status: 200
                    success: true
                    data:
                      id: 175515762
                      code: DEAL
                      type: fixed
                      status: active
                      is_apply_with_offer: true
                      amount:
                        amount: 30
                        currency: SAR
                      minimum_amount: null
                      maximum_amount:
                        amount: 0
                        currency: SAR
                      show_maximum_amount: false
                      expiry_date: '2023-03-17 00:00:00'
                      start_date: null
                      free_shipping: true
                      usage_limit: null
                      usage_limit_per_user: null
                      include_product_ids:
                        - '1626467363'
                      exclude_product_ids:
                        - '213592621'
                      is_sale_products_exclude: true
                      include_category_ids:
                        - '676928739'
                      exclude_category_ids:
                        - '1585249762'
                      include_customer_group_ids:
                        - '322729604'
                      exclude_customer_group_ids:
                        - '1830458757'
                      exclude_brands_ids:
                        - '1939592358'
                      exclude_shipping_ids:
                        - '1345871747'
                      include_customer_ids: []
                      include_payment_methods:
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
                      applied_in: all
                      is_group: true
                      group_name: Deals
                      group_coupons_count: 3
                      group_coupon_suffix: DEAL
                      group_coupons:
                        - code: DEALEmld
                        - code: DEALlUOc
                        - code: DEAL5W5z
                      beneficiary_domain: null
                      statistics:
                        num_of_usage: 0
                        num_of_customers: 0
                        coupon_sales:
                          amount: 0
                          currency: SAR
                      created_at:
                        date: '2022-04-06 11:13:33.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      updated_at:
                        date: '2022-04-06 11:13:33.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      marketing_active: false
                      marketing_name: null
                      marketing_type: null
                      marketing_amount: null
                      marketing_hide_total_sales: false
                      marketing_show_maximum_amount: false
                      marketing_maximum_amount: null
                      marketing_info: null
                      marketing_visits_count: null
                      marketing_url: null
                      marketing_statistics_url: null
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
                    marketing.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_validation_422'
              examples:
                '4':
                  summary: Example | Single Coupon Required Values
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        code:
                          - كود الكوبون مطلوب
                        type:
                          - نوع الكوبون مطلوب
                        amount:
                          - سعر الكوبون مطلوب
                        free_shipping:
                          - حقل تطبيق الشحن مطلوب.
                        expiry_date:
                          - حقل تاريخ نهاية التخفيض مطلوب.
                '5':
                  summary: Example | Group Coupon Required Values
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        code:
                          - كود الكوبون مطلوب
                        type:
                          - نوع الكوبون مطلوب
                        amount:
                          - سعر الكوبون مطلوب
                        free_shipping:
                          - حقل تطبيق الشحن مطلوب.
                        expiry_date:
                          - حقل تاريخ نهاية التخفيض مطلوب.
                        group_suffix:
                          - كود الكوبون يجب ان لا يتجاوز 5 حرفاً
                '6':
                  summary: Example | Marketing Coupon Required Values
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        marketing_name:
                          - يرجى اضافة اسم المسوق للكوبون
                        marketing_type:
                          - ' يرجى اضافة نوع كوبون التسويق'
                        marketing_amount:
                          - ' يرجى اضافة نوع سعر التسويق'
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: Coupon
      x-apidog-folder: Default module/Merchant API/APIs/Coupons
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394274-run
components:
  schemas:
    post_coupon_request_body:
      type: object
      properties:
        code:
          type: string
          description: >-
            Coupon Code. List Coupons Code can be found
            [here](https://docs.salla.dev/api-5394275).
          examples:
            - TestCoupon001
        type:
          type: string
          description: Coupon Type.
          enum:
            - Percentage
            - percentage
            - Fixed
            - fixed
            - F
            - f
            - P
            - p
          examples:
            - percentage
        amount:
          type: number
          description: Coupon Amount.
          examples:
            - 400
        status:
          type: string
          description: Coupon Status.
          examples:
            - inactive
        start_date:
          type: string
          description: >-
            Coupon Start Date. Supports two formats, either `YYYY-MM-DD` or
            `YYYY-MM-DD HH:MM:SS`
          format: date-time
          examples:
            - 2022-12-28 | 2022-12-28 10:50:01
        expiry_date:
          type: string
          description: >-
            Coupon Expiry Date. Value ***MUST*** be at least one day later than
            today. Supports two formats, either `YYYY-MM-DD` or `YYYY-MM-DD
            HH:MM:SS`
          format: date-time
          examples:
            - 2022-12-29 | 2022-12-29 11:55:21
        applied_in:
          type: string
          description: Coupon to be applied at. Value can either `all` or `web` or `app`
          enum:
            - all
            - web
            - app
          examples:
            - all
        is_group:
          type: boolean
          description: Whether or not the Coupon is of type `Group`.
          default: true
        is_apply_with_offer:
          type: boolean
          description: >-
            In case the variable is set to `true`, the coupon will be applied
            with the created offer that has an apply with coupon option
            activated in the offers; otherwise, it will not be applied.
          nullable: true
        group_name:
          type: string
          description: Group Name. `requiredif` `is_group` value is `true`
          examples:
            - Deals
        group_coupons_count:
          type: integer
          description: Group Coupons Count. `requiredif` `is_group` value is `true`
          examples:
            - 3
        group_suffix:
          type: string
          description: >-
            Group Name Suffix. `requiredif` `is_group` value is `true`. No
            spaces/numbers are allowed
          maxLength: 5
          examples:
            - xyz
        usage_limit:
          type: number
          description: Coupon Usage Limit
          examples:
            - 10
        usage_limit_per_user:
          type: number
          description: Coupon Usage Limit Per User
          examples:
            - 10
        minimum_amount:
          type: number
          description: Coupon Minimum Amount
          examples:
            - 10
        maximum_amount:
          type: number
          description: Coupon Maximum Amount. `requiredif` type is set to `percentage`
          examples:
            - 400
        free_shipping:
          type: boolean
          description: Whether or not the coupon include free shipping
          default: true
        exclude_sale_products:
          type: boolean
          description: Whether or not the coupon exclude on-sale products
          default: true
        show_maximum_amount:
          type: boolean
          description: Whether or not to show the maximum amount of the coupon
          default: true
        marketing_show_maximum_amount:
          type: boolean
          description: >-
            Whether or not to show the marketing maximum amount of the coupon to
            the marketer
          default: true
        marketing_active:
          type: boolean
          description: Whether or not the coupon include a marketer
          default: true
        marketing_name:
          type: string
          description: Marketer Name.
          examples:
            - User Test Marketing
        marketing_type:
          type: string
          description: Marketer Type.
          enum:
            - Percentage
            - percentage
            - Fixed
            - fixed
            - F
            - f
            - P
            - p
          examples:
            - Percentage
        marketing_amount:
          type: number
          description: Marketing Amount.
          examples:
            - 10
        marketing_hide_total_sales:
          type: boolean
          description: Whether or not hide total sales.
          default: true
        marketing_maximum_amount:
          type: number
          description: Marketing Maximum Amount Value
          examples:
            - 20
        marketing_info:
          type: string
          description: 'Marketing Additional Info '
          examples:
            - Additional Info
        beneficiary_domain:
          type: string
          description: Beneficiary Email Domain
          examples:
            - test.test
        products_include:
          type: array
          description: >-
            List of Included Products in the Coupon. List of products can be
            found [here](https://docs.salla.dev/api-5394168).
          items:
            type: string
            examples:
              - '1626467363'
        list_include_categories:
          type: array
          description: >-
            List of Included Categories in the Coupon. List of categories can be
            found [here](https://docs.salla.dev/api-5394207).
          items:
            type: string
            examples:
              - '676928739'
        products_exclude:
          type: array
          description: >-
            List of Excluded Products in the Coupon. List of products can be
            found [here](https://docs.salla.dev/api-5394168).
          items:
            type: string
            examples:
              - '213592621'
        list_exclude_categories:
          type: array
          description: >-
            List of Excluded Categories. List of categories can be found
            [here](https://docs.salla.dev/api-5394207).
          items:
            type: string
            examples:
              - '1585249762'
        list_exclude_brands:
          type: array
          description: >-
            List of Excluded Brands. List of brands can be found
            [here](https://docs.salla.dev/api-5394213). 
          items:
            type: string
            examples:
              - '1939592358'
        list_include_groups:
          type: array
          description: >-
            List of Included Customer Groups. List of customers can be found
            [here](https://docs.salla.dev/api-5394121).
          items:
            type: string
            examples:
              - '322729604'
        list_exclude_groups:
          type: array
          description: >-
            List of Excluded Customer Groups. List of customers can be found
            [here](https://docs.salla.dev/api-5394121).
          items:
            type: string
            examples:
              - '1830458757'
        list_exclude_shipping:
          type: array
          description: >-
            List of Excluded Shipping Companies. List of shipping companies can
            be found [here](https://docs.salla.dev/api-5394239)
          items:
            type: string
            examples:
              - '1345871747'
        payment_methods:
          type: array
          description: >-
            List of Included Payment Methods. List of available payment methods
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
      x-apidog-orders:
        - code
        - type
        - amount
        - status
        - start_date
        - expiry_date
        - applied_in
        - is_group
        - is_apply_with_offer
        - group_name
        - group_coupons_count
        - group_suffix
        - usage_limit
        - usage_limit_per_user
        - minimum_amount
        - maximum_amount
        - free_shipping
        - exclude_sale_products
        - show_maximum_amount
        - marketing_show_maximum_amount
        - marketing_active
        - marketing_name
        - marketing_type
        - marketing_amount
        - marketing_hide_total_sales
        - marketing_maximum_amount
        - marketing_info
        - beneficiary_domain
        - products_include
        - list_include_categories
        - products_exclude
        - list_exclude_categories
        - list_exclude_brands
        - list_include_groups
        - list_exclude_groups
        - list_exclude_shipping
        - payment_methods
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    coupon_response_body:
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
          $ref: '#/components/schemas/Coupon'
      x-apidog-orders:
        - status
        - success
        - data
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

## apis-coupons/Delete-Coupon-Salla-Merchant-API-Salla-Docs

# Delete Coupon

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /coupons/{coupon_id}:
    delete:
      summary: Delete Coupon
      deprecated: false
      description: |2-
         This endpoint allows you to delete a coupon by passing the `coupon_id` as a path parameter.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
          `marketing.read_write`- Marketing Read & Write
        </Accordion>
      operationId: delete-coupons-coupon.id
      tags:
        - Default module/Merchant API/APIs/Coupons
        - Coupons
      parameters:
        - name: coupon_id
          in: path
          description: ' Unique identification number assigned to the Coupon. List Coupon IDs can be found [here](https://docs.salla.dev/api-5394275).'
          required: true
          example: 0
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/delete_success'
              example:
                status: 202
                success: true
                data:
                  message: The coupon has been removed successfully
                  code: 202
          headers: {}
          x-apidog-name: Deleted Successfully
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
      security:
        - bearer: []
      x-salla-php-method-name: delete
      x-apidog-folder: Default module/Merchant API/APIs/Coupons
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394278-run
components:
  schemas:
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
        data:
          $ref: '#/components/schemas/DeleteSuccess'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
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

