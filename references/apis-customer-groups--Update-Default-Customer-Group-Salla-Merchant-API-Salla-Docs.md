# Apis Customer Groups  Update Default Customer Group Salla Merchant Api Salla Docs

## Table of Contents

- [apis-customer-groups/Update-Default-Customer-Group-Salla-Merchant-API-Salla-Docs](#apis-customer-groups-update-default-customer-group-salla-merchant-api-salla-docs)

---

## apis-customer-groups/Update-Default-Customer-Group-Salla-Merchant-API-Salla-Docs

# Update Default Customer Group

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/groups/default:
    post:
      summary: Update Default Customer Group
      deprecated: false
      description: >-
        This endpoint allows you to update the default customer group from this
        Endpoint. Each new customer is added automatically to the default
        customer group. 


        :::tip[Note]

        You can only change the group features:

        - Payment Methods 

        - Shipping Methods

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Update-Default-Group
      tags:
        - Default module/Merchant API/APIs/Customer Groups
        - Customer Groups
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/updateDefaultGroup_request_body'
            example:
              features:
                payment_method:
                  - credit_card
                  - mada
                  - bank
                  - cod
                  - apple_pay
                  - stc_pay
                shipping:
                  - all
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 201
                success: true
                data:
                  message: The default group has been updated successfully
                  code: 201
          headers: {}
          x-apidog-name: Progress In-Action
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
                    customers.read_write
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
                  code: validation_failed
                  message: Validation failed
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateDefault
      x-apidog-folder: Default module/Merchant API/APIs/Customer Groups
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394131-run
components:
  schemas:
    updateDefaultGroup_request_body:
      type: object
      deprecated: true
      properties:
        features:
          type: object
          properties:
            payment_method:
              type: array
              items:
                type: string
              description: >-
                The various methods of payment that are accessible or offered to
                a specific group of customers.  List of available payment
                methods can be found [here](https://docs.salla.dev/api-5394164).
            shipping:
              type: array
              items:
                type: string
              description: >-
                The various delivery options or methods that are accessible or
                offered to a specific group of customers.
          x-apidog-orders:
            - payment_method
            - shipping
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - features
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    progress_ActionSuccess:
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
            message:
              type: string
              description: >-
                A text or data communication generated by a system or
                application in response to a request.
            code:
              type: number
              description: >-
                A numerical or alphanumeric identifier used in various systems
                and protocols to indicate the status or outcome of a specific
                request.
          x-apidog-orders:
            - message
            - code
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

