# Apis Dns Records

## Table of Contents

- [apis-custom-urls/Import-Custom-URLs-Salla-Merchant-API-Salla-Docs](#apis-custom-urls-import-custom-urls-salla-merchant-api-salla-docs)
- [apis-dns-records/Create-DNS-Record-Salla-Merchant-API-Salla-Docs](#apis-dns-records-create-dns-record-salla-merchant-api-salla-docs)
- [apis-dns-records/Delete-DNS-Record-Salla-Merchant-API-Salla-Docs](#apis-dns-records-delete-dns-record-salla-merchant-api-salla-docs)
- [apis-dns-records/List-DNS-Records-Salla-Merchant-API-Salla-Docs](#apis-dns-records-list-dns-records-salla-merchant-api-salla-docs)

---

## apis-custom-urls/Import-Custom-URLs-Salla-Merchant-API-Salla-Docs

# Import Custom URLs

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /custom-urls/import:
    post:
      summary: Import Custom URLs
      deprecated: false
      description: >-
        This endpoint allows you to import custom URLs to the store.


        :::check[]

        You can get the template needed for this endpoint using the [Export
        Custom URLs](https://docs.salla.dev/api-10393831) endpoint

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `store-settings.read_write` - Store Settings Read & Write

        </Accordion>
      operationId: post-custom-urls-import
      tags:
        - Default module/Merchant API/APIs/Custom URLs
        - Custom URLs
      parameters: []
      requestBody:
        content:
          multipart/form-data:
            schema:
              type: object
              properties:
                file:
                  format: binary
                  type: string
                  description: 'Upload an Excel file '
                  example: ''
              required:
                - file
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
                  message: جاري إستيراد البيانات
                  code: 201
          headers: {}
          x-apidog-name: Created
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
                    store-settings.read_write
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
                  summary: Exception | File Content
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        file:
                          - >-
                            عفواً محتوى الملف غير مدعوم، يرجي التحقق من أن اسماء
                            الأعمدة وترتيبها في الملف المرفوع مطابقة لآخر نموذج
                            إستيراد من سلة، يرجى التواصل مع خدمة العملاء لمزيد
                            من المعلومات
                '4':
                  summary: Exception | File Type
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        file:
                          - >-
                            صيغة الملف غير مدعوم!، في حالة كان ملف إكسل، قد
                            يتطلب أن يكون تعديله عن طريق برنامج مايكروسوفت إكسل،
                            وليس برنامج آخر.
                '5':
                  summary: Exception | File Empty
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        file:
                          - الملف المرفوع فارغ!
          headers: {}
          x-apidog-name: Validation Error
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Custom URLs
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10393771-run
components:
  schemas:
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

## apis-dns-records/Create-DNS-Record-Salla-Merchant-API-Salla-Docs

# Create DNS Record

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /dns-records:
    post:
      summary: Create DNS Record
      deprecated: false
      description: >-
        This endpoint allows you to create DNS records such as A, CNAME, MX, and
        TXT records.

        :::info[Information]

        You can manage DNS records for a Salla store via the API using this
        endpoint.

        :::

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `dns-records.read_write`- DNS Records Read & Write

        </Accordion>
      operationId: post-dns_records
      tags:
        - Default module/Merchant API/APIs/DNS Records
        - DNS Records
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/DNSRecord_request_body'
            example:
              type: MX
              name: blog
              value: blog.yourwebsite.com
              priority: 0
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/DNSRecord_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 358857001
                  type: MX
                  name: blog
                  content: blog.yourwebsite.com
                  priority: 0
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
                    dns-records.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: DNS
      x-apidog-folder: Default module/Merchant API/APIs/DNS Records
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394252-run
components:
  schemas:
    DNSRecord_request_body:
      type: object
      properties:
        type:
          type: string
          enum:
            - A
            - ' AAAA '
            - 'CNAME '
            - 'SPF '
            - 'TXT '
            - MX
          description: 'Indicates the type of DNS record, such as the available enum ones '
        name:
          type: string
          description: Specifies the domain or subdomain to which the DNS record applies.
        value:
          type: string
          description: Refers to the data associated with a specific DNS record.
        priority:
          type: integer
          description: >-
            This is typically used for MX records to specify the order in which
            mail servers should be tried. Required if `type = MX`
      required:
        - type
        - name
        - value
      x-apidog-orders:
        - type
        - name
        - value
        - priority
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    DNSRecord_response_body:
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
          $ref: '#/components/schemas/DNS'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    DNS:
      type: object
      x-stoplight:
        id: 58075136603b8
      x-examples:
        Example:
          id: 358857001
          type: MX
          name: blog
          content: blog.yourwebsite.com
          priority: 0
      title: DNS
      properties:
        id:
          type: number
          description: A unique identifier for the DNS record within the DNS record.
        type:
          type: string
          description: Indicates the type of DNS record, such as A, CNAME, MX, or TXT.
          enum:
            - A
            - ' AAAA '
            - 'CNAME '
            - 'SPF '
            - 'TXT '
            - MX
          x-apidog-enum:
            - value: A
              name: ''
              description: ' Maps a domain to an IPv4 address.'
            - value: ' AAAA '
              name: ''
              description: ' Maps a domain to an IPv6 address.'
            - value: 'CNAME '
              name: ''
              description: ' Creates an alias for another domain name.'
            - value: 'SPF '
              name: ''
              description: ' Email authentication record to prevent spoofing.'
            - value: 'TXT '
              name: ''
              description: ' Stores arbitrary text'
            - value: MX
              name: ''
              description: ' Specifies mail servers for email delivery.'
        name:
          type: string
          description: Specifies the domain or subdomain to which the DNS record applies.
        content:
          type: string
          description: >-
            Contains the value associated with the DNS record. This could be an
            IP address for an A record, a domain name for a CNAME record, or
            other information depending on the record type.
          x-stoplight:
            id: tmmjthw881wt9
        priority:
          type: integer
          description: >-
            This is typically used for MX records to specify the order in which
            mail servers should be tried. Available if `type = MX`.
      x-tags:
        - Responses
      x-apidog-orders:
        - id
        - type
        - name
        - content
        - priority
      required:
        - id
        - type
        - name
        - content
        - priority
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

## apis-dns-records/Delete-DNS-Record-Salla-Merchant-API-Salla-Docs

# Delete DNS Record

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /dns-records/{dns_id}:
    delete:
      summary: Delete DNS Record
      deprecated: false
      description: >-
        This endpoint allows you to delete DNS records such as A, CNAME, MX, and
        TXT records, by passing the `dns_id` as a path parameter.


        :::info[Information]

        You can manage DNS records for a Salla store via the API using this
        endpoint.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `dns-records.read_write`- DNS Records Read & Write

        </Accordion>
      operationId: delete-dns_records-dns_id
      tags:
        - Default module/Merchant API/APIs/DNS Records
        - DNS Records
      parameters:
        - name: dns_id
          in: path
          description: >-
            Unique identification number assigned to the DNS. Get a list of DNS
            IDs from [here](https://docs.salla.dev/api-5394251)
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
                  message: تم حذف السجل بنجاح
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
                    dns-records.read_write
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: delete
      x-apidog-folder: Default module/Merchant API/APIs/DNS Records
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394253-run
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

## apis-dns-records/List-DNS-Records-Salla-Merchant-API-Salla-Docs

# List DNS Records

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /dns-records:
    get:
      summary: List DNS Records
      deprecated: false
      description: >
        This endpoint allows you to retrieve all of the DNS records, such as A,
        CNAME, MX, and TXT records.



        :::info

        You can manage DNS records for a Salla store via the API using this
        endpoint.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `dns-records.read`- DNS Records Read Only

        </Accordion>
      operationId: get-dns_records
      tags:
        - Default module/Merchant API/APIs/DNS Records
        - DNS Records
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/DNSRecords_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 1773697839
                    type: A
                    name: Test 1
                    content: 192.1.1.1
                  - id: 998677032
                    type: CNAME
                    name: Test Blog
                    content: blog.yourwebsite.com
                  - id: 358857001
                    type: MX
                    name: Test Security
                    content: security.yourwebsite.com
                    priority: 1
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
                    dns-records.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: DNS
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/DNS Records
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394251-run
components:
  schemas:
    DNSRecords_response_body:
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
            id: l5daevkqjfi5d
          items:
            $ref: '#/components/schemas/DNS'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    DNS:
      type: object
      x-stoplight:
        id: 58075136603b8
      x-examples:
        Example:
          id: 358857001
          type: MX
          name: blog
          content: blog.yourwebsite.com
          priority: 0
      title: DNS
      properties:
        id:
          type: number
          description: A unique identifier for the DNS record within the DNS record.
        type:
          type: string
          description: Indicates the type of DNS record, such as A, CNAME, MX, or TXT.
          enum:
            - A
            - ' AAAA '
            - 'CNAME '
            - 'SPF '
            - 'TXT '
            - MX
          x-apidog-enum:
            - value: A
              name: ''
              description: ' Maps a domain to an IPv4 address.'
            - value: ' AAAA '
              name: ''
              description: ' Maps a domain to an IPv6 address.'
            - value: 'CNAME '
              name: ''
              description: ' Creates an alias for another domain name.'
            - value: 'SPF '
              name: ''
              description: ' Email authentication record to prevent spoofing.'
            - value: 'TXT '
              name: ''
              description: ' Stores arbitrary text'
            - value: MX
              name: ''
              description: ' Specifies mail servers for email delivery.'
        name:
          type: string
          description: Specifies the domain or subdomain to which the DNS record applies.
        content:
          type: string
          description: >-
            Contains the value associated with the DNS record. This could be an
            IP address for an A record, a domain name for a CNAME record, or
            other information depending on the record type.
          x-stoplight:
            id: tmmjthw881wt9
        priority:
          type: integer
          description: >-
            This is typically used for MX records to specify the order in which
            mail servers should be tried. Available if `type = MX`.
      x-tags:
        - Responses
      x-apidog-orders:
        - id
        - type
        - name
        - content
        - priority
      required:
        - id
        - type
        - name
        - content
        - priority
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

