# Apis Shipments  Update Shipment Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-shipments/Update-Shipment-Details-Salla-Merchant-API-Salla-Docs](#apis-shipments-update-shipment-details-salla-merchant-api-salla-docs)

---

## apis-shipments/Update-Shipment-Details-Salla-Merchant-API-Salla-Docs

# Update Shipment Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /shipments/{shipment_id}:
    put:
      summary: Update Shipment Details
      deprecated: false
      description: >-
        This endpoint allows you to update specific shipment details by passing
        the `shipment_id` as a path parameter. 



        :::danger[Breaking Change Notice]

        Effective January 20th, 2025, the status variable will be a **required**
        field in the request payload.

        :::


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `shipping.read_write`- Shipping Read & Write

        </Accordion>
      operationId: put-shipments-shipment_id
      tags:
        - Default module/Merchant API/APIs/Shipments
        - Shipments
      parameters:
        - name: shipment_id
          in: path
          description: >-
            Shipment ID. Get a list of Shipment IDs from
            [here](https://docs.salla.dev/5394232e0)
          required: true
          example: 362985662
          schema:
            type: number
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/put_shipmentDetails_request_body'
            example:
              shipment_number: '846984645'
              order_id: 76587644
              tracking_number: '54563653'
              tracking_link: https://api.shipengine.com/v1/labels/498498496/track
              status: delivered
              status_note: The shipment has been delivered
              pdf_label: >-
                https://api.shipengine.com/v1/downloads/10/F91fByOB-0aJJadf7JLeww/label-63563751.pdf
              cost: 40
              external_company_name: Salla Express
              policy_options:
                boxes: 3
                number_of_delivery_attempts: 2
                shipment_content_type: document
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                x-apidog-refs:
                  01HRRY394HDZVM1EA85BFPCYKS:
                    $ref: '#/components/schemas/shipment_response_body'
                    x-apidog-overrides:
                      data: &ref_1
                        type: object
                        x-apidog-refs:
                          01HRRYKERNKPMFJSA1CFJ0NPYN: &ref_2
                            $ref: '#/components/schemas/Shipment'
                            x-apidog-overrides:
                              status: &ref_0
                                type: string
                                description: Shipment Status
                                enum:
                                  - created
                                  - in_progress
                                  - delivering
                                  - delivered
                                  - shipped
                                  - cancelled
                                examples:
                                  - in_progress
                                x-apidog-enum:
                                  - value: created
                                    name: ''
                                    description: ''
                                  - value: in_progress
                                    name: ''
                                    description: ''
                                  - value: delivering
                                    name: ''
                                    description: ''
                                  - value: delivered
                                    name: ''
                                    description: ''
                                  - value: shipped
                                    name: ''
                                    description: ''
                                  - value: cancelled
                                    name: ''
                                    description: ''
                        x-apidog-orders:
                          - 01HRRYKERNKPMFJSA1CFJ0NPYN
                        properties:
                          id:
                            type: number
                            description: >-
                              A unique identifier for the shipment. Shipment
                              list can be found
                              [here](https://docs.salla.dev/api-5394232).
                            examples:
                              - 987654321
                          order_id:
                            type: number
                            description: >-
                              A unique identifier for the order associated with
                              the shipment. List of orders can be found
                              [here](https://docs.salla.dev/api-5394146)
                            examples:
                              - 123456789
                          order_reference_id:
                            type: number
                            description: >-
                              This field refers to a reference ID that can be
                              used to look up additional information about the
                              order
                            nullable: true
                          reference:
                            type: object
                            properties:
                              external_id:
                                type: string
                                description: >-
                                  A unique identifier for the shipment provided
                                  by the external shipping company, used for
                                  cross-system reference.
                              external_additional_id:
                                type: string
                                description: >-
                                  An alternate or supplementary identifier for
                                  the shipment, used for additional tracking or
                                  internal references.
                            x-apidog-orders:
                              - external_id
                              - external_additional_id
                            x-apidog-ignore-properties: []
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
                            description: Date and time of shipment creations.
                            required:
                              - date
                              - timezone_type
                              - timezone
                            x-apidog-ignore-properties: []
                          type:
                            type: string
                            description: >-
                              Specifies the nature of the shipment, indicating
                              whether it is an outgoing delivery to a customer
                              ("shipment") or a return shipment sent back to the
                              merchant ("return").
                            enum:
                              - return
                              - shipment
                            examples:
                              - shipment
                            x-apidog-enum:
                              - value: return
                                name: ''
                                description: A shipment returned to the Merchant
                              - value: shipment
                                name: ''
                                description: A shipment sent to customer
                          courier_id:
                            type: integer
                            description: >-
                              Shipment courier identification. Find a complete
                              list of Shipment companies
                              [here](api-5578809/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
                            examples:
                              - 1723506348
                          courier_name:
                            type: string
                            description: >-
                              The full name of the courier or shipping company
                              responsible for transporting and delivering the
                              shipment to its destination.
                            examples:
                              - Semsa
                          courier_logo:
                            type: string
                            description: >-
                              A URL pointing to the official logo image of the
                              courier or shipping company, which can be used for
                              display in user interfaces or documentation.
                            examples:
                              - https://semsa.com/assets/logo.png
                          external_company_name:
                            type: string
                            description: >-
                              The name of the external shipping company used for
                              shipments created via the API, if different from
                              the standard courier list.
                          shipping_number:
                            type: string
                            description: >-
                              The unique shipping number assigned to the
                              shipment by the courier, used for internal
                              tracking and reference within the courier's
                              system.
                            examples:
                              - '192837465'
                          tracking_number:
                            type: string
                            description: >-
                              The unique tracking number provided by the
                              courier, allowing customers and merchants to track
                              the shipment's delivery status online.
                            examples:
                              - '918273645'
                          pickup_id:
                            type: number
                            description: >-
                              A unique identifier for the shipment's pickup
                              event, used to reference and manage the pickup
                              process with the courier or logistics provider.
                          trackable:
                            type: boolean
                            description: >-
                              Indicates whether the shipment can be tracked
                              online using a tracking number or link provided by
                              the courier.
                            examples:
                              - true
                          tracking_link:
                            type: string
                            description: >-
                              A direct URL to the courier's online tracking page
                              for this shipment, allowing real-time status
                              updates and location information.
                            examples:
                              - https://semsa.com/tracking/order_url.com
                          label:
                            type: object
                            properties:
                              format:
                                type: string
                                description: >-
                                  The file format of the shipment label (e.g.,
                                  PDF, PNG), which can be used for printing or
                                  digital reference.
                                examples:
                                  - pdf
                              url:
                                type: string
                                description: >-
                                  A direct URL to download or view the shipment
                                  label file, which contains all necessary
                                  shipping and tracking information.
                                examples:
                                  - >-
                                    https://semsa.com/tracking/order_url_file.pdf
                            x-apidog-orders:
                              - format
                              - url
                            description: >-
                              Detailed information about the shipment label,
                              including its file format and a link to access the
                              label.
                            required:
                              - format
                              - url
                            x-apidog-ignore-properties: []
                          payment_method:
                            type: string
                            description: >-
                              Specifies the payment method used for the
                              shipment, such as cash on delivery (cod) or
                              pre-paid, determining how the shipping cost is
                              settled.
                            enum:
                              - cod
                              - pre_paid
                            examples:
                              - cod
                            x-apidog-enum:
                              - value: cod
                                name: ''
                                description: Cash on delivery payment type
                              - value: pre_paid
                                name: ''
                                description: Pre-paid payment type.
                          source:
                            type: string
                            description: >-
                              Indicates the origin of the shipment request, such
                              as the dashboard, API, or other system sources.
                            examples:
                              - dashboard
                          status: *ref_0
                          total:
                            type: object
                            properties:
                              amount:
                                type: number
                                description: >-
                                  The total monetary value of the shipment,
                                  representing the sum of all items and services
                                  included.
                                examples:
                                  - 200
                              currency:
                                type: string
                                description: >-
                                  The currency code (e.g., SAR, USD) in which
                                  the total shipment amount is denominated.
                                examples:
                                  - sar
                            x-apidog-orders:
                              - amount
                              - currency
                            description: >-
                              Details about the total value and currency of the
                              shipment.
                            required:
                              - amount
                              - currency
                            x-apidog-ignore-properties: []
                          cash_on_delivery:
                            type: object
                            properties:
                              amount:
                                type: number
                                description: >-
                                  The amount to be collected from the recipient
                                  upon delivery if the payment method is cash on
                                  delivery.
                                examples:
                                  - 200
                              currency:
                                type: string
                                description: >-
                                  The currency code (e.g., SAR, USD) for the
                                  cash on delivery amount.
                                examples:
                                  - sar
                            x-apidog-orders:
                              - amount
                              - currency
                            description: >-
                              Details about the cash on delivery amount and its
                              currency.
                            required:
                              - amount
                              - currency
                            x-apidog-ignore-properties: []
                          is_international:
                            type: boolean
                            description: >-
                              Indicates whether the shipment is being sent to a
                              destination outside the origin country
                              (international shipping).
                            examples:
                              - true
                          total_weight:
                            type: object
                            properties:
                              value:
                                type: number
                                description: >-
                                  The total weight of the shipment, including
                                  all packages, measured in the specified units.
                                examples:
                                  - 1.5
                              units:
                                type: string
                                description: >-
                                  The unit of measurement for the total weight
                                  (e.g., kg, g, lb, oz).
                                examples:
                                  - kg
                            x-apidog-orders:
                              - value
                              - units
                            description: >-
                              Information about the total weight of the shipment
                              and its measurement units.
                            required:
                              - value
                              - units
                            x-apidog-ignore-properties: []
                          billing_account:
                            type: string
                            description: >-
                              Indicates which billing account is used for the
                              shipment charges, such as the merchant's own
                              account or a platform account (e.g., Salla).
                            enum:
                              - salla
                              - merchant
                            x-apidog-enum:
                              - value: salla
                                name: ''
                                description: The Merchant uses Salla AWBs
                              - value: merchant
                                name: ''
                                description: The Merchant uses own account
                          description:
                            type: string
                            description: >-
                              A brief summary or explanation of the contents or
                              purpose of the shipment.
                          remarks:
                            type: string
                            description: >-
                              Any additional notes, comments, or special
                              delivery instructions related to the shipment.
                          shipping_route:
                            type: object
                            properties:
                              id:
                                type: string
                                description: The unique identifier of the shipping route.
                              name:
                                type: string
                                description: >-
                                  The display name of the route assigned to the
                                  shipment.
                            x-apidog-orders:
                              - id
                              - name
                            required:
                              - id
                              - name
                            description: The delivery route assigned to a shipping order
                            x-apidog-ignore-properties: []
                            nullable: true
                          service_types:
                            type: array
                            items:
                              type: string
                            description: >-
                              A list of service types requested for the
                              shipment, Example:
                              `domestic`,`international`,`normal`,
                              `fulfillment`,`heavy`,`express`,`cash_on_delivery`,`cold`
                          packages:
                            type: array
                            items:
                              type: object
                              properties:
                                item_id:
                                  type: integer
                                  description: >-
                                    A unique identifier for the item within the
                                    package, used for inventory and tracking
                                    purposes.
                                  examples:
                                    - 2077288690
                                external_id:
                                  type: integer
                                  description: >-
                                    An external identifier for the item, which
                                    may be used by third-party systems or
                                    integrations.
                                  examples:
                                    - 909112677
                                  nullable: true
                                name:
                                  type: string
                                  description: >-
                                    The name or title of the item contained in
                                    the package.
                                  examples:
                                    - Package 1
                                sku:
                                  type: string
                                  description: >-
                                    The Stock Keeping Unit (SKU) code assigned
                                    to the item for inventory management.
                                  examples:
                                    - SKU-123-456
                                price:
                                  type: object
                                  properties:
                                    amount:
                                      type: number
                                      description: >-
                                        The price of a single unit of the item
                                        in the specified currency.
                                      examples:
                                        - 200
                                    currency:
                                      type: string
                                      description: >-
                                        The currency code for the item's price
                                        (e.g., SAR, USD).
                                      examples:
                                        - sar
                                  x-apidog-orders:
                                    - amount
                                    - currency
                                  x-apidog-ignore-properties: []
                                quantity:
                                  type: integer
                                  description: >-
                                    The number of units of the item included in
                                    the package.
                                  examples:
                                    - 2
                                weight:
                                  type: object
                                  properties:
                                    value:
                                      type: integer
                                      description: >-
                                        The weight of a single unit of the item,
                                        measured in the specified units.
                                      examples:
                                        - 2
                                    units:
                                      type: string
                                      description: >-
                                        The unit of measurement for the item's
                                        weight (e.g., kg, g, lb, oz).
                                      enum:
                                        - kg
                                        - g
                                        - lb
                                        - oz
                                      x-stoplight:
                                        id: q3n10oje63ua9
                                      examples:
                                        - kg
                                      x-apidog-enum:
                                        - value: kg
                                          name: ''
                                          description: Weight in Kilo Grams
                                        - value: g
                                          name: ''
                                          description: Weight in Grams
                                        - value: lb
                                          name: ''
                                          description: Weight in Pounds
                                        - value: oz
                                          name: ''
                                          description: Weight in Ounces
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
                                          A label describing a product variation
                                          or choice, such as size, color, or
                                          material.
                                      values:
                                        type: array
                                        items:
                                          type: object
                                          properties:
                                            name:
                                              type: string
                                              description: >-
                                                The descriptive label or text
                                                representing a specific choice or value
                                                within a product option.
                                            price:
                                              type: object
                                              properties:
                                                amount:
                                                  type: string
                                                  description: >-
                                                    The additional cost associated with this
                                                    option value, if any.
                                                currency:
                                                  type: string
                                                  description: >-
                                                    The currency code for the option value's
                                                    price.
                                              x-apidog-orders:
                                                - amount
                                                - currency
                                              required:
                                                - amount
                                                - currency
                                              x-apidog-ignore-properties: []
                                            value:
                                              type: string
                                              description: >-
                                                The actual value or selection for this
                                                product option.
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
                                          An array of possible values for this
                                          product option, each with its own name,
                                          value, and price.
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
                            description: >-
                              A list of packages included in the shipment, each
                              containing detailed information about the items,
                              quantities, weights, and options.
                          ship_from:
                            type: object
                            properties:
                              type:
                                type: string
                                description: >-
                                  Specifies the type of origin for the shipment,
                                  such as an address or branch location.
                                examples:
                                  - address
                              name:
                                type: string
                                description: >-
                                  The name of the sender or origin contact
                                  person for the shipment.
                                examples:
                                  - Username
                              email:
                                type: string
                                description: >-
                                  The email address of the sender or origin
                                  contact.
                                examples:
                                  - username@gmail.com
                              phone:
                                type: string
                                description: >-
                                  The phone number of the sender or origin
                                  contact.
                                examples:
                                  - 555-555-555
                              branch_id:
                                type: integer
                                description: >-
                                  The unique identifier for the branch or
                                  facility from which the shipment is sent, if
                                  applicable.
                                examples:
                                  - 194309
                              country:
                                type: string
                                description: >-
                                  The country from which the shipment is being
                                  sent.
                                examples:
                                  - Saudi Arabia
                              city:
                                type: string
                                description: >-
                                  The city from which the shipment is being
                                  sent.
                                examples:
                                  - Mecca
                              region:
                                type: object
                                properties:
                                  id:
                                    type: integer
                                    description: Region identifier
                                    examples:
                                      - 566146469
                                  name:
                                    type: string
                                    description: Region name
                                    examples:
                                      - منطقة مكة المكرمة
                                  code:
                                    type: string
                                    description: >-
                                      Region code as defined by national
                                      standards.
                                    examples:
                                      - MQ
                                x-apidog-orders:
                                  - id
                                  - name
                                  - code
                                required:
                                  - id
                                  - name
                                  - code
                                description: >-
                                  Represents the geographic region details for
                                  the address.
                                x-apidog-ignore-properties: []
                                nullable: true
                              address_line:
                                type: string
                                description: >-
                                  The street address or location details for the
                                  shipment's origin.
                                examples:
                                  - Mecca Street
                              street_number:
                                type: string
                                description: >-
                                  The street number for the shipment's origin
                                  address, if applicable.
                                nullable: true
                              block:
                                type: string
                                description: >-
                                  The block or building identifier for the
                                  shipment's origin address, if applicable. 
                                examples:
                                  - حي المشاعل
                                nullable: true
                              short_address:
                                type: string
                                description: >-
                                  A compact 8-character Saudi address code (4
                                  letters + 4 digits), e.g., RHMA3184.

                                  It provides a simplified, precise version of
                                  the National Address to speed up delivery and
                                  reduce input errors.
                                examples:
                                  - RHMA3184
                                nullable: true
                              building_number:
                                type: number
                                description: >-
                                  The National Address building number
                                  associated with the location.
                                examples:
                                  - 2846
                                nullable: true
                              additional_number:
                                type: number
                                description: >-
                                  An additional National Address identifier used
                                  for more precise location specification.
                                examples:
                                  - 7556
                                nullable: true
                              postal_code:
                                type: string
                                description: >-
                                  The postal or ZIP code for the shipment's
                                  origin address, if applicable.
                                nullable: true
                              latitude:
                                type: number
                                description: >-
                                  The latitude coordinate of the shipment's
                                  origin location, used for mapping and routing.
                                examples:
                                  - 10.2345
                              longitude:
                                type: number
                                description: >-
                                  The longitude coordinate of the shipment's
                                  origin location, used for mapping and routing.
                                examples:
                                  - 54.321
                            x-apidog-orders:
                              - type
                              - name
                              - email
                              - phone
                              - branch_id
                              - country
                              - city
                              - region
                              - address_line
                              - street_number
                              - block
                              - short_address
                              - building_number
                              - additional_number
                              - postal_code
                              - latitude
                              - longitude
                            description: >-
                              Detailed information about the sender or origin
                              location of the shipment, including contact
                              details and address.
                            required:
                              - type
                              - name
                              - email
                              - phone
                              - branch_id
                              - country
                              - city
                              - address_line
                              - street_number
                              - block
                              - short_address
                              - building_number
                              - additional_number
                              - postal_code
                              - latitude
                              - longitude
                            x-apidog-ignore-properties: []
                          ship_to:
                            type: object
                            properties:
                              type:
                                type: string
                                description: >-
                                  Specifies the type of destination for the
                                  shipment, such as an address or branch
                                  location.
                                examples:
                                  - address
                              name:
                                type: string
                                description: >-
                                  The name of the recipient or destination
                                  contact person for the shipment.
                                examples:
                                  - Username1
                              email:
                                type: string
                                description: >-
                                  The email address of the recipient or
                                  destination contact.
                                examples:
                                  - username1@gmail.com
                              phone:
                                type: string
                                description: >-
                                  The phone number of the recipient or
                                  destination contact.
                                examples:
                                  - 555-555-554
                              country:
                                type: string
                                description: >-
                                  The country to which the shipment is being
                                  sent.
                                examples:
                                  - Saudi Arabia
                              city:
                                type: string
                                description: The city to which the shipment is being sent.
                                examples:
                                  - Jeddah
                              region:
                                type: object
                                properties:
                                  id:
                                    type: integer
                                    description: Region identifier
                                    examples:
                                      - 566146469
                                  name:
                                    type: string
                                    description: Region name
                                    examples:
                                      - منطقة مكة المكرمة
                                  code:
                                    type: string
                                    description: >-
                                      Region code as defined by national
                                      standards.
                                    examples:
                                      - MQ
                                x-apidog-orders:
                                  - id
                                  - name
                                  - code
                                required:
                                  - id
                                  - name
                                  - code
                                description: >-
                                  Represents the geographic region details for
                                  the address.
                                x-apidog-ignore-properties: []
                                nullable: true
                              address_line:
                                type: string
                                description: >-
                                  The street address or location details for the
                                  shipment's destination.
                                examples:
                                  - Tahlia Street
                              street_number:
                                type: string
                                description: >-
                                  The street number for the shipment's
                                  destination address.
                              block:
                                type: string
                                description: >-
                                  The block or building identifier for the
                                  shipment's destination address.
                                examples:
                                  - التنعيم
                              short_address:
                                type: string
                                description: >-
                                  A compact 8-character Saudi address code (4
                                  letters + 4 digits), e.g., RHMA3184.

                                  It provides a simplified, precise version of
                                  the National Address to speed up delivery and
                                  reduce input errors.
                                examples:
                                  - RHMA3184
                                nullable: true
                              building_number:
                                type: number
                                description: >-
                                  The National Address building number
                                  associated with the location.
                                examples:
                                  - 2846
                                nullable: true
                              additional_number:
                                type: number
                                description: >-
                                  An additional National Address identifier used
                                  for more precise location specification.
                                examples:
                                  - 7556
                                nullable: true
                              postal_code:
                                type: string
                                description: >-
                                  The postal or ZIP code for the shipment's
                                  destination address.
                              latitude:
                                type: number
                                description: >-
                                  The latitude coordinate of the shipment's
                                  destination location, used for mapping and
                                  routing.
                                examples:
                                  - 22.3213
                              longitude:
                                type: number
                                description: >-
                                  The longitude coordinate of the shipment's
                                  destination location, used for mapping and
                                  routing.
                                examples:
                                  - 11.2323
                            x-apidog-orders:
                              - type
                              - name
                              - email
                              - phone
                              - country
                              - city
                              - region
                              - address_line
                              - street_number
                              - block
                              - short_address
                              - building_number
                              - additional_number
                              - postal_code
                              - latitude
                              - longitude
                            description: >-
                              Detailed information about the recipient or
                              destination location of the shipment, including
                              contact details and address.
                            required:
                              - type
                              - name
                              - email
                              - phone
                              - country
                              - city
                              - address_line
                              - street_number
                              - block
                              - short_address
                              - building_number
                              - additional_number
                              - postal_code
                              - latitude
                              - longitude
                            x-apidog-ignore-properties: []
                          meta:
                            type: object
                            properties:
                              app_id:
                                type: integer
                                description: >-
                                  A unique identifier for the application or
                                  system that created or manages the shipment.
                                examples:
                                  - 153082
                              policy_options:
                                type: object
                                description: >-
                                  Custom shipment policy details. Each key
                                  represents a policy option (e.g.
                                  number_of_boxes, shipment_content_type), and
                                  the value is a string. This allows flexibility
                                  for any store-defined policy.
                                customProperties:
                                  type: string
                                  description: >-
                                    Each custom key here defines a store-level
                                    policy rule such as how many delivery
                                    attempts to make or the nature of the
                                    shipment contents. The values must be
                                    strings.
                                x-apidog-orders: []
                                properties: {}
                                x-apidog-ignore-properties: []
                            x-apidog-orders:
                              - app_id
                              - policy_options
                            description: >-
                              Metadata providing additional context about the
                              shipment, such as the originating application and
                              policy options.
                            required:
                              - app_id
                            x-apidog-ignore-properties: []
                        required:
                          - id
                          - order_id
                          - order_reference_id
                          - reference
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
                          - is_international
                          - total_weight
                          - billing_account
                          - service_types
                          - packages
                          - ship_from
                          - ship_to
                          - meta
                        x-apidog-ignore-properties:
                          - id
                          - order_id
                          - order_reference_id
                          - reference
                          - created_at
                          - type
                          - courier_id
                          - courier_name
                          - courier_logo
                          - external_company_name
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
                          - billing_account
                          - description
                          - remarks
                          - shipping_route
                          - service_types
                          - packages
                          - ship_from
                          - ship_to
                          - meta
                x-apidog-orders:
                  - 01HRRY394HDZVM1EA85BFPCYKS
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
                  data: *ref_1
                x-apidog-ignore-properties:
                  - status
                  - success
                  - data
              example:
                status: 200
                success: true
                data:
                  id: 362985662
                  order_id: 560695738
                  order_reference_id: 48927
                  reference:
                    external_id: null
                    external_additional_id: null
                  created_at:
                    date: '2023-01-12 14:19:08.000000'
                    timezone_type: 3
                    timezone: Asia/Riyadh
                  type: shipment
                  courier:
                    id: 814202285
                    name: DHL
                    logo: https://company.com/logo.png
                  external_company_name: Salla Express
                  shipping_number: '0'
                  tracking_number: '0'
                  pickup_id: null
                  trackable: true
                  tracking_link: >-
                    https://www.company/tracking/tracking-express.html?submit=1&tracking-id=12345
                  label: []
                  payment_method: cod
                  source: api
                  status:
                    id: 566146469
                    name: بإنتظار المراجعة
                    slug: under_review
                  total:
                    amount: 7000
                    currency: SAR
                  cash_on_delivery:
                    amount: 15
                    currency: SAR
                  billing_account: salla
                  description: null
                  remarks: null
                  service_types: []
                  shipping_route:
                    id: 1967988572
                    name: Dammam Route
                  packages:
                    - item_id: 2077288690
                      external_id: null
                      name: Apple Watch
                      sku: 6ytrrhrhr
                      price:
                        amount: '1000.00'
                        currency: SAR
                      quantity: 2
                      weight:
                        value: '0.10'
                        unit: kg
                    - item_id: 2077288690
                      external_id: null
                      name: Apple Iphone 14 Pro Max
                      sku: 6ytrrhrhr3332
                      price:
                        amount: '5000.00'
                        currency: SAR
                      quantity: 1
                      weight:
                        value: '0.50'
                        unit: kg
                  ship_from:
                    type: branch
                    branch_id: 1723506348
                    name: Riyadh
                    email: null
                    phone: '0555555555'
                    country: السعودية
                    city: الرياض
                    address_line: "7687 طريق الملك فهد الفرعي، الملك فهد، الرياض 12262\_3010، السعودية"
                    street_number: 7687 طريق الملك فهد الفرعي
                    block: الملك فهد
                    postal_code: '12262'
                    geo_coordinates:
                      lat: '24.7431373'
                      lng: '46.6570741'
                  ship_to:
                    type: address
                    name: Username
                    email: username@email.com
                    phone: 050-948-0868
                    country: السعودية
                    city: الرياض
                    address_line: شارع عبدالله  سنابل السلام  مكة  السعوديه
                    street_number: '2345'
                    block: السلام
                    postal_code: '95128'
                    geo_coordinates:
                      lat: '21.382590509685'
                      lng: '39.773191030685'
                  meta:
                    app_id: null
                    policy_options:
                      boxes: 2
          headers: {}
          x-apidog-name: Success
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
                    courier_id:
                      - حقل رقم الشركة مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: Shipment
      x-apidog-folder: Default module/Merchant API/APIs/Shipments
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394233-run
components:
  schemas:
    put_shipmentDetails_request_body:
      type: object
      properties:
        shipment_number:
          type: string
          description: >-
            A unique identifier for the shipment that distinguishes it from
            other shipments.
          examples:
            - 846984645
        order_id:
          type: integer
          description: >-
            The order ID that the shipment will be assigned, list of orders can
            be found [here](https://docs.salla.dev/api-5394146).
        tracking_number:
          type: string
          description: >-
            A unique identifier for the tracking information associated with the
            shipment.
          examples:
            - 54563653
        tracking_link:
          type: string
          description: >-
            A URL that provides a link to the tracking information for the
            shipment.
          examples:
            - https://xyz-shipping.com/v1/labels/498498496/track
        status:
          type: string
          description: >-
            The current status of the shipment.


            :::danger[]

            Effective January 20th, 2025, the status variable will be a
            **required** field in the request payload.
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
          examples:
            - delivered
          x-apidog-enum:
            - name: ''
              value: created
              description: Shipment has been registered and is ready for processing.
            - name: ''
              value: in_progress
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
            - name: ''
              value: delivering
              description: Courier is currently delivering the shipment.
            - name: ''
              value: delivered
              description: Shipment has been successfully delivered.
            - value: partially_delivered
              name: ''
              description: Only some items in the shipment were delivered.
            - name: ''
              value: shipped
              description: Shipment has left the origin warehouse.
            - name: ''
              value: cancelled
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
        pdf_label:
          type: string
          description: >-
            A PDF label that contains information about the shipment, such as
            the sender's and recipient's address, tracking number, and other
            relevant details.
          examples:
            - >-
              https://xyz-shipping/v1/downloads/10/F91fByOB-0aJJadf7JLeww/label-63563751.pdf
        cost:
          type: integer
          description: >-
            The actual cost of the shipment that the Merchant will be charged
            for, which is calculated per the shipping company's actual costs.
            Ensure to include VAT in the cost.
          examples:
            - 40
        status_note:
          type: string
          x-stoplight:
            id: jco7shenqo2av
          description: >-
            The note field provides additional shipment information relevant
            factors, as it is used to clarify the shipment status and provide
            context.
          examples:
            - Parcel has been picked up by our logistics partner
        external_company_name:
          type: string
          description: The name of the shipping company for shipments created via the API
        policy_options:
          type: object
          description: >-
            Custom shipment policy details. Each key represents a policy option
            (e.g. number_of_boxes, shipment_content_type), and the value is a
            string. This allows flexibility for any store-defined policy.
          customProperties:
            type: string
            description: >-
              Each custom key here defines a store-level policy rule such as how
              many delivery attempts to make or the nature of the shipment
              contents. The values must be strings.
          x-apidog-orders: []
          properties: {}
          x-apidog-ignore-properties: []
      required:
        - shipment_number
        - status
      x-apidog-orders:
        - shipment_number
        - order_id
        - tracking_number
        - tracking_link
        - status
        - pdf_label
        - cost
        - status_note
        - external_company_name
        - policy_options
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    shipment_response_body:
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
        data: *ref_2
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Shipment:
      type: object
      properties:
        id:
          type: number
          description: >-
            A unique identifier for the shipment. Shipment list can be found
            [here](https://docs.salla.dev/api-5394232).
          examples:
            - 987654321
        order_id:
          type: number
          description: >-
            A unique identifier for the order associated with the shipment. List
            of orders can be found [here](https://docs.salla.dev/api-5394146)
          examples:
            - 123456789
        order_reference_id:
          type: number
          description: >-
            This field refers to a reference ID that can be used to look up
            additional information about the order
          nullable: true
        reference:
          type: object
          properties:
            external_id:
              type: string
              description: >-
                A unique identifier for the shipment provided by the external
                shipping company, used for cross-system reference.
            external_additional_id:
              type: string
              description: >-
                An alternate or supplementary identifier for the shipment, used
                for additional tracking or internal references.
          x-apidog-orders:
            - external_id
            - external_additional_id
          x-apidog-ignore-properties: []
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
          description: Date and time of shipment creations.
          required:
            - date
            - timezone_type
            - timezone
          x-apidog-ignore-properties: []
        type:
          type: string
          description: >-
            Specifies the nature of the shipment, indicating whether it is an
            outgoing delivery to a customer ("shipment") or a return shipment
            sent back to the merchant ("return").
          enum:
            - return
            - shipment
          examples:
            - shipment
          x-apidog-enum:
            - value: return
              name: ''
              description: A shipment returned to the Merchant
            - value: shipment
              name: ''
              description: A shipment sent to customer
        courier_id:
          type: integer
          description: >-
            Shipment courier identification. Find a complete list of Shipment
            companies [here](api-5578809/?nav=01HNA8MH78MVX1S0DRXDHE3A1K)
          examples:
            - 1723506348
        courier_name:
          type: string
          description: >-
            The full name of the courier or shipping company responsible for
            transporting and delivering the shipment to its destination.
          examples:
            - Semsa
        courier_logo:
          type: string
          description: >-
            A URL pointing to the official logo image of the courier or shipping
            company, which can be used for display in user interfaces or
            documentation.
          examples:
            - https://semsa.com/assets/logo.png
        external_company_name:
          type: string
          description: >-
            The name of the external shipping company used for shipments created
            via the API, if different from the standard courier list.
        shipping_number:
          type: string
          description: >-
            The unique shipping number assigned to the shipment by the courier,
            used for internal tracking and reference within the courier's
            system.
          examples:
            - '192837465'
        tracking_number:
          type: string
          description: >-
            The unique tracking number provided by the courier, allowing
            customers and merchants to track the shipment's delivery status
            online.
          examples:
            - '918273645'
        pickup_id:
          type: number
          description: >-
            A unique identifier for the shipment's pickup event, used to
            reference and manage the pickup process with the courier or
            logistics provider.
        trackable:
          type: boolean
          description: >-
            Indicates whether the shipment can be tracked online using a
            tracking number or link provided by the courier.
          examples:
            - true
        tracking_link:
          type: string
          description: >-
            A direct URL to the courier's online tracking page for this
            shipment, allowing real-time status updates and location
            information.
          examples:
            - https://semsa.com/tracking/order_url.com
        label:
          type: object
          properties:
            format:
              type: string
              description: >-
                The file format of the shipment label (e.g., PDF, PNG), which
                can be used for printing or digital reference.
              examples:
                - pdf
            url:
              type: string
              description: >-
                A direct URL to download or view the shipment label file, which
                contains all necessary shipping and tracking information.
              examples:
                - https://semsa.com/tracking/order_url_file.pdf
          x-apidog-orders:
            - format
            - url
          description: >-
            Detailed information about the shipment label, including its file
            format and a link to access the label.
          required:
            - format
            - url
          x-apidog-ignore-properties: []
        payment_method:
          type: string
          description: >-
            Specifies the payment method used for the shipment, such as cash on
            delivery (cod) or pre-paid, determining how the shipping cost is
            settled.
          enum:
            - cod
            - pre_paid
          examples:
            - cod
          x-apidog-enum:
            - value: cod
              name: ''
              description: Cash on delivery payment type
            - value: pre_paid
              name: ''
              description: Pre-paid payment type.
        source:
          type: string
          description: >-
            Indicates the origin of the shipment request, such as the dashboard,
            API, or other system sources.
          examples:
            - dashboard
        status:
          type: string
          description: >-
            Current status of the shipment in the delivery process, such as
            created, in_progress, delivered, cancelled, etc.
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
          examples:
            - in_progress
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
        total:
          type: object
          properties:
            amount:
              type: number
              description: >-
                The total monetary value of the shipment, representing the sum
                of all items and services included.
              examples:
                - 200
            currency:
              type: string
              description: >-
                The currency code (e.g., SAR, USD) in which the total shipment
                amount is denominated.
              examples:
                - sar
          x-apidog-orders:
            - amount
            - currency
          description: Details about the total value and currency of the shipment.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        cash_on_delivery:
          type: object
          properties:
            amount:
              type: number
              description: >-
                The amount to be collected from the recipient upon delivery if
                the payment method is cash on delivery.
              examples:
                - 200
            currency:
              type: string
              description: >-
                The currency code (e.g., SAR, USD) for the cash on delivery
                amount.
              examples:
                - sar
          x-apidog-orders:
            - amount
            - currency
          description: Details about the cash on delivery amount and its currency.
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        is_international:
          type: boolean
          description: >-
            Indicates whether the shipment is being sent to a destination
            outside the origin country (international shipping).
          examples:
            - true
        total_weight:
          type: object
          properties:
            value:
              type: number
              description: >-
                The total weight of the shipment, including all packages,
                measured in the specified units.
              examples:
                - 1.5
            units:
              type: string
              description: >-
                The unit of measurement for the total weight (e.g., kg, g, lb,
                oz).
              examples:
                - kg
          x-apidog-orders:
            - value
            - units
          description: >-
            Information about the total weight of the shipment and its
            measurement units.
          required:
            - value
            - units
          x-apidog-ignore-properties: []
        billing_account:
          type: string
          description: >-
            Indicates which billing account is used for the shipment charges,
            such as the merchant's own account or a platform account (e.g.,
            Salla).
          enum:
            - salla
            - merchant
          x-apidog-enum:
            - value: salla
              name: ''
              description: The Merchant uses Salla AWBs
            - value: merchant
              name: ''
              description: The Merchant uses own account
        description:
          type: string
          description: >-
            A brief summary or explanation of the contents or purpose of the
            shipment.
        remarks:
          type: string
          description: >-
            Any additional notes, comments, or special delivery instructions
            related to the shipment.
        shipping_route:
          type: object
          properties:
            id:
              type: string
              description: The unique identifier of the shipping route.
            name:
              type: string
              description: The display name of the route assigned to the shipment.
          x-apidog-orders:
            - id
            - name
          required:
            - id
            - name
          description: The delivery route assigned to a shipping order
          x-apidog-ignore-properties: []
          nullable: true
        service_types:
          type: array
          items:
            type: string
          description: >-
            A list of service types requested for the shipment, Example:
            `domestic`,`international`,`normal`,
            `fulfillment`,`heavy`,`express`,`cash_on_delivery`,`cold`
        packages:
          type: array
          items:
            type: object
            properties:
              item_id:
                type: integer
                description: >-
                  A unique identifier for the item within the package, used for
                  inventory and tracking purposes.
                examples:
                  - 2077288690
              external_id:
                type: integer
                description: >-
                  An external identifier for the item, which may be used by
                  third-party systems or integrations.
                examples:
                  - 909112677
                nullable: true
              name:
                type: string
                description: The name or title of the item contained in the package.
                examples:
                  - Package 1
              sku:
                type: string
                description: >-
                  The Stock Keeping Unit (SKU) code assigned to the item for
                  inventory management.
                examples:
                  - SKU-123-456
              price:
                type: object
                properties:
                  amount:
                    type: number
                    description: >-
                      The price of a single unit of the item in the specified
                      currency.
                    examples:
                      - 200
                  currency:
                    type: string
                    description: The currency code for the item's price (e.g., SAR, USD).
                    examples:
                      - sar
                x-apidog-orders:
                  - amount
                  - currency
                x-apidog-ignore-properties: []
              quantity:
                type: integer
                description: The number of units of the item included in the package.
                examples:
                  - 2
              weight:
                type: object
                properties:
                  value:
                    type: integer
                    description: >-
                      The weight of a single unit of the item, measured in the
                      specified units.
                    examples:
                      - 2
                  units:
                    type: string
                    description: >-
                      The unit of measurement for the item's weight (e.g., kg,
                      g, lb, oz).
                    enum:
                      - kg
                      - g
                      - lb
                      - oz
                    x-stoplight:
                      id: q3n10oje63ua9
                    examples:
                      - kg
                    x-apidog-enum:
                      - value: kg
                        name: ''
                        description: Weight in Kilo Grams
                      - value: g
                        name: ''
                        description: Weight in Grams
                      - value: lb
                        name: ''
                        description: Weight in Pounds
                      - value: oz
                        name: ''
                        description: Weight in Ounces
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
                        A label describing a product variation or choice, such
                        as size, color, or material.
                    values:
                      type: array
                      items:
                        type: object
                        properties:
                          name:
                            type: string
                            description: >-
                              The descriptive label or text representing a
                              specific choice or value within a product option.
                          price:
                            type: object
                            properties:
                              amount:
                                type: string
                                description: >-
                                  The additional cost associated with this
                                  option value, if any.
                              currency:
                                type: string
                                description: >-
                                  The currency code for the option value's
                                  price.
                            x-apidog-orders:
                              - amount
                              - currency
                            required:
                              - amount
                              - currency
                            x-apidog-ignore-properties: []
                          value:
                            type: string
                            description: >-
                              The actual value or selection for this product
                              option.
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
                        An array of possible values for this product option,
                        each with its own name, value, and price.
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
          description: >-
            A list of packages included in the shipment, each containing
            detailed information about the items, quantities, weights, and
            options.
        ship_from:
          type: object
          properties:
            type:
              type: string
              description: >-
                Specifies the type of origin for the shipment, such as an
                address or branch location.
              examples:
                - address
            name:
              type: string
              description: >-
                The name of the sender or origin contact person for the
                shipment.
              examples:
                - Username
            email:
              type: string
              description: The email address of the sender or origin contact.
              examples:
                - username@gmail.com
            phone:
              type: string
              description: The phone number of the sender or origin contact.
              examples:
                - 555-555-555
            branch_id:
              type: integer
              description: >-
                The unique identifier for the branch or facility from which the
                shipment is sent, if applicable.
              examples:
                - 194309
            country:
              type: string
              description: The country from which the shipment is being sent.
              examples:
                - Saudi Arabia
            city:
              type: string
              description: The city from which the shipment is being sent.
              examples:
                - Mecca
            region:
              type: object
              properties:
                id:
                  type: integer
                  description: Region identifier
                  examples:
                    - 566146469
                name:
                  type: string
                  description: Region name
                  examples:
                    - منطقة مكة المكرمة
                code:
                  type: string
                  description: Region code as defined by national standards.
                  examples:
                    - MQ
              x-apidog-orders:
                - id
                - name
                - code
              required:
                - id
                - name
                - code
              description: Represents the geographic region details for the address.
              x-apidog-ignore-properties: []
              nullable: true
            address_line:
              type: string
              description: >-
                The street address or location details for the shipment's
                origin.
              examples:
                - Mecca Street
            street_number:
              type: string
              description: >-
                The street number for the shipment's origin address, if
                applicable.
              nullable: true
            block:
              type: string
              description: >-
                The block or building identifier for the shipment's origin
                address, if applicable. 
              examples:
                - حي المشاعل
              nullable: true
            short_address:
              type: string
              description: >-
                A compact 8-character Saudi address code (4 letters + 4 digits),
                e.g., RHMA3184.

                It provides a simplified, precise version of the National
                Address to speed up delivery and reduce input errors.
              examples:
                - RHMA3184
              nullable: true
            building_number:
              type: number
              description: >-
                The National Address building number associated with the
                location.
              examples:
                - 2846
              nullable: true
            additional_number:
              type: number
              description: >-
                An additional National Address identifier used for more precise
                location specification.
              examples:
                - 7556
              nullable: true
            postal_code:
              type: string
              description: >-
                The postal or ZIP code for the shipment's origin address, if
                applicable.
              nullable: true
            latitude:
              type: number
              description: >-
                The latitude coordinate of the shipment's origin location, used
                for mapping and routing.
              examples:
                - 10.2345
            longitude:
              type: number
              description: >-
                The longitude coordinate of the shipment's origin location, used
                for mapping and routing.
              examples:
                - 54.321
          x-apidog-orders:
            - type
            - name
            - email
            - phone
            - branch_id
            - country
            - city
            - region
            - address_line
            - street_number
            - block
            - short_address
            - building_number
            - additional_number
            - postal_code
            - latitude
            - longitude
          description: >-
            Detailed information about the sender or origin location of the
            shipment, including contact details and address.
          required:
            - type
            - name
            - email
            - phone
            - branch_id
            - country
            - city
            - address_line
            - street_number
            - block
            - short_address
            - building_number
            - additional_number
            - postal_code
            - latitude
            - longitude
          x-apidog-ignore-properties: []
        ship_to:
          type: object
          properties:
            type:
              type: string
              description: >-
                Specifies the type of destination for the shipment, such as an
                address or branch location.
              examples:
                - address
            name:
              type: string
              description: >-
                The name of the recipient or destination contact person for the
                shipment.
              examples:
                - Username1
            email:
              type: string
              description: The email address of the recipient or destination contact.
              examples:
                - username1@gmail.com
            phone:
              type: string
              description: The phone number of the recipient or destination contact.
              examples:
                - 555-555-554
            country:
              type: string
              description: The country to which the shipment is being sent.
              examples:
                - Saudi Arabia
            city:
              type: string
              description: The city to which the shipment is being sent.
              examples:
                - Jeddah
            region:
              type: object
              properties:
                id:
                  type: integer
                  description: Region identifier
                  examples:
                    - 566146469
                name:
                  type: string
                  description: Region name
                  examples:
                    - منطقة مكة المكرمة
                code:
                  type: string
                  description: Region code as defined by national standards.
                  examples:
                    - MQ
              x-apidog-orders:
                - id
                - name
                - code
              required:
                - id
                - name
                - code
              description: Represents the geographic region details for the address.
              x-apidog-ignore-properties: []
              nullable: true
            address_line:
              type: string
              description: >-
                The street address or location details for the shipment's
                destination.
              examples:
                - Tahlia Street
            street_number:
              type: string
              description: The street number for the shipment's destination address.
            block:
              type: string
              description: >-
                The block or building identifier for the shipment's destination
                address.
              examples:
                - التنعيم
            short_address:
              type: string
              description: >-
                A compact 8-character Saudi address code (4 letters + 4 digits),
                e.g., RHMA3184.

                It provides a simplified, precise version of the National
                Address to speed up delivery and reduce input errors.
              examples:
                - RHMA3184
              nullable: true
            building_number:
              type: number
              description: >-
                The National Address building number associated with the
                location.
              examples:
                - 2846
              nullable: true
            additional_number:
              type: number
              description: >-
                An additional National Address identifier used for more precise
                location specification.
              examples:
                - 7556
              nullable: true
            postal_code:
              type: string
              description: The postal or ZIP code for the shipment's destination address.
            latitude:
              type: number
              description: >-
                The latitude coordinate of the shipment's destination location,
                used for mapping and routing.
              examples:
                - 22.3213
            longitude:
              type: number
              description: >-
                The longitude coordinate of the shipment's destination location,
                used for mapping and routing.
              examples:
                - 11.2323
          x-apidog-orders:
            - type
            - name
            - email
            - phone
            - country
            - city
            - region
            - address_line
            - street_number
            - block
            - short_address
            - building_number
            - additional_number
            - postal_code
            - latitude
            - longitude
          description: >-
            Detailed information about the recipient or destination location of
            the shipment, including contact details and address.
          required:
            - type
            - name
            - email
            - phone
            - country
            - city
            - address_line
            - street_number
            - block
            - short_address
            - building_number
            - additional_number
            - postal_code
            - latitude
            - longitude
          x-apidog-ignore-properties: []
        meta:
          type: object
          properties:
            app_id:
              type: integer
              description: >-
                A unique identifier for the application or system that created
                or manages the shipment.
              examples:
                - 153082
            policy_options:
              type: object
              description: >-
                Custom shipment policy details. Each key represents a policy
                option (e.g. number_of_boxes, shipment_content_type), and the
                value is a string. This allows flexibility for any store-defined
                policy.
              customProperties:
                type: string
                description: >-
                  Each custom key here defines a store-level policy rule such as
                  how many delivery attempts to make or the nature of the
                  shipment contents. The values must be strings.
              x-apidog-orders: []
              properties: {}
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - app_id
            - policy_options
          description: >-
            Metadata providing additional context about the shipment, such as
            the originating application and policy options.
          required:
            - app_id
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - order_id
        - order_reference_id
        - reference
        - created_at
        - type
        - courier_id
        - courier_name
        - courier_logo
        - external_company_name
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
        - billing_account
        - description
        - remarks
        - shipping_route
        - service_types
        - packages
        - ship_from
        - ship_to
        - meta
      required:
        - id
        - order_id
        - order_reference_id
        - reference
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
        - billing_account
        - service_types
        - packages
        - ship_from
        - ship_to
        - meta
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

