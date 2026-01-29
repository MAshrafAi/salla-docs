# Apis Product Quantity  Attach Digital Code Salla Merchant Api Salla Docs

## Table of Contents

- [apis-digitals-product/Attach-Digital-Code-Salla-Merchant-API-Salla-Docs](#apis-digitals-product-attach-digital-code-salla-merchant-api-salla-docs)
- [apis-digitals-product/Attach-Digital-File-Salla-Merchant-API-Salla-Docs](#apis-digitals-product-attach-digital-file-salla-merchant-api-salla-docs)
- [apis-digitals-product/Delete-Digital-File-Salla-Merchant-API-Salla-Docs](#apis-digitals-product-delete-digital-file-salla-merchant-api-salla-docs)
- [apis-product-quantity/List-Products-Quantities-Salla-Merchant-API-Salla-Docs](#apis-product-quantity-list-products-quantities-salla-merchant-api-salla-docs)

---

## apis-digitals-product/Attach-Digital-Code-Salla-Merchant-API-Salla-Docs

# Attach Digital Code

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/{product}/digital-codes:
    post:
      summary: Attach Digital Code
      deprecated: false
      description: >-
        This endpoint allows you to add digital codes to a specific product by
        passing the `product` as a path parameter. 



        :::tip[Note]

        You can only attach codes to a product.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Attach-Digital-Codes
      tags:
        - Default module/Merchant API/APIs/Digitals Product
        - Digitals Product
      parameters:
        - name: product
          in: path
          description: >-
            Unique identification number assigned to a product. List of products
            IDs can be found [here](https://docs.salla.dev/api-5394168).
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                codes:
                  type: array
                  description: >-
                    A unique alphanumeric or numerical identifiers assigned to
                    individual products.
                  items:
                    type: string
              x-apidog-orders:
                - codes
              required:
                - codes
              x-apidog-ignore-properties: []
            example:
              codes:
                - 232m322
                - 2D3w
                - sD21S
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
                  message: The entity has been created successfully
                  code: 201
          headers: {}
          x-apidog-name: Attached Successfully
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
                    products.read_write
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
                    codes:
                      - حقل codes مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: attachCode
      x-apidog-folder: Default module/Merchant API/APIs/Digitals Product
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394181-run
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

## apis-digitals-product/Attach-Digital-File-Salla-Merchant-API-Salla-Docs

# Attach Digital File

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/{product}/digital-files:
    post:
      summary: Attach Digital File
      deprecated: false
      description: >-
        This endpoint allows you to add digital files to a specific digital
        product by passing the `product` as a path parameter. 



        :::tip[Important]

        - You can only attach digital files to digital products.

        - You can only add one digital file per request.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Attache-Digital-File
      tags:
        - Default module/Merchant API/APIs/Digitals Product
        - Digitals Product
      parameters:
        - name: product
          in: path
          description: >-
            Unique identification number assigned to a product. List of products
            IDs can be found [here](https://docs.salla.dev/api-5394168).
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          multipart/form-data:
            schema:
              type: object
              properties:
                file:
                  description: The actual file to upload.
                  example: ''
                  type: string
                  format: binary
                file_name:
                  description: The name of the file which will display to customers.
                  example: ''
                  type: string
            example:
              file: document.pdf
              file_name: Great document
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productDigitalFile_response_body'
              example:
                status: 201
                success: true
                data:
                  name: YDKLARAVEL
                  url: >-
                    https://drive.google.com/file/d/1f1PJKAGj_09LH7jZTi0X7rydbR_XGvnN/view?usp=sharing
                  size: 297
          headers: {}
          x-apidog-name: Attached Successfully
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
                    products.read_write
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
                  code: validation_failed
                  message: The validation have failed
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: attachFile
      x-salla-php-return-type: ProductDigitalFile
      x-apidog-folder: Default module/Merchant API/APIs/Digitals Product
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394182-run
components:
  schemas:
    productDigitalFile_response_body:
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
          $ref: '#/components/schemas/ProductDigitalFile'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductDigitalFile:
      title: ProductDigitalFile
      type: object
      properties:
        name:
          type: string
          description: The name or title of a digital file associated with a product.
        url:
          type: string
          description: >-
            A web address or link that points to a specific digital file
            associated with a product.
        size:
          type: number
          description: Product digital file size.
      x-apidog-orders:
        - name
        - url
        - size
      required:
        - name
        - url
        - size
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

## apis-digitals-product/Delete-Digital-File-Salla-Merchant-API-Salla-Docs

# Delete Digital File

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/digital-files/{file}:
    delete:
      summary: Delete Digital File
      deprecated: false
      description: >-
        This endpoint allows you to delete a specific digital file, by passing
        the `file` as a path parameter. 


        :::tip[Note]

        You can get the file ID from the [Product
        Details](https://docs.salla.dev/api-5394169) endpoint.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: Delete-Digital-File
      tags:
        - Default module/Merchant API/APIs/Digitals Product
        - Digitals Product
      parameters:
        - name: file
          in: path
          description: 'Unique identifier assigned to the file. '
          required: true
          example: 0
          schema:
            type: integer
      responses:
        '202':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 202
                success: true
                data:
                  message: The Object has been removed successfully
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
                    products.read_write
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
      security:
        - bearer: []
      x-salla-php-method-name: deleteFile
      x-apidog-folder: Default module/Merchant API/APIs/Digitals Product
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394183-run
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

## apis-product-quantity/List-Products-Quantities-Salla-Merchant-API-Salla-Docs

# List Product Quantities

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/quantities:
    get:
      summary: List Product Quantities
      deprecated: false
      description: |-
        This endpoint allows you to fetch a list of products quantities

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `products.read`- Products Read Only
        </Accordion>
      operationId: get-product-inventory
      tags:
        - Default module/Merchant API/APIs/Product Quantity
        - Product Quantity
      parameters:
        - name: branch
          in: query
          description: >-
            Fetch products included in specific branch based on the branch ID.
            Get a list of Branch IDs from [here]()
          required: false
          example: branch=43957834
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productQuantities_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 532443002
                    name: T-Shirt Blue 2
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/ogEEayXo8KuuSUDMiRgxDCFPqr0IGvQsSFVciQyL.png
                    sku_id: null
                    sku: 250-SS
                    quantity: 40
                    sold_quantity: 18
                    price: 127
                    unlimited_quantity: false
                    variant: null
                  - id: 357354565
                    name: service
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/7yUJt9GZ80BsWgjnrmRQvItuENkSPlzfTVcgpBgu.png
                    sku_id: 1141551363
                    sku: null
                    quantity: 0
                    sold_quantity: 0
                    price: '127.00'
                    unlimited_quantity: true
                    variant: Fast - red
                  - id: 357354565
                    name: service
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/7yUJt9GZ80BsWgjnrmRQvItuENkSPlzfTVcgpBgu.png
                    sku_id: 299356172
                    sku: null
                    quantity: 0
                    sold_quantity: 0
                    price: '127.00'
                    unlimited_quantity: true
                    variant: Slow - white
                  - id: 1730800454
                    name: SSD
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/eIecMl7JsqYL29zVfYEwCzokxdYBAdKISlpYKX6M.jpg
                    sku_id: 442024243
                    sku: sam-ssd-128g
                    quantity: 127
                    sold_quantity: 340
                    price: '150.00'
                    unlimited_quantity: false
                    variant: 128G - black
                  - id: 1730800454
                    name: SSD
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/eIecMl7JsqYL29zVfYEwCzokxdYBAdKISlpYKX6M.jpg
                    sku_id: 1948639292
                    sku: sam-ssd-256g
                    quantity: 254
                    sold_quantity: 340
                    price: '150.00'
                    unlimited_quantity: false
                    variant: 256G - gold
                  - id: 780490562
                    name: عطر قريس 100 مل
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/MgB2A3gXUUAWFMt6cIkWUDN3zhSEoCQdzlkd76Ig.jpg
                    sku_id: null
                    sku: '123123123'
                    quantity: 123
                    sold_quantity: 450
                    price: 30
                    unlimited_quantity: false
                    variant: null
                  - id: 2019718723
                    name: عطر روشيل 100 مل
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/WTJWkpX7Jlm1BCoWEDqQSeo35fhlsxTEB4oTXDww.png
                    sku_id: null
                    sku: '4005900764911'
                    quantity: 412
                    sold_quantity: 187
                    price: 30
                    unlimited_quantity: true
                    variant: null
                  - id: 1246270796
                    name: S21
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/y2t0iITNahNxMoZKnKvDxjjL2xJPXZhkk6PuPCFX.png
                    sku_id: null
                    sku: S21-1200
                    quantity: 0
                    sold_quantity: 26
                    price: 127
                    unlimited_quantity: true
                    variant: null
                  - id: 375894947
                    name: بيتززا
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/IBNEPsIcIw1X9CkFZnFqJeWinuWdaCGcX0STxfGa.jpg
                    sku_id: null
                    sku: ''
                    quantity: 0
                    sold_quantity: 0
                    price: 127
                    unlimited_quantity: true
                    variant: null
                  - id: 1615647404
                    name: دورة اكتشاف الغوص - شاطئ
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/3B7XcB66NvgAsYSGvGrcwjwlQHearLPsEDy72SZj.png
                    sku_id: null
                    sku: ''
                    quantity: 0
                    sold_quantity: 0
                    price: 127
                    unlimited_quantity: true
                    variant: null
                  - id: 841609645
                    name: زينة خشبية رمضان كريم
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/gghxfBQRk7d30M9aKDmFM8FPD7v0SQQiB7SSHNLT.png
                    sku_id: null
                    sku: WSH001
                    quantity: 100
                    sold_quantity: 0
                    price: 34
                    unlimited_quantity: false
                    variant: null
                  - id: 267784366
                    name: متابعين تيك توك من دول العالم
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/nhNIKvPjOvyVYtKsC2MSIF6dSdEYHw4Kg9zR0dBZ.png
                    sku_id: null
                    sku: ''
                    quantity: 5
                    sold_quantity: 5
                    price: 50
                    unlimited_quantity: true
                    variant: null
                  - id: 1507016623
                    name: زيادة متابعين تويتر
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/7QPZ2FmvgEhwJbKM26HaQq6Pn3PwohtTDjwRW3Hd.png
                    sku_id: 1847391846
                    sku: null
                    quantity: 0
                    sold_quantity: 1003
                    price: '1.00'
                    unlimited_quantity: true
                    variant: 128G - blue
                  - id: 1507016623
                    name: زيادة متابعين تويتر
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/7QPZ2FmvgEhwJbKM26HaQq6Pn3PwohtTDjwRW3Hd.png
                    sku_id: 1006179687
                    sku: null
                    quantity: 0
                    sold_quantity: 1003
                    price: '1.00'
                    unlimited_quantity: true
                    variant: 256G - blue
                  - id: 1507016623
                    name: زيادة متابعين تويتر
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.comEVxp/7QPZ2FmvgEhwJbKM26HaQq6Pn3PwohtTDjwRW3Hd.png
                    sku_id: 1462421078
                    sku: null
                    quantity: 0
                    sold_quantity: 1003
                    price: 1
                    unlimited_quantity: true
                    variant: ابيض
                pagination:
                  count: 15
                  total: 84
                  perPage: 15
                  currentPage: 1
                  totalPages: 6
                  links:
                    next: >-
                      https://dashboard.test/admin/v2/products/quantities?branch=32772&page=3
                    previous: https://dashboard.test/admin/v2/products/quantities?
          headers: {}
          x-apidog-name: Success
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
          headers: {}
          x-apidog-name: unautorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Product Quantity
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9612796-run
components:
  schemas:
    productQuantities_response_body:
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
            $ref: '#/components/schemas/ProductQuantities'
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
    ProductQuantities:
      type: object
      properties:
        id:
          type: integer
          description: >-
            A unique identifier or code assigned to a specific product within a
            database, inventory system, or catalog to distinguish it from other
            products and enable efficient tracking and management.
        name:
          type: string
          description: >-
            A Product Name is a succinct label for a specific item, aiding in
            easy identification and categorization within a product listing.
        image:
          type: string
          description: >-
            The web addresses or hyperlinks that point to the online locations
            of images associated with the product, making it possible to display
            those images on websites, e-commerce platforms, or other online
            channels.
          nullable: true
        sku_id:
          type: integer
          description: A unique identifier for the sku or variant.
          nullable: true
        sku:
          type: string
          description: The product's SKU
          nullable: true
        quantity:
          type: integer
          description: >-
            The number of units or items of the product that is available in
            stock, to track and manage the available supply of a product.
        sold_quantity:
          type: integer
          description: The number of sold units
        price:
          type: string
          description: Product price value
        unlimited_quantity:
          type: boolean
          description: Option to indicate the product is of unlimited quantity
        variant:
          type: string
          description: >-
            SKU or variant name; only in case this variable is `variant` or
            `null`
          nullable: true
      x-apidog-orders:
        - id
        - name
        - image
        - sku_id
        - sku
        - quantity
        - sold_quantity
        - price
        - unlimited_quantity
        - variant
      required:
        - id
        - name
        - image
        - sku_id
        - sku
        - quantity
        - sold_quantity
        - price
        - unlimited_quantity
        - variant
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

