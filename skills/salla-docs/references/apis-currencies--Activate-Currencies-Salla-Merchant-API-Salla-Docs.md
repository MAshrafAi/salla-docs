# Apis Currencies  Activate Currencies Salla Merchant Api Salla Docs

## Table of Contents

- [apis-currencies/Activate-Currencies-Salla-Merchant-API-Salla-Docs](#apis-currencies-activate-currencies-salla-merchant-api-salla-docs)
- [apis-currencies/List-Available-Currencies](#apis-currencies-list-available-currencies)
- [apis-currencies/List-Currencies-Salla-Merchant-API-Salla-Docs](#apis-currencies-list-currencies-salla-merchant-api-salla-docs)
- [apis-languages/Add-Langugae-Salla-Merchant-API-Salla-Docs](#apis-languages-add-langugae-salla-merchant-api-salla-docs)
- [apis-languages/List-Languages-Salla-Merchant-API-Salla-Docs](#apis-languages-list-languages-salla-merchant-api-salla-docs)

---

## apis-currencies/Activate-Currencies-Salla-Merchant-API-Salla-Docs

# Activate Currencies

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /currencies:
    post:
      summary: Activate Currencies
      deprecated: false
      description: >-
        This endpoint allows activating either a single currency or a group of
        currencies.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: post-currencies
      tags:
        - Default module/Merchant API/APIs/Currencies
        - Currencies
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                currencies:
                  type: array
                  items:
                    type: object
                    properties:
                      code:
                        type: string
                        description: >-
                          Currency Code Value. For all enum values for the
                          Currency Code, use this [Endpoint](api-5394258).
                        examples:
                          - SAR
                      status:
                        type: boolean
                        default: true
                        description: Status of the Currency on the Store
                    x-apidog-orders:
                      - code
                      - status
                    x-apidog-ignore-properties: []
              x-apidog-orders:
                - currencies
              x-apidog-ignore-properties: []
            example:
              currencies:
                - code: SAR
                  status: true
                - code: USD
                  status: false
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/currencies_response_body'
              example:
                status: 200
                success: true
                data:
                  - name: ريال سعودي
                    code: SAR
                    symbol: ر.س
                    status: disabled
                  - name: درهم اماراتي
                    code: AED
                    symbol: ' د.إ'
                    status: enabled
                  - name: جنيه مصري
                    code: EGP
                    symbol: ج.م
                    status: enabled
                  - name: دولار أمريكي
                    code: USD
                    symbol: $
                    status: enabled
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
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_validation_422'
              examples:
                '3':
                  summary: Example
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        currencies:
                          - يجب تفعيل عملة واحدة على الأقل.
                '4':
                  summary: Example | Invalid Code Field
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        currencies.0.code:
                          - حقل currencies.0.code غير صالحٍ
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: activate
      x-salla-php-return-type: Currencies[]
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Currencies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394256-run
components:
  schemas:
    currencies_response_body:
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
            id: tiveeiv2mfvp2
          items:
            $ref: '#/components/schemas/Currencies'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Currencies:
      type: object
      properties:
        name:
          type: string
          description: Name of the currency
          examples:
            - ريال سعودي
        code:
          type: string
          description: Code of the currency
          examples:
            - SAR
        symbol:
          type: string
          description: Symbol of the currency
          examples:
            - ر.س
        status:
          type: string
          description: Status of the currency. The value is either `Enabled` or `Disabled`
          enum:
            - enabled
            - disabled
          examples:
            - disabled
          x-apidog-enum:
            - value: enabled
              name: ''
              description: Currency is enabled.
            - value: disabled
              name: ''
              description: Currency is diabled.
      x-apidog-orders:
        - name
        - code
        - symbol
        - status
      required:
        - name
        - code
        - symbol
        - status
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

## apis-currencies/List-Available-Currencies

# List Available Currencies

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /currencies/available:
    get:
      summary: List Available Currencies
      deprecated: false
      description: >-
        This endpoint allows you to fetch a list of available currencies
        alongside their details, such as `name`, `code`, `symbol` and `status`.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: get-currencies-available
      tags:
        - Default module/Merchant API/APIs/Currencies
        - Currencies
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/availableCurrencies_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1745409636
                    country_name_en: Saudi Arabia
                    country_name_ar: السعودية
                    country_code: SA
                    currency_code: SAR
                    currency_name_en: Riyals
                    currency_name_ar: ريال سعودي
                  - id: 566146469
                    country_name_en: United Arab Emirates
                    country_name_ar: الامارات
                    country_code: AE
                    currency_code: AED
                    currency_name_en: ''
                    currency_name_ar: درهم اماراتي
                  - id: 1914793182
                    country_name_en: Kuwait
                    country_name_ar: الكويت
                    country_code: KW
                    currency_code: KWD
                    currency_name_en: Dinar
                    currency_name_ar: دينار كويتي
                  - id: 82390046
                    country_name_en: Qatar
                    country_name_ar: قطر
                    country_code: QA
                    currency_code: QAR
                    currency_name_en: Rials
                    currency_name_ar: ريال قطري
                  - id: 1688289458
                    country_name_en: Bahrain
                    country_name_ar: البحرين
                    country_code: BH
                    currency_code: BHD
                    currency_name_en: Dinar
                    currency_name_ar: دينار بحريني
                  - id: 1350008014
                    country_name_en: Iraq
                    country_name_ar: العراق
                    country_code: IQ
                    currency_code: IQD
                    currency_name_en: Dinar
                    currency_name_ar: دينار عراقي
                  - id: 889477903
                    country_name_en: Oman
                    country_name_ar: عمان
                    country_code: OM
                    currency_code: OMR
                    currency_name_en: Rials
                    currency_name_ar: ريال عماني
                  - id: 1587042020
                    country_name_en: Egypt
                    country_name_ar: مصر
                    country_code: EG
                    currency_code: EGP
                    currency_name_en: Pounds
                    currency_name_ar: جنيه مصري
                  - id: 1637823335
                    country_name_en: Sudan
                    country_name_ar: السودان
                    country_code: SD
                    currency_code: SDG
                    currency_name_en: Pounds
                    currency_name_ar: جنيه سوداني
                  - id: 642580259
                    country_name_en: Libya
                    country_name_ar: ليبيا
                    country_code: LY
                    currency_code: LYD
                    currency_name_en: Dinar
                    currency_name_ar: دينار ليبي
                  - id: 1627982233
                    country_name_en: Algeria
                    country_name_ar: الجزائر
                    country_code: DZ
                    currency_code: DZD
                    currency_name_en: Dinar
                    currency_name_ar: دينار جزائري
                  - id: 195201146
                    country_name_en: Tunisia
                    country_name_ar: تونس
                    country_code: TN
                    currency_code: TND
                    currency_name_en: Dinar
                    currency_name_ar: دينار تونسي
                  - id: 1881742892
                    country_name_en: Morocco
                    country_name_ar: المغرب
                    country_code: MA
                    currency_code: MAD
                    currency_name_en: Dirham
                    currency_name_ar: درهم مغربي
                  - id: 55124855
                    country_name_en: Syria
                    country_name_ar: سوريا
                    country_code: SY
                    currency_code: SYP
                    currency_name_en: Pounds
                    currency_name_ar: ليرة سورية
                  - id: 1168042202
                    country_name_en: Lebanon
                    country_name_ar: لبنان
                    country_code: LB
                    currency_code: LBP
                    currency_name_en: Pounds
                    currency_name_ar: ليرة لبنانية
                  - id: 773200552
                    country_name_en: Australia
                    country_name_ar: استراليا
                    country_code: AU
                    currency_code: AUD
                    currency_name_en: Dollars
                    currency_name_ar: دولار استرالي
                  - id: 1337421468
                    country_name_en: Germany
                    country_name_ar: المانيا
                    country_code: DE
                    currency_code: EUR
                    currency_name_en: Euro
                    currency_name_ar: يورو
                  - id: 1834070720
                    country_name_en: Indonesia
                    country_name_ar: اندونيسيا
                    country_code: ID
                    currency_code: IDR
                    currency_name_en: Rupiahs
                    currency_name_ar: روبية إندونيسية
                  - id: 1201022676
                    country_name_en: Jordan
                    country_name_ar: الأردن
                    country_code: JO
                    currency_code: JOD
                    currency_name_en: Dinar
                    currency_name_ar: دينار أردني
                  - id: 852895898
                    country_name_en: Ecuador
                    country_name_ar: الإكوادور
                    country_code: EC
                    currency_code: USD
                    currency_name_en: Dollars
                    currency_name_ar: دولار أمريكي
                  - id: 862212704
                    country_name_en: Sweden
                    country_name_ar: السويد
                    country_code: SE
                    currency_code: SEK
                    currency_name_en: Kronor
                    currency_name_ar: كرونة سويدية
                  - id: 1661028235
                    country_name_en: China
                    country_name_ar: الصين
                    country_code: CN
                    currency_code: CNY
                    currency_name_en: Yuan Renminbi
                    currency_name_ar: رنمينبي
                  - id: 819911400
                    country_name_en: United Kingdom of Great Britain and Northern Ireland
                    country_name_ar: بريطانيا
                    country_code: GB
                    currency_code: GBP
                    currency_name_en: Pounds
                    currency_name_ar: جنيه استرليني
                  - id: 885866188
                    country_name_en: India
                    country_name_ar: الهند
                    country_code: IN
                    currency_code: INR
                    currency_name_en: Rupees
                    currency_name_ar: روبية هندية
                  - id: 292767189
                    country_name_en: Japan
                    country_name_ar: اليابان
                    country_code: JP
                    currency_code: JPY
                    currency_name_en: Yen
                    currency_name_ar: ين ياباني
                  - id: 406521109
                    country_name_en: Pakistan
                    country_name_ar: باكستان
                    country_code: PK
                    currency_code: PKR
                    currency_name_en: Rupees
                    currency_name_ar: روبية باكستانية
                  - id: 928298564
                    country_name_en: Turkey
                    country_name_ar: تركيا
                    country_code: TR
                    currency_code: TRY
                    currency_name_en: Lira
                    currency_name_ar: ليرة تركية
                  - id: 880152961
                    country_name_en: Canada
                    country_name_ar: كندا
                    country_code: CA
                    currency_code: CAD
                    currency_name_en: Dollars
                    currency_name_ar: دولار كندي
                  - id: 924690745
                    country_name_en: Malaysia
                    country_name_ar: ماليزيا
                    country_code: MY
                    currency_code: MYR
                    currency_name_en: Ringgits
                    currency_name_ar: رينغيت ماليزي
                  - id: 1980874802
                    country_name_en: Mauritania
                    country_name_ar: موريتانيا
                    country_code: MR
                    currency_code: MRO
                    currency_name_en: Mauritanian ouguiya
                    currency_name_ar: أوقية موريتانية
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
      x-salla-php-method-name: listAvailable
      x-salla-php-return-type: AvailableCurrencies
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Currencies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394258-run
components:
  schemas:
    availableCurrencies_response_body:
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
            id: 2h74zygb0aiay
          items:
            $ref: '#/components/schemas/AvailableCurrencies%20'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    'AvailableCurrencies ':
      title: AvailableCurrencies
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique code that identifies a specific currency. List of available
            currencies can be found [here](https://docs.salla.dev/api-5394258).
          examples:
            - 1745409636
        country_name_en:
          type: string
          description: Country name in English
          examples:
            - Saudi Arabia
        country_name_ar:
          type: string
          description: Country name in Arabic
          examples:
            - السعودية
        country_code:
          type: string
          description: >-
            A short alphanumeric identification code for countries and dependent
            areas.
          examples:
            - SA
        currency_code:
          type: string
          description: >-
            International Organization for Standardization (ISO) is a unique
            three-letter alphabetic code that identifies a specific currency
          examples:
            - SAR
        currency_name_en:
          type: string
          description: Currency name in English
          examples:
            - Riyals
          nullable: true
        currency_name_ar:
          type: string
          description: Currency name in Arabic
          examples:
            - ريال سعودي
      x-apidog-orders:
        - id
        - country_name_en
        - country_name_ar
        - country_code
        - currency_code
        - currency_name_en
        - currency_name_ar
      required:
        - id
        - country_name_en
        - country_name_ar
        - country_code
        - currency_code
        - currency_name_en
        - currency_name_ar
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

## apis-currencies/List-Currencies-Salla-Merchant-API-Salla-Docs

# List Currencies

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /currencies:
    get:
      summary: List Currencies
      deprecated: false
      description: >-
        This endpoint allows you to fetch a list of all currencies alongside
        their details, such as `name`, `code`, `symbol` and `status`.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: get-currencies
      tags:
        - Default module/Merchant API/APIs/Currencies
        - Currencies
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/currencies_response_body'
              example:
                status: 200
                success: true
                data:
                  - name: ريال سعودي
                    code: SAR
                    symbol: ر.س
                    status: disabled
                  - name: درهم اماراتي
                    code: AED
                    symbol: ' د.إ'
                    status: enabled
                  - name: جنيه مصري
                    code: EGP
                    symbol: ج.م
                    status: enabled
                  - name: دولار أمريكي
                    code: USD
                    symbol: $
                    status: enabled
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
      x-salla-php-method-name: list
      x-salla-php-return-type: Currencies
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Currencies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394257-run
components:
  schemas:
    currencies_response_body:
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
            id: tiveeiv2mfvp2
          items:
            $ref: '#/components/schemas/Currencies'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Currencies:
      type: object
      properties:
        name:
          type: string
          description: Name of the currency
          examples:
            - ريال سعودي
        code:
          type: string
          description: Code of the currency
          examples:
            - SAR
        symbol:
          type: string
          description: Symbol of the currency
          examples:
            - ر.س
        status:
          type: string
          description: Status of the currency. The value is either `Enabled` or `Disabled`
          enum:
            - enabled
            - disabled
          examples:
            - disabled
          x-apidog-enum:
            - value: enabled
              name: ''
              description: Currency is enabled.
            - value: disabled
              name: ''
              description: Currency is diabled.
      x-apidog-orders:
        - name
        - code
        - symbol
        - status
      required:
        - name
        - code
        - symbol
        - status
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

## apis-languages/Add-Langugae-Salla-Merchant-API-Salla-Docs

# Add Language

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /languages:
    post:
      summary: Add Language
      deprecated: false
      description: |-
        This endpoint allows you to add one or more languages to the store. 

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `metadata.read_write`- Metadata Read & Write
        </Accordion>
      operationId: post-languages
      tags:
        - Default module/Merchant API/APIs/Languages
        - Languages
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                locales:
                  type: array
                  items:
                    type: object
                    properties:
                      iso_code:
                        type: string
                        description: ISO Code of the Language
                        examples:
                          - fr
                      sort_order:
                        type: string
                        examples:
                          - '1'
                        description: The order of which a language will appear
                        nullable: true
                    x-apidog-orders:
                      - iso_code
                      - sort_order
                    x-apidog-ignore-properties: []
              x-apidog-orders:
                - locales
              x-apidog-ignore-properties: []
            example:
              locales:
                - iso_code: fr
                  sort_order: '1'
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Languages_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 12
                    name: suomen kieli
                    status: enabled
                    rtl: false
                    flag: https://assets.salla.sa/images/flags/fi.svg
                    iso_code: fi
                    country_code: fi
                    sort_order: 9
                  - id: 15
                    name: Ελληνικά
                    status: enabled
                    rtl: false
                    flag: https://assets.salla.sa/images/flags/el.svg
                    iso_code: el
                    country_code: gr
                    sort_order: 10
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
              examples:
                '3':
                  summary: Example
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        locales.0.iso_code:
                          - حقل locales.0.iso_code مطلوب.
                '4':
                  summary: Example 2
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        locales.0.iso_code:
                          - >-
                            يجب أن لا يتجاوز طول النّص locales.0.iso_code 3
                            حروفٍ/حرفًا
                          - حقل locales.0.iso_code غير صالحٍ
                '5':
                  summary: Example 3
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        locales.0.iso_code:
                          - لغة أضيفت بالفعل
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Languages
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394254-run
components:
  schemas:
    Languages_response_body:
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
            id: tqyb9o84m19gw
          items:
            $ref: '#/components/schemas/Languages'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Languages:
      type: object
      properties:
        id:
          type: number
          description: A unique identifier assigned to a specific Language.
          examples:
            - 1
        name:
          type: string
          description: Language label or name.
          examples:
            - العربية
        status:
          type: string
          description: Language status. Either `enabled` or `disabled`
          enum:
            - enabled
            - disabled
          examples:
            - enabled
          x-apidog-enum:
            - value: enabled
              name: ''
              description: Language is enabled
            - value: disabled
              name: ''
              description: Language is disabled
        rtl:
          type: boolean
          default: true
          description: Right-To-Left Supportability
        flag:
          type: string
          description: Icon/Flag of the Language
          examples:
            - https://i.ibb.co/jyqRQfQ/avatar-male.webp
        iso_code:
          type: string
          description: ISO Code of the Language
          examples:
            - ar
        country_code:
          type: string
          description: Country code of the language
          examples:
            - sa
        sort_order:
          type: string
          description: Display order of the language
          examples:
            - '2'
      x-apidog-orders:
        - id
        - name
        - status
        - rtl
        - flag
        - iso_code
        - country_code
        - sort_order
      required:
        - id
        - name
        - status
        - rtl
        - flag
        - iso_code
        - country_code
        - sort_order
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

## apis-languages/List-Languages-Salla-Merchant-API-Salla-Docs

# List Languages

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /languages:
    get:
      summary: List Languages
      deprecated: false
      description: >-
        This endpoint allows you to fetch a list of languages associated with
        your Salla Store.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: get-languages
      tags:
        - Default module/Merchant API/APIs/Languages
        - Languages
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Languages_response_body'
              example: |2-

                    "status": 200,
                    "success": true,
                    "data": [
                        {
                            "id": 1,
                            "name": "العربية",
                            "status": "enabled",
                            "rtl": true,
                            "flag": "https://assets.salla.sa/images/flags/ar.svg",
                            "iso_code": "ar",
                            "country_code": "sa",
                            "sort_order": 0
                        },
                        {
                            "id": 2,
                            "name": "English",
                            "status": "disabled",
                            "rtl": false,
                            "flag": "https://assets.salla.sa/images/flags/en.svg",
                            "iso_code": "en",
                            "country_code": "gb",
                            "sort_order": 0
                        },
                        {
                            "id": 12,
                            "name": "suomen kieli",
                            "status": "enabled",
                            "rtl": false,
                            "flag": "https://assets.salla.sa/images/flags/fi.svg",
                            "iso_code": "fi",
                            "country_code": "fi",
                            "sort_order": 9
                        },
                        {
                            "id": 15,
                            "name": "Ελληνικά",
                            "status": "enabled",
                            "rtl": false,
                            "flag": "https://assets.salla.sa/images/flags/el.svg",
                            "iso_code": "el",
                            "country_code": "gr",
                            "sort_order": 10
                        },
                        {
                            "id": 13,
                            "name": "français",
                            "status": "enabled",
                            "rtl": false,
                            "flag": "https://assets.salla.sa/images/flags/fr.svg",
                            "iso_code": "fr",
                            "country_code": "fr",
                            "sort_order": 31
                        }
                    ],
                    "pagination": {
                        "count": 5,
                        "total": 5,
                        "perPage": 15,
                        "currentPage": 1,
                        "totalPages": 1,
                        "links": {}
                    }
                }
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
      x-salla-php-method-name: list
      x-salla-php-return-type: ActivateDeactivateLanguages
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Languages
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5738815-run
components:
  schemas:
    Languages_response_body:
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
            id: tqyb9o84m19gw
          items:
            $ref: '#/components/schemas/Languages'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Languages:
      type: object
      properties:
        id:
          type: number
          description: A unique identifier assigned to a specific Language.
          examples:
            - 1
        name:
          type: string
          description: Language label or name.
          examples:
            - العربية
        status:
          type: string
          description: Language status. Either `enabled` or `disabled`
          enum:
            - enabled
            - disabled
          examples:
            - enabled
          x-apidog-enum:
            - value: enabled
              name: ''
              description: Language is enabled
            - value: disabled
              name: ''
              description: Language is disabled
        rtl:
          type: boolean
          default: true
          description: Right-To-Left Supportability
        flag:
          type: string
          description: Icon/Flag of the Language
          examples:
            - https://i.ibb.co/jyqRQfQ/avatar-male.webp
        iso_code:
          type: string
          description: ISO Code of the Language
          examples:
            - ar
        country_code:
          type: string
          description: Country code of the language
          examples:
            - sa
        sort_order:
          type: string
          description: Display order of the language
          examples:
            - '2'
      x-apidog-orders:
        - id
        - name
        - status
        - rtl
        - flag
        - iso_code
        - country_code
        - sort_order
      required:
        - id
        - name
        - status
        - rtl
        - flag
        - iso_code
        - country_code
        - sort_order
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

