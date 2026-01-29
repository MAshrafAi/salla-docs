# Apis Settings

## Table of Contents

- [apis-settings/Settings-Details-Salla-Merchant-API-Salla-Docs](#apis-settings-settings-details-salla-merchant-api-salla-docs)
- [apis-settings/Settings-List-Salla-Merchant-API-Salla-Docs](#apis-settings-settings-list-salla-merchant-api-salla-docs)
- [apis-settings/Update-Settings-Fields-Salla-Merchant-API-Salla-Docs](#apis-settings-update-settings-fields-salla-merchant-api-salla-docs)

---

## apis-settings/Settings-Details-Salla-Merchant-API-Salla-Docs

# Setting Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settings/fields/{slug}:
    get:
      summary: Setting Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch settings details for a specific slug
        by passing the `slug` as a path parameter.


        :::info[Read More]

        For more on Store Settings, check the Merchant's Help Desk article
        [here](https://help.salla.sa/article/1887201789)

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `store-settings.read`- Settings Read Only

        </Accordion>
      operationId: get-settings-slug
      tags:
        - Default module/Merchant API/APIs/Settings
        - Settings
      parameters:
        - name: slug
          in: path
          description: >-
            Unique identifier or URL-friendly name assigned to the Settings .
            Get a list of Settings Slugs from
            [here](https://docs.salla.dev/api-6965777)
          required: true
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/slugSettings_response_body'
              examples:
                '1':
                  summary: Success | Receive Orders
                  value:
                    status: 200
                    success: true
                    data:
                      receive_orders: true
                      limit:
                        enable: false
                        count: 50
                        message:
                          ar: "ياهلا {name}\r\n نعتذر عميلنا العزيز، لايمكن استقبال طلبك اليوم لوصولنا للحد الاعلى لطلبات اليوم، يمكنك الطلب بعد {time}."
                          en: "ياهلا {name}\r\n نعتذر عميلنا العزيز، لايمكن استقبال طلبك اليوم لوصولنا للحد الاعلى لطلبات اليوم، يمكنك الطلب بعد {time}."
                          zh: "ياهلا {name}\r\n نعتذر عميلنا العزيز، لايمكن استقبال طلبك اليوم لوصولنا للحد الاعلى لطلبات اليوم، يمكنك الطلب بعد {time}."
                '3':
                  summary: Success | Recieving Times
                  value:
                    saturday:
                      enabled: true
                      from: '00:00'
                      to: '23:55'
                    sunday:
                      enabled: false
                      from: '00:00'
                      to: '23:55'
                    monday:
                      enabled: false
                      from: '00:00'
                      to: '23:55'
                    tuesday:
                      enabled: false
                      from: '00:00'
                      to: '23:55'
                    wednesday:
                      enabled: false
                      from: '00:00'
                      to: '23:55'
                    thursday:
                      enabled: false
                      from: '00:00'
                      to: '23:55'
                    friday:
                      enabled: false
                      from: '00:00'
                      to: '23:55'
                '4':
                  summary: Success | Reports Order Statuses
                  value:
                    status: 200
                    success: true
                    data:
                      order_statuses:
                        - id: 1
                          name: بإنتظار الدفع
                          selected: true
                        - id: 2
                          name: بإنتظار المراجعة
                          selected: true
                        - id: 3
                          name: قيد التنفيذ
                          selected: true
                        - id: 4
                          name: تم التنفيذ
                          selected: true
                        - id: 8
                          name: جاري التوصيل
                          selected: true
                        - id: 9
                          name: تم التوصيل
                          selected: false
                        - id: 10
                          name: تم الشحن
                          selected: false
                        - id: 11
                          name: بإنتظار تأكيد الدفع
                          selected: true
                        - id: 13
                          name: طلب عرض سعر
                          selected: false
                '5':
                  summary: Success | Products Purchase Count
                  value:
                    enabled: true
                    condition:
                      enabled: false
                      categories: []
                '6':
                  summary: Success | Products Recommendations
                  value: |-
                    {
                        "enabled": true,
                        "types": "category" // random, category, brand, tag
                    }
                '7':
                  summary: Success | Products - Product Notify Availability
                  value:
                    enabled:
                      products: true
                      skus: true
                    channels:
                      - email
                      - sms
                    channels_status:
                      email: true
                      sms: true
                      mobile: false
                      whatsapp: false
                    content_title: '{product} صار متوفر!'
                    content_message: |-
                      ياهلا {name}،
                              قبل فترة حاولت تطلب ({product}) وكان مخلص عندنا
                              و عشانك وفرناه في المتجر لكن بكمية محدودة
                              ألحق اطلب من الرابط التالي:
                              {product_link}
                '8':
                  summary: Success | Products - Product Inventory
                  value: |-
                    {
                        "show_out_products": 0,
                        "manual_quantity": 1,
                        "display_product_quantity": "show" // hide, show, less_than_5
                    }
                '9':
                  summary: Success | Products - Brand Options
                  value:
                    status: 200
                    success: true
                    data:
                      show_banner: 0
                      show_in_menu: 1
                      menu_title:
                        en: ''
                        ar: الماركات التجارية
                      menu_order: '100'
                '10':
                  summary: Success | Products - Size Guides
                  value:
                    status: 200
                    success: true
                    data:
                      - id: 1298199463
                        name: Size 4
                        description: test size 4
                        type: 1
                        enablec: false
                        brands:
                          - 2079537577
                        translations:
                          ar:
                            name: Size 4
                            description: test size 4
                      - id: 1939592358
                        name: Size 3
                        description: test size 3
                        type: 2
                        enablec: false
                        categories:
                          - 1908230909
                        translations:
                          ar:
                            name: Size 3
                            description: test size 3
                      - id: 566146469
                        name: Size 2
                        description: test Size 2
                        type: 1
                        enablec: false
                        brands:
                          - 814202285
                        translations:
                          ar:
                            name: Size 2
                            description: test Size 2
                      - id: 1473353380
                        name: Size 1
                        description: test size 1
                        type: 2
                        enablec: false
                        categories:
                          - 1134193150
                        translations:
                          ar:
                            name: Size 1
                            description: test size 1
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
                  code: Unauthorized
                  message: >-
                    The access token should have access to one of those scopes:
                    exports.read_write
          headers: {}
          x-apidog-name: error_unauthorized_401
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
          headers: {}
          x-apidog-name: error_notFound_404
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Settings
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-6965781-run
components:
  schemas:
    slugSettings_response_body:
      anyOf:
        - type: object
          properties:
            status:
              type: integer
              description: >-
                Response status code, a numeric or alphanumeric identifier used
                to convey the outcome or status of a request, operation, or
                transaction in various systems and applications, typically
                indicating whether the action was successful, encountered an
                error, or resulted in a specific condition.
            success:
              type: string
              description: >-
                Response flag, boolean indicator used to signal a particular
                condition or state in the response of a system or application,
                often representing the presence or absence of certain conditions
                or outcomes.
            data:
              type: object
              properties:
                receive_orders:
                  type: boolean
                  description: >-
                    Whether or not the store receives orders from store
                    customers
                limit:
                  type: object
                  properties:
                    enable:
                      type: boolean
                      description: >-
                        Whether or not to enable the daily limit orders for the
                        store
                    count:
                      type: number
                      description: Number of orders to accept from the store customers
                    message:
                      type: object
                      properties:
                        ar:
                          type: string
                          description: Text message in the Arabic Language
                        en:
                          type: string
                          description: Text message in the English Language
                      x-apidog-orders:
                        - ar
                        - en
                      required:
                        - ar
                        - en
                      description: >-
                        Text message to appear when the store doesn't accept
                        orders
                      x-apidog-ignore-properties: []
                  x-apidog-orders:
                    - enable
                    - count
                    - message
                  required:
                    - enable
                    - count
                    - message
                  description: Daily limit orders for the store
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - receive_orders
                - limit
              required:
                - receive_orders
                - limit
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - status
            - success
            - data
          required:
            - status
            - success
            - data
          title: ''
          description: Receive Orders Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            dayOfTheWeek:
              type: object
              properties:
                enabled:
                  type: boolean
                  description: >-
                    Whether or not to enable selecting specific days of the week
                    to receive orders
                from:
                  type: string
                  description: Accepting orders From date value
                  format: date-time
                to:
                  type: string
                  description: Accepting orders To date value
                  format: date-time
              x-apidog-orders:
                - enabled
                - from
                - to
              required:
                - enabled
                - from
                - to
              description: >-
                Allowed values are:

                `saturday`, `sunday`, `monday`, `tuesday`, `wednesday`,
                `thursday`, `friday`
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - dayOfTheWeek
          required:
            - dayOfTheWeek
          title: ''
          description: Receive Order Times Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            status:
              type: string
              description: >-
                Response status code, a numeric or alphanumeric identifier used
                to convey the outcome or status of a request, operation, or
                transaction in various systems and applications, typically
                indicating whether the action was successful, encountered an
                error, or resulted in a specific condition.
            success:
              type: string
              description: >-
                Response flag, boolean indicator used to signal a particular
                condition or state in the response of a system or application,
                often representing the presence or absence of certain conditions
                or outcomes.
            data:
              type: object
              properties:
                id:
                  type: number
                  description: Order Status ID
                name:
                  type: string
                  description: Order Status Name
                selected:
                  type: boolean
                  description: Whether or not the order status is selected
              x-apidog-orders:
                - id
                - name
                - selected
              required:
                - id
                - name
                - selected
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - status
            - success
            - data
          required:
            - status
            - success
            - data
          title: ''
          description: Reports Order Statuses Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            enabled:
              type: boolean
              description: Whether or not to show the products' inventory value
            condition:
              type: object
              properties:
                enabled:
                  type: boolean
                  description: >-
                    Whether or not to show how many times the product was
                    purchased by other customers
                categories:
                  type: array
                  items:
                    type: string
                  description: >-
                    If `enabled` is set to `true`, select categories on which to
                    show how many times the product was purchased by other
                    customers
              x-apidog-orders:
                - enabled
                - categories
              required:
                - enabled
                - categories
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - enabled
            - condition
          required:
            - enabled
            - condition
          title: ''
          description: Products Purchase Count Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            enabled:
              type: boolean
              description: >-
                Whether or not to show products that the customer may like which
                appears as recommendation
            types:
              type: string
              enum:
                - random
                - category
                - brand
                - tag
              x-apidog-enum:
                - value: random
                  name: ''
                  description: ''
                - value: category
                  name: ''
                  description: ''
                - value: brand
                  name: ''
                  description: ''
                - value: tag
                  name: ''
                  description: ''
              description: Show product types based on one of the enum values
          x-apidog-orders:
            - enabled
            - types
          required:
            - enabled
            - types
          title: ''
          description: Products Recommendation Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            enabled:
              type: object
              properties:
                products:
                  type: boolean
                skus:
                  type: boolean
              x-apidog-orders:
                - products
                - skus
              required:
                - products
                - skus
              description: >-
                Whether or not to enable product availability notifications to
                alert customers when an item is back in stock.
              x-apidog-ignore-properties: []
            channels:
              type: object
              properties:
                email:
                  type: boolean
                  description: Whether or not to alert customers via email
                sms:
                  type: boolean
                  description: Whether or not to alert customers via SMS
              x-apidog-orders:
                - email
                - sms
              required:
                - email
                - sms
              x-apidog-ignore-properties: []
            channels_status:
              type: object
              properties:
                email:
                  type: string
                  description: Whether or not the email channel is enabled for alert
                sms:
                  type: string
                  description: Whether or not the sms channel is enabled for alert
                mobile:
                  type: string
                  description: >-
                    Whether or not the mobile phone number channel is enabled
                    for alert
                whatsapp:
                  type: string
                  description: Whether or not the whatsapp channel is enabled for alert
              x-apidog-orders:
                - email
                - sms
                - mobile
                - whatsapp
              required:
                - email
                - sms
                - mobile
                - whatsapp
              x-apidog-ignore-properties: []
            content_title:
              type: string
              description: Alert Message content title
            content_message:
              type: string
              description: Alert Message content value
          x-apidog-orders:
            - enabled
            - channels
            - channels_status
            - content_title
            - content_message
          required:
            - enabled
            - channels
            - channels_status
            - content_title
            - content_message
          title: ''
          description: Products Notification Availability Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            show_out_products:
              type: boolean
              description: 'Whether or not to show products being out of stock '
            manual_quantity:
              type: boolean
            display_product_quantity:
              type: string
              enum:
                - show
                - hide
                - less_than_five
              x-apidog-enum:
                - value: show
                  name: ''
                  description: ''
                - value: hide
                  name: ''
                  description: ''
                - value: less_than_five
                  name: ''
                  description: ''
              description: Show the product current quantity value
          x-apidog-orders:
            - show_out_products
            - manual_quantity
            - display_product_quantity
          required:
            - show_out_products
            - manual_quantity
            - display_product_quantity
          title: ''
          description: Products Inventory Data Schema
          x-apidog-ignore-properties: []
        - type: object
          properties:
            status:
              type: string
              description: >-
                Response status code, a numeric or alphanumeric identifier used
                to convey the outcome or status of a request, operation, or
                transaction in various systems and applications, typically
                indicating whether the action was successful, encountered an
                error, or resulted in a specific condition.
            sucess:
              type: string
              description: >-
                Response flag, boolean indicator used to signal a particular
                condition or state in the response of a system or application,
                often representing the presence or absence of certain conditions
                or outcomes.
            data:
              type: object
              properties:
                show_banner:
                  type: boolean
                  description: Whether or not to show banner
                show_in_menu:
                  type: string
                  description: Whether or not to show product in the menu
                menu_title:
                  type: object
                  properties:
                    en:
                      type: string
                      description: Menu title expressed in English language
                    ar:
                      type: string
                      description: Menu title expressed in Arabic language
                  x-apidog-orders:
                    - en
                    - ar
                  required:
                    - en
                    - ar
                  x-apidog-ignore-properties: []
                menu_order:
                  type: integer
                  description: Number of the menu order
              x-apidog-orders:
                - show_banner
                - show_in_menu
                - menu_title
                - menu_order
              required:
                - show_banner
                - show_in_menu
                - menu_title
                - menu_order
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - status
            - sucess
            - data
          description: Products Brand Options Data Schema
          required:
            - status
            - sucess
            - data
          title: ''
          x-apidog-ignore-properties: []
        - type: object
          properties:
            status:
              type: string
              description: >-
                Response status code, a numeric or alphanumeric identifier used
                to convey the outcome or status of a request, operation, or
                transaction in various systems and applications, typically
                indicating whether the action was successful, encountered an
                error, or resulted in a specific condition.
            sucess:
              type: string
              description: >-
                Response flag, boolean indicator used to signal a particular
                condition or state in the response of a system or application,
                often representing the presence or absence of certain conditions
                or outcomes.
            data:
              type: array
              items:
                type: object
                properties:
                  id:
                    type: integer
                    description: Uniques identifier for a specific product.
                  name:
                    type: string
                    description: Lable or title of the product
                  description:
                    type: string
                    description: A brief explanation of the product.
                  type:
                    type: integer
                    description: Type of the product.
                  enabled:
                    type: boolean
                    description: whether or not the option is enabled.
                  brands:
                    type: integer
                    description: The product brand.
                  categories:
                    type: integer
                    description: The product category.
                  translations:
                    type: object
                    properties:
                      ar:
                        type: string
                        description: Product details in Arabic.
                      name:
                        type: string
                        description: Product name in Arabic.
                      description:
                        type: string
                        description: Product description in Arabic.
                    x-apidog-orders:
                      - ar
                      - name
                      - description
                    required:
                      - ar
                      - name
                      - description
                    description: >-
                      Brand translations are based on the store's enabled
                      language locale. For instance, if the store supports both
                      Arabic and English, the translations object will return
                      two entries: ar for Arabic and en for English.
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - id
                  - name
                  - description
                  - type
                  - enabled
                  - brands
                  - categories
                  - translations
                required:
                  - id
                  - name
                  - description
                  - type
                  - enabled
                  - brands
                  - categories
                  - translations
                x-apidog-ignore-properties: []
          x-apidog-orders:
            - status
            - sucess
            - data
          description: Products Size Guide Data Schema
          required:
            - status
            - sucess
            - data
          title: ''
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

## apis-settings/Settings-List-Salla-Merchant-API-Salla-Docs

# Settings List

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settings:
    get:
      summary: Settings List
      deprecated: false
      description: >-
        This endpoint allows you to fetch the list of the main settings
        associated with the store to enable / disable / show / hide store
        features based on a specific entity


        :::info[Read More]

        For more on Store Settings, check the Merchant's Help Desk article
        [here](https://help.salla.sa/article/1887201789).

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `store-settings.read`- Settings Read Only

        </Accordion>
      operationId: get-settings-entity
      tags:
        - Default module/Merchant API/APIs/Settings
        - Settings
      parameters:
        - name: entity
          in: query
          description: 'Choose which entity to fetch the related settings '
          required: true
          example: orders
          schema:
            type: string
            enum:
              - products
              - orders
              - customers
              - reports
              - blogs
              - mahally
              - feedbacks
              - shipping
              - store
            x-apidog-enum:
              - name: ''
                value: products
                description: ''
              - name: ''
                value: orders
                description: ''
              - name: ''
                value: customers
                description: ''
              - name: ''
                value: reports
                description: ''
              - name: ''
                value: blogs
                description: ''
              - name: ''
                value: mahally
                description: ''
              - name: ''
                value: feedbacks
                description: ''
              - value: shipping
                name: ''
                description: ''
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/settings_response_body'
              examples:
                '1':
                  summary: Success | Orders Entity
                  value:
                    status: 200
                    success: true
                    data:
                      - slug: orders.receive_orders
                        type: form
                        value: null
                      - slug: orders.receiving_times
                        type: form
                        value: null
                      - slug: orders.order_notes
                        type: form
                        value: null
                      - slug: orders.cancel_order
                        type: form
                        value: null
                      - slug: orders.auto_complete
                        type: form
                        value: null
                      - slug: orders.auto_return_stock
                        type: form
                        value: null
                      - slug: orders.disable_bank_transfer_payment_period
                        type: boolean
                        value: false
                      - slug: orders.shipping_indicator
                        type: boolean
                        value: true
                      - slug: orders.price_quote
                        type: boolean
                        value: false
                      - slug: orders.reorder
                        type: boolean
                        value: true
                      - slug: orders.agreement
                        type: form
                        value: null
                      - slug: orders.complete_customization
                        type: form
                        value: null
                      - slug: orders.invoices_customization
                        type: form
                        value: null
                      - slug: orders.shipping_policy_deduction
                        type: form
                        value: null
                      - slug: orders.minimum_amount
                        type: string
                        value: '123.23'
                      - slug: orders.attache_note_notify_status
                        type: boolean
                        value: true
                      - slug: orders.status_notifications
                        type: dropdown
                        value:
                          - email
                      - slug: orders.digital_products_notify
                        type: dropdown
                        value:
                          - email
                          - sms
                '4':
                  summary: Success | Products Entity
                  value:
                    status: 200
                    success: true
                    data:
                      - slug: products.duplicate_product_in_cart
                        type: boolean
                        value: true
                      - slug: products.purchase_count
                        type: form
                        value: null
                      - slug: products.quantity_sort
                        type: boolean
                        value: true
                      - slug: products.more_details_button
                        type: boolean
                        value: true
                      - slug: products.zero_price_indicator
                        type: boolean
                        value: true
                      - slug: products.recommendations
                        type: form
                        value: null
                      - slug: products.show_special_offers
                        type: boolean
                        value: true
                      - slug: products.auto_add_product_offer_to_cart
                        type: boolean
                        value: true
                      - slug: products.show_start_from_price
                        type: boolean
                        value: false
                      - slug: products.digital_protection
                        type: boolean
                        value: false
                      - slug: products.show_weight
                        type: boolean
                        value: true
                      - slug: products.show_sku
                        type: boolean
                        value: false
                      - slug: products.show_hs_code
                        type: boolean
                        value: true
                      - slug: products.product_price_included_tax
                        type: boolean
                        value: true
                      - slug: products.default_weight
                        type: object
                        value:
                          unit: g
                          weight: 125
                      - slug: products.product_notify_availability
                        type: form
                        value: null
                      - slug: products.product_inventory
                        type: form
                        value: null
                      - slug: products.brand_options
                        type: form
                        value: null
                '5':
                  summary: Success| Reports Entity
                  value:
                    status: 200
                    success: true
                    data:
                      - slug: reports.order_statuses
                        type: form
                        value: null
                '6':
                  summary: Success | Empty response
                  value:
                    status: 200
                    success: true
                    data: []
                '7':
                  summary: Success | Marketing Entity
                  value:
                    status: 200
                    success: true
                    data:
                      - slug: marketing.settings.coupon_in_cart
                        type: boolean
                        value: false
                      - slug: marketing.settings.enable_offers_coupons
                        type: boolean
                        value: true
                      - slug: marketing.settings.show_offers
                        type: boolean
                        value: true
                '8':
                  summary: Success | Feedbacks Success
                  value:
                    status: 200
                    success: true
                    data:
                      - slug: feedbacks.publish_testimonials
                        type: boolean
                        value: true
                      - slug: feedbacks.publish_ratings
                        type: boolean
                        value: true
                      - slug: feedbacks.allow_attach_images
                        type: boolean
                        value: false
                      - slug: feedbacks.allow_likes
                        type: boolean
                        value: false
                      - slug: feedbacks.show_rating_summary
                        type: boolean
                        value: false
                      - slug: feedbacks.allow_contact_support
                        type: boolean
                        value: false
                      - slug: feedbacks.testimonials_enabled
                        type: boolean
                        value: false
                      - slug: feedbacks.shipping_enabled
                        type: boolean
                        value: false
                      - slug: feedbacks.products_enabled
                        type: boolean
                        value: false
                      - slug: feedbacks.allow_hidden_names
                        type: boolean
                        value: false
                      - slug: feedbacks.display_testimonials
                        type: boolean
                        value: false
                      - slug: feedbacks.display_customer_reviews
                        type: boolean
                        value: false
                      - slug: feedbacks.display_product_reviews_on_app
                        type: boolean
                        value: false
                      - slug: feedbacks.publish_comments
                        type: boolean
                        value: true
                      - slug: feedbacks.pages_feedback_enabled
                        type: boolean
                        value: true
                      - slug: feedbacks.products_feedback_enabled
                        type: boolean
                        value: true
                      - slug: feedbacks.disable_guest_feedback
                        type: boolean
                        value: true
                      - slug: feedbacks.rating_message
                        type: form
                        value: null
                      - slug: feedbacks.update_rating
                        type: form
                        value: null
                      - slug: feedbacks.thanks_message
                        type: form
                        value: null
                '9':
                  summary: Success | Store
                  value:
                    status: 200
                    success: true
                    data:
                      - slug: store.maintenance
                        type: form
                        value: null
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
                  code: Unauthorized
                  message: >-
                    The access token should have access to one of those scopes:
                    store-settings.read,store-settings.read_write
          headers: {}
          x-apidog-name: error_unauthorized_401
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
                    entity:
                      - حقل entity مطلوب.
          headers: {}
          x-apidog-name: error_validation_422
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Settings
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-6965777-run
components:
  schemas:
    settings_response_body:
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
            $ref: '#/components/schemas/Settings'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Settings:
      type: object
      properties:
        slug:
          type: string
          description: >-
            A unique identifier used to reference a specific setting or
            configuration within a system or application.
        type:
          type: string
          enum:
            - form
            - object
            - string
            - boolean
            - integer
            - dropdown
          description: Settings type enum values
          x-apidog-enum:
            - name: ''
              value: form
              description: >-
                Settings variable is of type form. Find more about Settings from
                [here](https://salla.dev/blog/stand-out-with-theme-settings/)
            - name: ''
              value: object
              description: >-
                Settings variable is of type object. Find more about Settings
                from
                [here](https://salla.dev/blog/stand-out-with-theme-settings/)
            - name: ''
              value: string
              description: >-
                Settings variable is of type string. Find more about Settings
                from
                [here](https://salla.dev/blog/stand-out-with-theme-settings/)
            - name: ''
              value: boolean
              description: >-
                Settings variable is of type boolean. Find more about Settings
                from
                [here](https://salla.dev/blog/stand-out-with-theme-settings/)
            - name: ''
              value: integer
              description: >-
                Settings variable is of type integer. Find more about Settings
                from
                [here](https://salla.dev/blog/stand-out-with-theme-settings/)
            - name: ''
              value: dropdown
              description: >-
                Settings variable is of type dropdown. Find more about Settings
                from
                [here](https://salla.dev/blog/stand-out-with-theme-settings/)
        value:
          type: string
      x-apidog-orders:
        - slug
        - type
        - value
      required:
        - slug
        - type
        - value
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

## apis-settings/Update-Settings-Fields-Salla-Merchant-API-Salla-Docs

# Update Setting Slug

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /settings/fields/{slug}:
    put:
      summary: Update Setting Slug
      deprecated: false
      description: >-
        This endpoint allows you to update a specific Setting slug based on a
        specific entity, where the payload will be changed based on the passed
        body parameter values 


        :::info[Read More]

        For more on Store Settings, check the Merchant's Help Desk article
        [here](https://help.salla.sa/article/1887201789)

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `store-settings.read_write`- Settings Read & Write

        </Accordion>
      operationId: put-settings-slug
      tags:
        - Default module/Merchant API/APIs/Settings
        - Settings
      parameters:
        - name: slug
          in: path
          description: >-
            Unique identifier or URL-friendly name assigned to the Settings .
            Get a list of Settings Slugs from
            [here](https://docs.salla.dev/api-6965777)
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/settings_request_body'
            example:
              value: true
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
                  message: The record has been updated successfully
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
          headers: {}
          x-apidog-name: error_notFound_404
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Settings
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-6965780-run
components:
  schemas:
    settings_request_body:
      type: object
      properties:
        value:
          anyOf:
            - type: boolean
              description: >-
                Send the `boolean` variable if the entity value `type` is set to
                `boolean`
            - type: string
              description: >-
                Send the `string` variable if the entity value `type` is set to
                `string`
            - type: array
              description: >-
                Send the `array` variable if the entity value `type` is set to
                `dropdown`
              items:
                type: string
          description: >-
            Required if entity type value is either: boolean, string, or
            dropdown
      x-apidog-orders:
        - value
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

