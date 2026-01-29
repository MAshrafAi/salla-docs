# Apis Shipping Companies  Create Shipping Company Salla Merchant Api Salla Docs

## Table of Contents

- [apis-shipping-companies/Create-Shipping-Company-Salla-Merchant-API-Salla-Docs](#apis-shipping-companies-create-shipping-company-salla-merchant-api-salla-docs)
- [apis-shipping-companies/Delete-Shipping-Company-Salla-Merchant-API-Salla-Docs](#apis-shipping-companies-delete-shipping-company-salla-merchant-api-salla-docs)
- [apis-shipping-companies/List-Estimate-Rates-Salla-Merchant-API-Salla-Docs](#apis-shipping-companies-list-estimate-rates-salla-merchant-api-salla-docs)
- [apis-shipping-companies/List-Shipping-Companies-Salla-Merchant-API-Salla-Docs](#apis-shipping-companies-list-shipping-companies-salla-merchant-api-salla-docs)
- [apis-shipping-companies/Shipping-Company-Details-Salla-Merchant-API-Salla-Docs](#apis-shipping-companies-shipping-company-details-salla-merchant-api-salla-docs)
- [apis-shipping-companies/Shipping-Company-Options-Salla-Merchant-API-Salla-Docs](#apis-shipping-companies-shipping-company-options-salla-merchant-api-salla-docs)

---

## apis-shipping-companies/Create-Shipping-Company-Salla-Merchant-API-Salla-Docs

# Create Shipping Company

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/companies/:
    post:
      summary: Create Shipping Company
      deprecated: false
      description: |2-
         This endpoint allows you to create a **custom** shipping company.

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `shipping.read_write`- Shipping Read & Write
        </Accordion>
      operationId: post-shipping-companies
      tags:
        - Default module/Merchant API/APIs/Shipping Companies
        - Shipping Companies
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                name:
                  type: string
                  description: Shipping Company Name
                  examples:
                    - Shipping Company
              required:
                - name
              x-apidog-orders:
                - name
              x-apidog-ignore-properties: []
            example:
              name: Shipping Company
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/shippingCompany_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 346226214
                  name: شركة
                  app_id: 765436
                  activation_type: api
                  slug: ''
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
                    shipping.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: ShippingCompany
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Companies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394238-run
components:
  schemas:
    shippingCompany_response_body:
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
          $ref: '#/components/schemas/ShippingCompany'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ShippingCompany:
      type: object
      title: ShippingCompany
      description: >-
        Detailed structure of the Shipping company model object showing its
        fields and data types.
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific shipping company or
            carrier. Shipping companies list can be found
            [here](https://docs.salla.dev/api-5394239)
          examples:
            - 441225901
        name:
          type: string
          description: >-
            The formal name or title of a carrier responsible for the
            transportation and delivery of goods.
          examples:
            - DHL
        app_id:
          type: string
          description: >-
            A unique identifier associated with a shipping or logistics
            application.
          examples:
            - '112233445'
        activation_type:
          type: string
          description: >-
            the method or process by which a shipping company or carrier
            activates its services, such as whether it's manual or API.
          enum:
            - manual
            - api
          x-apidog-enum:
            - value: manual
              name: ''
              description: Manual activation type
            - value: api
              name: ''
              description: Via API activation type
        slug:
          type: string
          description: >-
            A short form identifier for a shipping company's name. If the
            `activation_type` is set to `manual`, a `null` is returned;
            otherwise, you will receive a value.
          examples:
            - dhl
          nullable: true
      x-apidog-orders:
        - id
        - name
        - app_id
        - activation_type
        - slug
      required:
        - id
        - name
        - app_id
        - activation_type
        - slug
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

## apis-shipping-companies/Delete-Shipping-Company-Salla-Merchant-API-Salla-Docs

# Delete Shipping Company

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/companies/{company_id}:
    delete:
      summary: Delete Shipping Company
      deprecated: false
      description: >-
        This endpoint allows you to delete a **custom** shipping company
        associated with the store, by passing the `company_id` as a path
        parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read_write`- Shipping Read & Write

        </Accordion>
      operationId: delete-shipping-companies
      tags:
        - Default module/Merchant API/APIs/Shipping Companies
        - Shipping Companies
      parameters:
        - name: company_id
          in: path
          description: >-
            Unique identification number assigned to a Shipping Company. Get a
            list of Shpping companies IDs
            [here](https://docs.salla.dev/5578815e0)
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
                status: 200
                success: true
                data:
                  message: تم حذف الشركة بنجاح
                  code: 200
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
                    shipping.read_write
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/NotFoundResponse'
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
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Companies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394242-run
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
    NotFoundResponse:
      type: object
      title: NotFoundResponse
      properties:
        status:
          type: number
          description: Response status Code
        success:
          type: boolean
          description: Response flag
        error:
          type: object
          properties:
            code:
              type: integer
              description: Response code
            message:
              type: string
              description: Response message
          x-apidog-orders:
            - code
            - message
          x-apidog-ignore-properties: []
      x-examples:
        Example:
          success: false
          status: 404
          error:
            code: 404
            message: The content you are trying to access is no longer available
      x-tags:
        - Responses
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

## apis-shipping-companies/List-Estimate-Rates-Salla-Merchant-API-Salla-Docs

# List Estimate Rates

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/companies/estimate-rate:
    get:
      summary: List Estimate Rates
      deprecated: false
      description: >-
        This endpoint allows you to fetch all of the shipping companies'
        estimate rates, based on the customer's order address 
      operationId: get-shipping-companies-estimate-rate
      tags:
        - Default module/Merchant API/APIs/Shipping Companies
        - Shipping Companies
      parameters:
        - name: city_id
          in: query
          description: >-
            Unique identification number assigned to the City. Get a list of
            City IDs from [here](https://docs.salla.dev/api-5394230)
          required: true
          schema:
            type: integer
        - name: country_id
          in: query
          description: >-
            Unique identification number assigned to the Country. Get a list of
            Country IDs from [here](https://docs.salla.dev/api-5394228)
          required: true
          schema:
            type: integer
        - name: order_id
          in: query
          description: >-
            Unique identification number assigned to the Order . Get a list of
            Order IDs from [here](https://docs.salla.dev/api-5394146)
          required: false
          schema:
            type: integer
        - name: geocode
          in: query
          description: Geographic Location Code
          required: false
          schema:
            type: string
        - name: postal_code
          in: query
          description: Address Postal Code value
          required: false
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/estimateRates_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 534427805
                    company_id: 1892382264
                    title: ريدبوكس
                    logo: >-
                      https://cdn.salla.sa/qGNRv/EHSZest9WHlDTmTJjJnEWqgUu75NLQ5gNJin0FhA.png
                    working_days: >-
                      [استلم طلبك من خزائن ريد بوكس الذكية RedBox، بالوقت
                      المناسب لك، الإيداع سيكون من 1-3 أيام]
                    total:
                      amount: 14
                      currency: SAR
                    services:
                      - name: cod
                        amount:
                          amount: 0
                          currency: SAR
                  - id: 1680687267
                    company_id: 941683204
                    title: ارامكس - هيمو
                    logo: >-
                      https://cdn.salla.sa/qGNRv/EHSZest9WHlDTmTJjJnEWqgUu75NLQ5gNJin0FhA.png
                    working_days: من 1 - 2  يوم عمل
                    total:
                      amount: 24
                      currency: SAR
                    services:
                      - name: cod
                        amount:
                          amount: 8
                          currency: SAR
                  - id: 1055252317
                    company_id: 1926022186
                    title: dhl - هيمو
                    logo: >-
                      https://cdn.salla.sa/qGNRv/EHSZest9WHlDTmTJjJnEWqgUu75NLQ5gNJin0FhA.png
                    working_days: 7 -20 يوم عمل
                    total:
                      amount: 28
                      currency: SAR
                    services:
                      - name: cod
                        amount:
                          amount: 0
                          currency: SAR
                  - id: 1130138841
                    company_id: 478065722
                    title: سمسا
                    logo: >-
                      https://cdn.salla.sa/qGNRv/xPQymWwCmTITkScYSnApzJO7eQLm5PrsRCltN6uo.png
                    working_days: ١ - ٣ أيام عمل
                    total:
                      amount: 28
                      currency: SAR
                    services:
                      - name: cod
                        amount:
                          amount: 0
                          currency: SAR
                  - id: 1172876926
                    company_id: 98754
                    title: HeMo Hassan
                    logo: >-
                      https://cdn.salla.sa/qGNRv/EHSZest9WHlDTmTJjJnEWqgUu75NLQ5gNJin0FhA.png
                    working_days: خلال يومين من إتمام عملية الدفع
                    total:
                      amount: 50
                      currency: SAR
                    services:
                      - name: cod
                        amount:
                          amount: 0
                          currency: SAR
          headers: {}
          x-apidog-name: Success
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
                    city_id:
                      - حقل city id مطلوب.
                    country_id:
                      - حقل country id مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Companies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-6899590-run
components:
  schemas:
    estimateRates_response_body:
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
            $ref: '#/components/schemas/EstimateRates'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    EstimateRates:
      type: object
      properties:
        id:
          type: integer
          description: Estimated Rate ID
        company_id:
          type: integer
          description: >-
            Shipping company unique identifier. List of sipping companies can be
            found [here](https://docs.salla.dev/api-5394239)
          nullable: true
        title:
          type: string
          description: Shipping company title
        logo:
          type: string
          description: Shipping company logo
        working_days:
          type: string
          description: Shipping company working hours
        total:
          type: object
          properties:
            amount:
              type: integer
              description: Estimated Total Amount value
            currency:
              type: string
              description: Estimated Total Currency value
          x-apidog-orders:
            - amount
            - currency
          x-apidog-ignore-properties: []
        services:
          type: array
          items:
            type: object
            properties:
              name:
                type: string
                description: Service Name
              amount:
                type: object
                properties:
                  amount:
                    type: integer
                    description: Service Amount value
                  currency:
                    type: string
                    description: Service Currency value
                required:
                  - amount
                  - currency
                x-apidog-orders:
                  - amount
                  - currency
                x-apidog-ignore-properties: []
            x-apidog-orders:
              - name
              - amount
            required:
              - name
              - amount
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - company_id
        - title
        - logo
        - working_days
        - total
        - services
      required:
        - id
        - company_id
        - title
        - logo
        - working_days
        - total
        - services
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

## apis-shipping-companies/List-Shipping-Companies-Salla-Merchant-API-Salla-Docs

# List Shipping Companies

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/companies/:
    get:
      summary: List Shipping Companies
      deprecated: false
      description: >
        This endpoint allows you to list all active shipping companies
        associated with the store. 
         
        :::note

        If the `"activation_type"` is set to:

          - ***manual*** : which means that the shipping company is from the merchant side *(not available to be linked from salla dashboard)*

          - ***api*** : which means it has been linked through salla.
          :::
        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read`- Shipping Read Only

        </Accordion>
      operationId: list-shipping-companies
      tags:
        - Default module/Merchant API/APIs/Shipping Companies
        - Shipping Companies
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/shippingCompanies_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1723506348
                    name: سمسا
                    app_id: '1683195908'
                    activation_type: manual
                    slug: smsa
                  - id: 989286562
                    name: ارامكس
                    app_id: '1311345502'
                    activation_type: manual
                    slug: armx
                  - id: 2079537577
                    name: البريد السعودي | سُبل
                    app_id: '88903443'
                    activation_type: manual
                    slug: sbl
                  - id: 814202285
                    name: DHL Express
                    app_id: '827885927'
                    activation_type: api
                    slug: dhl-express
                  - id: 1130931637
                    name: Ajeek
                    app_id: '1499493023'
                    activation_type: api
                    slug: ajeek
                  - id: 665151403
                    name: أي مكان
                    app_id: '944213936'
                    activation_type: manual
                    slug: Imkan
                  - id: 915304371
                    name: UPS
                    app_id: '1218344689'
                    activation_type: api
                    slug: ups
                  - id: 1764372897
                    name: فتشر
                    app_id: '2099547131'
                    activation_type: api
                    slug: fetcher
                  - id: 1378987453
                    name: mlcGO
                    app_id: '1720219575'
                    activation_type: manual
                    slug: mlcgo
                  - id: 349994915
                    name: سلاسة
                    app_id: '456034465'
                    activation_type: manual
                    slug: slsh
                  - id: 1096243131
                    name: Storage Station
                    app_id: '1353087977'
                    activation_type: api
                    slug: storage-station
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
                    shipping.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: ShippingCompany
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Companies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394239-run
components:
  schemas:
    shippingCompanies_response_body:
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
            id: njmrw42s89jgj
          items:
            $ref: '#/components/schemas/ShippingCompany'
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
    ShippingCompany:
      type: object
      title: ShippingCompany
      description: >-
        Detailed structure of the Shipping company model object showing its
        fields and data types.
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific shipping company or
            carrier. Shipping companies list can be found
            [here](https://docs.salla.dev/api-5394239)
          examples:
            - 441225901
        name:
          type: string
          description: >-
            The formal name or title of a carrier responsible for the
            transportation and delivery of goods.
          examples:
            - DHL
        app_id:
          type: string
          description: >-
            A unique identifier associated with a shipping or logistics
            application.
          examples:
            - '112233445'
        activation_type:
          type: string
          description: >-
            the method or process by which a shipping company or carrier
            activates its services, such as whether it's manual or API.
          enum:
            - manual
            - api
          x-apidog-enum:
            - value: manual
              name: ''
              description: Manual activation type
            - value: api
              name: ''
              description: Via API activation type
        slug:
          type: string
          description: >-
            A short form identifier for a shipping company's name. If the
            `activation_type` is set to `manual`, a `null` is returned;
            otherwise, you will receive a value.
          examples:
            - dhl
          nullable: true
      x-apidog-orders:
        - id
        - name
        - app_id
        - activation_type
        - slug
      required:
        - id
        - name
        - app_id
        - activation_type
        - slug
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

## apis-shipping-companies/Shipping-Company-Details-Salla-Merchant-API-Salla-Docs

# Shipping Company Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/companies/{company_id}:
    get:
      summary: Shipping Company Details
      deprecated: false
      description: >
        This endpoint allows you to fetch details of a speicifc shipping company
        associated with the store by passing the `company_id` as a path
        parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read`- Shipping Read Only

        </Accordion>
      operationId: get-shipping-companies-company_id
      tags:
        - Default module/Merchant API/APIs/Shipping Companies
        - Shipping Companies
      parameters:
        - name: company_id
          in: path
          description: >-
            Unique identification number assigned to a Shipping Company. Get a
            list of Shpping companies IDs
            [here](https://docs.salla.dev/5578815e0)
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
                $ref: '#/components/schemas/shippingCompany_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 976721503
                  name: Shipping Company
                  app_id: '505994491'
                  activation_type: api
                  slug: shipping-company
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
                    shipping.read
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
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: ShippingCompany
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Companies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394240-run
components:
  schemas:
    shippingCompany_response_body:
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
          $ref: '#/components/schemas/ShippingCompany'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ShippingCompany:
      type: object
      title: ShippingCompany
      description: >-
        Detailed structure of the Shipping company model object showing its
        fields and data types.
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific shipping company or
            carrier. Shipping companies list can be found
            [here](https://docs.salla.dev/api-5394239)
          examples:
            - 441225901
        name:
          type: string
          description: >-
            The formal name or title of a carrier responsible for the
            transportation and delivery of goods.
          examples:
            - DHL
        app_id:
          type: string
          description: >-
            A unique identifier associated with a shipping or logistics
            application.
          examples:
            - '112233445'
        activation_type:
          type: string
          description: >-
            the method or process by which a shipping company or carrier
            activates its services, such as whether it's manual or API.
          enum:
            - manual
            - api
          x-apidog-enum:
            - value: manual
              name: ''
              description: Manual activation type
            - value: api
              name: ''
              description: Via API activation type
        slug:
          type: string
          description: >-
            A short form identifier for a shipping company's name. If the
            `activation_type` is set to `manual`, a `null` is returned;
            otherwise, you will receive a value.
          examples:
            - dhl
          nullable: true
      x-apidog-orders:
        - id
        - name
        - app_id
        - activation_type
        - slug
      required:
        - id
        - name
        - app_id
        - activation_type
        - slug
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

## apis-shipping-companies/Shipping-Company-Options-Salla-Merchant-API-Salla-Docs

# Shipping Company Options

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipping/companies/{company_id}/options:
    get:
      summary: Shipping Company Options
      deprecated: false
      description: >-
        This endpoint is used to show the shipping company's options when
        issuing an AWB for an order
      tags:
        - Default module/Merchant API/APIs/Shipping Companies
        - Shipping Companies
      parameters:
        - name: company_id
          in: path
          description: >-
            Unique identification number assigned to a Shipping Company. Get a
            list of Shpping companies IDs
            [here](https://docs.salla.dev/5578815e0)
          required: true
          example: 1723506348
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/shippingCompanyOptions_response_body'
              example:
                status: 200
                success: true
                data:
                  - name: boxes
                    label: عدد الكراتين
                    type: items
                    format: dropdown-list
                    required: true
                    description: ''
                    options:
                      - value: 1
                        label: 1
                      - value: 2
                        label: 2
                      - value: 3
                        label: 3
                      - value: 4
                        label: 4
                      - value: 5
                        label: 5
                      - value: 6
                        label: 6
                      - value: 7
                        label: 7
                      - value: 8
                        label: 8
                      - value: 9
                        label: 9
                      - value: 10
                        label: 10
                  - name: without_products
                    label: عدم ارسال تفاصيل المنتجات في البوليصة
                    type: boolean
                    format: checkbox
                    required: false
                    description: ''
          headers: {}
          x-apidog-name: Success
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
                  code: 404
                  message: المحتوى الذي تحاول الوصول اليه غير متوفر
          headers: {}
          x-apidog-name: error_notFound_404
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Shipping Companies
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-8817101-run
components:
  schemas:
    shippingCompanyOptions_response_body:
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
            $ref: '#/components/schemas/shippingCompanyOptions'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    shippingCompanyOptions:
      type: object
      properties:
        name:
          type: string
          description: The label used to describe a specific option
        label:
          type: string
          description: >-
            The title used to describe a specific option associated with a
            company.
        type:
          type: string
          description: >-
            Type of the company option, it can be items or a boolean  

            Allowed values: `items`, `boolean`,`number`, `string`,`collection`,
            `static`
        format:
          type: string
          description: >-
            The format of the company option can be a dropdown-list or checkbox.


            Allowed values: `dropdown-list`,`radio-list`, `checkbox`, `switch`,
            `text`, `number`, `slider`
        required:
          type: boolean
          description: This is to indicate if the company option is obligatory.
        description:
          type: string
          description: >-
            A detailed information about an option or attribute associated with
            a company.
        options:
          type: array
          items:
            type: object
            properties:
              value:
                type: string
                description: The value associated with a specific option.
              label:
                type: string
                description: The description associated with a specific option.
            x-apidog-orders:
              - value
              - label
            x-apidog-ignore-properties: []
      x-apidog-orders:
        - name
        - label
        - type
        - format
        - required
        - description
        - options
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

