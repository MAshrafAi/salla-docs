# Apis Webhooks

## Table of Contents

- [apis-webhooks/Deactivate-Webhook-Salla-Merchant-API-Salla-Docs](#apis-webhooks-deactivate-webhook-salla-merchant-api-salla-docs)
- [apis-webhooks/List-Active-Webhooks-Salla-Merchant-API-Salla-Docs](#apis-webhooks-list-active-webhooks-salla-merchant-api-salla-docs)
- [apis-webhooks/List-Events-Salla-Merchant-API-Salla-Docs](#apis-webhooks-list-events-salla-merchant-api-salla-docs)
- [apis-webhooks/Register-Webhook-Salla-Merchant-API-Salla-Docs](#apis-webhooks-register-webhook-salla-merchant-api-salla-docs)
- [apis-webhooks/Update-Webhook-Salla-Merchant-API-Salla-Docs](#apis-webhooks-update-webhook-salla-merchant-api-salla-docs)

---

## apis-webhooks/Deactivate-Webhook-Salla-Merchant-API-Salla-Docs

# Deactivate Webhook

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /webhooks/unsubscribe:
    delete:
      summary: Deactivate Webhook
      deprecated: false
      description: >-
        This endpoint allows you to unsubscribe/deactivate a webhook from the
        active webhooks list at your store. 


        :::tip[Note]


        - You can define which webhook to delete by using `url` and/or `id` in
        the query parameters.


        :::


        :::caution[Alert]

        - Using `url` will **delete** all registered webhooks to this URL.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `webhooks.read_write`- Webhooks Read & Write

        </Accordion>
      operationId: Delete-webhook
      tags:
        - Default module/Merchant API/APIs/Webhooks
        - Webhooks
      parameters:
        - name: id
          in: query
          description: >-
            Webhook ID. `requiredif` no URL passed. List of Webhook IDs can be
            found [here](https://docs.salla.dev/api-5394135).
          required: false
          schema:
            type: number
        - name: url
          in: query
          description: Webhook registered URL. `requiredif` no ID is passed.
          required: false
          schema:
            type: string
      responses:
        '202':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/delete_success'
              example:
                status: 202
                success: true
                data:
                  message: The Object has been removed successfully
                  code: 202
          headers: {}
          x-apidog-name: Object Deleted Successfully.
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
                    webhooks.read_write
          headers: {}
          x-apidog-name: Unauthorized
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
          x-apidog-name: Record Not Found
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
                    id:
                      - يجب أن يكون حقل id عددًا صحيحًا
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: deactivate
      x-apidog-folder: Default module/Merchant API/APIs/Webhooks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394137-run
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

## apis-webhooks/List-Active-Webhooks-Salla-Merchant-API-Salla-Docs

# List Active Webhooks

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /webhooks:
    get:
      summary: List Active Webhooks
      deprecated: false
      description: >-
        This endpoint allows you to list all available, registered, and active
        webhooks related to the store.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `webhooks.read`- Webhooks Read Only

        </Accordion>
      operationId: get-webhooks
      tags:
        - Default module/Merchant API/APIs/Webhooks
        - Webhooks
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/webhooks_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 831980095
                    name: Customer Login
                    event: customer.login
                    version: 2
                    rule: first_name = `User`
                    type: manual
                    url: https://webhook.site/ae7ff328-b54d-42d0-bc7c-94673cd2e982
                    headers:
                      Authorization: Your Secret Token
                      Accept-Language: AR
                pagination:
                  count: 0
                  total: 0
                  perPage: 65
                  currentPage: 0
                  totalPages: 0
                  links:
                    - string
          headers: {}
          x-apidog-name: OK
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
                    webhooks.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: Webhook
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Webhooks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394135-run
components:
  schemas:
    webhooks_response_body:
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
            id: gha86ioae9hl8
          items:
            $ref: '#/components/schemas/Webhook'
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
    Webhook:
      type: object
      x-examples:
        example:
          id: 60587520
          name: Salla Update Customer Event
          event: customer.updated
          url: https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
          version: 2
          rule: payment_method = mada
          headers:
            Authorization: Your Secret token
            Accept-Language: AR
      title: Webhook
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: A unique identifier assigned to a webhook.
          examples:
            - 60587520
        name:
          type: string
          description: The designated label assigned to a webhook.
          examples:
            - Salla Update Customer Event
        event:
          type: string
          description: >-
            An event that triggers a webhook to send real-time data between
            applications (from the events list).
          examples:
            - customer.updated
        type:
          type: string
          description: Webhook type.
        url:
          type: string
          description: >-
            The address where a webhook sends data when a predefined event
            occurs.
          examples:
            - https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
        version:
          type: number
          description: >-
            The webhook version, with values of `1` or `2`, reflecting changes
            or updates to its functionality or structure.
          enum:
            - 1
            - 2
          examples:
            - 2
          x-apidog-enum:
            - value: 1
              name: ''
              description: Webhook Version 1 (not used currently)
            - value: 2
              name: ''
              description: Webhook Version 2 (current one)
        rule:
          type: string
          description: >-
            operations, expressions, and conditions to your webhook, like =, !=,
            AND, or OR. For example: payment_method = YOUR_PAYMENT_METHOD ,
            payment_method = mada OR price < 50

            This enables precise response filtering based on your criteria.
          examples:
            - payment_method = mada
        headers:
          type: object
          description: >-
            Details included in webhook requests, such as authentication and
            content metadata, ensure secure and accurate communication between
            web services. These are represented by `headers.key` and
            `headers.value`.
          properties:
            Authorization:
              type: string
              description: >-
                Any header key, with its corresponding value, is sent within the
                POST request to the webhook URL.
              examples:
                - Your Secret token
            Accept-Language:
              type: string
              description: >-
                The value transmitted to the webhook, like this example:
                `cf-ray: 669af54ecf55dfcb-FRA`.
              examples:
                - AR
          x-apidog-orders:
            - Authorization
            - Accept-Language
          required:
            - Authorization
            - Accept-Language
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - event
        - type
        - url
        - version
        - rule
        - headers
      required:
        - id
        - name
        - event
        - type
        - url
        - version
        - rule
        - headers
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

## apis-webhooks/List-Events-Salla-Merchant-API-Salla-Docs

# List Events

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /webhooks/events:
    get:
      summary: List Events
      deprecated: false
      description: >-
        This endpoint allows you to list all the available events that can be
        used in registering webhooks from this endpoint.


        :::info[Information]

        Read more about Webhook Events
        [here](https://docs.salla.dev/doc-421119).

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `webhooks.read`- Webhooks Read Only

        </Accordion>
      operationId: List-Events
      tags:
        - Default module/Merchant API/APIs/Webhooks
        - Webhooks
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/webhookEvents_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    label: تم إنشاء طلب
                    event: order.created
                  - id: 566146469
                    label: تم تحديث بيانات طلب
                    event: order.updated
                  - id: 1939592358
                    label: تم إنشاء منتج
                    event: product.created
                  - id: 1298199463
                    label: تم تحديث بيانات منتج
                    event: product.updated
                  - id: 525144736
                    label: تم حذف منتج
                    event: product.deleted
                  - id: 1764372897
                    label: تمت إضافة عميل
                    event: customer.created
                  - id: 989286562
                    label: تم تحديث بيانات عميل
                    event: customer.updated
                  - id: 349994915
                    label: تمت إضافة تصنيف
                    event: category.created
                  - id: 1723506348
                    label: تم تحديث بيانات تصنيف
                    event: category.updated
          headers: {}
          x-apidog-name: >+
            A successful call returns a payload that contains a current list of
            the available webhooks events.

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
                    webhooks.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: listEvents
      x-salla-php-return-type: Events
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Webhooks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394136-run
components:
  schemas:
    webhookEvents_response_body:
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
            $ref: '#/components/schemas/Events'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Events:
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with the data or information received
            as a response to a specific event triggered by a webhook or API
            request.
        label:
          type: string
          description: >-
            A specific identifier or name used to reference and extract data
            from the response received when a webhook event is triggered.
        event:
          type: string
          description: Event text to be used to register new webhook.
      x-apidog-orders:
        - id
        - label
        - event
      required:
        - id
        - label
        - event
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

## apis-webhooks/Register-Webhook-Salla-Merchant-API-Salla-Docs

# Register Webhook

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /webhooks/subscribe:
    post:
      summary: Register Webhook
      deprecated: false
      description: >-
        This endpoint allows you to register a new webhook. 


        :::tip[Note] 

        - The webhook used is to notify/update/delete an external service when
        an event has occurred. 

        - To trigger your webhook to send data, you can choose one event from
        the [List Events](https://docs.salla.dev/doc-421119) endpoint. 

        :::


        :::info[Information]

        Read more on Webhooks [here](https://docs.salla.dev/doc-421119).

        :::


        :::caution[Alert]

        • New subscriptions with the same URL will update events / restore old
        webhooks *(if they exist)*.

        • The added URL **must** accept `POST` requests.

        • By default, all new webhooks are registered as version `2`. To use
        version `1`, specify it in your request parameters.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `webhooks.read_write`- Webhooks Read & Write

        </Accordion>
      operationId: Create-webhook
      tags:
        - Default module/Merchant API/APIs/Webhooks
        - Webhooks
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/webhook_request_body'
            example:
              name: Salla Update Customer Event
              event: customer.updated
              url: https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
              version: 2
              rule: payment_method = mada OR price < 50
              headers:
                - key: Your Secret token key name
                  value: Your Secret token value
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/webhook_response_body'
              examples:
                '1':
                  summary: Webhook V2
                  value:
                    status: 200
                    success: true
                    data:
                      id: 60587520
                      name: Salla Update Customer Event
                      event: customer.updated
                      type: manual
                      url: >-
                        https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
                      version: 2
                      rule: payment_method = mada OR price < 50
                      headers:
                        Authorization: abcd1234
                        Accept-Language: AR
                '3':
                  summary: Webhook V1
                  value:
                    status: 200
                    success: true
                    data:
                      id: 60587520
                      name: Salla Update Customer Event
                      event: customer.updated
                      url: >-
                        https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
                      headers:
                        Authorization: abcd1234
                        Accept-Language: AR
          headers: {}
          x-apidog-name: New webhook has been registered successfully
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
                    webhooks.read_write
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
                    url:
                      - >-
                        لابد أن يكون الرابط صالح وفعّال (لا يحتوي على localhost
                        أو test.)
                    event:
                      - حقل event غير صالحٍ
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: register
      x-salla-php-return-type: Webhook
      x-apidog-folder: Default module/Merchant API/APIs/Webhooks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394134-run
components:
  schemas:
    webhook_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            Webhook name. List of Webhook names can be found
            [here](https://docs.salla.dev/api-5394135).
          examples:
            - Salla Update Customer Event
        event:
          type: string
          description: >-
            Webhook event. List of events can be found [here](doc-421119), you
            can use one from the list.
          examples:
            - customer.updated
        url:
          type: string
          description: Webhook URL.
          examples:
            - https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
        version:
          type: integer
          description: Version of the webhook; either valued as `1` or `2`.
          enum:
            - 1
            - 2
          examples:
            - 2
          x-apidog-enum:
            - value: 1
              name: ''
              description: Webhook verion 1.
            - value: 2
              name: ''
              description: Webhook version 2.
        rule:
          type: string
          description: >-
            Operations, expressions and conditions to your webhook. For example,
            you may use `=`,`!=`,`AND`,`OR` etc in such a menner:
            `payment_method = YOUR_PAYMENT_METHOD` or in combination `company_id
            = 871291 OR price < 50`. That adds more capbility to filter the
            response based on conditions
          examples:
            - payment_method = mada OR price < 50
        headers:
          type: array
          description: Webhook headers.
          items:
            type: object
            properties:
              key:
                type: string
                description: >-
                  Any header key, which its value is sent in the post request to
                  the webhook URL
                examples:
                  - Your Secret token key name
              value:
                type: string
                description: >-
                  The value sent to the webhook; for example: `cf-ray:
                  669af54ecf55dfcb-FRA`
                examples:
                  - Your Secret token value
            x-apidog-orders:
              - key
              - value
            x-apidog-ignore-properties: []
      required:
        - event
        - url
      x-apidog-orders:
        - name
        - event
        - url
        - version
        - rule
        - headers
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    webhook_response_body:
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
          $ref: '#/components/schemas/Webhook'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Webhook:
      type: object
      x-examples:
        example:
          id: 60587520
          name: Salla Update Customer Event
          event: customer.updated
          url: https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
          version: 2
          rule: payment_method = mada
          headers:
            Authorization: Your Secret token
            Accept-Language: AR
      title: Webhook
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: A unique identifier assigned to a webhook.
          examples:
            - 60587520
        name:
          type: string
          description: The designated label assigned to a webhook.
          examples:
            - Salla Update Customer Event
        event:
          type: string
          description: >-
            An event that triggers a webhook to send real-time data between
            applications (from the events list).
          examples:
            - customer.updated
        type:
          type: string
          description: Webhook type.
        url:
          type: string
          description: >-
            The address where a webhook sends data when a predefined event
            occurs.
          examples:
            - https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
        version:
          type: number
          description: >-
            The webhook version, with values of `1` or `2`, reflecting changes
            or updates to its functionality or structure.
          enum:
            - 1
            - 2
          examples:
            - 2
          x-apidog-enum:
            - value: 1
              name: ''
              description: Webhook Version 1 (not used currently)
            - value: 2
              name: ''
              description: Webhook Version 2 (current one)
        rule:
          type: string
          description: >-
            operations, expressions, and conditions to your webhook, like =, !=,
            AND, or OR. For example: payment_method = YOUR_PAYMENT_METHOD ,
            payment_method = mada OR price < 50

            This enables precise response filtering based on your criteria.
          examples:
            - payment_method = mada
        headers:
          type: object
          description: >-
            Details included in webhook requests, such as authentication and
            content metadata, ensure secure and accurate communication between
            web services. These are represented by `headers.key` and
            `headers.value`.
          properties:
            Authorization:
              type: string
              description: >-
                Any header key, with its corresponding value, is sent within the
                POST request to the webhook URL.
              examples:
                - Your Secret token
            Accept-Language:
              type: string
              description: >-
                The value transmitted to the webhook, like this example:
                `cf-ray: 669af54ecf55dfcb-FRA`.
              examples:
                - AR
          x-apidog-orders:
            - Authorization
            - Accept-Language
          required:
            - Authorization
            - Accept-Language
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - event
        - type
        - url
        - version
        - rule
        - headers
      required:
        - id
        - name
        - event
        - type
        - url
        - version
        - rule
        - headers
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

## apis-webhooks/Update-Webhook-Salla-Merchant-API-Salla-Docs

# Update Webhook

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /webhooks/{id}:
    put:
      summary: Update Webhook
      deprecated: false
      description: >-
        This endpoint allows you to update an existing webhook by passing the
        `id` as path parameter



        :::tip[Note] 

        - The webhook used is to notify/update/delete an external service when
        an event has occurred. 

        - To trigger your webhook to send data, you can choose one event from
        the [List Events](https://docs.salla.dev/doc-421119) endpoint. 

        :::


        :::info[Information]

        Read more on Webhooks [here](https://docs.salla.dev/doc-421119).

        :::


        :::caution[Alert]

        • New subscriptions with the same URL will update events / restore old
        webhooks *(if they exist)*.

        • The added URL **must** accept `PUT` requests.

        • By default, all new webhooks are registered as version `2`. To use
        version `1`, specify it in your request parameters.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `webhooks.read_write`- Webhooks Read & Write

        </Accordion>
      operationId: Create-webhook
      tags:
        - Default module/Merchant API/APIs/Webhooks
        - Webhooks
      parameters:
        - name: id
          in: path
          description: >-
            Webhook ID. Get a list of Webhooks IDs from
            [here]https://docs.salla.dev/api-5394135)
          required: true
          example: 773200552
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/updateWebhook_request_body'
            example:
              name: Salla Update Customer Evensst
              version: 2
              rule: payment_method = mada OR price < 50
              headers:
                - key: Your Secret token key name
                  value: Your Secret token value
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
                    type: object
                    properties:
                      id:
                        type: integer
                        description: Webhook ID
                      name:
                        type: string
                        description: 'Webhook name '
                      event:
                        type: string
                        description: Webhook event
                      version:
                        type: integer
                        description: Webhook version
                      rule:
                        type: string
                        description: Webhook rule
                      url:
                        type: string
                        description: Webhook url
                      headers:
                        type: object
                        properties:
                          Your Secret token key name:
                            type: string
                            description: 'The secret token '
                        required:
                          - Your Secret token key name
                        x-apidog-orders:
                          - Your Secret token key name
                        x-apidog-ignore-properties: []
                      type:
                        type: string
                        description: Webhook type
                      security:
                        type: object
                        properties:
                          strategy:
                            type: string
                            description: The security strategy
                          secret:
                            type: 'null'
                            description: The security secrete number
                        required:
                          - strategy
                          - secret
                        x-apidog-orders:
                          - strategy
                          - secret
                        x-apidog-ignore-properties: []
                    required:
                      - id
                      - name
                      - event
                      - version
                      - rule
                      - url
                      - headers
                      - type
                      - security
                    x-apidog-orders:
                      - id
                      - name
                      - event
                      - version
                      - rule
                      - url
                      - headers
                      - type
                      - security
                    x-apidog-ignore-properties: []
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  id: 773200552
                  name: Salla Update Customer Evensst
                  event: test
                  version: 2
                  rule: payment_method = mada OR price < 50
                  url: https://webhook.site/fake_url
                  headers:
                    Your Secret token key name: Your Secret token value
                  type: manual
                  security:
                    strategy: ''
                    secret: null
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
                    webhooks.read_write
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
                    url:
                      - >-
                        لابد أن يكون الرابط صالح وفعّال (لا يحتوي على localhost
                        أو test.)
                    event:
                      - حقل event غير صالحٍ
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: register
      x-salla-php-return-type: Webhook
      x-apidog-folder: Default module/Merchant API/APIs/Webhooks
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10312606-run
components:
  schemas:
    updateWebhook_request_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            Webhook name. List of Webhook names can be found
            [here](https://docs.salla.dev/api-5394135).
          examples:
            - Salla Update Customer Event
        url:
          type: string
          description: Webhook registered URL. `requiredif` no ID is passed.
          examples:
            - https://webhook.site/07254470-c763-4ee3-bef1-ab2480262814
        version:
          type: integer
          description: Version of the webhook; either valued as `1` or `2`
          enum:
            - 1
            - 2
          examples:
            - 2
        rule:
          type: string
          description: >-
            Operations, expressions and conditions to your webhook. For example,
            you may use `=`,`!=`,`AND`,`OR` etc in such a menner:
            `payment_method = YOUR_PAYMENT_METHOD` or in combination `company_id
            = 871291 OR price < 50`. That adds more capbility to filter the
            response based on conditions
          examples:
            - payment_method = mada OR price < 50
        headers:
          type: array
          description: Webhook headers
          items:
            type: object
            properties:
              key:
                type: string
                description: >-
                  Any header key, which its value is sent in the post request to
                  the webhook URL
                examples:
                  - Your Secret token key name
              value:
                type: string
                description: >-
                  The value sent to the webhook; for example: `cf-ray:
                  669af54ecf55dfcb-FRA`
                examples:
                  - Your Secret token value
            x-apidog-orders:
              - key
              - value
            x-apidog-ignore-properties: []
        security_strategy:
          type: string
          description: in:signature,token
          nullable: true
        secret:
          type: string
          description: required_if:security_strategy,signature
      x-apidog-orders:
        - name
        - url
        - version
        - rule
        - headers
        - security_strategy
        - secret
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

