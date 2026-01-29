# Apis Countries

## Table of Contents

- [apis-cities/List-Cities-Salla-Merchant-API-Salla-Docs](#apis-cities-list-cities-salla-merchant-api-salla-docs)
- [apis-countries/Country-Details-Salla-Merchant-API-Salla-Docs](#apis-countries-country-details-salla-merchant-api-salla-docs)
- [apis-countries/List-Countries-Salla-Merchant-API-Salla-Docs](#apis-countries-list-countries-salla-merchant-api-salla-docs)
- [apis-districts/List-Districts-Salla-Merchant-API-Salla-Docs](#apis-districts-list-districts-salla-merchant-api-salla-docs)

---

## apis-cities/List-Cities-Salla-Merchant-API-Salla-Docs

# List Cities

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /countries/{country}/cities:
    get:
      summary: List Cities
      deprecated: false
      description: >-
        This endpoint allows you to list all available cities for a specific
        country by passing the `country` as a path parameter. 



        :::note

        [Country details](https://docs.salla.dev/api-5394229) will also be
        returned in the payload.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: List-Cities
      tags:
        - Default module/Merchant API/APIs/Cities
        - Cities
      parameters:
        - name: country
          in: path
          description: >-
            Unique identification number assigned to the Country. Get a list of
            country IDs [here](https://docs.salla.dev/5394228e0).
          required: true
          example: 0
          schema:
            type: integer
        - name: page
          in: query
          description: The Pagination page number
          required: false
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/cities_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: Riyadh
                    name_en: Riyadh
                    country_id: 1473353380
                  - id: 566146469
                    name: Jeddah
                    name_en: Jeddah
                    country_id: 1473353380
                  - id: 1939592358
                    name: Mecca
                    name_en: Mecca
                    country_id: 1473353380
                  - id: 1298199463
                    name: Medina
                    name_en: Medina
                    country_id: 1473353380
                  - id: 525144736
                    name: Dammam
                    name_en: Dammam
                    country_id: 1473353380
                  - id: 1764372897
                    name: Al Ahsa
                    name_en: Al Ahsa
                    country_id: 1473353380
                  - id: 989286562
                    name: Al Qatif
                    name_en: Al Qatif
                    country_id: 1473353380
                  - id: 349994915
                    name: Khamis Mushait
                    name_en: Khamis Mushait
                    country_id: 1473353380
                  - id: 1723506348
                    name: Almuzaylif
                    name_en: Almuzaylif
                    country_id: 1473353380
                  - id: 814202285
                    name: Tabuk
                    name_en: Tabuk
                    country_id: 1473353380
                  - id: 40688814
                    name: Al Hofuf
                    name_en: Al Hofuf
                    country_id: 1473353380
                  - id: 1548352431
                    name: Al Mubarraz
                    name_en: Al Mubarraz
                    country_id: 1473353380
                  - id: 773200552
                    name: Najran
                    name_en: Najran
                    country_id: 1473353380
                  - id: 2079537577
                    name: Hafar Al Batin
                    name_en: Hafar Al Batin
                    country_id: 1473353380
                  - id: 1440241834
                    name: Al Jubail
                    name_en: Al Jubail
                    country_id: 1473353380
                country:
                  id: 1473353380
                  name: Saudi Arabia
                  code: SA
                pagination:
                  count: 15
                  total: 905
                  perPage: 15
                  currentPage: 1
                  totalPages: 61
                  links:
                    next: >-
                      http://api.salla.dev/admin/v2/countries/1473353380/cities?page=2
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
        '404':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties: {}
              example:
                success: false
                status: 404
                error:
                  code: 404
                  message: The content you are trying to access is no longer available
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: City
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Cities
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394230-run
components:
  schemas:
    cities_response_body:
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
            id: 5ci3iu1w4j585
          items:
            $ref: '#/components/schemas/City'
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
    City:
      description: >-
        Detailed structure of the city model object showing its fields and data
        types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: City
      properties:
        id:
          type: number
          description: A unique identifier or code assigned to a specific city.
        name:
          type: string
          description: >-
            The lable used for a specific urban area or municipality within a
            country or region.
        name_en:
          type: string
          description: City name expressed in English characters.
      x-apidog-orders:
        - id
        - name
        - name_en
      required:
        - id
        - name
        - name_en
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

## apis-countries/Country-Details-Salla-Merchant-API-Salla-Docs

# Country Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /countries/{country}:
    get:
      summary: Country Details
      deprecated: false
      description: >-
        This endpoint allows you to return the details for a specific country by
        passing the `country` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read`- Metadata Read Only

        </Accordion>
      operationId: Country-Details
      tags:
        - Default module/Merchant API/APIs/Countries
        - Countries
      parameters:
        - name: country
          in: path
          description: >-
            Unique identification number assigned to the Country. Get a list of
            country IDs [here](https://docs.salla.dev/5394228e0).
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
                $ref: '#/components/schemas/country_response_body'
              example:
                success: true
                status: 200
                data:
                  id: 1473353380
                  name: السعودية
                  name_en: Saudi Arabia
                  code: SA
                  mobile_code: '+966'
                  capital: Riyadh
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
          x-apidog-name: error_unautUnauthorizedhorized_401
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
              example:
                success: false
                status: 404
                error:
                  code: 404
                  message: The content you are trying to access is no longer available
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: Country
      x-apidog-folder: Default module/Merchant API/APIs/Countries
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394229-run
components:
  schemas:
    country_response_body:
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
          $ref: '#/components/schemas/Country'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Country:
      description: >-
        Detailed structure of the country model object showing its fields and
        data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: Country
      properties:
        id:
          description: A unique identifier assigned to a specific country.
          type: number
        name:
          type: string
          description: >-
            The official or commonly used name of a specific nation or
            geographic region.
        name_en:
          type: string
          description: Country name expressed in English characters.
        code:
          type: string
          description: >-
            Country iso code , a standardized, three-letter code assigned to
            each country by the International Organization for Standardization.
        mobile_code:
          type: string
          description: >-
            The international dialing code used to make phone calls to a
            specific country from abroad, also known as the country's "calling
            code."
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

## apis-countries/List-Countries-Salla-Merchant-API-Salla-Docs

# List Countries

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /countries:
    get:
      summary: List Countries
      deprecated: false
      description: |-
        This endpoint allows you to list all available countries. 

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `metadata.read`- Metadata Read Only
        </Accordion>
      operationId: List-Countries
      tags:
        - Default module/Merchant API/APIs/Countries
        - Countries
      parameters:
        - name: page
          in: query
          description: The Pagination page number
          required: false
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/countries_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: السعودية
                    name_en: Saudi Arabia
                    code: SA
                    mobile_code: '+966'
                    capital: Riyadh
                  - id: 566146469
                    name: الامارات
                    name_en: United Arab Emirates
                    code: AE
                    mobile_code: '+971'
                    capital: Abu Dhabi
                  - id: 1939592358
                    name: الكويت
                    name_en: Kuwait
                    code: KW
                    mobile_code: '+965'
                    capital: Kuwait City
                  - id: 1298199463
                    name: قطر
                    name_en: Qatar
                    code: QA
                    mobile_code: '+974'
                    capital: Doha
                  - id: 525144736
                    name: البحرين
                    name_en: Bahrain
                    code: BH
                    mobile_code: '+973'
                    capital: Manama
                  - id: 1764372897
                    name: العراق
                    name_en: Iraq
                    code: IQ
                    mobile_code: '+964'
                    capital: Baghdad
                  - id: 989286562
                    name: عمان
                    name_en: Oman
                    code: OM
                    mobile_code: '+968'
                    capital: Muscat
                  - id: 349994915
                    name: اليمن
                    name_en: Yemen
                    code: YE
                    mobile_code: '+967'
                    capital: Sanaa
                  - id: 1723506348
                    name: مصر
                    name_en: Egypt
                    code: EG
                    mobile_code: '+20'
                    capital: Cairo
                  - id: 814202285
                    name: السودان
                    name_en: Sudan
                    code: SD
                    mobile_code: '+249'
                    capital: Khartoum
                  - id: 40688814
                    name: ليبيا
                    name_en: Libya
                    code: LY
                    mobile_code: '+218'
                    capital: Tripoli
                  - id: 1548352431
                    name: الجزائر
                    name_en: Algeria
                    code: DZ
                    mobile_code: '+213'
                    capital: Algiers
                  - id: 773200552
                    name: تونس
                    name_en: Tunisia
                    code: TN
                    mobile_code: '+216'
                    capital: Tunis
                  - id: 2079537577
                    name: المغرب
                    name_en: Morocco
                    code: MA
                    mobile_code: '+212'
                    capital: Rabat
                  - id: 1440241834
                    name: سوريا
                    name_en: Syria
                    code: SY
                    mobile_code: '+963'
                    capital: Damascus
                pagination:
                  count: 15
                  total: 240
                  perPage: 15
                  currentPage: 1
                  totalPages: 16
                  links:
                    next: https://api.salla.dev/admin/v2/countries?page=2
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
      x-salla-php-return-type: Country
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Countries
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394228-run
components:
  schemas:
    countries_response_body:
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
            id: 9gvz22sl2eadi
          items:
            $ref: '#/components/schemas/Country'
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
    Country:
      description: >-
        Detailed structure of the country model object showing its fields and
        data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: Country
      properties:
        id:
          description: A unique identifier assigned to a specific country.
          type: number
        name:
          type: string
          description: >-
            The official or commonly used name of a specific nation or
            geographic region.
        name_en:
          type: string
          description: Country name expressed in English characters.
        code:
          type: string
          description: >-
            Country iso code , a standardized, three-letter code assigned to
            each country by the International Organization for Standardization.
        mobile_code:
          type: string
          description: >-
            The international dialing code used to make phone calls to a
            specific country from abroad, also known as the country's "calling
            code."
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

## apis-districts/List-Districts-Salla-Merchant-API-Salla-Docs

# List Districts

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /cities/{city}/districts:
    get:
      summary: List Districts
      deprecated: false
      description: >+
        This endpoint allows you to list all available districts for a specific
        city by passing the `city` as a path parameter.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read` - Metadata Read Only

        </Accordion>

      operationId: List-Districts
      tags:
        - Default module/Merchant API/APIs/Districts
        - Districts
      parameters:
        - name: city
          in: path
          description: >-
            Unique identification number assigned to the City. Get a list of
            city IDs [here](https://docs.salla.dev/5394230e0).
          required: true
          schema:
            type: integer
        - name: page
          in: query
          description: The Pagination page number
          required: false
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
                      Response flag, boolean indicator used to signal a
                      particular condition or state in the response of a system
                      or application, often representing the presence or absence
                      of certain conditions or outcomes.
                  data:
                    type: array
                    items:
                      type: object
                      properties:
                        id:
                          type: integer
                          description: The district unique identifier
                        name:
                          type: string
                          description: District Arabic Name
                          examples:
                            - الوادي
                        name_en:
                          type: string
                          description: District English Name
                          examples:
                            - Al Wadi
                      x-apidog-orders:
                        - id
                        - name
                        - name_en
                      x-apidog-ignore-properties: []
                  city:
                    type: object
                    properties:
                      id:
                        type: integer
                        description: Queried City Unique identifier
                      name:
                        type: string
                        description: Queried  City Name in Arabic
                        examples:
                          - جدة
                          - الرياض
                    x-apidog-orders:
                      - id
                      - name
                    x-apidog-ignore-properties: []
                  pagination: &ref_0
                    $ref: '#/components/schemas/Pagination'
                x-apidog-orders:
                  - 01K5RENJBPM745SHW7T2XN1YGW
                x-apidog-refs:
                  01K5RENJBPM745SHW7T2XN1YGW:
                    $ref: '#/components/schemas/DistrictsResponse'
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
                  - city
                  - pagination
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: حي العمل
                    name_en: Al Amal Dist.
                  - id: 566146469
                    name: حي النموذجية
                    name_en: Al Namudhajiyah Dist.
                  - id: 1939592358
                    name: حي الجرادية
                    name_en: Al Jarradiyah Dist.
                  - id: 1298199463
                    name: حي الصناعية
                    name_en: Al Sinaiyah Dist.
                  - id: 525144736
                    name: حي منفوحة الجديدة
                    name_en: Manfuha Al Jadidah Dist.
                  - id: 1764372897
                    name: حي الفاخرية
                    name_en: Al Fakhiriyah Dist.
                  - id: 989286562
                    name: حي الديرة
                    name_en: Al Dirah Dist.
                  - id: 349994915
                    name: حي ام الحمام الشرقي
                    name_en: East Umm Al Hamam Dist.
                  - id: 1723506348
                    name: حي الشرفية
                    name_en: Al Sharafiyah Dist.
                  - id: 814202285
                    name: حي الهدا
                    name_en: Al Hada Dist.
                  - id: 40688814
                    name: حي المعذر الشمالي
                    name_en: North Mathar Dist.
                  - id: 1548352431
                    name: حي ام الحمام الغربي
                    name_en: West Umm Al Hamam Dist.
                  - id: 773200552
                    name: حي الرحمانية
                    name_en: Ar Rahmaniyah Dist.
                  - id: 2079537577
                    name: حي لبن
                    name_en: Laban Dist.
                  - id: 1440241834
                    name: حي الرفيعة
                    name_en: Ar Rafiah Dist.
                city:
                  id: 1473353380
                  name: Riyadh
                pagination:
                  count: 15
                  total: 189
                  perPage: 15
                  currentPage: 1
                  totalPages: 13
                  links:
                    next: >-
                      https://salla-dashboard.test/admin/v2/cities/1473353380/districts?page=2
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
                  code: Invalid-token
                  message: please provide a valid API Key
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: District
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Districts
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-21655021-run
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
    DistrictsResponse:
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
            type: object
            properties:
              id:
                type: integer
                description: The district unique identifier
              name:
                type: string
                description: District Arabic Name
                examples:
                  - الوادي
              name_en:
                type: string
                description: District English Name
                examples:
                  - Al Wadi
            x-apidog-orders:
              - id
              - name
              - name_en
            x-apidog-ignore-properties: []
        city:
          type: object
          properties:
            id:
              type: integer
              description: Queried City Unique identifier
            name:
              type: string
              description: Queried  City Name in Arabic
              examples:
                - جدة
                - الرياض
          x-apidog-orders:
            - id
            - name
          x-apidog-ignore-properties: []
        pagination: *ref_0
      x-apidog-orders:
        - status
        - success
        - data
        - city
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

