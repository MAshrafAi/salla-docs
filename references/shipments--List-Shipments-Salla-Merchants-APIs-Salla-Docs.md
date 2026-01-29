# Shipments  List Shipments Salla Merchants Apis Salla Docs

## Table of Contents

- [shipments/List-Shipments-Salla-Merchants-APIs-Salla-Docs](#shipments-list-shipments-salla-merchants-apis-salla-docs)

---

## shipments/List-Shipments-Salla-Merchants-APIs-Salla-Docs

# List Shipments

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipments:
    get:
      summary: List Shipments
      deprecated: false
      description: >-
        You can list all shipments related to your store directly from this
        endpoint. Also, it allows you to filter them using by shipping company
        slug.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read`- Shipping Read Only

        </Accordion>
      operationId: get-shipments
      tags:
        - Default module/Shipping and Fulfilment API/Shipments
        - Shipments
      parameters:
        - name: order_id
          in: query
          description: >-
            Order ID. Get a list of Order IDs from
            [here](https://docs.salla.dev/api-5394146/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: 1743861419
          schema:
            type: integer
        - name: courier_id
          in: query
          description: >-
            Courier ID. Get a list of Courier IDs from
            [here](https://docs.salla.dev/api-5578815/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
          required: false
          example: 1723506348
          schema:
            type: integer
        - name: courier_slug
          in: query
          description: >-
            Courier Slug. Get a list of Courier Slugs from
            [here](https://docs.salla.dev/api-5578815/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
          required: false
          example: smsa
          schema:
            type: string
        - name: status
          in: query
          description: Shipment Status; value can be one of the listed enum variables
          required: false
          example: delivered
          schema:
            type: string
            enum:
              - created
              - in_progress
              - in_transit
              - received_at_final_hub
              - to_be_reattempted
              - reattempted
              - unable_to_deliver
              - delivering
              - delivered
              - partially_delivered
              - shipped
              - cancelled
              - lost
              - damaged
              - return_to_origin
              - return_in_progress
            x-apidog-enum:
              - value: created
                name: ''
                description: Shipment has been registered and is ready for processing.
              - value: in_progress
                name: ''
                description: Shipment is being prepared or picked up.
              - value: in_transit
                name: ''
                description: Shipment is moving between hubs or facilities.
              - value: received_at_final_hub
                name: ''
                description: Shipment reached the final hub before delivery.
              - value: to_be_reattempted
                name: ''
                description: Delivery attempt failed. Retry is scheduled.
              - value: reattempted
                name: ''
                description: Another delivery attempt has been made.
              - value: unable_to_deliver
                name: ''
                description: Courier could not complete the delivery.
              - value: delivering
                name: ''
                description: Courier is currently delivering the shipment.
              - value: delivered
                name: ''
                description: Shipment has been successfully delivered.
              - value: partially_delivered
                name: ''
                description: Only some items in the shipment were delivered.
              - value: shipped
                name: ''
                description: Shipment has left the origin warehouse.
              - value: cancelled
                name: ''
                description: Shipment has been cancelled by sender or system.
              - value: lost
                name: ''
                description: Shipment location is unknown and cannot be tracked.
              - value: damaged
                name: ''
                description: Shipment arrived with visible or reported damage.
              - value: return_to_origin
                name: ''
                description: Shipment is being returned to the sender.
              - value: return_in_progress
                name: ''
                description: Return process has started and is underway.
        - name: shipment_type
          in: query
          description: Shipment Type; value can either `"shipment"` or `"return"`
          required: false
          example: shipment
          schema:
            type: string
        - name: payment_method
          in: query
          description: Payment Method; value can either `"pre_paid"` or `"cod"`
          required: false
          example: pre_paid
          schema:
            type: string
        - name: from_date
          in: query
          description: Shipment starting date range
          required: false
          example: '2024-11-29'
          schema:
            type: string
        - name: to_date
          in: query
          description: Shipment ending date range
          required: false
          example: '2024-12-29'
          schema:
            type: string
        - name: ship_to[country_id]
          in: query
          description: >-
            Shipment Country Destination. Get a list of Country IDs from
            [here](https://docs.salla.dev/api-5394228/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: 1473353380
          schema:
            type: integer
        - name: ship_to[country_code]
          in: query
          description: >-
            Shipment Country Code Destination. Get a list of Country Codes from
            [here](https://docs.salla.dev/api-5394228/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: SA
          schema:
            type: string
        - name: ship_to[city_id]
          in: query
          description: >-
            Shipment City Destination. Get a list of City IDs from
            [here](https://docs.salla.dev/api-5394230/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: 566146469
          schema:
            type: integer
        - name: ship_from[country_id]
          in: query
          description: >-
            Shipment Country Origin. Get a list of Country IDs from
            [here](https://docs.salla.dev/api-5394228/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: 1473353380
          schema:
            type: integer
        - name: ship_from[country_code]
          in: query
          description: >-
            Shipment Country Code Origin. Get a list of Country Codes from
            [here](https://docs.salla.dev/api-5394228/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: SA
          schema:
            type: string
        - name: ship_from[city_id]
          in: query
          description: >-
            Shipment City Origin. Get a list of City IDs from
            [here](https://docs.salla.dev/api-5394230/?nav=01J1Y9KTRRDA57Q8ZSW95TTVDB)
          required: false
          example: 566146469
          schema:
            type: integer
        - name: source
          in: query
          description: Shipment Source; value can be one of the listed enum variables
          required: false
          example: api
          schema:
            type: string
        - name: per_page
          in: query
          description: Shipments limit per page
          required: false
          example: 5
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ShipmentsResponse'
              example:
                status: 200
                success: true
                data:
                  - id: 362985662
                    order_id: 560695738
                    order_reference_id: 48927
                    created_at:
                      date: '2023-01-18 09:35:03.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    type: return
                    courier_id: 814202285
                    courier_name: DHL
                    courier_logo: https://company.com/logo.png
                    shipping_number: '0'
                    tracking_number: '0'
                    pickup_id: null
                    trackable: true
                    tracking_link: >-
                      https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345
                    label: []
                    payment_method: cod
                    source: api
                    status: creating
                    total:
                      amount: 0
                      currency: SAR
                    cash_on_delivery:
                      amount: '10.70'
                      currency: SAR
                    meta:
                      app_id: null
                      policy_options: []
                    ship_from:
                      type: address
                      name: Username
                      email: username@email.com
                      phone: 055-555-555
                      country_id: 1939592358
                      country_code: KW
                      city: ABBASIYA
                      city_id: 1313869267
                      address_line: >-
                        2345,السلام,95128, شارع عبدالله  سنابل السلام  مكة 
                        السعوديه, RIYADH,السعودية
                      street_number: '2345'
                      block: السلام
                      postal_code: '95128'
                      latitude: 21.382590509685
                      longitude: 39.773191030685
                    ship_to:
                      type: branch
                      name: Riyadh
                      email: ''
                      phone: '0555555555'
                      country_id: 1939592358
                      country_code: KW
                      city: ABBASIYA
                      city_id: 1313869267
                      address_line: "7687 طريق الملك فهد الفرعي,الملك فهد,12262, 7687 طريق الملك فهد الفرعي، الملك فهد، الرياض 12262\_3010، السعودية, الرياض,السعودية"
                      street_number: 7687 طريق الملك فهد الفرعي
                      block: الملك فهد
                      postal_code: '12262'
                      latitude: 24.7431373
                      longitude: 46.6570741
                      branch_id: 1723506348
                    packages: []
                    billing_account: salla
                  - id: 362985663
                    order_id: 560695739
                    order_reference_id: 48928
                    created_at:
                      date: '2023-01-16 23:37:59.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    type: return
                    courier_id: 814202285
                    courier_name: DHL
                    courier_logo: https://company.com/logo.png
                    shipping_number: '23424234354434'
                    tracking_number: '23424234354434'
                    pickup_id: null
                    trackable: true
                    tracking_link: >-
                      https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345
                    label: []
                    payment_method: cod
                    source: api
                    status: creating
                    total:
                      amount: 100
                      currency: SAR
                    cash_on_delivery:
                      amount: '10.70'
                      currency: SAR
                    meta:
                      app_id: null
                      policy_options: []
                    ship_from:
                      type: branch
                      name: Riyadh
                      email: ''
                      phone: '0555555555'
                      country: السعودية
                      country_id: 1939592358
                      country_code: KW
                      city: ABBASIYA
                      city_id: 1313869267
                      address_line: "7687 طريق الملك فهد الفرعي,الملك فهد,12262, 7687 طريق الملك فهد الفرعي، الملك فهد، الرياض 12262\_3010، السعودية, RIYADH,السعودية"
                      street_number: 7687 طريق الملك فهد الفرعي
                      block: الملك فهد
                      postal_code: '12262'
                      latitude: 24.7431373
                      longitude: 46.6570741
                      branch_id: 1723506348
                    ship_to:
                      type: address
                      name: Username
                      email: username@email.com
                      phone: 055-555-555
                      country: السعودية
                      country_id: 1939592358
                      country_code: KW
                      city: ABBASIYA
                      city_id: 1313869267
                      address_line: ' شارع 2345، الحي السلام 95128،, شارع عبدالله  سنابل السلام  مكة  السعوديه,, الرياض, السعودية'
                      street_number: '2345'
                      block: السلام
                      postal_code: '95128'
                      latitude: 21.382590509685
                      longitude: 39.773191030685
                    packages:
                      - name: منتج تجريبي
                        sku: 6ytrrhrhr
                        price:
                          amount: '50.00'
                          currency: SAR
                        quantity: 2
                        weight:
                          value: '1.00'
                          unit: kg
                    billing_account: salla
                  - id: 362985660
                    order_id: 560695732
                    order_reference_id: 48922
                    created_at:
                      date: '2023-01-16 23:26:15.000000'
                      timezone_type: 3
                      timezone: Asia/Riyadh
                    type: shipment
                    courier_id: 814202285
                    courier_name: DHL
                    courier_logo: https://company.com/logo.png
                    shipping_number: '0'
                    tracking_number: '0'
                    pickup_id: null
                    trackable: true
                    tracking_link: >-
                      https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345
                    label: []
                    payment_method: cod
                    source: api
                    status: creating
                    total:
                      amount: 100
                      currency: SAR
                    cash_on_delivery:
                      amount: '10.70'
                      currency: SAR
                    meta:
                      app_id: null
                      policy_options:
                        boxes: 2
                    ship_from:
                      type: branch
                      name: Riyadh
                      email: ''
                      phone: '0555555555'
                      country: السعودية
                      country_id: 1939592358
                      country_code: KW
                      city: ABBASIYA
                      city_id: 1313869267
                      address_line: "7687 طريق الملك فهد الفرعي,الملك فهد,12262, 7687 طريق الملك فهد الفرعي، الملك فهد، الرياض 12262\_3010، السعودية, RIYADH,السعودية"
                      street_number: 7687 طريق الملك فهد الفرعي
                      block: الملك فهد
                      postal_code: '12262'
                      latitude: 24.7431373
                      longitude: 46.6570741
                      branch_id: 1723506348
                    ship_to:
                      type: address
                      name: Username
                      email: username@email.com
                      phone: 055-555-555
                      country: السعودية
                      country_id: 1939592358
                      country_code: KW
                      city: ABBASIYA
                      city_id: 1313869267
                      address_line: ' شارع 2345، الحي السلام 95128،, شارع عبدالله  سنابل السلام  مكة  السعوديه,, الرياض, السعودية'
                      street_number: '2345'
                      block: السلام
                      postal_code: '95128'
                      latitude: 21.382590509685
                      longitude: 39.773191030685
                    packages:
                      - name: منتج تجريبي
                        sku: 6ytrrhrhr
                        price:
                          amount: '50.00'
                          currency: SAR
                        quantity: 2
                        weight:
                          value: '1.00'
                          unit: kg
                    billing_account: salla
                pagination:
                  count: 3
                  total: 32
                  perPage: 3
                  currentPage: 1
                  totalPages: 11
                  links:
                    next: https://company.com/shipments?page=2
          headers: {}
          x-apidog-name: Success
        '422':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ValidationResponse'
              example:
                status: 422
                success: false
                error:
                  code: error
                  message: alert.invalid_fields
                  fields:
                    courier_slug:
                      - حقل ترميز الشركة يحتوي على قيم غير صحيحة
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-apidog-folder: Default module/Shipping and Fulfilment API/Shipments
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5578809-run
components:
  schemas:
    ShipmentsResponse:
      type: object
      title: Shipments Response
      description: >-
        This schema describes a model for a shipment response, including details
        about shipments made by a courier service, their associated orders, and
        shipment properties like ID, type, courier, tracking info, payment
        method, source, and status, as well as package details like name, SKU,
        price, quantity, and weight. Other info, such as creation date,
        currency, and trackability, is also included in the response, returned
        as **an array of objects** for use in a RESTful API for querying
        shipment data.
      properties:
        status:
          type: string
          description: Response Status Code
          examples:
            - '200'
        success:
          type: boolean
          description: Whether or not the response was successful
          examples:
            - true
        data:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: This field refers to a unique identifier for the shipment.
                examples:
                  - 987654321
              order_id:
                type: number
                description: >-
                  This field refers to the unique identifier for the order
                  associated with the shipment. 
                examples:
                  - 123456789
              order_reference_id:
                type: number
                description: >-
                  This field refers to a reference ID that can be used to look
                  up additional information about the order
                nullable: true
              created_at:
                type: object
                properties:
                  date:
                    type: string
                    description: Shipment Created At Date
                    examples:
                      - '2023-01-18 09:35:03.000000'
                  timezone_type:
                    type: integer
                    description: Shipment Created At Timezone Type
                    examples:
                      - 3
                  timezone:
                    type: string
                    description: Shipment Created At Timezone
                    examples:
                      - Asia/Riyadh
                x-apidog-orders:
                  - date
                  - timezone_type
                  - timezone
                x-apidog-ignore-properties: []
              type:
                type: string
                enum:
                  - return
                  - shipment
                description: Shipment Type
                examples:
                  - shipment
              courier_id:
                type: integer
                description: >-
                  Shipment Courier ID. Find a complete list of Shipment
                  companies
                  [here](https://docs.salla.dev/docs/shipping-providers-api/a4c3f0cd7533a-list-shipping-companies)
                examples:
                  - 1723506348
              courier_name:
                type: string
                description: Shipment Courier Name
                examples:
                  - Semsa
              courier_logo:
                type: string
                description: Shipment Courier Logo
                examples:
                  - https://semsa.com/assets/logo.png
              shipping_number:
                type: string
                description: Shipment Shipping Number
                examples:
                  - '192837465'
              tracking_number:
                type: string
                description: Shipment Tracking Number
                examples:
                  - '918273645'
              pickup_id:
                description: Shipment Pickup ID
                type: 'null'
                examples:
                  - '10954392'
              trackable:
                type: boolean
                description: Whether or not the shipment is trackable
                examples:
                  - true
              tracking_link:
                type: string
                description: Shipment Tracking Link
                examples:
                  - https://semsa.com/tracking/order_url.com
              label:
                type: object
                properties:
                  format:
                    type: string
                    description: Shipment Label Format
                    examples:
                      - pdf
                  url:
                    type: string
                    description: 'Shipment Label '
                    examples:
                      - https://semsa.com/tracking/order_url_file.pdf
                x-apidog-orders:
                  - format
                  - url
                x-apidog-ignore-properties: []
              payment_method:
                type: string
                enum:
                  - cod
                  - pre_paid
                description: Shipment Payment Method
                examples:
                  - cod
              source:
                type: string
                description: Shipment Source
                examples:
                  - dashboard
              status:
                type: string
                enum:
                  - creating
                  - created
                  - pending
                  - delivered
                  - returned
                  - in_progress
                  - cancelled
                  - delivering
                description: Shipment Status
                examples:
                  - in_progress
              total:
                type: object
                properties:
                  amount:
                    type: number
                    description: Shipment Total Amount
                    examples:
                      - 200
                  currency:
                    type: string
                    description: >-
                      Shipment Total Currency. You may refer to the external
                      Merchant API Docs for the List of Currencies from
                      [here](https://docs.salla.dev/docs/merchant/f18b629e987b8-list-currencies)
                    examples:
                      - sar
                x-apidog-orders:
                  - amount
                  - currency
                x-apidog-ignore-properties: []
              cash_on_delivery:
                type: object
                properties:
                  amount:
                    type: number
                    description: Shipment Cash On Delivery Amount
                    examples:
                      - 200
                  currency:
                    type: string
                    description: >-
                      Shipment Cash On Delivery Currency. You may refer to the
                      external Merchant API Docs for the List of Currencies from
                      [here](https://docs.salla.dev/docs/merchant/f18b629e987b8-list-currencies)
                    examples:
                      - sar
                x-apidog-orders:
                  - amount
                  - currency
                x-apidog-ignore-properties: []
              is_international:
                type: boolean
                description: Whether the shipment is shipped internationally
                examples:
                  - true
              total_weight:
                type: object
                properties:
                  value:
                    type: number
                    description: Shipment Total Weight Value
                    examples:
                      - 1.5
                  units:
                    type: string
                    description: Shipment Total Weight Units
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
                            Currencies from
                            [here](https://docs.salla.dev/docs/merchant/f18b629e987b8-list-currencies)
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
                          examples:
                            - kg
                      x-apidog-orders:
                        - value
                        - units
                      x-apidog-ignore-properties: []
                  x-apidog-orders:
                    - item_id
                    - external_id
                    - name
                    - sku
                    - price
                    - quantity
                    - weight
                  x-apidog-ignore-properties: []
              ship_from:
                type: object
                properties:
                  type:
                    type: string
                    description: Shipment Ship From Type
                    examples:
                      - address
                  name:
                    type: string
                    description: Shipment Ship From Name
                    examples:
                      - Username
                  email:
                    type: string
                    description: Shipment Ship From Email
                    examples:
                      - username@gmail.com
                  phone:
                    type: string
                    description: Shipment Ship From Phone
                    examples:
                      - 555-555-555
                  country:
                    type: string
                    description: Shipment Ship From Country
                    examples:
                      - Saudi Arabia
                  city:
                    type: string
                    description: Shipment Ship From City
                    examples:
                      - Mecca
                  address_line:
                    type: string
                    description: Shipment Ship From Address Line
                    examples:
                      - Mecca Street
                  street_number:
                    description: Shipment Ship From Street Number
                    type: 'null'
                    examples:
                      - 120B
                  block:
                    description: Shipment Ship From Block
                    type: 'null'
                    examples:
                      - Block AB
                  postal_code:
                    description: Shipment Ship From Postal Code
                    type: 'null'
                    examples:
                      - '1000'
                  latitude:
                    type: number
                    description: Shipment Ship From Latitude
                    examples:
                      - 10.2345
                  longitude:
                    type: number
                    description: Shipment Ship From Longitude
                    examples:
                      - 54.321
                  branch_id:
                    type: integer
                    description: Shipment Ship From Branch ID
                    examples:
                      - 194309
                x-apidog-orders:
                  - type
                  - name
                  - email
                  - phone
                  - country
                  - city
                  - address_line
                  - street_number
                  - block
                  - postal_code
                  - latitude
                  - longitude
                  - branch_id
                x-apidog-ignore-properties: []
              ship_to:
                type: object
                properties:
                  type:
                    type: string
                    description: Shipment Ship To Type
                    examples:
                      - address
                  name:
                    type: string
                    description: Shipment Ship To Name
                    examples:
                      - Username1
                  email:
                    type: string
                    description: Shipment Ship To Email
                    examples:
                      - username1@gmail.com
                  phone:
                    type: string
                    description: Shipment Ship To Phone
                    examples:
                      - 555-555-554
                  country:
                    type: string
                    description: Shipment Ship To Country
                    examples:
                      - Saudi Arabia
                  city:
                    type: string
                    description: Shipment Ship To City
                    examples:
                      - Jeddah
                  address_line:
                    type: string
                    description: Shipment Ship To Address Line
                    examples:
                      - Tahlia Street
                  street_number:
                    type: string
                    description: Shipment Ship To Street Number
                    examples:
                      - 119A
                  block:
                    type: string
                    description: Shipment Ship To Block
                    examples:
                      - Block BA
                  postal_code:
                    type: string
                    description: Shipment Ship To Postal Code
                    examples:
                      - '0001'
                  latitude:
                    type: number
                    description: Shipment Ship To Latitude
                    examples:
                      - 22.3213
                  longitude:
                    type: number
                    description: Shipment Ship To Longitude
                    examples:
                      - 11.2323
                x-apidog-orders:
                  - type
                  - name
                  - email
                  - phone
                  - country
                  - city
                  - address_line
                  - street_number
                  - block
                  - postal_code
                  - latitude
                  - longitude
                x-apidog-ignore-properties: []
              meta:
                type: object
                properties:
                  app_id:
                    type: integer
                    description: App ID
                    examples:
                      - 153082
                  policy_options:
                    type: object
                    properties:
                      shipment_content_type:
                        type: array
                        description: the type of packaging used for a shipment
                        items:
                          type: string
                          enum:
                            - document
                            - dry
                            - food_stuff
                            - liquid
                      packaging_type:
                        type: array
                        description: the type of content being shipped
                        items:
                          type: string
                          enum:
                            - basket
                            - box
                            - buble_wrapper
                            - pallet
                            - paper_wrapper
                      boxes:
                        type: integer
                        description: Shipment Boxes
                        examples:
                          - 2
                    x-apidog-orders:
                      - shipment_content_type
                      - packaging_type
                      - boxes
                    x-apidog-ignore-properties: []
                x-apidog-orders:
                  - app_id
                  - policy_options
                x-apidog-ignore-properties: []
              billing_account:
                type: string
                enum:
                  - salla
                  - merchant
                x-apidog-enum:
                  - value: salla
                    name: ''
                    description: The merchant uses Salla Awbs
                  - value: merchant
                    name: ''
                    description: The merchant uses his own account
                description: The type of the company billing account
              pagination:
                type: object
                properties: {}
                x-apidog-orders: []
                x-apidog-ignore-properties: []
            x-apidog-orders:
              - id
              - order_id
              - order_reference_id
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
              - status
              - total
              - cash_on_delivery
              - is_international
              - total_weight
              - packages
              - ship_from
              - ship_to
              - meta
              - billing_account
              - pagination
            x-apidog-ignore-properties: []
      x-examples:
        Example:
          status: 200
          success: true
          data:
            - id: 362985662
              order_id: 560695738
              order_reference_id: 48927
              created_at:
                date: '2023-01-18 09:35:03.000000'
                timezone_type: 3
                timezone: Asia/Riyadh
              type: return
              courier_id: 814202285
              courier_name: DHL
              courier_logo: https://company.com/logo.png
              shipping_number: '0'
              tracking_number: '0'
              pickup_id: null
              trackable: true
              tracking_link: >-
                https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345
              label: []
              payment_method: cod
              source: api
              status: creating
              total:
                amount: 0
                currency: SAR
              cash_on_delivery:
                amount: '10.70'
                currency: SAR
              meta:
                app_id: null
                policy_options:
                  shipment_content_type:
                    - document
                    - dry
                    - food_stuff
                    - liquid
                  packaging_type:
                    - basket
                    - box
                    - buble_wrapper
                    - pallet
                    - paper_wrapper
                  boxes: 1
              ship_from:
                type: address
                name: Username
                email: username@email.com
                phone: 055-555-555
                country: السعودية
                city: RIYADH
                address_line: >-
                  2345,السلام,95128, شارع عبدالله  سنابل السلام  مكة  السعوديه,
                  RIYADH,السعودية
                street_number: '2345'
                block: السلام
                postal_code: '95128'
                latitude: 21.382590509685
                longitude: 39.773191030685
              ship_to:
                type: branch
                name: Riyadh
                email: ''
                phone: '0555555555'
                country: السعودية
                city: الرياض
                address_line: >-
                  7687 طريق الملك فهد الفرعي,الملك فهد,12262, 7687 طريق الملك
                  فهد الفرعي، الملك فهد، الرياض 12262 3010، السعودية,
                  الرياض,السعودية
                street_number: 7687 طريق الملك فهد الفرعي
                block: الملك فهد
                postal_code: '12262'
                latitude: 24.7431373
                longitude: 46.6570741
                branch_id: 1723506348
              packages: []
            - id: 362985661
              order_id: 560695737
              order_reference_id: 48926
              created_at:
                date: '2023-01-16 23:37:59.000000'
                timezone_type: 3
                timezone: Asia/Riyadh
              type: return
              courier_id: 814202285
              courier_name: DHL
              courier_logo: https://company.com/logo.png
              shipping_number: '23424234354434'
              tracking_number: '23424234354434'
              pickup_id: null
              trackable: true
              tracking_link: >-
                https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345
              label: []
              payment_method: cod
              source: api
              status: creating
              total:
                amount: 100
                currency: SAR
              cash_on_delivery:
                amount: '10.70'
                currency: SAR
              meta:
                app_id: null
                policy_options:
                  shipment_content_type:
                    - document
                    - dry
                    - food_stuff
                    - liquid
                  packaging_type:
                    - basket
                    - box
                    - buble_wrapper
                    - pallet
                    - paper_wrapper
                  boxes: 1
              ship_from:
                type: branch
                name: Riyadh
                email: ''
                phone: '0555555555'
                country: السعودية
                city: RIYADH
                address_line: >-
                  7687 طريق الملك فهد الفرعي,الملك فهد,12262, 7687 طريق الملك
                  فهد الفرعي، الملك فهد، الرياض 12262 3010، السعودية,
                  RIYADH,السعودية
                street_number: 7687 طريق الملك فهد الفرعي
                block: الملك فهد
                postal_code: '12262'
                latitude: 24.7431373
                longitude: 46.6570741
                branch_id: 1723506348
              ship_to:
                type: address
                name: Username
                email: username@email.com
                phone: 055-555-555
                country: السعودية
                city: الرياض
                address_line: ' شارع 2345، الحي السلام 95128،, شارع عبدالله  سنابل السلام  مكة  السعوديه,, الرياض, السعودية'
                street_number: '2345'
                block: السلام
                postal_code: '95128'
                latitude: 21.382590509685
                longitude: 39.773191030685
              packages:
                - item_id: 2077288690
                  external_id: null
                  name: منتج تجريبي
                  sku: 6ytrrhrhr
                  price:
                    amount: '50.00'
                    currency: SAR
                  quantity: 2
                  weight:
                    value: '1.00'
                    unit: kg
            - id: 362985660
              order_id: 560695736
              order_reference_id: 48925
              created_at:
                date: '2023-01-16 23:26:15.000000'
                timezone_type: 3
                timezone: Asia/Riyadh
              type: shipment
              courier_id: 814202285
              courier_name: DHL
              courier_logo: https://company.com/logo.png
              shipping_number: '0'
              tracking_number: '0'
              pickup_id: null
              trackable: true
              tracking_link: >-
                https://www.logistics.dhl/us-en/home/tracking/tracking-express.html?submit=1&tracking-id=0
              label: []
              payment_method: cod
              source: api
              status: creating
              total:
                amount: 100
                currency: SAR
              cash_on_delivery:
                amount: '10.70'
                currency: SAR
              meta:
                app_id: null
                policy_options:
                  shipment_content_type:
                    - document
                    - dry
                    - food_stuff
                    - liquid
                  packaging_type:
                    - basket
                    - box
                    - buble_wrapper
                    - pallet
                    - paper_wrapper
                  boxes: 1
              ship_from:
                type: branch
                name: Riyadh
                email: ''
                phone: '0555555555'
                country: السعودية
                city: RIYADH
                address_line: >-
                  7687 طريق الملك فهد الفرعي,الملك فهد,12262, 7687 طريق الملك
                  فهد الفرعي، الملك فهد، الرياض 12262 3010، السعودية,
                  RIYADH,السعودية
                street_number: 7687 طريق الملك فهد الفرعي
                block: الملك فهد
                postal_code: '12262'
                latitude: 24.7431373
                longitude: 46.6570741
                branch_id: 1723506348
              ship_to:
                type: address
                name: Username
                email: username@email.com
                phone: 055-555-555
                country: السعودية
                city: الرياض
                address_line: ' شارع 2345، الحي السلام 95128،, شارع عبدالله  سنابل السلام  مكة  السعوديه,, الرياض, السعودية'
                street_number: '2345'
                block: السلام
                postal_code: '95128'
                latitude: 21.382590509685
                longitude: 39.773191030685
              packages:
                - item_id: 2077288690
                  external_id: null
                  name: منتج تجريبي
                  sku: 6ytrrhrhr
                  price:
                    amount: '50.00'
                    currency: SAR
                  quantity: 2
                  weight:
                    value: '1.00'
                    unit: kg
          pagination:
            count: 3
            total: 32
            perPage: 3
            currentPage: 1
            totalPages: 11
            links:
              next: https://company.com/shipments?page=2
      x-tags:
        - Responses
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ValidationResponse:
      type: object
      title: ValidationResponse
      properties:
        status:
          type: number
          description: Response status Code
          examples:
            - 422
        success:
          type: boolean
          description: Response flag
          examples:
            - false
        error:
          type: object
          properties:
            code:
              type: string
              description: Response code
              examples:
                - validation_field
            message:
              type: string
              description: Response message
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
          x-apidog-ignore-properties: []
      x-examples:
        Example:
          status: 422
          success: false
          error:
            code: validation_failed
            message: 'null'
            fields:
              '{field-name}':
                - The {field-label} field is required.
      x-tags:
        - Responses
      x-apidog-orders:
        - status
        - success
        - error
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

