# Apis Customers  Ban Customer Salla Merchant Api Salla Docs

## Table of Contents

- [apis-customers/Ban-Customer-Salla-Merchant-API-Salla-Docs](#apis-customers-ban-customer-salla-merchant-api-salla-docs)
- [apis-customers/Create-Customer-Salla-Merchant-API-Salla-Docs](#apis-customers-create-customer-salla-merchant-api-salla-docs)
- [apis-customers/Customer-Details-Salla-Merchant-API-Salla-Docs](#apis-customers-customer-details-salla-merchant-api-salla-docs)
- [apis-customers/Delete-Customer-Salla-Merchant-API-Salla-Docs](#apis-customers-delete-customer-salla-merchant-api-salla-docs)

---

## apis-customers/Ban-Customer-Salla-Merchant-API-Salla-Docs

# Ban Customer

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/blacklist/{customer}:
    put:
      summary: Ban Customer
      deprecated: false
      description: >-
        This endpoint allows you to ban, aka Add to blacklist, one of your
        customers by passing the `customer` as a path parameter. 



        :::tip[Note]

        Even though banned customer won't be able to create new orders, they
        will still be able to login to the store.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Ban-Customer
      tags:
        - Default module/Merchant API/APIs/Customers
        - Customers
      parameters:
        - name: customer
          in: path
          description: >-
            Unique identifier assigned to the Customer. List of Customers IDs
            can be found [here](https://docs.salla.dev/api-5394121).
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
                reason:
                  type: string
                  description: >-
                    Explanation or rationale provided uopon requesting a ban or
                    restriction on an account or accessibility to a service.
              x-apidog-orders:
                - reason
              required:
                - reason
              x-apidog-ignore-properties: []
            example:
              reason: untrusted customer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/progress_ActionSuccess'
              example:
                status: 201
                success: true
                data:
                  message: The Blacklist has been updated successfully
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
                  message: Validation failed
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: ban
      x-apidog-folder: Default module/Merchant API/APIs/Customers
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394125-run
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

## apis-customers/Create-Customer-Salla-Merchant-API-Salla-Docs

# Create Customer

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers:
    post:
      summary: Create Customer
      deprecated: false
      description: >-
        This endpoint allows you to create Customers within your store at Salla
        by providing the required data in this endpoint. 


        :::tip[Note]

        - You may need the [Countries
        List](https://docs.salla.dev/endpoint-5394228) endpoint to get the
        mobile and country codes.

        - Also, you may use the [Customer Groups
        list](https://docs.salla.dev/endpoint-5394129) to add the group's IDs
        for the new customer.

        - Customer's email and mobile number are **unique**.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Create-Customer
      tags:
        - Default module/Merchant API/APIs/Customers
        - Customers
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/customer_request_body'
            example:
              first_name: Ahmed
              last_name: Ali
              mobile: '777777777'
              mobile_code_country: '+967'
              gender: female
              birthday: '1997-06-03'
              email: ahmedali@test.test
              groups:
                - '11323141'
                - '11323142'
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/customer_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 2075683582
                  first_name: Ahmed
                  last_name: Ali
                  mobile: 777777777
                  mobile_code: '967'
                  email: ahmedali@test.test
                  urls:
                    customer: https://shtara.com/profile
                    admin: https://shtara.com/profiley
                  avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  gender: male
                  city: Riyadh
                  country: السعودية
                  location: Alaziziiah street, building number 3
                  updated_at:
                    date: '2020-04-02 22:43:26.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  groups:
                    - 11323141
                    - 11323142
          headers: {}
          x-apidog-name: Created Successfully
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
                  message: Validation is not successfull
                  fields:
                    '{field-name}':
                      - The {field-label} field is required.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: Customer
      x-apidog-folder: Default module/Merchant API/APIs/Customers
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394120-run
components:
  schemas:
    customer_request_body:
      type: object
      x-examples:
        Example:
          first_name: Ahmed
          last_name: Ali
          mobile: '555555555'
          mobile_code_country: '+966'
          country_code: SA
          email: ahmedali@test.test
          gender: female
          birthday: '1997-06-03'
          groups:
            - 11323141
            - 11323142
      properties:
        first_name:
          type: string
          description: Customer given name.
          examples:
            - User
        last_name:
          type: string
          description: Customer family name.
          examples:
            - name
        mobile:
          type: string
          description: >-
            The numerical contact information belonging to a customer that
            allows communication via telephone, without country code.
          examples:
            - '555555555'
        mobile_code_country:
          type: string
          description: >-
            The numeric prefix indicating a customer's country for mobile
            communication.
          examples:
            - '+966'
        email:
          type: string
          description: Email address of the customer used for electronic communication.
          examples:
            - username@email.com
        gender:
          type: string
          description: >-
            The categorization of an individual as male, female, based on their 
            biologically determined characteristics.
          enum:
            - male
            - female
          examples:
            - male
          x-apidog-enum:
            - value: male
              name: ''
              description: Customer gender is male.
            - value: female
              name: ''
              description: Customer gender is female.
        birthday:
          type: string
          description: The customer date of brith.
          pattern: YYYY-MM-DD
          examples:
            - '1950-10-20'
        groups:
          type: array
          x-stoplight:
            id: 35g4rr1ibyob3
          description: A unique identifier for a group to which a customer belongs.
          items:
            x-stoplight:
              id: 489hy2q2mf4d2
            type: integer
      x-apidog-orders:
        - first_name
        - last_name
        - mobile
        - mobile_code_country
        - email
        - gender
        - birthday
        - groups
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    customer_response_body:
      type: object
      x-examples:
        Example:
          status: 200
          success: true
          data:
            id: 2075683582
            first_name: Ahmed
            last_name: Ali
            mobile: 12565786839
            mobile_code: '999'
            email: ahmedali@test.test
            avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
            gender: male
            city: Riyadh
            country: السعودية
            location: 'null'
            updated_at:
              date: '2020-04-02 22:43:26.000000'
              timezone_type: 3
              timezone: Asia/Riyadh
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
          $ref: '#/components/schemas/Customer'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Customer:
      description: >-
        Detailed structure of the customer model object showing its fields and
        data types.
      type: object
      x-tags:
        - Models
      title: Customer
      x-examples:
        Example:
          id: 2107468057
          first_name: Mohammed
          last_name: Ali
          mobile: 665323256199
          mobile_code: '+999'
          email: customer@demo.com
          avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
          gender: male
          birthday:
            date: '1997-06-03 00:00:00.000000'
            timezone_type: 3
            timezone: Asia/Riyadh
          city: الرياض
          country: السعودية
          country_code: sa
          currency: SAR
          location: '35.35418'
          updated_at: '2020-01-01 01:01:00.000000'
          groups:
            - 11323141
            - 11323142
      properties:
        id:
          type: number
          description: A unique identifier for the customer.
        first_name:
          type: string
          description: The customer's first name.
          maxLength: 25
        last_name:
          type: string
          description: The customer's last name.
          maxLength: 25
        mobile:
          type: number
          description: The customer's mobile phone number without the country code.
        mobile_code:
          type: string
          description: The country code for the customer's mobile phone number.
        email:
          type: string
          format: email
          description: The customer's email address.
        urls:
          $ref: '#/components/schemas/URLs'
          description: >-
            A list of URLs associated with the customer, such as their website
            or social media profiles.
        avatar:
          type: string
          description: A URL to the customer's avatar image.
        gender:
          type: string
          description: The customer's gender
          enum:
            - male
            - female
          x-apidog-enum:
            - value: male
              name: ''
              description: Male Person
            - value: female
              name: ''
              description: Female Person
        birthday:
          type: object
          properties:
            date:
              type: string
              format: date-time
              description: The customer's date of birth.
            timezone_type:
              type: integer
              format: int32
              description: The time zone type for the customer's date of birth.
            timezone:
              type: string
              description: The time zone for the customer's date of birth.
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          required:
            - date
            - timezone_type
          description: The customer date of birth
          x-apidog-ignore-properties: []
        city:
          type: string
          description: The city where the customer lives.
        country:
          type: string
          description: The country where the customer lives.
        country_code:
          type: string
          description: The country code for the customer's country.
        currency:
          type: string
          description: The currency that the customer uses.
        location:
          type: string
          description: The customer's location, represented as a string.
        updated_at:
          $ref: '#/components/schemas/Date'
          description: The date and time when the customer's information was last updated.
        groups:
          type: array
          items:
            type: integer
          description: A list of group IDs that the customer belongs to.
      required:
        - id
        - first_name
        - last_name
        - mobile
        - mobile_code
        - email
        - urls
        - avatar
        - gender
        - birthday
        - city
        - country
        - country_code
        - currency
        - location
        - updated_at
        - groups
      x-apidog-orders:
        - id
        - first_name
        - last_name
        - mobile
        - mobile_code
        - email
        - urls
        - avatar
        - gender
        - birthday
        - city
        - country
        - country_code
        - currency
        - location
        - updated_at
        - groups
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Date:
      type: object
      title: Date
      x-examples:
        Example:
          date: '2020-10-14 14:28:03.000000'
          timezone_type: 3
          timezone: Asia/Riyadh
      x-tags:
        - Models
      properties:
        date:
          type: string
          format: date-time
          description: >-
            A specific point in time, typically expressed in terms of a calendar
            system, including the day, month, year, hour, minutes, seconds and
            nano seconds. For example: "2020-10-14 14:28:03.000000"
        timezone_type:
          type: number
          description: 'Timezone type of the date, for Middel East = 3 '
        timezone:
          type: string
          description: Timezone value "Asia/Riyadh"
      x-apidog-orders:
        - date
        - timezone_type
        - timezone
      required:
        - date
        - timezone_type
        - timezone
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    URLs:
      description: >-
        To help companies and merchants, Salla provides a “urls” attribute that
        has been added to different modules to guide the merchants to have the
        full URL of this module from both scopes, the dashboard scope as a store
        admin, and as a customer.
      type: object
      title: Urls
      x-examples:
        Example:
          customer: https://shtara.com/profile
          admin: https://shtara.com/profiles
      x-tags:
        - Models
      properties:
        customer:
          type: string
          description: Customer link directly to the order.
          examples:
            - https://salla.sa/StoreLink
        admin:
          type: string
          description: Admin dashboard link directly to the order.
          examples:
            - https://s.salla./YourStoreDashboard
        digital_content:
          type: string
          description: >-
            A direct URL link to the digital asset, such as an e-book, image,
            PDF, video, or any downloadable file linked to the order or product.
        rating:
          type: string
          description: >-
            Order Rating Link. <br> Note that the order has to be of either of
            the following statuses: `completed`, `delivered`, or `shipped`. The
            merchant has to allow the product to be rated from the [Store
            Settings](https://s.salla.sa/settings) > Rating Settings
        checkout:
          type: string
          description: >-
            Order Checkout URL. <br>Note that the variable will only be returned
            if the order is unpaid. If the order is already paid, the variable
            will not appear in the response.
      x-apidog-orders:
        - customer
        - admin
        - digital_content
        - rating
        - checkout
      required:
        - customer
        - admin
        - digital_content
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

## apis-customers/Customer-Details-Salla-Merchant-API-Salla-Docs

# Customer Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/{customer}:
    get:
      summary: Customer Details
      deprecated: false
      description: >-
        This endpoint allows you to return a specific customer's details by
        passing the `customer` as a path parameter. 


        :::info[]

        The rate limit for the customers endpoints is **`500`** request per
        **`10`** minutes. For more details, please visit the [Rate
        Limiting](https://docs.salla.dev/421125m0) & [change
        log](https://docs.salla.dev/421127m0#291---2024-04-16) documentation
        page.

        :::



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read`- Customers Read Only

        </Accordion>
      operationId: Customer-Details
      tags:
        - Default module/Merchant API/APIs/Customers
        - Customers
      parameters:
        - name: customer
          in: path
          description: >-
            Unique identifier assigned to the Customer. List of Customers ID can
            be found [here](https://docs.salla.dev/api-5394121).
          required: true
          example: 0
          schema:
            type: integer
        - name: fields
          in: query
          description: >-
            Extra fields that can be included in the response. Example:
            ?fields[]=is_blocked&fields[]=block_reason
          required: false
          example: '?fields[]=is_blocked&fields[]=block_reason'
          schema:
            type: array
            items:
              type: string
              enum:
                - is_blocked
                - is_whitelisted
                - block_reason
                - is_inactive
                - orders_count
                - orders_amount
                - orders_average
                - orders_complete_ratio
                - orders_cancel_ratio
                - orders_cancel
                - latest_purchase
                - abandoned_carts_items
                - wallet_balance
                - total_points
                - country_id
                - custom_fields
                - current_store_customer
                - is_orders_rated
                - is_notifications_enabled
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/customer_response_body'
              examples:
                '1':
                  summary: Example
                  value:
                    status: 200
                    success: true
                    data:
                      id: 2075683582
                      first_name: Ahmed
                      last_name: Ali
                      mobile: 777777777
                      mobile_code: '967'
                      email: ahmedali@test.test
                      urls:
                        customer: https://shtara.com/profile
                        admin: https://shtara.com/profiley
                      avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                      gender: male
                      city: Riyadh
                      country: السعودية
                      country_code: sa
                      location: Alnaseem Street, house number 1
                      updated_at:
                        date: '2020-04-02 22:43:26.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      groups:
                        - 11323141
                        - 11323142
                '3':
                  summary: Example With Extra Keys
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1188233194
                      full_name: Ali Ahmed
                      first_name: Ali
                      last_name: Ahmed
                      mobile: 560000000
                      mobile_code: '+966'
                      email: ali@email.sa
                      urls:
                        customer: https://demostore.salla.sa/demo/profile
                        admin: https://s.salla.sa/customers/243798
                      avatar: >-
                        https://cdn.assets.salla.network/prod/admin/cp/assets/images/avatar_male.png
                      gender: male
                      birthday:
                        date: '2001-02-02 00:00:00.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      city: ''
                      country: السعودية
                      country_code: SA
                      currency: SAR
                      location: ''
                      lang: ar
                      created_at:
                        date: '2025-03-10 12:55:51.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      updated_at:
                        date: '2025-03-17 12:18:35.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      stats:
                        orders_count: 5
                        orders_amount: 720.91
                      is_orders_rated: false
                      pending_rating_count: 3
                      groups:
                        - 474034050
                        - 2134252254
                      abandoned_carts_items: null
                      block_reason: null
                      country_id: null
                      current_store_customer:
                        id: 295154194
                        approval_status: 1
                        reason: null
                        created_at:
                          date: '2025-03-10 12:55:51.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                        updated_at:
                          date: '2025-07-24 12:22:46.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                        last_login_date: null
                      custom_fields: []
                      is_blocked: false
                      is_inactive: false
                      is_notifications_enabled: true
                      latest_purchase:
                        date: '2025-07-21 11:30:40.000000'
                        timezone_type: 3
                        timezone: Asia/Riyadh
                      orders_average: 144.18
                      orders_cancel: 4
                      orders_cancel_ratio: 3
                      orders_complete_ratio: 88
                      total_points: 21
                      wallet_balance: 0
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
                    customers.read
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
      security:
        - bearer: []
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: Customer
      x-apidog-folder: Default module/Merchant API/APIs/Customers
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394122-run
components:
  schemas:
    customer_response_body:
      type: object
      x-examples:
        Example:
          status: 200
          success: true
          data:
            id: 2075683582
            first_name: Ahmed
            last_name: Ali
            mobile: 12565786839
            mobile_code: '999'
            email: ahmedali@test.test
            avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
            gender: male
            city: Riyadh
            country: السعودية
            location: 'null'
            updated_at:
              date: '2020-04-02 22:43:26.000000'
              timezone_type: 3
              timezone: Asia/Riyadh
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
          $ref: '#/components/schemas/Customer'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Customer:
      description: >-
        Detailed structure of the customer model object showing its fields and
        data types.
      type: object
      x-tags:
        - Models
      title: Customer
      x-examples:
        Example:
          id: 2107468057
          first_name: Mohammed
          last_name: Ali
          mobile: 665323256199
          mobile_code: '+999'
          email: customer@demo.com
          avatar: https://i.ibb.co/jyqRQfQ/avatar-male.webp
          gender: male
          birthday:
            date: '1997-06-03 00:00:00.000000'
            timezone_type: 3
            timezone: Asia/Riyadh
          city: الرياض
          country: السعودية
          country_code: sa
          currency: SAR
          location: '35.35418'
          updated_at: '2020-01-01 01:01:00.000000'
          groups:
            - 11323141
            - 11323142
      properties:
        id:
          type: number
          description: A unique identifier for the customer.
        first_name:
          type: string
          description: The customer's first name.
          maxLength: 25
        last_name:
          type: string
          description: The customer's last name.
          maxLength: 25
        mobile:
          type: number
          description: The customer's mobile phone number without the country code.
        mobile_code:
          type: string
          description: The country code for the customer's mobile phone number.
        email:
          type: string
          format: email
          description: The customer's email address.
        urls:
          $ref: '#/components/schemas/URLs'
          description: >-
            A list of URLs associated with the customer, such as their website
            or social media profiles.
        avatar:
          type: string
          description: A URL to the customer's avatar image.
        gender:
          type: string
          description: The customer's gender
          enum:
            - male
            - female
          x-apidog-enum:
            - value: male
              name: ''
              description: Male Person
            - value: female
              name: ''
              description: Female Person
        birthday:
          type: object
          properties:
            date:
              type: string
              format: date-time
              description: The customer's date of birth.
            timezone_type:
              type: integer
              format: int32
              description: The time zone type for the customer's date of birth.
            timezone:
              type: string
              description: The time zone for the customer's date of birth.
          x-apidog-orders:
            - date
            - timezone_type
            - timezone
          required:
            - date
            - timezone_type
          description: The customer date of birth
          x-apidog-ignore-properties: []
        city:
          type: string
          description: The city where the customer lives.
        country:
          type: string
          description: The country where the customer lives.
        country_code:
          type: string
          description: The country code for the customer's country.
        currency:
          type: string
          description: The currency that the customer uses.
        location:
          type: string
          description: The customer's location, represented as a string.
        updated_at:
          $ref: '#/components/schemas/Date'
          description: The date and time when the customer's information was last updated.
        groups:
          type: array
          items:
            type: integer
          description: A list of group IDs that the customer belongs to.
      required:
        - id
        - first_name
        - last_name
        - mobile
        - mobile_code
        - email
        - urls
        - avatar
        - gender
        - birthday
        - city
        - country
        - country_code
        - currency
        - location
        - updated_at
        - groups
      x-apidog-orders:
        - id
        - first_name
        - last_name
        - mobile
        - mobile_code
        - email
        - urls
        - avatar
        - gender
        - birthday
        - city
        - country
        - country_code
        - currency
        - location
        - updated_at
        - groups
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Date:
      type: object
      title: Date
      x-examples:
        Example:
          date: '2020-10-14 14:28:03.000000'
          timezone_type: 3
          timezone: Asia/Riyadh
      x-tags:
        - Models
      properties:
        date:
          type: string
          format: date-time
          description: >-
            A specific point in time, typically expressed in terms of a calendar
            system, including the day, month, year, hour, minutes, seconds and
            nano seconds. For example: "2020-10-14 14:28:03.000000"
        timezone_type:
          type: number
          description: 'Timezone type of the date, for Middel East = 3 '
        timezone:
          type: string
          description: Timezone value "Asia/Riyadh"
      x-apidog-orders:
        - date
        - timezone_type
        - timezone
      required:
        - date
        - timezone_type
        - timezone
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    URLs:
      description: >-
        To help companies and merchants, Salla provides a “urls” attribute that
        has been added to different modules to guide the merchants to have the
        full URL of this module from both scopes, the dashboard scope as a store
        admin, and as a customer.
      type: object
      title: Urls
      x-examples:
        Example:
          customer: https://shtara.com/profile
          admin: https://shtara.com/profiles
      x-tags:
        - Models
      properties:
        customer:
          type: string
          description: Customer link directly to the order.
          examples:
            - https://salla.sa/StoreLink
        admin:
          type: string
          description: Admin dashboard link directly to the order.
          examples:
            - https://s.salla./YourStoreDashboard
        digital_content:
          type: string
          description: >-
            A direct URL link to the digital asset, such as an e-book, image,
            PDF, video, or any downloadable file linked to the order or product.
        rating:
          type: string
          description: >-
            Order Rating Link. <br> Note that the order has to be of either of
            the following statuses: `completed`, `delivered`, or `shipped`. The
            merchant has to allow the product to be rated from the [Store
            Settings](https://s.salla.sa/settings) > Rating Settings
        checkout:
          type: string
          description: >-
            Order Checkout URL. <br>Note that the variable will only be returned
            if the order is unpaid. If the order is already paid, the variable
            will not appear in the response.
      x-apidog-orders:
        - customer
        - admin
        - digital_content
        - rating
        - checkout
      required:
        - customer
        - admin
        - digital_content
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

## apis-customers/Delete-Customer-Salla-Merchant-API-Salla-Docs

# Delete Customer

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /customers/{customer}:
    delete:
      summary: Delete Customer
      deprecated: false
      description: >-
        This endpoint allows you to delete a customer from the store customers
        list by passing the `customer` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `customers.read_write`- Customers Read & Write

        </Accordion>
      operationId: Delete-Customer
      tags:
        - Default module/Merchant API/APIs/Customers
        - Customers
      parameters:
        - name: customer
          in: path
          description: >-
            Unique identifier assigned to the Customer. List of Customers IDs
            can be found [here](https://docs.salla.dev/api-5394121).
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
                      specific condition.Response status Code
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
                      type: string
                x-apidog-refs: {}
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
              example:
                status: 200
                success: true
                data:
                  - تم حذف Customer بنجاح
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
                    customers.read_write
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
      security:
        - bearer: []
      x-salla-php-method-name: delete
      x-apidog-folder: Default module/Merchant API/APIs/Customers
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394124-run
components:
  schemas:
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

