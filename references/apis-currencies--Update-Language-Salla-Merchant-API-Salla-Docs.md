# Apis Currencies  Update Language Salla Merchant Api Salla Docs

## Table of Contents

- [apis-languages/Update-Language-Salla-Merchant-API-Salla-Docs](#apis-languages-update-language-salla-merchant-api-salla-docs)

---

## apis-languages/Update-Language-Salla-Merchant-API-Salla-Docs

# Update Language

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /languages/{locale}:
    put:
      summary: Update Language
      deprecated: false
      description: >-
        This endpoint allows you to update a specific language by passing the
        `locale` as the path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `metadata.read_write`- Metadata Read & Write

        </Accordion>
      tags:
        - Default module/Merchant API/APIs/Languages
        - Languages
      parameters:
        - name: locale
          in: path
          description: >-
            Unique identification number assigned to the Language to be updated.
            List of languages IDs can be found
            [here](https://docs.salla.dev/api-5738815)
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                status:
                  type: boolean
                  description: >-
                    Whether to disable or enable a specific language.
                    `RequiredIf` the variable `sort_order` is not sent 
                sort_order:
                  type: integer
                  description: >-
                    The order of which a language will appear. `RequiredIf` the
                    variable `status` is not sent in this request
              x-apidog-orders:
                - status
                - sort_order
              x-apidog-ignore-properties: []
            example:
              status: true
              sort_order: 1
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
                  - id: 13
                    name: français
                    status: enabled
                    rtl: false
                    flag: https://assets.salla.sa/images/flags/fr.svg
                    iso_code: fr
                    country_code: fr
                    sort_order: 1
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
                  message: لم يتم العثور على اللغة
          headers: {}
          x-apidog-name: Not Found
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
                    sort_order:
                      - يجب على حقل sort order أن يكون رقماً
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Languages
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5738833-run
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

