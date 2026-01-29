# Apis Merchant  List Store Scopes Salla Merchant Apis Salla Docs

## Table of Contents

- [apis-store-scopes/List-Store-Scopes-Salla-Merchant-APIs-Salla-Docs](#apis-store-scopes-list-store-scopes-salla-merchant-apis-salla-docs)
- [apis-store-scopes/Store-Scope-Details-Salla-Merchant-APIs-Salla-Docs](#apis-store-scopes-store-scope-details-salla-merchant-apis-salla-docs)

---

## apis-store-scopes/List-Store-Scopes-Salla-Merchant-APIs-Salla-Docs

# List Store Scopes

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /scopes:
    get:
      summary: List Store Scopes
      deprecated: false
      description: >-
        This endpoint allows you to list store scopes for multi-country
        functionality.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read`- Products Read Only

        </Accordion>
      operationId: List-Store-Scopes
      tags:
        - Default module/Merchant API/APIs/Store Scopes
        - Store Scopes
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/list_store_scopes_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: welcome
                    countries:
                      - id: 1473353380
                        name: Saudi Arabia
                        code: SA
                    primary_currency:
                      code: SAR
                      name: Saudi Riyal
                      symbol: SAR
                    default_language:
                      id: 1
                      name: العربية
                      status: enabled
                      rtl: true
                      flag: https://assets.salla.sa/images/flags/ar.svg
                      iso_code: ar
                      country_code: sa
                      sort_order: 0
                      is_default: true
                      auto_translate: false
                    is_default: true
                    domain: newxDom.mozdstore.com
                    url: https://mozdstore.com/en/?scope=1473353380
                    status: '1'
                    store_id: 67593
                    theme_customization_id: null
                    created_at: 1744549302
                    updated_at: 1765889285
                    branches:
                      - id: 1255900674
                        name: Silsala Warehouse - Riyadh. - Ahmed
                        status: active
                        is_default: true
                        priority: 0
                      - id: 1689312780
                        name: Dubai Branch
                        status: active
                        is_default: false
                        priority: 1
                      - id: 297123410
                        name: UAE branch
                        status: active
                        is_default: false
                        priority: 2
                      - id: 1429885875
                        name: الصحافة - الرياض
                        status: active
                        is_default: false
                        priority: 3
                    supported_languages:
                      - id: 2
                        name: English
                        status: enabled
                        rtl: false
                        flag: https://assets.salla.sa/images/flags/en.svg
                        iso_code: en
                        country_code: gb
                        sort_order: 0
                        is_default: false
                        auto_translate: false
                      - id: 1
                        name: العربية
                        status: enabled
                        rtl: true
                        flag: https://assets.salla.sa/images/flags/ar.svg
                        iso_code: ar
                        country_code: sa
                        sort_order: 0
                        is_default: true
                        auto_translate: false
                  - id: 289292369
                    name: سوق الامارات1
                    countries:
                      - id: 566146469
                        name: United Arab Emirates
                        code: AE
                    primary_currency:
                      code: AED
                      name: UAE Dirham
                      symbol: AED
                    default_language:
                      id: 1
                      name: العربية
                      status: enabled
                      rtl: true
                      flag: https://assets.salla.sa/images/flags/ar.svg
                      iso_code: ar
                      country_code: sa
                      sort_order: 0
                      is_default: true
                      auto_translate: false
                    is_default: false
                    domain: mozdstore.com
                    url: https://mozdstore.com/en/?scope=289292369
                    status: '0'
                    store_id: 67593
                    theme_customization_id: null
                    created_at: 1759937004
                    updated_at: 1766303973
                    branches:
                      - id: 732008664
                        name: Eastern District Warehouse
                        status: active
                        is_default: true
                        priority: 0
                      - id: 1937883793
                        name: Main warehouse - Mecca
                        status: active
                        is_default: false
                        priority: 1
                    supported_languages:
                      - id: 37
                        name: اُردُو‎
                        status: enabled
                        rtl: true
                        flag: https://assets.salla.sa/images/flags/ur.svg
                        iso_code: ur
                        country_code: pk
                        sort_order: 0
                        is_default: false
                        auto_translate: false
                      - id: 35
                        name: Türkçe
                        status: enabled
                        rtl: false
                        flag: https://assets.salla.sa/images/flags/tr.svg
                        iso_code: tr
                        country_code: tr
                        sort_order: 0
                        is_default: false
                        auto_translate: false
                      - id: 1
                        name: العربية
                        status: enabled
                        rtl: true
                        flag: https://assets.salla.sa/images/flags/ar.svg
                        iso_code: ar
                        country_code: sa
                        sort_order: 0
                        is_default: true
                        auto_translate: false
                pagination:
                  count: 2
                  total: 2
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
                  message: token is not valid
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-salla-php-method-name: get
      x-salla-php-return-type: json
      x-salla-php-return-base-type: json
      x-apidog-folder: Default module/Merchant API/APIs/Store Scopes
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-15104922-run
components:
  schemas:
    list_store_scopes_response_body:
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
          description: >
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          type: array
          items:
            $ref: '#/components/schemas/List%20Store%20Scopes%20'
        pagination:
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
    'List Store Scopes ':
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier of the store.
        name:
          type: string
          description: Display name of the store.
        countries:
          type: array
          description: List of countries where the store operates or is available.
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identifier of the country.
              name:
                type: string
                description: Full name of the country.
              code:
                type: string
                description: ISO country code.
            required:
              - id
              - name
              - code
            x-apidog-orders:
              - id
              - name
              - code
            x-apidog-ignore-properties: []
        primary_currency:
          type: object
          description: Primary currency used for store transactions.
          properties:
            code:
              type: string
              description: ISO currency code (e.g., SAR, USD).
            name:
              type: string
              description: Full name of the currency.
            symbol:
              type: string
              description: Currency symbol displayed in the store.
          required:
            - code
            - name
            - symbol
          x-apidog-orders:
            - code
            - name
            - symbol
          x-apidog-ignore-properties: []
        default_language:
          type: object
          description: Default language used for the store interface and content.
          properties:
            id:
              type: integer
              description: Unique identifier of the language.
            name:
              type: string
              description: Language display name.
            status:
              type: string
              description: Language availability status.
            rtl:
              type: boolean
              description: Indicates whether the language is right-to-left.
            flag:
              type: string
              description: Flag icon representing the language.
            iso_code:
              type: string
              description: ISO language code.
            country_code:
              type: string
              description: Associated country code.
            sort_order:
              type: integer
              description: Display order of the language.
            is_default:
              type: boolean
              description: Indicates whether this is the default language.
            auto_translate:
              type: boolean
              description: Indicates whether automatic translation is enabled.
          required:
            - id
            - name
            - status
            - rtl
            - flag
            - iso_code
            - country_code
            - sort_order
            - is_default
            - auto_translate
          x-apidog-orders:
            - id
            - name
            - status
            - rtl
            - flag
            - iso_code
            - country_code
            - sort_order
            - is_default
            - auto_translate
          x-apidog-ignore-properties: []
        is_default:
          type: boolean
          description: Indicates whether this store is set as the default store.
        domain:
          type: string
          description: Primary domain name assigned to the store.
        url:
          type: string
          description: Public URL used to access the store.
        status:
          type: string
          description: Current operational status of the store.
        store_id:
          type: integer
          description: Parent store identifier associated with this record.
        theme_customization_id:
          type: integer
          description: Identifier of the applied theme customization, if available.
        created_at:
          type: integer
          description: Unix timestamp representing when the store was created.
        updated_at:
          type: integer
          description: Unix timestamp representing the last update to the store.
        branches:
          type: array
          description: List of store branches or warehouses.
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identifier of the branch.
              name:
                type: string
                description: Name of the branch.
              status:
                type: string
                description: Operational status of the branch.
              is_default:
                type: boolean
                description: Indicates whether this branch is the default branch.
              priority:
                type: integer
                description: Priority level used for order fulfillment.
            required:
              - id
              - name
              - status
              - is_default
              - priority
            x-apidog-orders:
              - id
              - name
              - status
              - is_default
              - priority
            x-apidog-ignore-properties: []
        supported_languages:
          type: array
          description: List of languages supported by the store.
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identifier of the language.
              name:
                type: string
                description: Language display name.
              status:
                type: string
                description: Language availability status.
              rtl:
                type: boolean
                description: Indicates whether the language is right-to-left.
              flag:
                type: string
                description: Flag icon representing the language.
              iso_code:
                type: string
                description: ISO language code.
              country_code:
                type: string
                description: Associated country code.
              sort_order:
                type: integer
                description: Display order of the language.
              is_default:
                type: boolean
                description: Indicates whether this language is the default.
              auto_translate:
                type: boolean
                description: Indicates whether automatic translation is enabled.
            required:
              - id
              - name
              - status
              - rtl
              - flag
              - iso_code
              - country_code
              - sort_order
              - is_default
              - auto_translate
            x-apidog-orders:
              - id
              - name
              - status
              - rtl
              - flag
              - iso_code
              - country_code
              - sort_order
              - is_default
              - auto_translate
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - countries
        - primary_currency
        - default_language
        - is_default
        - domain
        - url
        - status
        - store_id
        - theme_customization_id
        - created_at
        - updated_at
        - branches
        - supported_languages
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

## apis-store-scopes/Store-Scope-Details-Salla-Merchant-APIs-Salla-Docs

# Store Scope Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /scopes/{scope}:
    get:
      summary: Store Scope Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch the associated store scope details of
        a specific branch (scope) for multi-country functionality by passing the
        `scope` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read`- Products Read Only

        </Accordion>
      operationId: Show-Store-Scope
      tags:
        - Default module/Merchant API/APIs/Store Scopes
        - Store Scopes
      parameters:
        - name: scope
          in: path
          description: List of store scope. Get the list of store scope [here]()
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/show_store_scopes_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1473353380
                  name: سوق المملكة العربية السعودية
                  countries:
                    - id: 1473353380
                      name: السعودية
                      code: SA
                  cities: []
                  branches:
                    - id: 1255900674
                      name: مستودع سلاسة 1
                      status: active
                      is_default: true
                      priority: 0
                    - id: 1689312780
                      name: Dubai Branch
                      status: active
                      is_default: false
                      priority: 1
                    - id: 297123410
                      name: فرع  الامارات
                      status: active
                      is_default: false
                      priority: 2
                    - id: 1429885875
                      name: الصحافة - الرياض
                      status: active
                      is_default: false
                      priority: 3
                  is_default: true
                  primary_currency:
                    code: SAR
                    name: ريال سعودي
                    symbol: ر.س
                  supported_currencies:
                    - code: AED
                      name: درهم اماراتي
                      symbol: ' د.إ'
                    - code: BHD
                      name: دينار بحريني
                      symbol: د.ب
                  default_language:
                    id: 1
                    name: العربية
                    status: enabled
                    rtl: true
                    flag: https://assets.salla.sa/images/flags/ar.svg
                    iso_code: ar
                    country_code: sa
                    sort_order: 0
                    is_default: true
                    auto_translate: false
                  supported_languages:
                    - id: 2
                      name: English
                      status: enabled
                      rtl: false
                      flag: https://assets.salla.sa/images/flags/en.svg
                      iso_code: en
                      country_code: gb
                      sort_order: 0
                      is_default: false
                      auto_translate: false
                    - id: 1
                      name: العربية
                      status: enabled
                      rtl: true
                      flag: https://assets.salla.sa/images/flags/ar.svg
                      iso_code: ar
                      country_code: sa
                      sort_order: 0
                      is_default: true
                      auto_translate: false
                  domain: newxDom.mozdstore.com
                  status: true
                  settings:
                    show_product_availability: true
                    stock_deduction_strategy: null
                    stock_quantity:
                      - priority
                    shipment_strategy:
                      type: one_shipment
                      calculate_method: general_total_shipment
                      assignment_strategy: less_price
                      calculate_method_value: '25'
                      assign_free_shipping_orders: true
                      ship_unlimited_products_from_default_branch: true
                  contacts:
                    phone: null
                    mobile: null
                    whatsapp: null
                    phone_country_code: null
                    mobile_country_code: null
                    whatsapp_country_code: null
                  store_id: 30708142
                  design_settings:
                    id: 277388345
                    name: رائد
                    avatar: >-
                      https://salla-dev-portal.s3.eu-central-1.amazonaws.com/uploads/1UFGYZnUj1ypyKCXPoziMiFMru6RBfFf35fsde.png
                    is_active: true
                    version: 1.282.0
                    version_details:
                      id: 1158271679
                      name: تنسيق رائد رقم (7)
                      theme: 1298199463
                      is_default: true
                      updated_at: 1766322841
                  tax_profile:
                    id: 525144736
                    country:
                      id: 1939592358
                      name: الكويت
                      code: KW
                    tax_number: '23431234565432'
                  created_at: 1744549302
                  updated_at: 1765889285
                  translations:
                    ar:
                      name: سوق المملكة العربية السعودية
                    en:
                      name: welcome
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
                  message: token is not valid
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-salla-php-method-name: get
      x-salla-php-return-type: json
      x-salla-php-return-base-type: json
      x-apidog-folder: Default module/Merchant API/APIs/Store Scopes
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-15107150-run
components:
  schemas:
    show_store_scopes_response_body:
      type: object
      properties:
        status:
          type: number
          description: >
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.
        success:
          type: boolean
          description: >
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/Show%20Store%20Scopes%20Details'
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
    Show Store Scopes Details:
      type: object
      properties:
        id:
          type: integer
          description: Unique identifier of the store.
        name:
          type: string
          description: Display name or title of the store.
        countries:
          type: array
          description: List of countries where the store operates or is available.
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identifier of the country.
              name:
                type: string
                description: Full name of the country.
              code:
                type: string
                description: ISO country code (e.g., SA, AE).
            x-apidog-orders:
              - id
              - name
              - code
            x-apidog-ignore-properties: []
        cities:
          type: array
          description: List of cities where the store operates.
          items:
            type: string
            description: City name.
        branches:
          type: array
          description: List of store branches.
          items:
            type: object
            properties:
              id:
                type: integer
                description: Unique identifier of the branch.
              name:
                type: string
                description: Name of the branch.
              status:
                type: string
                description: Operational status of the branch.
              is_default:
                type: boolean
                description: Indicates whether this branch is the default branch.
              priority:
                type: integer
                description: Priority used for order fulfillment.
            x-apidog-orders:
              - id
              - name
              - status
              - is_default
              - priority
            x-apidog-ignore-properties: []
        is_default:
          type: boolean
          description: Indicates whether this store is set as the default store.
        primary_currency:
          type: object
          description: Primary currency used for store transactions.
          properties:
            code:
              type: string
              description: ISO currency code. eg. USD, SAR
            name:
              type: string
              description: Full name of the currency.
            symbol:
              type: string
              description: Currency symbol displayed to customers. eg. $
          x-apidog-orders:
            - code
            - name
            - symbol
          x-apidog-ignore-properties: []
        supported_currencies:
          type: array
          description: List of currencies supported by the store.
          items:
            type: object
            properties:
              code:
                type: string
                description: ISO currency code.
              name:
                type: string
                description: Full name of the currency.
              symbol:
                type: string
                description: Currency symbol.
            x-apidog-orders:
              - code
              - name
              - symbol
            x-apidog-ignore-properties: []
        default_language:
          type: object
          description: Default language configuration for the store.
          properties:
            id:
              type: integer
              description: Unique identifier of the language.
            name:
              type: string
              description: Language display name.
            status:
              type: string
              description: Language availability status.
            rtl:
              type: boolean
              description: Indicates whether the language is right-to-left.
            flag:
              type: string
              description: Flag icon representing the language.
            iso_code:
              type: string
              description: ISO language code.
            country_code:
              type: string
              description: Associated country code.
            sort_order:
              type: integer
              description: Display order of the language.
            is_default:
              type: boolean
              description: Indicates whether this is the default language.
            auto_translate:
              type: boolean
              description: Indicates whether automatic translation is enabled.
          x-apidog-orders:
            - id
            - name
            - status
            - rtl
            - flag
            - iso_code
            - country_code
            - sort_order
            - is_default
            - auto_translate
          x-apidog-ignore-properties: []
        supported_languages:
          type: array
          description: List of languages supported by the store.
          items:
            type: object
            description: Language configuration details.
            properties:
              id:
                type: integer
                description: Unique identifier of the language.
              name:
                type: string
                description: Language display name.
              status:
                type: string
                description: Language availability status.
              rtl:
                type: boolean
                description: Indicates if the language is right-to-left.
              flag:
                type: string
                description: Flag icon for the language.
              iso_code:
                type: string
                description: 'ISO language code. '
              country_code:
                type: string
                description: Associated country code.
              sort_order:
                type: integer
                description: Display order.
              is_default:
                type: boolean
                description: Indicates if this language is default.
              auto_translate:
                type: boolean
                description: Indicates if auto-translation is enabled.
            x-apidog-orders:
              - id
              - name
              - status
              - rtl
              - flag
              - iso_code
              - country_code
              - sort_order
              - is_default
              - auto_translate
            x-apidog-ignore-properties: []
        domain:
          type: string
          description: Domain assigned to the store.
        status:
          type: boolean
          description: Indicates whether the store is active.
        settings:
          type: object
          description: Store shipping and inventory settings.
          properties:
            show_product_availability:
              type: boolean
              description: Controls visibility of product availability.
            stock_deduction_strategy:
              type: 'null'
              description: Strategy used for stock deduction.
            stock_quantity:
              type: array
              description: Stock quantity configuration values.
              items:
                type: string
            shipment_strategy:
              type: object
              description: Shipment creation and assignment configuration.
              properties:
                type:
                  type: string
                  description: Shipment type strategy.
                calculate_method:
                  type: string
                  description: Shipping fee calculation method.
                assignment_strategy:
                  type: string
                  description: Shipment assignment strategy.
                calculate_method_value:
                  type: string
                  description: Value used for shipping calculation.
                assign_free_shipping_orders:
                  type: boolean
                  description: Assign free shipping orders automatically.
                ship_unlimited_products_from_default_branch:
                  type: boolean
                  description: Allow unlimited shipments from the default branch.
              x-apidog-orders:
                - type
                - calculate_method
                - assignment_strategy
                - calculate_method_value
                - assign_free_shipping_orders
                - ship_unlimited_products_from_default_branch
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - show_product_availability
            - stock_deduction_strategy
            - stock_quantity
            - shipment_strategy
          x-apidog-ignore-properties: []
        contacts:
          type: object
          description: Store contact information.
          properties:
            phone:
              type: 'null'
              description: Store landline phone number.
            mobile:
              type: 'null'
              description: Store mobile phone number.
            whatsapp:
              type: 'null'
              description: Store WhatsApp number.
            phone_country_code:
              type: 'null'
              description: Country code for landline phone.
            mobile_country_code:
              type: 'null'
              description: Country code for mobile phone.
            whatsapp_country_code:
              type: 'null'
              description: Country code for WhatsApp number.
          x-apidog-orders:
            - phone
            - mobile
            - whatsapp
            - phone_country_code
            - mobile_country_code
            - whatsapp_country_code
          x-apidog-ignore-properties: []
        store_id:
          type: integer
          description: Parent store identifier.
        design_settings:
          type: object
          description: Theme and design configuration.
          properties:
            id:
              type: integer
              description: Theme identifier.
            name:
              type: string
              description: Theme name.
            avatar:
              type: string
              description: Theme preview image URL.
            is_active:
              type: boolean
              description: Indicates if the theme is active.
            version:
              type: string
              description: Theme version.
          x-apidog-orders:
            - id
            - name
            - avatar
            - is_active
            - version
          x-apidog-ignore-properties: []
        tax_profile:
          type: object
          description: Tax configuration for the store.
          properties:
            id:
              type: integer
              description: Tax profile identifier.
            country:
              type: object
              description: Country associated with the tax profile.
              properties:
                id:
                  type: integer
                  description: Country identifier.
                name:
                  type: string
                  description: Country name.
                code:
                  type: string
                  description: Country code.
              x-apidog-orders:
                - id
                - name
                - code
              x-apidog-ignore-properties: []
            tax_number:
              type: string
              description: Registered tax number.
          x-apidog-orders:
            - id
            - country
            - tax_number
          x-apidog-ignore-properties: []
        created_at:
          type: integer
          description: Unix timestamp when the store was created.
        updated_at:
          type: integer
          description: Unix timestamp of the last update.
        translations:
          type: object
          description: Localized store names.
          properties:
            ar:
              type: object
              description: Arabic translation.
              properties:
                name:
                  type: string
                  description: Store name in Arabic.
              x-apidog-orders:
                - name
              x-apidog-ignore-properties: []
            en:
              type: object
              description: English translation.
              properties:
                name:
                  type: string
                  description: Store name in English.
              x-apidog-orders:
                - name
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - ar
            - en
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - countries
        - cities
        - branches
        - is_default
        - primary_currency
        - supported_currencies
        - default_language
        - supported_languages
        - domain
        - status
        - settings
        - contacts
        - store_id
        - design_settings
        - tax_profile
        - created_at
        - updated_at
        - translations
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

