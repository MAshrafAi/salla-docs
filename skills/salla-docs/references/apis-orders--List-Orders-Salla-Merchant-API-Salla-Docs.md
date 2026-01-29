# Apis Orders  List Orders Salla Merchant Api Salla Docs

## Table of Contents

- [apis-orders/List-Orders-Salla-Merchant-API-Salla-Docs](#apis-orders-list-orders-salla-merchant-api-salla-docs)
- [apis-orders/Order-Actions-Salla-Merchant-API-Salla-Docs](#apis-orders-order-actions-salla-merchant-api-salla-docs)

---

## apis-orders/List-Orders-Salla-Merchant-API-Salla-Docs

# List Orders

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders:
    get:
      summary: List Orders
      deprecated: false
      description: >+
        This endpoint allows you to list all orders related to your store.



        :::tip[Note]

        • For old apps (expanded query parameter), the `shipping_details_id`
        inside the `shipping` object response matches the `id` returned by the
        [shipping estimated rate endpoint](https://docs.salla.dev/6899590e0).

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read` - Orders Read Only

        </Accordion>

      operationId: List-Orders
      tags:
        - Default module/Merchant API/APIs/Orders
        - Orders
      parameters:
        - name: keyword
          in: query
          description: >
            Listing the orders by keywords such as
            [tag_name](https://docs.salla.dev/api-5394180/?nav=1) and
            [shipping_number](https://docs.salla.dev/api-5394160/?nav=1)
          required: false
          example: ''
          schema:
            type: string
            enum:
              - customer.mobile
              - customer.name
              - shipping_number
              - reference_id
              - tag_name
            x-apidog-enum:
              - name: ''
                value: customer.mobile
                description: The customer phone number
              - name: ''
                value: customer.name
                description: 'The name of the customer '
              - name: ''
                value: shipping_number
                description: A number assigned to the shipping.
              - name: ''
                value: reference_id
                description: The unique identification number assigned to the order.
              - name: ''
                value: tag_name
                description: Tage name
        - name: payment_method
          in: query
          description: >-
            Find orders for specific payment method. List of available payment
            methods can be found
            [here](https://docs.salla.dev/api-5394164/?nav=1)
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: status
          in: query
          description: >-
            Find orders for specific status (array of ID integers). List of
            statuses can be found
            [here](https://docs.salla.dev/api-5394150/?nav=1)
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: from_date
          in: query
          description: Find orders created after a specific date.
          required: false
          example: ''
          schema:
            type: string
            format: date
            examples:
              - '2024-01-01'
            pattern: yyyy-mm-dd
        - name: to_date
          in: query
          description: Find orders created before a specific date.
          required: false
          example: ''
          schema:
            type: string
            pattern: yyyy-mm-dd
            format: date
            examples:
              - '2024-01-02'
        - name: country
          in: query
          description: >-
            Find orders for specific country. List of countries can be found
            [here](https://docs.salla.dev/api-5394228/?nav=1)
          required: false
          example: 0
          schema:
            type: integer
        - name: city
          in: query
          description: >-
            Find orders for specific city. List of cities can be found
            [here](https://docs.salla.dev/api-5394230/?nav=1)
          required: false
          example: ''
          schema:
            type: string
            examples:
              - jeddah
        - name: product
          in: query
          description: >-
            Find orders for specific product via its `name` variable. List of
            products can be found
            [here](https://docs.salla.dev/api-5394168/?nav=1)
          required: false
          example: ''
          schema:
            type: string
        - name: branch
          in: query
          description: >-
            Find orders for specific branch (array of integers). List of
            branches can be found
            [here](https://docs.salla.dev/api-5394224/?nav=1)
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: tags
          in: query
          description: >-
            Find orders for specific tags (array of ID integers). List of tags
            can be found [here](https://docs.salla.dev/api-5394154/?nav=1)
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: expanded
          in: query
          description: >-
            Get full details of orders same as [order
            details](https://docs.salla.dev/api-5394147/?nav=1) response by
            setting the value to `true`.
          required: false
          example: ''
          schema:
            type: boolean
            deprecated: true
          deprecated: true
        - name: page
          in: query
          description: The Pagination page number
          required: false
          example: 0
          schema:
            type: integer
        - name: reference_id
          in: query
          description: >-
            Unique identification refrence number that appears to the store
            owner
          required: false
          example: 0
          schema:
            type: integer
        - name: coupon
          in: query
          description: Discount code, extracted from `discount.code`
          required: false
          example: ''
          schema:
            type: string
        - name: customer_id
          in: query
          description: Customer unique identification number.
          required: false
          example: 0
          schema:
            type: number
        - name: shipping_app_id
          in: query
          description: Number array of Shipping Application unique identification number.
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: source
          in: query
          description: Order source.
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: sort_by
          in: query
          description: >-
            Sort the retrieved orders based on one attribute from the enum
            values. For example, if we need to sort the order by the `id` in
            ascending or descending order. we will concatenate either `asc` or
            `desc` with one of the enum values; in this case, we will use
            `id-asc` or `id-desc`.
          required: false
          example: ''
          schema:
            type: string
            enum:
              - id
              - total
              - updated_at
              - created_at
            x-apidog-enum:
              - name: ''
                value: id
                description: Order id
              - name: ''
                value: total
                description: Order total
              - name: ''
                value: updated_at
                description: The date of updating the order
              - name: ''
                value: created_at
                description: The date of creating the order
        - name: accounting_services
          in: query
          description: >-
            To filter the orders that did not get sent to the accounting
            services.
          required: false
          example: ''
          schema:
            type: string
            enum:
              - qoyod
              - daftra
              - zoho_books
            x-apidog-enum:
              - name: ''
                value: qoyod
                description: ''
              - name: ''
                value: daftra
                description: ''
              - name: ''
                value: zoho_books
                description: ''
        - name: unread
          in: query
          description: Find the unread orders that merchant did not open yet.
          required: false
          example: ''
          schema:
            type: boolean
        - name: assign_employee
          in: query
          description: >-
            Find the orders that are assigned to one or more employees. List of
            employees can be found
            [here](https://docs.salla.dev/api-5394259/?nav=1)
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
        - name: selling_channel
          in: query
          description: >-
            The order-selling channel which can be one of the allowed enum
            values
          required: false
          example: ''
          schema:
            type: array
            items:
              type: string
              enum:
                - mobile
                - mobile-app
                - desktop
                - affiliate
                - mahly-app
        - name: created_by
          in: query
          description: >-
            Employee unique identification number who created the order(s). List
            of employees can be found
            [here](https://docs.salla.dev/api-5394259/?nav=1)
          required: false
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/get_orders_response_body'
              examples:
                '1':
                  summary: Example
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 1017120475
                        reference_id: 40497536
                        total:
                          amount: 55
                          currency: SAR
                        exchange_rate:
                          base_currency: SAR
                          exchange_currency: USD
                          rate: 0.266592
                        date:
                          date: '2022-06-16 14:48:20.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                        status:
                          id: 566146469
                          name: بإنتظار المراجعة
                          slug: under_review
                          customized:
                            id: 986688842
                            name: بإنتظار المراجعة
                        can_cancel: false
                        can_reorder: true
                        payment_method: bank
                        is_pending_payment: false
                        pending_payment_ends_at: 0
                        features:
                          digitalable: true
                          shippable: true
                          has_suspicious_alert: false
                        items:
                          - name: تي شيرت بلاك
                            quantity: 1
                            thumbnail: >-
                              https://salla-dev.s3.eu-central-1.amazonaws.com/Mvyk/c151972a-c2d1-4a4d-b374-b46fd0bca79e-500x333.33333333333-WfHaI7WVXTosOlksBhesYbWlxhMFf9fJVDK6JlJj.jpg
                      - id: 1013578136
                        reference_id: 40497469
                        total:
                          amount: 0
                          currency: SAR
                        date:
                          date: '2022-06-16 14:46:42.000000'
                          timezone_type: 3
                          timezone: Asia/Riyadh
                        status:
                          id: 525144736
                          name: ملغي
                          slug: canceled
                          customized:
                            id: 1718741844
                            name: ملغي
                        can_cancel: false
                        can_reorder: true
                        is_pending_payment: true
                        pending_payment_ends_at: 0
                        items:
                          - name: Custom Shirt
                            quantity: 3
                    pagination:
                      count: 2
                      total: 2
                      perPage: 15
                      currentPage: 1
                      totalPages: 1
                      links: {}
                '2':
                  summary: Unauthorized
                  value:
                    status: 401
                    success: false
                    error:
                      code: Unauthorized
                      message: >-
                        The access token should have access to one of those
                        scopes: orders.read
          headers: {}
          x-apidog-name: 'Success '
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
          headers: {}
          x-apidog-name: Unauthorized
      security:
        - bearer: []
      x-salla-php-method-name: list
      x-salla-php-return-type: ListOrders
      x-salla-php-return-base-type: array
      x-apidog-folder: Default module/Merchant API/APIs/Orders
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394146-run
components:
  schemas:
    get_orders_response_body:
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
            id: orurptuq9pvoy
          items:
            $ref: '#/components/schemas/ListOrders'
          description: >-
            Detailed structure of the List Order model object showing its fields
            and data types.
        pagination:
          $ref: '#/components/schemas/Pagination'
          description: >-
            For a better response behavior as well as maintain the best security
            level, All retrieving API endpoints use a mechanism to retrieve data
            in chunks called pagination. Pagination working by return only a
            specific number of records in each response, and through passing the
            page number you can navigate the different pages.
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
    ListOrders:
      type: object
      title: ListOrders
      properties:
        id:
          type: number
          description: >-
            A unique alphanumeric code or identifier assigned to a specific
            order.
        reference_id:
          type: number
          description: A specific alphanumeric code or identifier associated with an order.
        total:
          type: object
          description: >-
            The amount representing the total expense incurred for all the items
            in the order.
          properties:
            amount:
              type: number
              description: Order total cost amount.
            currency:
              type: string
              description: Order total cost currency
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        date: &ref_0
          $ref: '#/components/schemas/Date'
          description: Date of the order.
        status:
          $ref: '#/components/schemas/NewOrderStatus'
          description: Status of the order.
        draft:
          type: boolean
          description: Whether or not the order is a draft or no.
        read:
          type: boolean
          description: Whether or not the order is read by the merchant or not
        can_cancel:
          type: boolean
          description: >-
            Whether or not the order is allowed to be cancelled by store
            customers.<br>

            `True` value should be set if the order status is in under review
            and in progress, as according to the store settings.
        can_reorder:
          type: boolean
          description: Whether or not the order allowed to be re-order by customers.
        payment_method:
          type: string
          description: The order's payment method
        is_pending_payment:
          type: boolean
          description: >-
            Whether or not the order is waiting to be paid or the order status
            is `payment_pending`.
        pending_payment_ends_at:
          type: string
          description: The time untill the payment has to be made by the cusotmer
        features:
          type: object
          properties:
            digitalable:
              type: boolean
              description: Whether or not there is a digital label for the order
            shippable:
              type: boolean
              description: Whether or not this order is shippable by shipping companies
            has_suspicious_alert:
              type: boolean
              description: Whether or not the order contains any suspicious fraud payments
          x-apidog-orders:
            - digitalable
            - shippable
            - has_suspicious_alert
          description: Order features details.
          required:
            - digitalable
            - shippable
          x-apidog-ignore-properties: []
        items:
          type: array
          items:
            type: object
            properties:
              name:
                type: string
                description: The label or description associated with a specific item.
              quantity:
                type: number
                description: >-
                  The numerical value representing the number of units or items
                  of a specific product.
              thumbnail:
                type: string
                description: The item image | thumbnail
            x-apidog-orders:
              - name
              - quantity
              - thumbnail
            x-apidog-ignore-properties: []
          description: Order items (products)
        customer:
          $ref: '#/components/schemas/Customer'
          description: Customer details.
      x-apidog-orders:
        - id
        - reference_id
        - total
        - date
        - status
        - draft
        - read
        - can_cancel
        - can_reorder
        - payment_method
        - is_pending_payment
        - pending_payment_ends_at
        - features
        - items
        - customer
      required:
        - id
        - reference_id
        - total
        - date
        - status
        - draft
        - read
        - can_cancel
        - can_reorder
        - payment_method
        - is_pending_payment
        - pending_payment_ends_at
        - features
        - items
        - customer
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
        updated_at: *ref_0
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
    NewOrderStatus:
      type: object
      title: NewOrderStatus
      x-examples:
        Example | Custom Status Type:
          status: 200
          success: true
          data:
            - id: 863076598
              name: في انتظار الدفع
              type: custom
              slug: payment_pending
              parent: null
              original:
                id: 1473353380
                name: بإنتظار الدفع
            - id: 224309239
              name: جاري مراجعة طلبك
              type: custom
              slug: under_review
              parent: null
              original:
                id: 566146469
                name: بإنتظار المراجعة
            - id: 1597755120
              name: بنفذ طلبك
              type: custom
              slug: in_progress
              parent: null
              original:
                id: 1939592358
                name: قيد التنفيذ
            - id: 1638621685
              name: تم التنفيذ
              type: custom
              slug: completed
              parent: null
              original:
                id: 1298199463
                name: تم التنفيذ
            - id: 1422535667
              name: جاري التوصيل
              type: custom
              slug: delivering
              parent:
                id: 1638621685
                name: تم التنفيذ
              original:
                id: 349994915
                name: جاري التوصيل
            - id: 647449340
              name: تم التوصيل
              type: custom
              slug: delivered
              parent:
                id: 1638621685
                name: تم التنفيذ
              original:
                id: 1723506348
                name: تم التوصيل
            - id: 1887201789
              name: تم الشحن
              type: custom
              slug: shipped
              parent:
                id: 1638621685
                name: تم التنفيذ
              original:
                id: 814202285
                name: تم الشحن
            - id: 687926769
              name: ملغي
              type: custom
              slug: canceled
              parent: null
              original:
                id: 525144736
                name: ملغي
            - id: 2062355698
              name: مسترجع
              type: custom
              slug: restored
              parent: null
              original:
                id: 989286562
                name: مسترجع
            - id: 1113229566
              name: قيد الإسترجاع
              type: custom
              slug: restoring
              parent: null
              original:
                id: 1548352431
                name: قيد الإسترجاع
        Example | Original Status Type:
          status: 200
          success: true
          data:
            - id: 1473353380
              name: بإنتظار الدفع
              type: original
              slug: payment_pending
              original: null
              parent: null
            - id: 566146469
              name: بإنتظار المراجعة
              type: original
              slug: under_review
              original: null
              parent: null
            - id: 1939592358
              name: قيد التنفيذ
              type: original
              slug: in_progress
              original: null
              parent: null
            - id: 1298199463
              name: تم التنفيذ
              type: original
              slug: completed
              original: null
              parent: null
            - id: 349994915
              name: جاري التوصيل
              type: original
              slug: delivering
              original: null
              parent: null
            - id: 1723506348
              name: تم التوصيل
              type: original
              slug: delivered
              original: null
              parent: null
            - id: 814202285
              name: تم الشحن
              type: original
              slug: shipped
              original: null
              parent: null
            - id: 525144736
              name: ملغي
              type: original
              slug: canceled
              original: null
              parent: null
            - id: 989286562
              name: مسترجع
              type: original
              slug: restored
              original: null
              parent: null
            - id: 1548352431
              name: قيد الإسترجاع
              type: original
              slug: restoring
              original: null
              parent: null
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: >-
            A unique alphanumeric code or identifier assigned to a specific
            order.
          examples:
            - 863076598
        name:
          type: string
          description: Descriptive label associated with the current status of an order.
          examples:
            - في انتظار الدفع
        slug:
          type: string
          description: A unique string or identifier used to represent a specific order .
          examples:
            - payment_pending
        customized:
          type: object
          properties:
            id:
              type: integer
              description: A unique identifier assigned to a specific order status.
            name:
              type: string
              description: Customized order status name.
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          x-apidog-ignore-properties: []
      description: ''
      x-apidog-orders:
        - id
        - name
        - slug
        - customized
      required:
        - id
        - name
        - slug
        - customized
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

## apis-orders/Order-Actions-Salla-Merchant-API-Salla-Docs

# Order Actions

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/actions:
    post:
      summary: Order Actions
      deprecated: false
      description: >-
        This endpoint allows you to perform bulk actions on the orders related
        to the store.


        :::tip[Tip]
         Find the actions that can be performed in the `action_name` variable's enum values. 
        :::


        ::: caution Important

        Some order actions are not to be triggered on the same request.
        Otherwise, you will get an error response. Below are an example of some
        of the actions that cannot be run together at the same time:

        - `create_shipping_policy`

        - `print_shipping_policy`

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-actions
      tags:
        - Default module/Merchant API/APIs/Orders
        - Orders
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/bulkActions_request_body'
            example:
              operations:
                - action_name: print_prepare_list
                - action_name: change_status
                  value:
                    status: 525144736
                    send_status_sms: true
                    return_police: true
                    restore_items: true
                    note: one note
                    branch_id: 21123
                - action_name: assign_users
                  value:
                    - 461258256
                    - 1968921873
                - action_name: assign_tags
                  value:
                    - new tag
                    - tag 3
              filters:
                order_ids:
                  - 1296837389
                  - 1936133132
                order_status:
                  - 3
                  - 5
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/bulkActions_response_body'
              example:
                status: 200
                success: true
                data:
                  - operation_id: 9c248334-f4cb-491b-84d0-57c415347d34
                    action_name: print_prepare_list
                    status: in_progress
                  - operation_id: 9c248334-f4cb-491b-84d0-57c415347dd5
                    action_name: change_status
                    status: in_progress
                  - operation_id: 9c248336-0080-440f-a936-68ee195e4139
                    action_name: assign_users
                    status: success
                  - operation_id: 9c1ab67e-fd53-47da-a4d1-12cd69f7b656
                    action_name: assign_tags
                    status: failed
                    message: 'لم يتم العثور على التاقات '
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
                    orders.read_write
          headers: {}
          x-apidog-name: Unauthorized
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
                  message: لا يمكن تنفيذ بعض الاجراءات معاً
                  actions:
                    - create_shipping_policy
                    - print_shipping_policy
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Orders
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-7549669-run
components:
  schemas:
    bulkActions_request_body:
      type: object
      properties:
        operations:
          type: array
          items:
            type: object
            properties:
              action_name:
                type: string
                description: >-
                  The actions to be conducted in bulk, which the value can only
                  be from the enum list mentioned.
                enum:
                  - create_shipping_policy
                  - create_return_policy
                  - print_shipping_policy
                  - cancel_policy
                  - assign_users
                  - export
                  - assign_tags
                  - change_status
                  - print_prepare_list
                  - print_invoice
                  - send_invoice
                  - print_invoice_summary
                  - send_payment_link
                  - extend_payment_due
                  - resend_codes
                  - send_rating
                  - mark_as_read
                  - refund
                  - delete
                x-apidog-enum:
                  - name: ''
                    value: create_shipping_policy
                    description: Create Shipping Policy
                  - name: ''
                    value: create_return_policy
                    description: Create Return policy
                  - name: ''
                    value: print_shipping_policy
                    description: Print Shipping Policy
                  - name: ''
                    value: cancel_policy
                    description: Cancel Shipping policy
                  - name: ''
                    value: assign_users
                    description: Assign Users to Order
                  - name: ''
                    value: export
                    description: Export Orders
                  - name: ''
                    value: assign_tags
                    description: Assign Tags to Order
                  - name: ''
                    value: change_status
                    description: Change Order Status
                  - name: ''
                    value: print_prepare_list
                    description: Print Prepare Order List
                  - name: ''
                    value: print_invoice
                    description: Print Order invoice
                  - name: ''
                    value: send_invoice
                    description: Send order invoice
                  - name: ''
                    value: print_invoice_summary
                    description: Print invoice summary
                  - name: ''
                    value: send_payment_link
                    description: Send payment link
                  - name: ''
                    value: extend_payment_due
                    description: Extend payment due
                  - name: ''
                    value: resend_codes
                    description: Resend digital codes
                  - name: ''
                    value: send_rating
                    description: Send rating
                  - name: ''
                    value: mark_as_read
                    description: Mark as read
                  - name: ''
                    value: refund
                    description: Refund Order
                  - name: ''
                    value: delete
                    description: Delete Order
              value:
                type: array
                items:
                  anyOf:
                    - type: object
                      properties:
                        status:
                          type: string
                          description: Status value
                        send_status_sms:
                          type: boolean
                          description: Whether or not to send the status via sms
                        return_police:
                          type: boolean
                          description: Whether or not to return the policy
                        restore_items:
                          type: boolean
                          description: Whether or not to restore items
                        note:
                          type: string
                          description: Status note
                        branch_id:
                          type: number
                          description: >
                            Unique branch ID number. Get a list of Branch IDs
                            from
                            [here](https://docs.salla.dev/api-5394224/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
                      x-apidog-orders:
                        - status
                        - send_status_sms
                        - return_police
                        - restore_items
                        - note
                        - branch_id
                      required:
                        - status
                      description: >-
                        When the `action_name` is set to `change_status` send
                        the following variables.
                      x-apidog-ignore-properties: []
                    - type: array
                      items:
                        type: integer
                      description: >
                        When the `action_name` is set to `assign_users` send an
                        array of [Users
                        IDs](https://docs.salla.dev/api-5394259/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
                    - type: array
                      items:
                        type: string
                      description: >-
                        When the `action_name` is set to `assign_tags` send an
                        array of [Order
                        Tags](https://docs.salla.dev/api-5394154/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB).
                description: >-
                  Value can either be an object, an array of strings or array of
                  integers. This variable is not required for some actions, such
                  as `print_prepare_list`, but required in some other actions,
                  such as `change_status`
            required:
              - action_name
            x-apidog-orders:
              - action_name
              - value
            x-apidog-ignore-properties: []
        filters:
          type: object
          properties:
            order_ids:
              type: array
              items:
                type: integer
              description: >-
                List of Order IDs. Fetch a list of orders from
                [here](https://docs.salla.dev/api-5394146)
            order_status:
              type: array
              items:
                type: integer
              description: >-
                List of Order Statuses. Fetch a list of orders statuses from
                [here](https://docs.salla.dev/api-5394150)
          x-apidog-orders:
            - order_ids
            - order_status
          x-apidog-ignore-properties: []
      required:
        - operations
        - filters
      x-apidog-orders:
        - operations
        - filters
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    bulkActions_response_body:
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
            $ref: '#/components/schemas/BulkActions'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    BulkActions:
      type: object
      title: BulkActions
      properties:
        operation_id:
          type: string
          description: >-
            A unique identifier assigned to a specific operation or task within
            a system.
        action_name:
          type: string
          description: Action name
          enum:
            - create_shipping_policy
            - print_shipping_policy
            - assign_users
            - export
            - assign_tags
            - change_status
            - print_prepare_list
            - delete
            - refund
          x-apidog-enum:
            - name: ''
              value: create_shipping_policy
              description: Bulk action name is create shipping policy
            - name: ''
              value: print_shipping_policy
              description: Bulk action name is print shipping policy
            - name: ''
              value: assign_users
              description: Bulk action name is assign users
            - name: ''
              value: export
              description: Bulk action name is export.
            - name: ''
              value: assign_tags
              description: Bulk action name is assign tags.
            - name: ''
              value: change_status
              description: Bulk action name is change status.
            - name: ''
              value: print_prepare_list
              description: Bulk action name is print prepare list
            - name: ''
              value: delete
              description: Bulk action name is delete
            - name: ''
              value: refund
              description: Bulk action name is refund
        status:
          type: string
          description: Action performed status
        message:
          type: string
          description: In the case of action failure, textual message will appear
      x-apidog-orders:
        - operation_id
        - action_name
        - status
        - message
      required:
        - operation_id
        - action_name
        - status
        - message
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

