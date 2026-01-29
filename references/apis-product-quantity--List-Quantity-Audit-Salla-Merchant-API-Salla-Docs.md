# Apis Product Quantity  List Quantity Audit Salla Merchant Api Salla Docs

## Table of Contents

- [apis-product-quantity/List-Quantity-Audit-Salla-Merchant-API-Salla-Docs](#apis-product-quantity-list-quantity-audit-salla-merchant-api-salla-docs)
- [apis-product-quantity/List-Quantity-Change-Reasosn-Salla-Merchant-API-Salla-Docs](#apis-product-quantity-list-quantity-change-reasosn-salla-merchant-api-salla-docs)
- [apis-product-quantity/Update-Bulk-Quantities-Salla-Merchant-API-Salla-Docs](#apis-product-quantity-update-bulk-quantities-salla-merchant-api-salla-docs)
- [apis-product-tags/Create-Product-Tag-Salla-Merchant-API-Salla-Docs](#apis-product-tags-create-product-tag-salla-merchant-api-salla-docs)
- [apis-product-tags/List-Product-Tags-Salla-Merchant-API-Salla-Docs](#apis-product-tags-list-product-tags-salla-merchant-api-salla-docs)

---

## apis-product-quantity/List-Quantity-Audit-Salla-Merchant-API-Salla-Docs

# List Quantity Audit

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/quantities/audit:
    get:
      summary: List Quantity Audit
      deprecated: false
      description: >-
        This endpoint allows you to retrieve audited changes in product
        quantities.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read`- Products Read Only

        </Accordion>
      operationId: get-products-quantity-log
      tags:
        - Default module/Merchant API/APIs/Product Quantity
        - Product Quantity
      parameters:
        - name: keyword
          in: query
          description: Search using a keyword
          required: false
          example: phones
          schema:
            type: string
        - name: categories
          in: query
          description: >-
            Fetch products included in specific category based on the category
            ID.  Get a list of Category IDs from
            [here](https://docs.salla.dev/api-5394207)
          required: false
          example:
            - categories[]=43957834
          schema:
            type: array
            items:
              type: string
        - name: brands
          in: query
          description: >-
            Fetch products included in specific brand based on the brand ID. Get
            a list of Brand IDs from [here](https://docs.salla.dev/api-5394213)
          required: false
          example:
            - brands[]=43957834
          schema:
            type: array
            items:
              type: string
        - name: tags
          in: query
          description: >-
            Fetch products included in specific tags based on the tag ID. Get a
            list of Tag IDs from [here](https://docs.salla.dev/api-5394180)
          required: false
          example:
            - tags[]=43957834
          schema:
            type: array
            items:
              type: string
        - name: branch
          in: query
          description: >-
            Fetch products included in specific branch based on the branch ID.
            Get a list of Branch IDs from
            [here](https://docs.salla.dev/api-5394224)
          required: false
          example: branch=43957834
          schema:
            type: array
            items:
              type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/quantityAudit_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 2015276628
                    name: كتاب الخوارزميات
                    image: https://img.youtube.com/vi/42-k6YQLa_I/mqdefault.jpg
                    sku: 23-TD23-32
                    created_at: '2024-08-22'
                    old_quantity: 27
                    new_quantity: 29
                    variant: blue-small
                    unlimited_quantity: false
                    reason: تصحيح
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1724121935
                    name: كتاب الخوارزميات
                    image: https://img.youtube.com/vi/42-k6YQLa_I/mqdefault.jpg
                    sku: 23-TD23-32
                    created_at: '2024-08-20'
                    old_quantity: 115
                    new_quantity: 65
                    variant: arabic
                    unlimited_quantity: false
                    reason: إعادة تخزين
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1809389117
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-27'
                    old_quantity: 16
                    new_quantity: 14
                    variant: red-L
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 436008764
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-27'
                    old_quantity: 21
                    new_quantity: 19
                    variant: blue-small
                    unlimited_quantity: false
                    reason: منتجات تالفة
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 79326263
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-27'
                    old_quantity: 16
                    new_quantity: 22
                    variant: blue-small
                    unlimited_quantity: false
                    reason: زيادة في المخزن
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 719146294
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-27'
                    old_quantity: 21
                    new_quantity: 19
                    variant: red-L
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1729697987
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-18'
                    old_quantity: 1
                    new_quantity: 3
                    variant: black-Xlarge
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 356317634
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-18'
                    old_quantity: 6
                    new_quantity: 8
                    variant: red-L
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 995613377
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-18'
                    old_quantity: 3
                    new_quantity: 1
                    variant: red-medium
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1770699712
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: 23-TD23-32
                    created_at: '2024-06-18'
                    old_quantity: 8
                    new_quantity: 6
                    variant: red-L
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 531471559
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-18'
                    old_quantity: 2
                    new_quantity: 3
                    variant: red-small
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1304919494
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-18'
                    old_quantity: 7
                    new_quantity: 8
                    variant: red-L
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1164912883
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: SKKR
                    created_at: '2024-06-18'
                    old_quantity: 4
                    new_quantity: 3
                    variant: red-large
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                  - id: 1803684338
                    name: Product
                    image: >-
                      https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/3d2b9bb2-528c-406e-8eb6-5b1c87038317-500x333.33333333333-pSTnvE7jS8iI4V4wjxutnULFvjVoLydQxueIR5qc.jpg
                    sku: 23-TD23-32
                    created_at: '2024-06-18'
                    old_quantity: 9
                    new_quantity: 8
                    variant: blue-small
                    unlimited_quantity: false
                    reason: ''
                    user:
                      id: 525144736
                      type: user
                      first_name: Joseph
                cursor:
                  current: 1
                  previous: 0
                  next: 1
                  count: 14
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
                    products.read_write
          headers: {}
          x-apidog-name: unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Product Quantity
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-9613070-run
components:
  schemas:
    quantityAudit_response_body:
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
            $ref: '#/components/schemas/QuantityAudit'
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
    QuantityAudit:
      type: object
      properties:
        id:
          type: integer
          description: >-
            The Product ID, a unique identifier or code assigned to a specific
            product within a database, inventory system, or catalog to
            distinguish it from other products and enable efficient tracking and
            management. List of Product ID can be found
            [here](https://docs.salla.dev/api-5394168).
        name:
          type: string
          description: >-
            A succinct label for a specific item, aiding in easy identification
            and categorization within a product listing.
        image:
          type: string
          description: >-
            The web addresses or hyperlinks that point to the online locations
            of images associated with the product, making it possible to display
            those images on websites, e-commerce platforms, or other online
            channels.
        sku:
          type: string
          description: >-
            Stock Keeping Unit. It's a unique code assigned to a specific
            product variant to identify and track inventory levels. 
          nullable: true
        created_at:
          type: string
          description: >-
            A specific point in time, typically expressed in terms of a calendar
            system, including the day, month, and year.
        old_quantity:
          type: integer
          description: Previous quantity value
        new_quantity:
          type: integer
          description: Current quantity value
        unlimited_quantity:
          type: boolean
          description: Option to indicate the product is of unlimited quantity
        reason:
          type: string
          description: Reason for quantity update
        user:
          type: object
          properties:
            id:
              type: integer
              description: User's ID
            type:
              type: string
              description: User's type
            first_name:
              type: string
              description: User's first name
          x-apidog-orders:
            - id
            - type
            - first_name
          description: The user responsible for the changes
          required:
            - id
            - type
            - first_name
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - image
        - sku
        - created_at
        - old_quantity
        - new_quantity
        - unlimited_quantity
        - reason
        - user
      required:
        - id
        - name
        - image
        - sku
        - created_at
        - old_quantity
        - new_quantity
        - unlimited_quantity
        - reason
        - user
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

## apis-product-quantity/List-Quantity-Change-Reasosn-Salla-Merchant-API-Salla-Docs

# List Quantity Change Reasons 

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/quantities/quantity-change-reason:
    get:
      summary: 'List Quantity Change Reasons '
      deprecated: false
      description: >-
        This endpoint allows you to retrieve a list of reasons for inventory
        quantity changes on products.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read`- Products Read Only

        </Accordion>
      operationId: get-quantity-change-reason
      tags:
        - Default module/Merchant API/APIs/Product Quantity
        - Product Quantity
      parameters: []
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
                          description: A unique identifier of the inventory change reason
                        name:
                          type: string
                          description: Description of quantity change
                      x-apidog-orders:
                        - id
                        - name
                      x-apidog-ignore-properties: []
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  - id: 1473353380
                    name: لا يوجد
                  - id: 566146469
                    name: تصحيح
                  - id: 1939592358
                    name: إعادة تخزين
                  - id: 1298199463
                    name: استقبال
                  - id: 525144736
                    name: تالف
                  - id: 1764372897
                    name: السرقة أو الضياع
                  - id: 989286562
                    name: توريد
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
                    products.read_write
          headers: {}
          x-apidog-name: unauthorized
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Product Quantity
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-10094923-run
components:
  schemas:
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

## apis-product-quantity/Update-Bulk-Quantities-Salla-Merchant-API-Salla-Docs

# Update Bulk Quantities

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/quantities/bulk:
    post:
      summary: Update Bulk Quantities
      deprecated: false
      description: >-
        This endpoint allows you to update bulk quantities by providing the IDs
        or Skus of the products you want to update its quantity in your body
        request


        ### Modes


        | Mode | Best Used For | Example Use Cases |

        |------|---------------|-------------------|

        | `increment` | Adding stock | • Receiving new inventory<br>• Restocking
        returned items<br>• Correcting undercounted stock |

        | `decrement` | Removing stock | • Processing sales<br>• Handling
        damaged goods<br>• Inventory adjustments |

        | `overwrite` | Initial setup only | • Setting initial stock levels<br>•
        Complete inventory resets<br>• Syncing with external systems (use with
        caution) |



        :::tip[]

        When updating product quantities, we **strongly recommend** using the
        `increment` and `decrement` modes instead of the `overwrite` mode for
        better inventory management and data integrity.

        :::



        ### Why Choose Increment/Decrement Modes?


        #### 1. **Concurrency Safety**

        When multiple systems or users update inventory simultaneously,
        increment/decrement operations provide better concurrency control:


        - **Safe**: `"mode": "decrement", "quantity": 5` removes exactly 5 units
        regardless of concurrent operations

        - **Risky**: `"mode": "overwrite", "quantity": 95` might overwrite
        changes made by other processes


        #### 2. **Prevents Race Conditions**

        In high-traffic scenarios where inventory updates happen frequently:


        ```json

        // Scenario: Current stock is 100 units

        // Two simultaneous operations occur:


        // Operation A (GOOD - using decrement)

        {
          "mode": "decrement",
          "quantity": 3  // Safely removes 3 units
        }


        // Operation B (GOOD - using decrement) 

        {
          "mode": "decrement", 
          "quantity": 2  // Safely removes 2 units
        }

        // Final result: 95 units (100 - 3 - 2) ✅


        // VS


        // Operation A (RISKY - using overwrite)

        {
          "mode": "overwrite",
          "quantity": 97  // Sets to 97 (100-3)
        }


        // Operation B (RISKY - using overwrite)

        {
          "mode": "overwrite",
          "quantity": 98  // Sets to 98 (100-2), overwrites Operation A
        }

        // Final result: 98 units (incorrect, should be 95) ❌

        ```


        #### 3. **Better Audit Trail**

        Increment/decrement operations provide clearer tracking of inventory
        changes:

        - **Clear intent**: "Decremented by 10 due to lost" vs "Set to 40 for
        unknown reason"

        - **Easier debugging**: You can trace each quantity change and its
        impact

        - **Better reporting**: Sum all increments/decrements to understand
        total movement


        #### 4. **Improved Data Integrity**

        - **Atomic operations**: Each increment/decrement is a single,
        indivisible operation

        - **Consistent state**: Inventory levels remain accurate even with
        concurrent updates

        - **Error recovery**: Easier to reverse specific operations if needed



        ### Implementation Example


        ```json

        {
          "products": [
            {
              "identifer_type": "id",
              "identifer": "613398835",
              "quantity": 5,
              "mode": "decrement",  // ✅ Recommended: Remove 5 units from current stock
              "branch": "349994915",
              "reason_id": 566146469
            },
            {
              "identifer_type": "id", 
              "identifer": "9834759404",
              "quantity": 20,
              "mode": "increment",  // ✅ Recommended: Add 20 units to current stock
              "branch": "349994915",
              "reason_id": 566146469
            }
          ]
        }

        ```



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: post-products-quantities-bulk
      tags:
        - Default module/Merchant API/APIs/Product Quantity
        - Product Quantity
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/updateBulkQuantity_request_body'
            example:
              products:
                - identifer_type: id
                  identifer: '613398835'
                  quantity: 60
                  mode: increment
                  branch: '349994915'
                  reason_id: 566146469
                  unlimited_quantity: true
                - identifer_type: id
                  identifer: '9834759404'
                  quantity: 80
                  mode: overwrite
                  branch: '349994915'
                  reason_id: 566146469
                  unlimited_quantity: true
                - identifer_type: variant_id
                  identifer: '3498732894'
                  quantity: 14
                  mode: decrement
                  branch: '349994915'
                  reason_id: 566146469
                - identifer_type: variant_id
                  identifer: '8439405958'
                  quantity: 140
                  branch: '349994915'
                  reason_id: 566146469
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
                  message: >-
                    The details has been queued to update, it may take several
                    minutes to finish the process
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
                    products.read_write
          headers: {}
          x-apidog-name: unauthorized
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
                        products.0.quantity:
                          - حقل الكمية مطلوب.
                '4':
                  summary: Example 2
                  value:
                    status: 422
                    success: false
                    error:
                      code: error
                      message: alert.invalid_fields
                      fields:
                        products.0.identifer_type:
                          - حقل products.0.identifer_type مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: updateBulk
      x-apidog-folder: Default module/Merchant API/APIs/Product Quantity
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394192-run
components:
  schemas:
    updateBulkQuantity_request_body:
      type: object
      properties:
        products:
          type: array
          items:
            type: object
            properties:
              identifer_type:
                type: string
                description: >-
                  Identifier Type. Value can either be `id` , `variant_id` or
                  `sku`
                enum:
                  - id
                  - variant_id
                  - sku
                x-apidog-enum:
                  - name: ''
                    value: id
                    description: product id
                  - name: ''
                    value: variant_id
                    description: variant id
                  - value: sku
                    name: ''
                    description: sku
              identifer:
                type: string
                description: Identifier Value, such as Product ID or and sku
                examples:
                  - '1210921'
              quantity:
                type: integer
                description: Quantity Value
              mode:
                type: string
                enum:
                  - overwrite
                  - increment
                  - decrement
                default: overwrite
                x-apidog-enum:
                  - name: ''
                    value: overwrite
                    description: Overwrite the current quantity
                  - name: ''
                    value: increment
                    description: >-
                      Increment the current quantitiy based on the `quantity`
                      variable's value
                  - name: ''
                    value: decrement
                    description: >-
                      Decrement the current quantitiy based on the `quantity`
                      variable's value
                description: Mode of quantity update; one of the allowed enum values
                nullable: true
              unlimited_quantity:
                type: boolean
                description: Option to indicate the product is of unlimited quantity
              branch:
                type: integer
                description: Branch ID
              reason_id:
                type: integer
                description: Reason ID for the update
            required:
              - identifer_type
              - identifer
              - quantity
            x-apidog-orders:
              - identifer_type
              - identifer
              - quantity
              - mode
              - unlimited_quantity
              - branch
              - reason_id
            x-apidog-ignore-properties: []
      required:
        - products
      x-apidog-orders:
        - products
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

## apis-product-tags/Create-Product-Tag-Salla-Merchant-API-Salla-Docs

# Create Product Tag

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/tags:
    post:
      summary: Create Product Tag
      deprecated: false
      description: >-
        This endpoint allows you to create Product Tags within your store at
        Salla by providing the required data.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read_write`- Products Read & Write

        </Accordion>
      operationId: post-products-tags
      tags:
        - Default module/Merchant API/APIs/Product Tags
        - Product Tags
      parameters:
        - name: tag_name
          in: query
          description: >-
            Product tag name. List of Product tags can be found
            [here](https://docs.salla.dev/api-5394180).
          required: true
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productTag_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 2129257534
                    name: T-Shirts
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
                    products.read_write
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
                    tag_name:
                      - حقل اسم الوسم مطلوب
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: ProductTag
      x-apidog-folder: Default module/Merchant API/APIs/Product Tags
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394179-run
components:
  schemas:
    productTag_response_body:
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
          $ref: '#/components/schemas/ProductTag'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductTag:
      title: ProductTag
      type: object
      properties:
        id:
          type: number
          description: Product tage unique identification.
          examples:
            - 2129257534
        name:
          type: string
          description: Product tag name.
          examples:
            - T-Shirts
      x-apidog-orders:
        - id
        - name
      required:
        - id
        - name
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

## apis-product-tags/List-Product-Tags-Salla-Merchant-API-Salla-Docs

# List Product Tags

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/tags:
    get:
      summary: List Product Tags
      deprecated: false
      description: >-
        This endpoint allows you to list all available product tags related to
        your store.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read`- Products Read Only

        </Accordion>
      operationId: get-products-tags
      tags:
        - Default module/Merchant API/APIs/Product Tags
        - Product Tags
      parameters: []
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/productTags_response_body'
              example:
                status: 200
                success: true
                data:
                  - id: 2129257534
                    name: T-Shirts
                  - id: 2129257534
                    name: ازر
                pagenation:
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
                  message: >-
                    The access token should have access to one of those scopes:
                    products.read
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: ProductTag
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Product Tags
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394180-run
components:
  schemas:
    productTags_response_body:
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
            id: ctlxz7h26mcgj
          items:
            $ref: '#/components/schemas/ProductTag'
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
    ProductTag:
      title: ProductTag
      type: object
      properties:
        id:
          type: number
          description: Product tage unique identification.
          examples:
            - 2129257534
        name:
          type: string
          description: Product tag name.
          examples:
            - T-Shirts
      x-apidog-orders:
        - id
        - name
      required:
        - id
        - name
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

