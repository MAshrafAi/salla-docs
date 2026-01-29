# Apis Merchant  List Employees Salla Merchant Api Salla Docs

## Table of Contents

- [apis-employees/List-Employees-Salla-Merchant-API-Salla-Docs](#apis-employees-list-employees-salla-merchant-api-salla-docs)
- [apis-merchant/Store-Information-Salla-Merchant-API-Salla-Docs](#apis-merchant-store-information-salla-merchant-api-salla-docs)
- [apis-merchant/User-Information-Details-Salla-Merchant-API-Salla-Docs](#apis-merchant-user-information-details-salla-merchant-api-salla-docs)
- [apis-seo/List-SEO-Settings-Salla-Merchant-API-Salla-Docs](#apis-seo-list-seo-settings-salla-merchant-api-salla-docs)
- [apis-seo/Update-SEO-Settings-Salla-Merchant-API-Salla-Docs](#apis-seo-update-seo-settings-salla-merchant-api-salla-docs)

---

## apis-employees/List-Employees-Salla-Merchant-API-Salla-Docs

# List Employees

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /users:
    get:
      summary: List Employees
      deprecated: false
      description: |
        This endpoint allows you to fetch a list of your store employees.
      operationId: get-users
      tags:
        - Default module/Merchant API/APIs/Employees
        - Employees
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/employees_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 282459793
                    name: User Name1
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user1@test.sa
                    role: team
                    status: suspended
                  - id: 1148378730
                    name: User Name2
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user2@test.sa
                    role: team
                    status: suspended
                  - id: 1697216187
                    name: User Name3
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user3@test.sa
                    role: user
                    status: suspended
                  - id: 1296225140
                    name: User Name4
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user4@test.sa
                    role: team
                    status: suspended
                  - id: 467410228
                    name: User Name5
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user5@test.sa
                    role: user
                    status: suspended
                  - id: 355137381
                    name: User Name6
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user6@test.sa
                    role: team
                    status: suspended
                  - id: 115245908
                    name: User Name7
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user7@test.sa
                    role: team
                    status: suspended
                  - id: 1072903216
                    name: User Name8
                    mobile: '555555555'
                    mobile_code: '+966'
                    email: user8@test.sa
                    role: user
                    status: suspended
                  - id: 1689171978
                    name: User
                    mobile: '555555555'
                    mobile_code: '+966'
                    email: user@test.sa
                    role: user
                    status: active
                  - id: 2133460396
                    name: User Name9
                    mobile: '555555555'
                    mobile_code: '+966'
                    email: user9@test.sa
                    role: team
                    status: suspended
                  - id: 1279539873
                    name: User Name Test
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: test@user.sa
                    role: user
                    status: active
                  - id: 27854744
                    name: User Name10
                    mobile: '555555555'
                    mobile_code: '+966'
                    email: user10@test.sa
                    role: user
                    status: active
                  - id: 446255397
                    name: User Name11
                    mobile: '555555555'
                    mobile_code: '+966'
                    email: user11@test.sa
                    role: team
                    status: active
                  - id: 1192353076
                    name: User Name12
                    mobile: '777654321'
                    mobile_code: '+967'
                    email: user12@test.sa
                    role: user
                    status: active
                pagination:
                  count: 16
                  total: 16
                  perPage: 30
                  currentPage: 1
                  totalPages: 1
                  links: []
          headers: {}
          x-apidog-name: Success
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Employees
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Employees
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394259-run
components:
  schemas:
    employees_response_body:
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
            id: 2bb48nte96n99
          items:
            $ref: '#/components/schemas/Employees'
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
    Employees:
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier assigned to an individual employee working at a
            specific store. List of employees can be found
            [here](https://docs.salla.dev/api-5394259).
          examples:
            - 282459793
        name:
          type: string
          description: Given name of store employee.
          examples:
            - Taleb
        mobile:
          type: string
          description: Store employee mobile number.
          examples:
            - '580885751'
        mobile_code:
          type: string
          description: Store employee mobile Code
          examples:
            - '+966'
        email:
          type: string
          description: Email address of the store employee.
          examples:
            - taleb@marketing.agency
        role:
          type: string
          description: Role of the store employee. Value can either be `user` or `team`
          enum:
            - user
            - team
          examples:
            - team
          x-apidog-enum:
            - value: user
              name: ''
              description: User is of type user.
            - value: team
              name: ''
              description: User is of type team.
        status:
          type: string
          description: >-
            Status of the store employee. Value can either be `active` or
            `suspended`
          enum:
            - active
            - suspended
          examples:
            - suspended
          x-apidog-enum:
            - value: active
              name: ''
              description: User is active.
            - value: suspended
              name: ''
              description: User is suspended.
      x-apidog-orders:
        - id
        - name
        - mobile
        - mobile_code
        - email
        - role
        - status
      required:
        - id
        - name
        - mobile
        - mobile_code
        - email
        - role
        - status
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

## apis-merchant/Store-Information-Salla-Merchant-API-Salla-Docs

# Store Information

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /store/info:
    get:
      summary: Store Information
      deprecated: false
      description: |
        This endpoint allows you to return the Store's detail information.
      operationId: get-store-info
      tags:
        - Default module/Merchant API/APIs/Merchant
        - Store
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                x-examples:
                  Example 1:
                    status: 200
                    success: true
                    data:
                      id: 1601633483
                      username: ataba
                      name: العتبة
                      entity: company
                      email: salama@salla.sa
                      mobile: '+966111112121'
                      phone: '00201025557999'
                      avatar: >-
                        https://salla-dev.s3.eu-central-1.amazonaws.com/mKZa/ByziCuUQgAstAtQckVYu6Km4ETu6EAu4pD3mNKKg.png
                      store_location: 30.0778,31.2852
                      plan: pro
                      status: active
                      verified: false
                      currency: SAR
                      domain: >-
                        https://web-e5982bee6d091dbad7d59ff119030e2b.salla.group/ar/ataba
                      about: متجر العتبة هو مجمع لكل ما ترغب فيه
                      created_at: '2021-08-11 12:15:24'
                      default_branch:
                        id: 1846327032
                        name: مركز الجمال
                        status: active
                        location:
                          lat: '30.0778'
                          lng: '31.2852'
                        street: الرحمة
                        address_description: 123 شارع الرحمة
                        additional_number: '6666'
                        building_number: '6666'
                        local: omm
                        postal_code: '66666'
                        contacts:
                          phone: '+966508265874'
                          whatsapp: '+966508265874'
                          telephone: '012526886'
                        preparation_time: '6'
                        is_open: true
                        closest_time: null
                        working_hours:
                          - name: السبت
                            times:
                              - from: '09:00'
                                to: '23:55'
                          - name: الأحد
                            times:
                              - from: '09:00'
                                to: '23:55'
                          - name: الإثنين
                            times:
                              - from: '09:00'
                                to: '23:55'
                          - name: الثلاثاء
                            times:
                              - from: '09:00'
                                to: '23:55'
                          - name: الأربعاء
                            times:
                              - from: '09:00'
                                to: '23:55'
                          - name: الخميس
                            times:
                              - from: '09:00'
                                to: '23:55'
                          - name: الجمعة
                            times:
                              - from: '19:00'
                                to: '23:55'
                        is_cod_available: true
                        is_default: true
                        type: branch
                        cod_cost: '5.00'
                        country:
                          id: 1723506348
                          name: مصر
                          name_en: Egypt
                          code: EG
                          mobile_code: '+20'
                          capital: null
                        city:
                          id: 1355786303
                          name: CAIRO
                          name_en: CAIRO
                          country_id: 1723506348
                      licenses:
                        tax_number: '454364654'
                        commercial_number: null
                        freelance_number: '0000000000'
                      social:
                        website: ''
                        telegram: https://t.me/engsalama
                        twitter: https://twitter.com/SallaApp
                        facebookb: https://facebook.com
                        maroof: https://maroof.sa/
                        youtube: https://www.youtube.com/c/SallaApp
                        snapchat: https://snapchat.com
                        whatsapp: '+201025557999'
                      owner:
                        id: 1649301559
                        name: Username
                        email: demo@user.sa
                        mobile: '+966523185265'
                        created_at: '2021-08-11 12:15:24'
                properties:
                  status:
                    type: integer
                    description: Response Status
                  success:
                    type: boolean
                    description: 'Whether or not the response was successfully returned '
                  data:
                    type: object
                    properties:
                      id:
                        type: number
                        description: Store ID
                      name:
                        type: string
                        description: Store Name
                      entity:
                        type: string
                        description: Store Entity
                        enum:
                          - person
                          - company
                          - charity
                          - firm
                      email:
                        type: string
                        description: Store Email
                      avatar:
                        type: string
                        description: 'Store Avatar '
                      plan:
                        type: string
                        description: 'Store Plan '
                        enum:
                          - basic
                          - plus
                          - pro
                          - special
                        x-stoplight:
                          id: 2ovorzwlmwv4w
                      type:
                        type: string
                        description: Store Type
                        enum:
                          - demo
                          - development
                          - live
                        x-stoplight:
                          id: xymmxl5o554m7
                      status:
                        type: string
                        description: 'Store '
                        enum:
                          - active
                          - inactive
                      verified:
                        type: boolean
                        description: Whether ot not the Store is verified
                      currency:
                        type: string
                        description: Store Currency
                      domain:
                        type: string
                        description: Store Domain Name
                      description:
                        type: string
                        description: Store Description
                      licenses:
                        type: object
                        properties:
                          tax_number:
                            type: string
                            description: 'License '
                            nullable: true
                          commercial_number:
                            description: License Commercial Number
                            type: string
                            nullable: true
                          freelance_number:
                            type: string
                            description: License Freelance Number
                            nullable: true
                        x-apidog-orders:
                          - tax_number
                          - commercial_number
                          - freelance_number
                      social:
                        type: object
                        properties:
                          telegram:
                            type: string
                            description: Store Telegram Account/Username
                            nullable: true
                          twitter:
                            type: string
                            description: Store Twitter Account/Username
                            nullable: true
                          facebook:
                            type: string
                            description: Store Facebook Account/Username
                            nullable: true
                          maroof:
                            type: string
                            description: Store Maroof Account/Username
                            nullable: true
                          youtube:
                            type: string
                            description: Store YouTube Account
                            nullable: true
                          snapchat:
                            type: string
                            description: Store Snapchat Account/Username
                            nullable: true
                          whatsapp:
                            type: string
                            description: Store Whats Account/UsernameNumber
                            nullable: true
                          appstore_link:
                            type: string
                            description: Apple Store Link
                            nullable: true
                          googleplay_link:
                            type: string
                            description: Google Play Link
                            nullable: true
                        x-apidog-orders:
                          - telegram
                          - twitter
                          - facebook
                          - maroof
                          - youtube
                          - snapchat
                          - whatsapp
                          - appstore_link
                          - googleplay_link
                    x-apidog-orders:
                      - id
                      - name
                      - entity
                      - email
                      - avatar
                      - plan
                      - type
                      - status
                      - verified
                      - currency
                      - domain
                      - description
                      - licenses
                      - social
                x-apidog-orders:
                  - status
                  - success
                  - data
              example:
                status: 200
                success: true
                data:
                  id: 1305146709
                  name: dev-wofftr4xsra5xtlv
                  entity: company
                  email: salama@salla.sa
                  avatar: >-
                    https://salla-dev.s3.eu-central-1.amazonaws.com/logo/logo-fashion.jpg
                  plan: pro
                  type: demo
                  status: active
                  verified: false
                  currency: SAR
                  domain: https://salla.sa/dev-wofftr4xsra5xtlv
                  description: متجر تجريبي
                  licenses:
                    tax_number: '65464645654'
                    commercial_number: '8765282634'
                    freelance_number: '42333222'
                  social:
                    telegram: www.telegram.com
                    twitter: https://twitter.com/SallaApp
                    facebook: https://facebook.com
                    maroof: https://maroof.sa/
                    youtube: https://www.youtube.com/c/SallaApp
                    snapchat: https://snapchat.com
                    whatsapp: '+966501806978'
                    appstore_link: https://www.youtube.com/c/SallaApp
                    googleplay_link: https://www.youtube.com/c/SallaApp
          headers: {}
          x-apidog-name: Success
      security:
        - bearer: []
      x-salla-php-method-name: retrieveStoreInfo
      x-salla-php-return-type: StoreInformation
      x-apidog-folder: Default module/Merchant API/APIs/Merchant
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394261-run
components:
  schemas: {}
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

## apis-merchant/User-Information-Details-Salla-Merchant-API-Salla-Docs

# User Information Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /oauth2/user/info:
    get:
      summary: User Information Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch User information based on the [Access
        Token](https://docs.salla.dev/doc-421118) you have received, with a
        detailed response showcasing Store information.


        :::tip

        The `ID` , `email`, `name`, `mobile` and `role` are the information of
        the user who _authorized_ the app to be installed and it is __not__
        always the store owner as it can be one of the store team.

        :::
      operationId: get-user-info
      tags:
        - Default module/Merchant API/APIs/Merchant
        - Store
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                description: ''
                type: object
                x-examples:
                  Example:
                    status: 200
                    success: true
                    data:
                      id: 1689171978
                      name: User Name
                      email: user@test.sa
                      mobile: '+967772221188'
                      role: user
                      created_at: '2021-03-27 21:51:56'
                      store:
                        id: 847769313
                        owner_id: 1689171978
                        owner_name: User Name
                        username: username
                        name: تين و زيتون | أفضل متجر لبيع الفواكة
                        avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                        store_location: 21.39089898430621,39.8854900222291
                        plan: pro
                        status: active
                        created_at: '2017-09-15 03:34:29'
                properties:
                  status:
                    type: number
                    description: Response Status
                    examples:
                      - 200
                  success:
                    type: boolean
                    default: true
                    description: Whether or not the response is successful
                  data:
                    $ref: '#/components/schemas/UserInformation'
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  id: 1689171978
                  name: Test User
                  email: test@gmail.com
                  mobile: '+96652318526'
                  role: user
                  created_at: '2021-03-27 21:51:56'
                  merchant:
                    id: 847769313
                    username: User_name123
                    name: User Name
                    avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                    store_location: 21.589481104199123,39.67869125586653
                    plan: pro
                    status: active
                    domain: https://www.domain.com
                    tax_number: '424243241321234'
                    commercial_number: '3552100509'
                    created_at: '2021-12-31 12:59:59'
          headers: {}
          x-apidog-name: Success
      security:
        - bearer: []
      x-salla-php-method-name: retrieveUserInfo
      x-salla-php-return-type: UserInformation
      x-apidog-folder: Default module/Merchant API/APIs/Merchant
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9466620-run
components:
  schemas:
    UserInformation:
      title: UserInformation
      type: object
      properties:
        id:
          type: number
          description: A unique identifier assigned to a user of a system.
          examples:
            - 1689171978
        name:
          type: string
          description: User full given name.
          examples:
            - Test User
        email:
          type: string
          description: Email address of the user.
          examples:
            - test@gmail.com
        mobile:
          type: string
          description: User mobile number
          examples:
            - '+96652318526'
        role:
          type: string
          description: >-
            User role. Value can be either `user` or `team`, where` user` can be
            an admin, as a the owner of the store, while `team` can be referred
            to employees.
          enum:
            - user
            - team
          examples:
            - user
          x-apidog-enum:
            - value: user
              name: ''
              description: User type is user.
            - value: team
              name: ''
              description: User type is team.
        created_at:
          type: string
          description: User account creation date
          examples:
            - '2021-03-27 21:51:56'
        merchant:
          type: object
          properties:
            id:
              type: number
              description: A unique identification number assigned to a business.
              examples:
                - 847769313
            username:
              type: string
              description: The name used in the system.
              examples:
                - User_name123
            name:
              type: string
              description: The given full name.
              examples:
                - User Name
            avatar:
              type: string
              description: The merchant avatar.
              examples:
                - https://i.ibb.co/jyqRQfQ/avatar-male.webp
            store_location:
              type: string
              description: The geographical location of the store.
              examples:
                - 21.589481104199123,39.67869125586653
            plan:
              type: string
              description: The stoe plan associated with Salla.
              examples:
                - pro
            status:
              type: string
              description: Store status or condition.
              examples:
                - active
            domain:
              type: string
              description: Store domain name.
              examples:
                - https://www.domain.com
            tax_number:
              type: string
              description: Merchant tax number.
              examples:
                - '3552100509'
            commercial_number:
              type: string
              description: Merchant commercial number
              examples:
                - '424243241321234'
            created_at:
              type: string
              description: Merchant created at Timestamp
              examples:
                - '2021-12-31 12:59:59'
          x-apidog-orders:
            - id
            - username
            - name
            - avatar
            - store_location
            - plan
            - status
            - domain
            - tax_number
            - commercial_number
            - created_at
          required:
            - id
            - username
            - name
            - avatar
            - store_location
            - plan
            - status
            - domain
            - tax_number
            - commercial_number
            - created_at
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - email
        - mobile
        - role
        - created_at
        - merchant
      required:
        - id
        - name
        - email
        - mobile
        - role
        - created_at
        - merchant
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

## apis-seo/List-SEO-Settings-Salla-Merchant-API-Salla-Docs

# List SEO Settings

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /seo:
    get:
      summary: List SEO Settings
      deprecated: false
      description: >-
        This endpoint allows you to show your Store's SEO Settings, such as
        Title, Keywords, and Description.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: get-seo
      tags:
        - Default module/Merchant API/APIs/SEO
        - SEO
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/seo_response_body'
              example:
                status: 200
                success: true
                data:
                  title: Product for Health
                  keywords: Health
                  description: This product is for your health
                  url: https://salla.sa/testweb/sitemap.xml
                  friendly_urls_status: true
                  refersh_sitemap: https://salla.sa/testweb/sitemap/generate/1305146709
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
                    metadata.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: listSEO
      x-apidog-folder: Default module/Merchant API/APIs/SEO
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394262-run
components:
  schemas:
    seo_response_body:
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
          properties:
            title:
              type: string
              description: SEO Title. 🌐 [Support multi-language](doc-421122)
              examples:
                - SEO 101
            keywords:
              type: string
              description: SEO Keywords. 🌐 [Support multi-language](doc-421122)
              examples:
                - SEO Marketing
            description:
              type: string
              description: SEO Description. 🌐 [Support multi-language](doc-421122)
              examples:
                - That is SEO Marketing
            url:
              type: string
              description: Sitemap URL
              examples:
                - https://salla.sa/testweb/sitemap.xml
            friendly_urls_status:
              type: boolean
              description: 'Whether or not the SEO enabled for friendly URLS '
              default: true
            refersh_sitemap:
              type: string
              description: Sitemap Refresh URL
              examples:
                - https://salla.sa/testweb/sitemap/generate/1305146709
          x-apidog-orders:
            - title
            - keywords
            - description
            - url
            - friendly_urls_status
            - refersh_sitemap
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

## apis-seo/Update-SEO-Settings-Salla-Merchant-API-Salla-Docs

# Update SEO Settings

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /seo:
    put:
      summary: Update SEO Settings
      deprecated: false
      description: >-
        This endpoint allows you to update your Store's SEO Settings, such as
        Title, Keywords, and Description.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read_write`- Metadata Read & Write

        </Accordion>
      operationId: put-seo
      tags:
        - Default module/Merchant API/APIs/SEO
        - SEO
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/seo_request_body'
            example:
              title: SEO Title
              description: SEO Description
              keywords: SEO Keywords
              friendly_urls_status: true
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/seo_response_body'
              example:
                status: 200
                success: true
                data:
                  description: SEO Description
                  keywords: SEO Keywords
                  title: SEO Title
                  url: https://salla.sa/your-store/sitemap.xml
                  friendly_urls_status: true
                  refersh_sitemap: https://salla.sa/your-store/sitemap/generate/1305146709
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
                    metadata.read_write
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
                    friendly_urls_status:
                      - >-
                        يجب أن تكون قيمة حقل friendly urls status إما true أو
                        false 
                    title:
                      - يجب أن يكون حقل اللقب نصآ.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateSEO
      x-apidog-folder: Default module/Merchant API/APIs/SEO
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394263-run
components:
  schemas:
    seo_request_body:
      type: object
      properties:
        title:
          type: string
          description: >-
            SEO Title.  🌐 [Support
            multi-language](https://docs.salla.dev/doc-421122)
          examples:
            - SEO Title
        description:
          type: string
          description: >-
            SEO Description. 🌐 [Support
            multi-language](https://docs.salla.dev/doc-421122)
          examples:
            - SEO Description
        keywords:
          type: string
          description: SEO Keywords. 🌐 [Support multi-language](doc-421122)
          examples:
            - SEO Keywords
        url:
          type: string
          description: Sitemap URL.
          examples:
            - https://salla.sa/your-store/sitemap.xml
        friendly_urls_status:
          type: boolean
          default: true
          description: Whether or not the SEO enabled for friendly URLS .
        refersh_sitemap:
          type: boolean
          description: Whether or not to refresh the sitemap.
      x-apidog-orders:
        - title
        - description
        - keywords
        - url
        - friendly_urls_status
        - refersh_sitemap
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    seo_response_body:
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
          properties:
            title:
              type: string
              description: SEO Title. 🌐 [Support multi-language](doc-421122)
              examples:
                - SEO 101
            keywords:
              type: string
              description: SEO Keywords. 🌐 [Support multi-language](doc-421122)
              examples:
                - SEO Marketing
            description:
              type: string
              description: SEO Description. 🌐 [Support multi-language](doc-421122)
              examples:
                - That is SEO Marketing
            url:
              type: string
              description: Sitemap URL
              examples:
                - https://salla.sa/testweb/sitemap.xml
            friendly_urls_status:
              type: boolean
              description: 'Whether or not the SEO enabled for friendly URLS '
              default: true
            refersh_sitemap:
              type: string
              description: Sitemap Refresh URL
              examples:
                - https://salla.sa/testweb/sitemap/generate/1305146709
          x-apidog-orders:
            - title
            - keywords
            - description
            - url
            - friendly_urls_status
            - refersh_sitemap
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
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

