# Apis Orders  Duplicate Order Salla Merchant Api Salla Docs

## Table of Contents

- [apis-orders/Duplicate-Order-Salla-Merchant-API-Salla-Docs](#apis-orders-duplicate-order-salla-merchant-api-salla-docs)

---

## apis-orders/Duplicate-Order-Salla-Merchant-API-Salla-Docs

# Duplicate Order

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /orders/duplicate:
    post:
      summary: Duplicate Order
      deprecated: false
      description: >-
        This endpoint allows you to duplicate the details of a specific order


        :::danger[Deprecation Notice]

        The variables, `items.codes` and `items.files`, are deprecated. We
        recommend using instead the `data.urls.digital_content` variable.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `orders.read_write` - Orders Read & Write

        </Accordion>
      operationId: post-orders-duplicate
      tags:
        - Default module/Merchant API/APIs/Orders
        - Orders
      parameters: []
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                order_id:
                  type: integer
                  description: >-
                    Order ID. List of Order ID can be found
                    [here](https://docs.salla.dev/api-5394146)
                  examples:
                    - 1773697839
              x-apidog-orders:
                - order_id
              required:
                - order_id
              x-apidog-ignore-properties: []
            example:
              order_id: 212342
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/order_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 1773697839
                  cart_reference_id: null
                  reference_id: 140
                  urls:
                    customer: >-
                      https://store.test/ar/theoriginalstore/order/Bl4xzL8g3nAq5paqQ8aRVY0D7oJZ2ebN
                    admin: /orders/order/Bl4xzL8g3nAq5paqQ8aRVY0D7oJZ2ebN
                  date:
                    date: '2024-05-08 11:05:59.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  updated_at:
                    date: '2024-05-08 11:05:59.481304'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  source: dashboard
                  draft: true
                  read: true
                  source_device: desktop
                  source_details:
                    type: dashboard
                    value: null
                    device: desktop
                    user-agent: HTTPie
                    ip: null
                  status: []
                  is_price_quote: false
                  payment_method: null
                  receipt_image: null
                  currency: SAR
                  amounts:
                    sub_total:
                      amount: 0
                      currency: SAR
                    shipping_cost:
                      amount: 0
                      currency: SAR
                    cash_on_delivery:
                      amount: 0
                      currency: SAR
                    tax:
                      percent: '0.00'
                      amount:
                        amount: 0
                        currency: SAR
                    discounts: []
                    total:
                      amount: 0
                      currency: SAR
                  can_cancel: false
                  show_weight: false
                  can_reorder: false
                  is_pending_payment: true
                  pending_payment_ends_at: 283766
                  total_weight: null
                  rating_link: null
                  shipping: null
                  shipments: null
                  checkout_url: https://store.test/ar/theoriginalstore/order_complete/LvZZ
                  pending_payment_start_at:
                    date: '2024-05-08 17:55:26.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  shipment_branch: []
                  customer:
                    id: 2079537577
                    first_name: اويس
                    last_name: الشيخ
                    mobile: 544519727
                    mobile_code: '+966'
                    email: owieselshaikh@gmail.com
                    urls:
                      customer: https://store.test/ar/theoriginalstore/profile
                      admin: /customers/AkKqLmyR78Zjn9WxZ132pGevzVB0QOox
                    avatar: >-
                      https://s3-us-west-1.amazonaws.com/salla/Hf3zWgOwlxd9H8KEKY3beI34HiUuzLFvfFkObBUI.jpeg
                    gender: male
                    birthday:
                      date: '1984-05-19 00:00:00.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    city: مكة
                    country: السعودية
                    country_code: SA
                    currency: SAR
                    location: Near the skies
                    updated_at:
                      date: '2024-05-05 17:50:13.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    groups: []
                  items: []
                  bank: null
                  tags: []
                  store:
                    id: 1764372897
                    store_id: 1764372897
                    user_id: 525144736
                    user_email: owieselshikh@gmail.com
                    username: theoriginalstore
                    name:
                      ar: متجر الاصلي
                      en: null
                    avatar: >-
                      https://s3-eu-central-1.amazonaws.com/salla-cdn/Q5fH1B1EoWCVwX0KFxvLPuiG8yUomtnjr3yem358.
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
                    orders.read_write
          headers: {}
          x-apidog-name: Unauthorised
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
                  code: 422
                  message: عفوا لا يمكنك تكرار طلب تبرع سريع
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Merchant API/APIs/Orders
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-7102947-run
components:
  schemas:
    order_response_body:
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
          $ref: '#/components/schemas/Order'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Order:
      description: >-
        Detailed structure of the Order model object showing its fields and data
        types.
      type: object
      title: Order
      x-tags:
        - Models
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            A unique alphanumeric code or identifier assigned to a specific
            order. List of orders can be found
            [here](https://docs.salla.dev/api-5394146)
        cart_reference_id:
          type: number
          description: >-
            A unique alphanumeric code or identifier assigned to a specific
            order cart.
        reference_id:
          type: number
          description: A specific alphanumeric identifier associated with an order.
        urls:
          description: Customer and Admin urls.
          type: object
          x-apidog-refs:
            01JT5ZFPGW0SRW63GYSGWR0WDN: &ref_1
              $ref: '#/components/schemas/URLs'
              x-apidog-overrides: {}
          x-apidog-orders:
            - 01JT5ZFPGW0SRW63GYSGWR0WDN
          properties:
            customer: &ref_2
              type: string
              description: Customer link directly to the order.
              examples:
                - https://salla.sa/StoreLink
            admin: &ref_3
              type: string
              description: Admin dashboard link directly to the order.
              examples:
                - https://s.salla./YourStoreDashboard
            digital_content: &ref_4
              type: string
              description: >-
                A direct URL link to the digital asset, such as an e-book,
                image, PDF, video, or any downloadable file linked to the order
                or product.
            rating: &ref_5
              type: string
              description: >-
                Order Rating Link. <br> Note that the order has to be of either
                of the following statuses: `completed`, `delivered`, or
                `shipped`. The merchant has to allow the product to be rated
                from the [Store Settings](https://s.salla.sa/settings) > Rating
                Settings
            checkout: &ref_6
              type: string
              description: >-
                Order Checkout URL. <br>Note that the variable will only be
                returned if the order is unpaid. If the order is already paid,
                the variable will not appear in the response.
          required:
            - customer
            - admin
            - digital_content
          x-apidog-ignore-properties:
            - customer
            - admin
            - digital_content
            - rating
            - checkout
        date: &ref_0
          $ref: '#/components/schemas/Date'
          description: Date and time of the order.
        updated_at: *ref_0
        source:
          type: string
          description: The source of the order.
          enum:
            - store
            - landing
            - forgotten_basket
            - abandoned-cart
            - campaign
            - dashboard
            - buy_as_gift
            - mahly-app
            - buy_now
            - one-click
            - complete_order
          x-apidog-enum:
            - value: store
              name: ''
              description: The online store where customers browse and purchase products.
            - value: landing
              name: ''
              description: >-
                The first page a user sees, designed to guide them toward a
                specific action, like a purchase or signup.
            - value: forgotten_basket
              name: ''
              description: >-
                When a customer adds items to their cart but doesn't complete
                the purchase, often prompting a reminder.
            - value: abandoned-cart
              name: ''
              description: >-
                When customers leave items in their cart without buying,
                triggering reminders to encourage checkout.
            - value: campaign
              name: ''
              description: >-
                A marketing effort, such as ads or promotions, aimed at driving
                sales or engagement.
            - value: dashboard
              name: ''
              description: >-
                A central control panel where users can manage settings, view
                stats, and track activities.
            - value: buy_as_gift
              name: ''
              description: >-
                An option to purchase an item and send it as a gift to someone
                else.
            - value: mahly-app
              name: ''
              description: >-
                A reference to the Mahly app, a platform for browsing and
                purchasing products.
            - value: buy_now
              name: ''
              description: >-
                A quick purchase option that lets customers buy products
                instantly with minimal steps.
            - value: one-click
              name: ''
              description: >-
                A streamlined purchase process that allows customers to buy with
                just a single click.
            - value: complete_order
              name: ''
              description: >-
                The final step in the checkout process where the customer
                confirms and places their order.
        draft:
          type: boolean
          description: Whether or not  the order 's status is set to `draft`
        read:
          type: boolean
          description: 'Whether or not the Merchant has read the order '
        source_device:
          type: string
          description: The machine or device used when the customer placed the order.
        source_details:
          type: object
          properties:
            type:
              type: string
              description: Order Source Type
            value:
              type: string
              description: Order Source Value
              nullable: true
            device:
              type: string
              description: >-
                The electronic device, such as a computer, smartphone, or
                tablet, through which an order or purchase is initiated or
                processed.
            user-agent:
              type: string
              description: >-
                a piece of information sent by a web browser or other client
                software, that provides details about the user's browser,
                device, and operating system when an order or action is
                initiated.
            ip:
              type: string
              description: >-
                The Internet Protocol (IP) address associated with the device or
                network location from which an order or transaction request
                originates, providing information about the geographical or
                network source of the order.
          x-apidog-orders:
            - type
            - value
            - device
            - user-agent
            - ip
          description: Order source details.
          x-apidog-ignore-properties: []
        status:
          $ref: '#/components/schemas/NewOrderStatus'
          description: Order status.
        is_price_quote:
          type: boolean
          description: Whether or not to quote order price.
        payment_method:
          type: string
          description: >-
            The specific payment option chosen by a customer to pay for a
            product or service as part of an order.
        receipt_image:
          type: string
          description: Order's image receipt.
        currency:
          type: string
          description: >-
            The currency in which order costs and prices are expressed and
            processed.
        amounts:
          type: object
          properties:
            sub_total:
              type: object
              properties:
                amount:
                  type: integer
                  description: Order sub total amount
                currency:
                  type: string
                  description: Order sub total currency
              x-apidog-orders:
                - amount
                - currency
              description: Order subtotal.
              x-apidog-ignore-properties: []
            shipping_cost:
              type: object
              properties:
                amount:
                  type: integer
                  description: Order shipping cost amount
                currency:
                  type: string
                  description: Order shipping cost amount
              x-apidog-orders:
                - amount
                - currency
              description: Order shipping cost.
              x-apidog-ignore-properties: []
            cash_on_delivery:
              type: object
              properties:
                amount:
                  type: integer
                  description: Order cash on delivery cost amount
                currency:
                  type: string
                  description: Order cash on delivery cost curreny
              x-apidog-orders:
                - amount
                - currency
              description: 'Order cash on delivery price. '
              x-apidog-ignore-properties: []
            tax:
              type: object
              properties:
                percent:
                  type: string
                  description: Tax percentage value
                amount:
                  type: object
                  properties:
                    amount:
                      type: integer
                      description: Order tax amount
                    currency:
                      type: string
                      description: Order tax amount currency
                  x-apidog-orders:
                    - amount
                    - currency
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - percent
                - amount
              description: Order tax.
              x-apidog-ignore-properties: []
            discounts:
              type: array
              items:
                type: object
                properties:
                  title:
                    type: string
                    description: >-
                      The name or label given to a specific discount or
                      promotional offer applied to an order, helping to identify
                      and describe the type of discount or deal being applied to
                      the order's total cost.
                  type:
                    type: string
                    description: >-
                      The category or classification of the discount or
                      promotional offer applied to an order, indicating the
                      nature or mechanism of the discount, such as
                      percentage-based, fixed amount, free shipping, buy one get
                      one free, or any other specific type of discount.
                  code:
                    type: string
                    description: >-
                      A unique alphanumeric sequence or code that can be u
                      during the checkout process to apply a specific discount.
                  discount:
                    type: string
                    description: >-
                      The numerical amount or percentage by which the total cost
                      of an order is reduced as a result of a discount or
                      promotional offer, representing the savings or reduction
                      in price that the customer receives.
                  discounted_shipping:
                    type: integer
                    description: >-
                      A reduction in the cost of shipping services associated
                      with an order, typically provided as part of a promotional
                      offer or incentive, resulting in a lower shipping fee.
                x-apidog-orders:
                  - title
                  - type
                  - code
                  - discount
                  - discounted_shipping
                x-apidog-ignore-properties: []
              description: Order discount.
            total:
              type: object
              properties:
                amount:
                  type: integer
                  description: >-
                    The final sum that is required to be paid for the order,
                    including the prices of all items or services ordered, any
                    applicable taxes, fees, and shipping costs, as well as any
                    discounts or promotional savings that have been applied.
                currency:
                  type: string
                  description: >-
                    he specific currency in which the total cost of an order is
                    expressed, representing the monetary unit used for
                    calculating and displaying the final amount required to be
                    paid for the order.
              x-apidog-orders:
                - amount
                - currency
              description: Order total.
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - sub_total
            - shipping_cost
            - cash_on_delivery
            - tax
            - discounts
            - total
          description: Order amounts.
          x-apidog-ignore-properties: []
        exchange_rate:
          type: object
          properties:
            base_currency:
              type: string
              description: The default currency for the store
              examples:
                - SAR
            exchange_currency:
              type: string
              description: Order Exchange Currency
              examples:
                - USD
            rate:
              type: integer
              description: >-
                The rate which the base currency got converted when placing the
                order
              examples:
                - 3.75
          x-apidog-orders:
            - base_currency
            - exchange_currency
            - rate
          description: The order exchange rate.
          x-apidog-ignore-properties: []
        can_cancel:
          type: boolean
          description: >-
            The option to enable order cancellation by the store customer.<br>

            `True` value should be set if the order status is in under review
            and in progress, as according to the store settings.
        show_weight:
          type: boolean
          description: Whether or not to show the weight value.
        can_reorder:
          type: boolean
          description: Whether or not to enable reorder .
        is_pending_payment:
          type: boolean
          description: >-
            The option of displaying order is pending payment to the customer
            when the order status is `payment_pending`.
        rating_link:
          type: string
          description: >-
            The rating URL to review the order.


            🛑 The variable is to be deprecated; use `data.urls.rating` variable
            instead.
          deprecated: true
        checkout_url:
          type: string
          description: >-
            The checkout URL to settle payments related to the order


            🛑 The variable is to be deprecated; use `data.urls.checkout`
            variable instead.
          deprecated: true
        pending_payment_ends_at:
          type: integer
          description: Last date allowed to customer to pay the order.
        total_weight:
          type: string
          description: Total weight value
        shipping:
          type: object
          properties:
            id:
              type: number
              description: >-
                A unique identifier, typically numerical or alphanumeric,
                assigned to a specific shipping or delivery process associated
                with an order within a system or database, facilitating tracking
                and management of the shipping details and status related to
                that order.
            app_id:
              type: number
              description: >-
                A unique identifier, typically numerical or alphanumeric,
                associated with a specific shipping application used to manage
                and track the shipping and delivery of orders.
              nullable: true
            shipping_details_id:
              type: string
              description: >-
                Shipping Estimate Rate ID. Get a list of estimate rate IDs from
                [here](https://docs.salla.dev/api-6899590)
            company:
              type: string
              description: >-
                The company or service provider responsible for the
                transportation and delivery of an order from the seller or
                sender to the recipient or customer.
            logo:
              type: string
              description: >-
                A text or string variable that stores the name or path to the
                image file of a shipping company's logo.
            receiver:
              type: object
              properties:
                name:
                  type: string
                  description: >-
                    The name of the customer designated to receive and take
                    possession of the goods or services specified in an order.
                email:
                  type: string
                  description: >-
                    he email address associated with the customer designated as
                    the recipient of an order, often used for communication,
                    notifications, and confirmation related to the order,
                    including shipping updates and order-related information.
                phone:
                  type: string
                  description: >-
                    The telephone number associated with the customer designated
                    as the recipient of an order, commonly used for
                    communication, coordination, and contact purposes,
                    particularly in the context of order delivery or customer
                    service inquiries.
              x-apidog-orders:
                - name
                - email
                - phone
              description: Order receiver details.
              x-apidog-ignore-properties: []
            shipper:
              type: object
              properties:
                name:
                  type: string
                  description: ' the name of the individual, business, or entity responsible for shipping and sending out an order, typically used for identifying the sender or shipper of the goods or services specified in the order.'
                company_name:
                  type: string
                  description: >-
                    The name of the company or business entity responsible for
                    shipping and sending out an order.
                email:
                  type: string
                  description: >-
                    The email address associated with the individual or entity
                    responsible for shipping and sending out an order, often
                    used for communication and contact purposes related to the
                    shipping and fulfillment of the order.
                phone:
                  type: string
                  description: >-
                    The telephone number associated with the individual or
                    entity responsible for shipping and sending out an order,
                    typically used for communication, coordination, and contact
                    purposes, particularly in matters related to the shipment
                    and fulfillment of the order.
              x-apidog-orders:
                - name
                - company_name
                - email
                - phone
              description: Order shipper details.
              x-apidog-ignore-properties: []
            pickup_address:
              type: object
              properties:
                country:
                  type: string
                  description: >-
                    The specific country in which the location or address for
                    picking up an order is situated.
                country_code:
                  type: string
                  description: >-
                    A standardized code or abbreviation that represents the
                    specific country where the location or address for picking
                    up an order is situated.
                city:
                  type: string
                  description: >-
                    The name of the city or urban area where the location or
                    address for picking up an order is situated.
                shipping_address:
                  type: string
                  description: >-
                    The location or address where the order is to be delivered
                    or shipped to in order to be picked up.
                street_number:
                  type: string
                  description: >-
                    The specific numerical identifier associated with a building
                    or location on a street where a customer intends to pick up
                    an order.
                block:
                  type: string
                  description: >-
                    The particular block or section on a street where a customer
                    intends to pick up their order.
                postal_code:
                  type: string
                  description: >-
                    The postal code associated with the location where a
                    customer plans to pick up their order, aiding in precise
                    order retrieval.
                geo_coordinates:
                  type: object
                  properties:
                    lat:
                      type: number
                      description: 'Pick Up address GEO coordinates latitude '
                    lng:
                      type: number
                      description: Pick Up address GEO coordinates longitude
                  x-apidog-orders:
                    - lat
                    - lng
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - country
                - country_code
                - city
                - shipping_address
                - street_number
                - block
                - postal_code
                - geo_coordinates
              description: Order pickup address details.
              x-apidog-ignore-properties: []
            address:
              type: object
              properties:
                country:
                  type: string
                  description: >-
                    The country specified in the address where an order is to be
                    shipped, providing the destination for the order's delivery.
                country_code:
                  type: string
                  description: >-
                    The code for the destination country in an order's shipping
                    address, often following ISO standards (e.g., "US" for the
                    United States).
                city:
                  type: string
                  description: >-
                    The name of the city or urban area specified in the address
                    where an order is to be shipped, identifying the destination
                    city for the order's delivery.
                shipping_address:
                  type: string
                  description: >-
                    The complete address provided for the delivery of an order,
                    typically including details such as street name, house or
                    building number, city or locality, postal or ZIP code, and
                    country, ensuring accurate shipment to the intended
                    destination.
                street_number:
                  type: string
                  description: >-
                    The specific numerical identifier associated with a building
                    or location on a street in the address provided for the
                    delivery of an order.
                block:
                  type: string
                  description: ' specific section or segment of a street or road mentioned in the address for the delivery of an order.'
                postal_code:
                  type: string
                  description: >-
                    The numeric or alphanumeric code included in the address for
                    the delivery of an order, representing a specific geographic
                    area within a country or region.
                geo_coordinates:
                  type: object
                  properties:
                    lat:
                      type: integer
                      description: 'Address GEO latitude '
                    lng:
                      type: integer
                      description: Address GEO longitude
                  x-apidog-orders:
                    - lat
                    - lng
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - country
                - country_code
                - city
                - shipping_address
                - street_number
                - block
                - postal_code
                - geo_coordinates
              description: Order address details.
              x-apidog-ignore-properties: []
            shipment:
              type: object
              properties:
                id:
                  type: number
                  description: >-
                    A unique identifier, typically numerical or alphanumeric,
                    assigned to a specific shipment or parcel associated with
                    the order.
                pickup_id:
                  type: integer
                  description: >-
                    A unique identifier for the pickup or collection of a
                    shipment related to an order, aiding in tracking and
                    management.
                tracking_link:
                  type: string
                  description: >-
                    A URL provided to customers for real-time order status
                    updates.
                label:
                  type: array
                  items:
                    type: object
                    properties:
                      format:
                        type: string
                        description: >-
                          The layout of information on a shipment label, aiding
                          in proper identification during shipping.
                      url:
                        type: string
                        description: A textual context to represent the shipment URL.
                    x-apidog-orders:
                      - format
                      - url
                    x-apidog-ignore-properties: []
              x-apidog-orders:
                - id
                - pickup_id
                - tracking_link
                - label
              description: Order shipment details.
              x-apidog-ignore-properties: []
            policy_options:
              type: array
              items:
                type: object
                properties:
                  boxes:
                    type: string
                    description: ' the quantity or count of individual boxes or packages associated with a shipment when creating an Air Waybill (AWB)'
                x-apidog-orders:
                  - boxes
                x-apidog-ignore-properties: []
              description: Order policy options.
          x-apidog-orders:
            - id
            - app_id
            - shipping_details_id
            - company
            - logo
            - receiver
            - shipper
            - pickup_address
            - address
            - shipment
            - policy_options
          description: Order Shipping details.
          deprecated: true
          x-apidog-ignore-properties: []
        shipments:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier, typically numerical or alphanumeric,
                  assigned to individual shipments.
                examples:
                  - '5396365553'
              created_at:
                type: string
                description: >-
                  Timestamp indicating time and date of creating the order
                  shipment.
                nullable: true
              type:
                type: string
                description: >-
                  Calssification of the characteristics and handling
                  requirements of a shipment.
                examples:
                  - shipment
              courier_id:
                type: number
                description: A unique code for a courier or delivery service provider
                examples:
                  - 665151403
              courier_name:
                type: string
                description: >-
                  The title or label that identifies a specific courier or
                  delivery service provider.
                examples:
                  - أي مكان
              courier_logo:
                type: string
                description: >-
                  A textual representation, often in the form of a file path or
                  URL, that specifies the location or reference to the image
                  file containing the logo of a courier or delivery service
                  provider.
                examples:
                  - https://logo.com/shipping/aymakan.png
              shipping_number:
                type: string
                description: >-
                  A reference or identification number associated with a
                  specific shipment, typically used for tracking and monitoring
                  the status and progress of the shipment during the
                  transportation and delivery process.
                examples:
                  - '0'
              tracking_number:
                type: string
                description: >-
                  A unique identifier assigned to a shipment, allowing customers
                  and logistics personnel to track and monitor its status and
                  location during transit.
                examples:
                  - '0'
              pickup_id:
                type: integer
                description: >-
                  A unique identifier, typically numerical or alphanumeric,
                  assigned to a specific pickup request or arrangement related
                  to shipments, helping to track and manage the pickup details
                  for various shipments.
                nullable: true
              trackable:
                type: boolean
                default: true
                description: The option to indicate that the shipment is trackable.
              tracking_link:
                type: string
                description: >-
                  A  web link provided to track the status and location of a
                  shipment in real-time.
                examples:
                  - https://aymakan.com.sa/ar/tracking/0
              label:
                type: object
                properties:
                  format:
                    type: string
                    description: >-
                      The layout and structure used to display information on a
                      label affixed to a shipment.
                  url:
                    type: string
                    description: >-
                      A web link that provides access to a digital shipment
                      label for tracking and identification during shipping.
                x-apidog-orders:
                  - format
                  - url
                x-apidog-ignore-properties: []
              payment_method:
                type: string
                description: The way a customer chooses to pay for a product or service.
                examples:
                  - cod
              source:
                type: string
                description: >-
                  The origin or source of a shipment, providing information
                  about where the shipment was initiated or generated.
              total:
                type: object
                properties:
                  amount:
                    type: string
                    description: Total Amount Value
                  currency:
                    type: string
                    description: Total Amount Currency
                x-apidog-orders:
                  - amount
                  - currency
                x-apidog-ignore-properties: []
              cash_on_delivery:
                type: object
                properties:
                  amount:
                    type: string
                    description: Cash On Delivery Amount Value
                  currency:
                    type: string
                    description: Cash On Delivery Amount Currency
                x-apidog-orders:
                  - amount
                  - currency
                x-apidog-ignore-properties: []
              ship_to:
                type: object
                properties:
                  type:
                    type: string
                    description: >-
                      The classification or categorization of the destination or
                      recipient for a shipment, often used to differentiate
                      between various delivery addresses or locations.
                    examples:
                      - address
                  name:
                    type: string
                    description: >-
                      The name of the individual or entity to whom a shipment
                      has been sent or delivered. It identifies the recipient or
                      destination for the shipped items.
                    examples:
                      - Username
                  email:
                    type: string
                    description: >-
                      The email address associated with the individual or entity
                      to whom a shipment has been sent or delivered.
                    examples:
                      - username@gmail.com
                  phone:
                    type: string
                    description: >-
                      The phone number associated with the individual or entity
                      to whom a shipment has been sent or delivered.
                    examples:
                      - '96652318526'
                  country:
                    type: string
                    description: >-
                      The country associated with the individual or entity to
                      whom a shipment has been sent or delivered.
                    examples:
                      - SA
                  country_id:
                    type: number
                    description: A unique idnetifier for the country for the country
                  country_code:
                    type: string
                    description: >-
                      A code that represents the specific destination country to
                      which a shipment has been sent or is being delivered.
                    examples:
                      - SA
                  city:
                    type: string
                    description: >-
                      The city associated with the individual or entity to whom
                      a shipment has been sent or delivered.
                    examples:
                      - جدة
                  city_id:
                    type: number
                    description: A unique idnetifier for the country for the city
                  address_line:
                    type: string
                    description: >-
                      A specific part of an address that typically contains a
                      portion of the location details, such as the street name,
                      house or building number, apartment or suite number, and
                      any other relevant information necessary for proper
                      identification and delivery of mail or shipments.
                    examples:
                      - >-
                        شارع Makkah, Makkah، الحي NEW YORK 11434،, Makkah,
                        Makkah,, جدة, السعودية
                  street_number:
                    type: string
                    description: >-
                      The specific numerical identifier associated with the
                      street or road address to which a shipment has been sent. 
                    examples:
                      - Makkah, Makkah
                  block:
                    type: string
                    description: >-
                      A specific section or segment of a street or road
                      mentioned in the address where a shipment is being
                      delivered.
                    examples:
                      - NEW YORK
                  postal_code:
                    type: string
                    description: >-
                      The code in a shipment address used for accurate location
                      sorting.
                    examples:
                      - '11414'
                  latitude:
                    type: number
                    description: Shipped To Latitude Geocoordiantes
                    examples:
                      - 40.6413111
                  longitude:
                    type: number
                    description: Shipped To Longitude Geocoordiantes
                    examples:
                      - -73.7781391
                x-apidog-orders:
                  - type
                  - name
                  - email
                  - phone
                  - country
                  - country_id
                  - country_code
                  - city
                  - city_id
                  - address_line
                  - street_number
                  - block
                  - postal_code
                  - latitude
                  - longitude
                x-apidog-ignore-properties: []
              ship_from:
                type: object
                properties:
                  type:
                    type: string
                    description: >-
                      The name of the branch or location from which a shipment
                      originates or is sent. It specifies the point of origin
                      for the shipment.
                    examples:
                      - branch
                  name:
                    type: string
                    description: >-
                      The name of the individual or entity that is sending or
                      originating the shipment, indicating the sender's identity
                      or organization.
                    examples:
                      - المستودع الرئيسي
                  company_name:
                    type: string
                    description: >-
                      The name of the company or business entity that is sending
                      or originating the shipment, identifying the organization
                      responsible for sending the items.
                    examples:
                      - Routine
                  email:
                    type: string
                    description: >-
                      The email address associated with the individual or entity
                      that is sending or originating the shipment, often used
                      for communication and contact purposes related to the
                      shipment's origin.
                    examples:
                      - companyuser@gmail.com
                  phone:
                    type: string
                    description: >-
                      The telephone number associated with the individual,
                      company, or entity that is sending or originating a
                      shipment. This phone number is often used for contact,
                      communication, or inquiries related to the shipment's
                      origin or pickup.
                    examples:
                      - '96652318526'
                  country:
                    type: string
                    description: >-
                      The country from which a shipment originates or is sent.
                      It identifies the location or country of the sender or the
                      point of origin for the shipment.
                    examples:
                      - السعودية
                  country_id:
                    type: string
                    description: A unique idnetifier for the country
                    examples:
                      - '48587334'
                  country_code:
                    type: string
                    description: >-
                      A code that represents the specific destination country to
                      which a shipment has been sent or is being delivered.
                    examples:
                      - SA
                  city:
                    type: string
                    description: >-
                      The city from which a shipment is sent. It identifies the
                      city of the sender or the point of origin for the
                      shipment.
                    examples:
                      - Riyadh
                  city_id:
                    type: number
                    description: A unique idnetifier for the country for the city
                    examples:
                      - 92384793
                  address_line:
                    type: string
                    description: >-
                      A part of the shipment's origin address that typically
                      contains details such as the sender's street name, house
                      or building number, apartment or suite number, and any
                      other relevant information.
                    examples:
                      - >-
                        3481,السلي,62465, 3481، السلي، الرياض 14322 7487،
                        السعودية, Riyadh,السعودية
                  street_number:
                    type: string
                    description: >-
                      The specific numerical identifier associated with the
                      street or road address from which a shipment has been
                      sent. 
                    examples:
                      - '3481'
                  block:
                    type: string
                    description: >-
                      A specific section or segment of a street or road
                      mentioned in the address where a shipment is being sent
                      from.
                    examples:
                      - السلي
                  postal_code:
                    type: string
                    description: >-
                      The code in a shipment address used for accurate location
                      sorting.
                    examples:
                      - '62'
                  latitude:
                    type: number
                    description: Shipped from latitude geocoordiantes
                    examples:
                      - 18.2952212
                  longitude:
                    type: number
                    description: Shipped from longitude geocoordiantes.
                    examples:
                      - 42.755331
                  branch_id:
                    type: integer
                    description: >-
                      A unique identifier, often numerical or alphanumeric,
                      associated with the specific branch or location where a
                      shipment originates or is dispatched. 
                    examples:
                      - 1790435930
                x-apidog-orders:
                  - type
                  - name
                  - company_name
                  - email
                  - phone
                  - country
                  - country_id
                  - country_code
                  - city
                  - city_id
                  - address_line
                  - street_number
                  - block
                  - postal_code
                  - latitude
                  - longitude
                  - branch_id
                x-apidog-ignore-properties: []
              total_weight:
                type: object
                properties:
                  value:
                    type: number
                    description: Total weight value
                    examples:
                      - 8.052
                  units:
                    type: string
                    description: >-
                      The units of measurement used to express the total weight
                      of a shipment. This could be in kilograms (kg), pounds
                      (lb), grams (g), or any other weight measurement unit.
                    examples:
                      - kg
                x-apidog-orders:
                  - value
                  - units
                x-apidog-ignore-properties: []
              packages:
                type: array
                items:
                  type: object
                  properties:
                    item_id:
                      type: integer
                      description: Package Item ID
                      examples:
                        - 2077288690
                    external_id:
                      type: integer
                      description: Package External ID
                      examples:
                        - 909112677
                      nullable: true
                    name:
                      type: string
                      description: Shipment Packages Name
                      examples:
                        - Package 1
                    sku:
                      type: string
                      description: Shipment Packages SKU
                      examples:
                        - SKU-123-456
                    price:
                      type: object
                      properties:
                        amount:
                          type: number
                          description: Shipment Packages Price Amount
                          examples:
                            - 200
                        currency:
                          type: string
                          description: >-
                            Shipment Packages Price Currency. You may refer to
                            the external Merchant API Docs for the List of
                            Currencies from [here](api-5394257/?nav=1)
                          examples:
                            - sar
                      x-apidog-orders:
                        - amount
                        - currency
                      x-apidog-ignore-properties: []
                    quantity:
                      type: integer
                      description: Shipment Packages Quantity
                      examples:
                        - 2
                    weight:
                      type: object
                      properties:
                        value:
                          type: integer
                          description: 'Shipment Packages Weight '
                          examples:
                            - 2
                        units:
                          type: string
                          enum:
                            - kg
                            - g
                            - lb
                            - oz
                          description: Shipment Packages Weight Unit
                          x-stoplight:
                            id: q3n10oje63ua9
                          examples:
                            - kg
                      x-apidog-orders:
                        - value
                        - units
                      x-apidog-ignore-properties: []
                    options:
                      type: array
                      items:
                        type: object
                        properties:
                          name:
                            type: string
                            description: >-
                              A label for a product variation or choice, like
                              size or color.
                          values:
                            type: array
                            items:
                              type: object
                              properties:
                                name:
                                  type: string
                                  description: >-
                                    The descriptive label or text representing a
                                    specific choice or value within a product
                                    option.
                                price:
                                  type: object
                                  properties:
                                    amount:
                                      type: string
                                      description: Option value amount.
                                    currency:
                                      type: string
                                      description: Option value currency.
                                  x-apidog-orders:
                                    - amount
                                    - currency
                                  required:
                                    - amount
                                    - currency
                                  x-apidog-ignore-properties: []
                                value:
                                  type: string
                                  description: The value of the option
                              x-apidog-orders:
                                - name
                                - price
                                - value
                              required:
                                - name
                                - price
                                - value
                              x-apidog-ignore-properties: []
                            description: >-
                              If `type` value is set to `radio` or `checkbox`,
                              the returned response is an array. Otherwise, an
                              object is returned in all other available `type`
                              values.
                        x-apidog-orders:
                          - name
                          - values
                        required:
                          - name
                          - values
                        x-apidog-ignore-properties: []
                  x-apidog-orders:
                    - item_id
                    - external_id
                    - name
                    - sku
                    - price
                    - quantity
                    - weight
                    - options
                  x-apidog-ignore-properties: []
                description: Shipment packages details.
              is_international:
                type: boolean
                default: false
                description: The option to indicate if the shipment is internationa
              meta:
                type: object
                properties:
                  app_id:
                    type: string
                    description: >-
                      A unique code or label used to identify and distinguish a
                      specific App.
                    examples:
                      - '944213936'
                  policy_options:
                    type: object
                    properties:
                      boxes:
                        type: string
                        description: Policy Options Boxes
                        examples:
                          - '1'
                      dimensions:
                        type: object
                        properties:
                          length:
                            type: string
                            examples:
                              - '2'
                          width:
                            type: string
                            examples:
                              - '1'
                          height:
                            type: string
                            examples:
                              - '1'
                        x-apidog-orders:
                          - length
                          - width
                          - height
                        description: Box dimensions
                        x-apidog-ignore-properties: []
                    x-apidog-orders:
                      - boxes
                      - dimensions
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - app_id
                  - policy_options
                x-apidog-ignore-properties: []
            x-apidog-orders:
              - id
              - created_at
              - type
              - courier_id
              - courier_name
              - courier_logo
              - shipping_number
              - tracking_number
              - pickup_id
              - trackable
              - tracking_link
              - label
              - payment_method
              - source
              - total
              - cash_on_delivery
              - ship_to
              - ship_from
              - total_weight
              - packages
              - is_international
              - meta
            x-apidog-ignore-properties: []
          description: Order shipment details.
          deprecated: true
        pickup_branch:
          description: Order pickup branch details.
          $ref: '#/components/schemas/Branch'
          deprecated: true
        shipment_branch:
          description: Order shipment branch details.
          $ref: '#/components/schemas/ShipmentBranch'
          deprecated: true
        customer:
          $ref: '#/components/schemas/Customer'
          description: Customer details.
        items:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier, typically numerical or alphanumeric,
                  assigned to an individual item or product within an order.
              name:
                type: string
                description: >-
                  he name or description of an individual item or product within
                  an order.
              sku:
                type: string
                description: >-
                  Stock Keeping Unit, and it is a unique code or identifier used
                  to track and manage individual products or items in inventory,
                  facilitating inventory management, sales tracking, and product
                  identification.
              quantity:
                type: integer
                description: >-
                  The numerical count of a specific item or product included in
                  an order, indicating how many of that particular item have
                  been purchased or are part of the order.
              currency:
                type: string
                description: >-
                  The specific currency in which the price or value of an
                  individual item within an order is expressed, indicating the
                  monetary unit used for pricing that particular item.
              weight:
                type: number
                description: >-
                  The numerical measurement representing the weight of an
                  individual item or product within an order. 
              weight_label:
                type: string
                description: >-
                  A textual label or description associated with the weight of
                  an individual item within an order, typically used to indicate
                  the unit of measurement (e.g., kg, lb) and provide clarity
                  regarding how the item's weight is expressed.
              amounts:
                type: object
                properties:
                  price_without_tax:
                    type: object
                    properties:
                      amount:
                        type: integer
                        description: 'Order item amounts price without tax '
                      currency:
                        type: string
                        description: Order item amounts price without tax currency
                    x-apidog-orders:
                      - amount
                      - currency
                    x-apidog-ignore-properties: []
                  total_discount:
                    type: object
                    properties:
                      amount:
                        type: integer
                        description: Total discount amount of the order item amounts.
                      currency:
                        type: string
                        description: Order item amounts total discount currency
                    x-apidog-orders:
                      - amount
                      - currency
                    x-apidog-ignore-properties: []
                  tax:
                    type: object
                    properties:
                      percent:
                        type: string
                        description: Order item amounts tax percent
                      amount:
                        type: object
                        properties:
                          amount:
                            type: integer
                            description: Order item amounts tax amount
                          currency:
                            type: string
                            description: Order item amounts tax caurrency
                        x-apidog-orders:
                          - amount
                          - currency
                        x-apidog-ignore-properties: []
                    x-apidog-orders:
                      - percent
                      - amount
                    x-apidog-ignore-properties: []
                  total:
                    type: object
                    properties:
                      amount:
                        type: integer
                        description: Order item amounts total amount
                      currency:
                        type: string
                        description: Total discount currency of the order item amounts.
                    x-apidog-orders:
                      - amount
                      - currency
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - price_without_tax
                  - total_discount
                  - tax
                  - total
                x-apidog-ignore-properties: []
              notes:
                type: string
                description: Order items notes
              product:
                $ref: '#/components/schemas/ProductCard'
              options:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: number
                      description: >-
                        A unique identifier, often numerical or alphanumeric,
                        assigned to a specific item.
                    product_option_id:
                      type: number
                      description: >-
                        A unique identifier, often numerical or alphanumeric,
                        assigned to a specific product option , enabling easy
                        tracking and management of various product
                        configurations, such as size, color, or other
                        customizable features.
                    name:
                      type: string
                      description: >-
                        A label for a product variation or choice, like size or
                        color.
                    type:
                      type: string
                      description: Type of the product option.
                      enum:
                        - adio
                        - date
                        - datetime
                        - image
                        - text
                        - text area
                        - number
                        - checkbox
                        - splitter
                    value:
                      type: array
                      description: >-
                        If `type` value is set to `radio` or `checkbox`, the
                        returned response is an object. Otherwise, a string is
                        returned in all other available `type` values.
                      items:
                        type: object
                        properties:
                          id:
                            type: number
                            description: >-
                              A unique identifier, typically numerical or
                              alphanumeric, associated with a specific value or
                              choice within a product option.
                          name:
                            type: string
                            description: >-
                              The descriptive label or text representing a
                              specific choice or value within a product option.
                          price:
                            type: object
                            properties:
                              amount:
                                type: integer
                                description: Option value amount.
                              currency:
                                type: string
                                description: Option value currency.
                            x-apidog-orders:
                              - amount
                              - currency
                            x-apidog-ignore-properties: []
                        x-apidog-orders:
                          - id
                          - name
                          - price
                        x-apidog-ignore-properties: []
                  x-apidog-orders:
                    - id
                    - product_option_id
                    - name
                    - type
                    - value
                  x-apidog-ignore-properties: []
              images:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: number
                      description: >-
                        A unique identifier, typically numerical or
                        alphanumeric, associated with a specific product image
                        in a database or system, enabling easy tracking and
                        referencing of images used for a product.
                    image:
                      type: string
                      description: >-
                        Textual reference, such as a file path or URL link, that
                        points to the location of an image file representing a
                        product. 
                    type:
                      type: string
                      description: Type of the product image.
                  x-apidog-orders:
                    - id
                    - image
                    - type
                  x-apidog-ignore-properties: []
              codes:
                type: array
                items:
                  type: object
                  properties:
                    code:
                      type: string
                      description: Product codes value
                    status:
                      type: string
                      description: Product codes status
                  x-apidog-orders:
                    - code
                    - status
                  x-apidog-ignore-properties: []
              files:
                type: array
                items:
                  type: object
                  properties:
                    url:
                      type: string
                      description: >-
                        A web address (URL) that provides access to a file
                        associated with a product.
                    name:
                      type: string
                      description: the name or title of a file associated with a product.
                    size:
                      type: number
                      description: >-
                        The numerical measurement that represents the size of a
                        file associated with a product.
                  x-apidog-orders:
                    - url
                    - name
                    - size
                  x-apidog-ignore-properties: []
              reservations:
                type: string
              product_reservations:
                type: array
                items:
                  type: string
            x-apidog-orders:
              - id
              - name
              - sku
              - quantity
              - currency
              - weight
              - weight_label
              - amounts
              - notes
              - product
              - options
              - images
              - codes
              - files
              - reservations
              - product_reservations
            required:
              - product_reservations
            x-apidog-ignore-properties: []
          deprecated: true
        bank:
          type: object
          properties:
            id:
              type: number
              description: >-
                A unique identifier, often numerical or alphanumeric, associated
                with a specific bank account .
            bank_name:
              type: string
              description: Bank name
            bank_id:
              type: number
              description: Bank unique identifier.
            account_name:
              type: string
              description: Bank account holder name
            account_number:
              type: string
              description: Bank account number
            iban_number:
              type: string
              description: Bank account iban number
            status:
              type: string
              description: Bank status
          x-apidog-orders:
            - id
            - bank_name
            - bank_id
            - account_name
            - account_number
            - iban_number
            - status
          x-apidog-ignore-properties: []
        tags:
          $ref: '#/components/schemas/OrderTag'
          description: Order tag details.
        store:
          type: object
          properties:
            id:
              type: string
              description: A unique identifer for the store
            store_id:
              type: string
              description: A unique identifer for the store
            user_id:
              type: string
              description: A unique identifer for the store user
            user_email:
              type: string
              description: Store email
            username:
              type: string
              description: Store username
            name:
              type: object
              properties:
                ar:
                  type: string
                  description: Store name in Arabic
                en:
                  type: string
                  description: Store name in English
              x-apidog-orders:
                - ar
                - en
              description: Store name
              x-apidog-ignore-properties: []
            avatar:
              type: string
              description: Store logo in URL format
          x-apidog-orders:
            - id
            - store_id
            - user_id
            - user_email
            - username
            - name
            - avatar
          description: Order store details.
          deprecated: true
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - cart_reference_id
        - reference_id
        - urls
        - date
        - updated_at
        - source
        - draft
        - read
        - source_device
        - source_details
        - status
        - is_price_quote
        - payment_method
        - receipt_image
        - currency
        - amounts
        - exchange_rate
        - can_cancel
        - show_weight
        - can_reorder
        - is_pending_payment
        - rating_link
        - checkout_url
        - pending_payment_ends_at
        - total_weight
        - shipping
        - shipments
        - pickup_branch
        - shipment_branch
        - customer
        - items
        - bank
        - tags
        - store
      required:
        - id
        - cart_reference_id
        - reference_id
        - urls
        - date
        - updated_at
        - source
        - draft
        - read
        - source_device
        - source_details
        - status
        - is_price_quote
        - payment_method
        - receipt_image
        - currency
        - amounts
        - exchange_rate
        - can_cancel
        - show_weight
        - can_reorder
        - is_pending_payment
        - pending_payment_ends_at
        - total_weight
        - shipping
        - shipments
        - pickup_branch
        - shipment_branch
        - customer
        - items
        - bank
        - tags
        - store
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    OrderTag:
      description: >-
        Detailed structure of the orders tag model object showing its fields and
        data types.
      type: object
      x-examples: {}
      title: OrderTag
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: A unique identifier assigned to a tag associated with an order.
        name:
          type: string
          description: >-
            A textual identifier used to describe a tag associated with an
            order.
      x-apidog-orders:
        - id
        - name
      required:
        - id
        - name
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductCard:
      description: >-
        Detailed structure of the Product short payload model object showing its
        fields and data types.
      type: object
      title: ProductCard
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: A unique identifier associated with a specific product.
        type:
          type: string
          description: >-
            The category or classification that a specific product belongs to
            based on its attributes, characteristics, or intended use.
          enum:
            - product
            - service
            - group_products
            - codes
            - digital
            - food
            - donating
          x-apidog-enum:
            - value: product
              name: ''
              description: Tangible and shippable products
            - value: service
              name: ''
              description: >-
                Servecable products, such as design, rsearch, printing, writing
                etc
            - value: group_products
              name: ''
              description: More than a product under one product
            - value: codes
              name: ''
              description: >-
                Chargable cards (PlayStation Cards), sellable account (Netflix)
                etc
            - value: digital
              name: ''
              description: Electronic books, Courses, Downloadable files etc
            - value: food
              name: ''
              description: Food and drinks that require special shipping
            - value: donating
              name: ''
              description: Only in case when the store is of type charity
        promotion:
          type: object
          description: Product promotion details.
          properties:
            title:
              type: string
              description: >-
                The name or label assigned to a specific marketing or
                promotional campaign, deal, or offer.
            sub_title:
              type: string
              description: >-
                The additional name or label assigned to a specific marketing or
                promotional campaign, deal, or offer. 
          x-apidog-orders:
            - title
            - sub_title
          required:
            - title
            - sub_title
          x-apidog-ignore-properties: []
        status:
          type: string
          description: The product status. available values 'hidden','sale','out'.
        is_available:
          type: boolean
          description: Check if the product is available to order or in-stock.
        sku:
          type: string
          description: >-
            A unique Stock Keeping Unit (SKU) identifier assigned to a specific
            variant of a product.
        name:
          type: string
          description: The name or title of a product.
        price:
          type: object
          description: Product price details
          properties:
            amount:
              type: number
              description: Product price amount
            currency:
              type: string
              description: Product price currency
          x-apidog-orders:
            - amount
            - currency
          x-apidog-ignore-properties: []
        sale_price:
          type: object
          description: Product sale price details
          properties:
            amount:
              type: number
              description: Product sale price amount
            currency:
              type: string
              description: Product sale price curren
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        url:
          type: string
          description: 'Product url '
        has_special_price:
          type: boolean
          description: Whether or not the product has a special price
        regular_price:
          type: object
          description: Product regular price details
          properties:
            amount:
              type: number
              description: Product regular price amount
            currency:
              type: string
              description: Product regular price currency
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        currency:
          type: string
          description: The specific currency of the product price.
        thumbnail:
          type: string
          description: Scaled-down image or visual representation of a product.
        calories:
          type: string
          description: Calories amount of the product.
          nullable: true
        mpn:
          type: string
          description: >-
            Manufacturer Part Number, a unique identifier assigned by a
            manufacturer to a specific product or component, which helps
            distinguish it from other similar products and facilitates inventory
            management, product tracking, and ordering processes.
          nullable: true
        gtin:
          type: string
          description: >-
            "Global Trade Item Number" (GTIN), a unique and standardized
            identifier used to uniquely represent products, items, or services
            in the global marketplace, to enable efficient tracking and
            management across supply chains and retail sectors.
          nullable: true
        favorite:
          type: string
          description: Product marked as favorite
          nullable: true
        starting_price:
          description: Product starting price
          type: string
          nullable: true
      x-apidog-orders:
        - id
        - type
        - promotion
        - status
        - is_available
        - sku
        - name
        - price
        - sale_price
        - url
        - has_special_price
        - regular_price
        - currency
        - thumbnail
        - calories
        - mpn
        - gtin
        - favorite
        - starting_price
      required:
        - id
        - type
        - promotion
        - status
        - is_available
        - sku
        - name
        - price
        - sale_price
        - url
        - has_special_price
        - regular_price
        - currency
        - thumbnail
        - calories
        - mpn
        - gtin
        - favorite
        - starting_price
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
        urls: *ref_1
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
    ShipmentBranch:
      title: ShipmentBranch
      type: object
      x-tags:
        - Models
      description: Shipment branch details in case of order is being shipped from a branch
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific branch. Shipping
            companies list can be found
            [here](https://docs.salla.dev/api-5394239)
        name:
          type: string
          description: The formal name or title of a specific branch.
        status:
          type: string
          description: >-
            Indicates whether a specific branch of an organization is currently
            active and operational (active) or not in use or temporarily closed
            (inactive). 
        is_default:
          type: boolean
          description: Whether or not this brnach is the default branch for all operations.
        type:
          type: string
          description: >-
            The category or classification that defines the nature or function
            of a specific branch either a branch or warehouse.
      x-apidog-orders:
        - id
        - name
        - status
        - is_default
        - type
      required:
        - id
        - name
        - status
        - is_default
        - type
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Branch:
      description: >-
        Detailed structure of the branch model object showing its fields and
        data types.
      type: object
      title: Branch
      x-tags:
        - Models
      properties:
        id:
          description: The unique identifier of a branch.
          type: number
        name:
          type: string
          description: >-
            The label given to a specific branch. 🌐 [Support
            multi-language](doc-421122)
        status:
          type: string
          description: >-
            The status of the branch, indicating whether it is "Active" as open
            for business or "Inactive" as closed.
          enum:
            - active
            - inactive
          x-apidog-enum:
            - value: active
              name: ''
              description: Open for business
            - value: inactive
              name: ''
              description: Closed for business
        location:
          type: object
          description: Branch's location on map in both longitude and latitude
          properties:
            lat:
              type: string
              description: Latitude of the location.
            lng:
              type: string
              description: Longitude of the location.
          x-apidog-orders:
            - lat
            - lng
          required:
            - lat
            - lng
          x-apidog-ignore-properties: []
        street:
          type: string
          description: Branch's street name. 🌐 [Support multi-language](doc-421122)
        address_description:
          type: string
          description: >-
            Branch's address description. 🌐 [Support
            multi-language](doc-421122)
        additional_number:
          type: string
          description: 'Branch''s additional (alternative) phone number. '
        building_number:
          type: string
          description: 'Branch''s building number. '
        local:
          type: string
          description: Branch's local district. 🌐 [Support multi-language](doc-421122)
        postal_code:
          type: string
          description: Branch's postal code. Value length is 5 characters long.
        contacts:
          type: object
          description: Branch's contacts details.
          properties:
            phone:
              type: string
              description: Branch phone number.
            whatsapp:
              type: string
              description: Branch whatsapp number.
            telephone:
              type: string
              description: Branch telephone number.
          x-apidog-orders:
            - phone
            - whatsapp
            - telephone
          required:
            - phone
            - whatsapp
            - telephone
          x-apidog-ignore-properties: []
        preparation_time:
          type: string
          description: >-
            The time required for the branch to get an order ready for shipping
            or pickup.
        is_open:
          type: boolean
          description: Whether or not the branch is currently `open` or `closed`
        closest_time:
          type: object
          properties:
            from:
              type: string
            to:
              type: string
          x-apidog-orders:
            - from
            - to
          description: >-
            The time when the branch will be closed based on the request time.
            Each request may have a different value. 
          x-apidog-ignore-properties: []
          nullable: true
        working_hours:
          description: Branch working hours. Required if `branch.type is "branch"`
          type: array
          items:
            type: object
            properties:
              name:
                type: string
              times:
                type: array
                items:
                  type: object
                  properties:
                    from:
                      type: string
                    to:
                      type: string
                  x-apidog-orders:
                    - from
                    - to
                  x-apidog-ignore-properties: []
            x-apidog-orders:
              - name
              - times
            x-apidog-ignore-properties: []
        is_cod_available:
          type: boolean
          description: Whether or not Cash on delivery available.
        is_default:
          type: boolean
          description: Whether or not this branch is the default branch for all operations.
        type:
          type: string
          description: Branch type, either a standard `branch` or `warehouse`
          enum:
            - branch
            - warehouse
          x-apidog-enum:
            - value: branch
              name: ''
              description: >-
                A physical location where customers can shop, interact, and
                access services.
            - value: warehouse
              name: ''
              description: >-
                A facility for storing inventory and managing order fulfillment
                logistics.
        cod_cost:
          type: string
          description: |+
            Cash on delivery cost value

        country:
          $ref: '#/components/schemas/Country'
        city:
          type: object
          properties:
            id:
              type: number
              description: A unique identifier or code assigned to a specific city.
            name:
              type: string
              description: >-
                The lable used for a specific urban area or municipality within
                a country or region.
            name_en:
              type: string
              description: City name expressed in English characters.
            country_id:
              type: number
              description: Unique identifier of the country
          x-apidog-refs: {}
          x-apidog-orders:
            - id
            - name
            - name_en
            - country_id
          required:
            - id
            - name
            - name_en
            - country_id
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - status
        - location
        - street
        - address_description
        - additional_number
        - building_number
        - local
        - postal_code
        - contacts
        - preparation_time
        - is_open
        - closest_time
        - working_hours
        - is_cod_available
        - is_default
        - type
        - cod_cost
        - country
        - city
      required:
        - id
        - name
        - status
        - location
        - street
        - address_description
        - additional_number
        - building_number
        - local
        - postal_code
        - contacts
        - preparation_time
        - is_open
        - closest_time
        - working_hours
        - is_cod_available
        - is_default
        - type
        - cod_cost
        - country
        - city
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Country:
      description: >-
        Detailed structure of the country model object showing its fields and
        data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: Country
      properties:
        id:
          description: A unique identifier assigned to a specific country.
          type: number
        name:
          type: string
          description: >-
            The official or commonly used name of a specific nation or
            geographic region.
        name_en:
          type: string
          description: Country name expressed in English characters.
        code:
          type: string
          description: >-
            Country iso code , a standardized, three-letter code assigned to
            each country by the International Organization for Standardization.
        mobile_code:
          type: string
          description: >-
            The international dialing code used to make phone calls to a
            specific country from abroad, also known as the country's "calling
            code."
      x-apidog-orders:
        - id
        - name
        - name_en
        - code
        - mobile_code
      required:
        - id
        - name
        - name_en
        - code
        - mobile_code
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
        customer: *ref_2
        admin: *ref_3
        digital_content: *ref_4
        rating: *ref_5
        checkout: *ref_6
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

