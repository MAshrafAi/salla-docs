# Apis Affiliates  Delete Affiliate Salla Merchant Api Salla Docs

## Table of Contents

- [apis-affiliates/Delete-Affiliate-Salla-Merchant-API-Salla-Docs](#apis-affiliates-delete-affiliate-salla-merchant-api-salla-docs)
- [apis-affiliates/List-Affiliate-Links-Salla-Merchant-API-Salla-Docs](#apis-affiliates-list-affiliate-links-salla-merchant-api-salla-docs)
- [apis-affiliates/List-Affiliates-Salla-Merchant-API-Salla-Docs](#apis-affiliates-list-affiliates-salla-merchant-api-salla-docs)

---

## apis-affiliates/Delete-Affiliate-Salla-Merchant-API-Salla-Docs

# Delete Affiliate

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /affiliates/{affiliates_id}:
    delete:
      summary: Delete Affiliate
      deprecated: false
      description: >-
        This endpoint allows you to delete an affiliate by passing the
        `affiliate_id` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read_write`- Marketing Read & Write

        </Accordion>
      operationId: delete-affiliates-affiliates.id
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
                $ref: '#/components/schemas/delete_success'
              example:
                status: 202
                success: true
                data:
                  message: The affiliate has been removed successfully
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
      x-apidog-folder: Default module/Merchant API/APIs/Affiliates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394273-run
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

## apis-affiliates/List-Affiliate-Links-Salla-Merchant-API-Salla-Docs

# List Affiliate Links

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /affiliates/{affiliates_id}/links:
    get:
      summary: List Affiliate Links
      deprecated: false
      description: >-
        This endpoint allows you to fetch links for  a specific affiliate by
        passing the `affiliate_id` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `marketing.read`- Marketing Read Only

        </Accordion>
      operationId: get-affiliates-affiliates.links
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
                $ref: '#/components/schemas/affiliate_links_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 611208326
                    status: active
                    marketer:
                      id: 611208326
                      name: Affiliater name
                    link: https://mtjr.at/CODE
                    statistics:
                      sales:
                        amount: 930.25
                        currency: SAR
                      visits: 11
                      profit:
                        amount: 263.16
                        currency: SAR
                      orders_count: 1
                pagination:
                  count: 10
                  total: 10
                  perPage: 65
                  currentPage: 10
                  totalPages: 10
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
      x-salla-php-method-name: retrieveretrieve
      x-salla-php-return-type: Affiliate
      x-apidog-folder: Default module/Merchant API/APIs/Affiliates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-13902666-run
components:
  schemas:
    affiliate_links_response_body:
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
            $ref: '#/components/schemas/AffiliateLink'
        pagination:
          $ref: '#/components/schemas/Pagination'
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      required:
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
    AffiliateLink:
      type: object
      x-apidog-refs: {}
      properties:
        id:
          type: number
          description: |-
            Affiliate unique identifier.
            Example: `611208326`
          x-apidog-mock: '611208326'
        status:
          type: string
          description: Status of the affiliate link
        marketer:
          type: object
          properties:
            id:
              type: number
              description: Marketer ID
            name:
              type: string
              description: Marketer Name
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          x-apidog-ignore-properties: []
        link:
          type: string
          description: Affiliate auto-generated link
        statistics:
          $ref: '#/components/schemas/AffiliateStatistics'
      x-apidog-orders:
        - id
        - status
        - marketer
        - link
        - statistics
      required:
        - id
        - status
        - marketer
        - link
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

## apis-affiliates/List-Affiliates-Salla-Merchant-API-Salla-Docs

# List Affiliates

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /affiliates:
    get:
      summary: List Affiliates
      deprecated: false
      description: >-
        This endpoint allows you to fetch a list of marketing affiliates.


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
      operationId: get-affiliates
      tags:
        - Default module/Merchant API/APIs/Affiliates
        - Affiliates
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/affiliates_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 611208326
                    title: Affiliate Test
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
                pagination:
                  count: 1
                  total: 1
                  perPage: 15
                  currentPage: 1
                  totalPages: 1
                  links: []
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
        x-200:Deprecated Response:
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/old_affiliates_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 611208326
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
                pagination:
                  count: 1
                  total: 1
                  perPage: 15
                  currentPage: 1
                  totalPages: 1
                  links: []
          headers: {}
          x-apidog-name: Deprecated Response
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Affiliate
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Affiliates
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394270-run
components:
  schemas:
    affiliates_response_body:
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
            id: zamj52ohgx06j
          items:
            type: object
            x-apidog-refs:
              01K9MGXWPRNZZXN95YSK3K3QAW:
                $ref: '#/components/schemas/NewAffiliate'
                x-apidog-overrides:
                  hide_total_stats: null
                  statistics: null
            x-apidog-orders:
              - 01K9MGXWPRNZZXN95YSK3K3QAW
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
                  Specifies where the affiliate link should apply — either to
                  the first order or to all orders.
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
                      The type of affiliate discount, either `fixed` or
                      `percent`. If the type is `percent`, the `value` will
                      range from `0` to `100%`.
                    enum:
                      - fixed
                      - percent
                    x-apidog-enum:
                      - value: fixed
                        name: ''
                        description: A fixed discount amount applied to the total price.
                      - value: percent
                        name: ''
                        description: >-
                          A percentage-based discount applied to the total
                          price.
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
                        The scope to which the affiliate applies, either
                        `store`, `product`, `category`.
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
                description: >-
                  The specific scope where the affiliate program will be
                  applied.
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
        pagination: &ref_19
          $ref: '#/components/schemas/Pagination'
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
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
        hide_total_stats:
          type: boolean
          description: >-
            Hide aggregate statistics. When this is set to `true`, the sales
            field will report `0` regardless of actual figures.
        statistics:
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
    old_affiliates_response_body:
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
            $ref: '#/components/schemas/OldAffiliate'
        pagination: *ref_19
      x-apidog-orders:
        - status
        - success
        - data
        - pagination
      required:
        - data
        - pagination
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

