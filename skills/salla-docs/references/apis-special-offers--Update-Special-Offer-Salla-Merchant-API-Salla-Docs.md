# Apis Special Offers  Update Special Offer Salla Merchant Api Salla Docs

## Table of Contents

- [apis-special-offers/Update-Special-Offer-Salla-Merchant-API-Salla-Docs](#apis-special-offers-update-special-offer-salla-merchant-api-salla-docs)

---

## apis-special-offers/Update-Special-Offer-Salla-Merchant-API-Salla-Docs

# Update Special Offer

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /specialoffers/{specialoffer}:
    put:
      summary: Update Special Offer
      deprecated: false
      description: >-
        This endpoint allows you to update special offer details by passing the
        `specialoffers` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `specialoffers.read_write`- Special Offers Read & Write

        </Accordion>
      operationId: Update-Special-Offer
      tags:
        - Default module/Merchant API/APIs/Special Offers
        - Special Offers
      parameters:
        - name: specialoffer
          in: path
          description: >-
            Unique identification number assigned to the Special Offer. List of
            Special Offers IDs can be found
            [here](https://docs.salla.dev/api-5394218)
          required: true
          example: 0
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/specialOffer_request_body'
            example:
              name: Offer with Countries Condition
              message: Buy One Get One Free
              applied_channel: browser_and_application
              offer_type: buy_x_get_y
              applied_to: product
              start_date: '2025-12-26'
              expiry_date: '2026-12-31'
              min_purchase_amount: 10
              min_items_count: 2
              buy:
                type: product
                min_amount: 10
                quantity: 1
                products:
                  - 1462551237
              get:
                type: product
                discount_type: percentage
                discount_amount: 50
                quantity: 1
                products:
                  - 1668259787
              countries:
                - 566146469
                - 1473353380
              select_by: mobile
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/specialOffer_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 476380627
                  name: Offer with Countries Condition
                  message: Buy One Get One Free
                  expiry_date: '2026-12-31 00:00:00'
                  start_date: '2026-01-26 00:00:00'
                  offer_type: buy_x_get_y
                  status: inactive
                  show_price_after_discount: false
                  show_discounts_table_message: false
                  countries:
                    - 566146469
                    - 1473353380
                  customer_groups: []
                  applied_to: product
                  select_by: mobile
                  options: []
                  based_on: null
                  buy:
                    type: product
                    quantity: 1
                    products: []
                  get:
                    type: product
                    discount_type: percentage
                    quantity: '1'
                    products: []
                    discount_amount: '50.00'
                  tiers: []
                  apply_type: null
                  with_current_cart: false
                  special_price: null
                  applied_with_coupon: false
                  scopes: []
                  exclude_sale_items: false
                  excluded_buy_products_ids: []
                  excluded_buy_categories_ids: []
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
                    specialoffers.read_write
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
                    expiry_date:
                      - يجب أن يكون تاريخ اليوم أو في المستقبل
                      - لا يتوافق حقل تاريخ نهاية العرض مع الشكل Y/m/d.
                    get.products:
                      - حقل المنتجات (مطلوب)
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: update
      x-salla-php-return-type: SpecialOffer
      x-apidog-folder: Default module/Merchant API/APIs/Special Offers
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394220-run
components:
  schemas:
    specialOffer_request_body:
      allOf:
        - type: object
          properties:
            name:
              type: string
              description: >-
                The title or label used to identify a specific promotional or
                discounted offer. 🌐 [Support
                multi-language](https://docs.salla.dev/doc-421122)
            message:
              type: string
              description: >-
                A brief statement or communication that conveys the details or
                benefits of a specific promotional or discount offer. 🌐
                [Support multi-language](https://docs.salla.dev/doc-421122)
            applied_channel:
              type: string
              description: >-
                The specific platforms, channels, or methods through which a
                promotional or special offer is made available or applied.
              enum:
                - browser
                - browser_and_application
            offer_type:
              type: string
              description: >-
                The category or nature of a particular promotional or discount
                offer, such as buy-x get-y.
              enum:
                - buy_x_get_y
                - percentage
                - fixed_amount
                - discounts_table
                - special_price
              x-apidog-enum:
                - name: ''
                  value: buy_x_get_y
                  description: ''
                - name: ''
                  value: percentage
                  description: ''
                - name: ''
                  value: fixed_amount
                  description: ''
                - name: ''
                  value: discounts_table
                  description: ''
                - value: special_price
                  name: ''
                  description: ''
            applied_to:
              type: string
              description: >-
                The specific products, services, or items to which a particular
                promotional or discount offer is intended or allowed to be used
                or applied, specifying what the offer covers within a product or
                service catalog.
              enum:
                - order
                - product
                - category
                - paymentMethod
            start_date:
              type: string
              description: >-
                The date on which a promotional or discount offer start, before
                which it is not permitted to take advantage of the offer's
                benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            expiry_date:
              type: string
              description: >-
                The date on which a promotional or discount offer expires or
                becomes no longer valid, after which it is not permitted to take
                advantage of the offer's benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            min_purchase_amount:
              type: number
              description: >-
                The total minimum order amount to be purchased for this offer to
                be activated
            min_items_count:
              type: number
              description: The minimum order items count to activate this offer.
            buy:
              type: object
              description: Specifics on items required for offer eligibility.
              properties:
                type:
                  type: string
                  description: >-
                    Product Type to buy to be eligible for the special offer.
                    Required if `offer_type = buy_x_get_y`
                  enum:
                    - category
                    - product
                quantity:
                  type: number
                  description: >-
                    Product Quantity to buy to be eligible for the special
                    offer. Required if `offer_type = buy_x_get_y`
                products:
                  type: array
                  uniqueItems: true
                  description: >-
                    The Products to be purchased that are included in the
                    special offer. Make sure to pass the Product IDs in an
                    array. This field is mandatory when `buy.type` is set to
                    `product`.
                  items: &ref_0
                    $ref: '#/components/schemas/ProductCard'
                categories:
                  type: array
                  description: >
                    The Categories included in the special offer. Make sure to
                    pass the Category IDs in an array. This field is mandatory
                    when `buy.type` is set to `category`.
                  items: &ref_1
                    $ref: '#/components/schemas/Category'
              x-apidog-orders:
                - type
                - quantity
                - products
                - categories
              x-apidog-ignore-properties: []
            get:
              type: object
              description: Specifics of the offer.
              properties:
                type:
                  type: string
                  description: The type of the offer.
                discount_type:
                  type: string
                  description: >-
                    Discount Type to get if eligible for the special offer.
                    Required if `offer_type = buy_x_get_y`
                  enum:
                    - 'percentage '
                    - free-product
                quantity:
                  type: integer
                  description: >-
                    Product Quantity to get if eligible for the special offer.
                    Required if `offer_type = buy_x_get_y`
                products:
                  type: array
                  uniqueItems: true
                  description: >-
                    The Products to get if eligible for the special offer that
                    are included in the special offer. Make sure to pass the
                    Product IDs in an array. This field is mandatory when
                    `get.type` is set to `product`.
                  items: *ref_0
                categories:
                  type: array
                  description: >
                    The Categories included in the special offer. Make sure to
                    pass the Product IDs in an array. This field is mandatory
                    when `get.type` is set to `category`.
                  items: *ref_1
              x-apidog-orders:
                - type
                - discount_type
                - quantity
                - products
                - categories
              x-apidog-ignore-properties: []
            price:
              type: string
              description: >-
                Required if the offer type is `special_price`. Specifies the
                special price that the customer will get with the offer (tax
                exclusive).
            quantity:
              type: string
              description: >-
                Required if the offer type is `special_price`. Specifies the
                quantity that must be added to the cart for the offer to apply.
            scopes_ids:
              type: string
              description: >-
                Specifies the scopes ids for the markets which the offer applies
                to
            countries:
              type: array
              items:
                type: integer
              description: A list of customer countries that the offer applies to.
            select_by:
              type: string
              description: >-
                Required if `countries` array is provided. Specifies whether the
                customer country should be determined based on `mobile`,
                `shipping` or `ip`
              enum:
                - mobile
                - shipping
                - ip
              x-apidog-enum:
                - value: mobile
                  name: ''
                  description: ''
                - value: shipping
                  name: ''
                  description: ''
                - value: ip
                  name: ''
                  description: ''
            customer_groups:
              type: array
              items:
                type: integer
              description: A list of customer groups which the offer applies to.
          x-apidog-orders:
            - name
            - message
            - applied_channel
            - offer_type
            - applied_to
            - start_date
            - expiry_date
            - min_purchase_amount
            - min_items_count
            - buy
            - get
            - price
            - quantity
            - scopes_ids
            - countries
            - select_by
            - customer_groups
          description: 'Other Offer Types '
          required:
            - name
            - applied_channel
            - offer_type
            - applied_to
            - start_date
            - expiry_date
          title: ''
          x-apidog-ignore-properties: []
        - type: object
          properties:
            name:
              type: string
              description: >-
                The title or label used to identify a specific promotional or
                discounted offer. 🌐 [Support multi-language](doc-421122)
            applied_channel:
              type: string
              description: >-
                The specific platforms, channels, or methods through which a
                promotional or special offer is made available or applied.
              enum:
                - browser
                - browser_and_application
            offer_type:
              type: string
              description: >-
                The category or nature of a particular promotional or discount
                offer, such as buy-x get-y.
              enum:
                - discounts_table
              x-apidog-enum:
                - name: ''
                  value: discounts_table
                  description: ''
            applied_to:
              type: string
              description: >-
                The specific products, services, or items to which a particular
                promotional or discount offer is intended or allowed to be used
                or applied, specifying what the offer covers within a product or
                service catalog.
              enum:
                - order
                - product
                - category
              x-apidog-enum:
                - name: ''
                  value: order
                  description: ''
                - name: ''
                  value: product
                  description: ''
                - name: ''
                  value: category
                  description: ''
            start_date:
              type: string
              description: >-
                The date on which a promotional or discount offer start, before
                which it is not permitted to take advantage of the offer's
                benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            expiry_date:
              type: string
              description: >-
                The date on which a promotional or discount offer expires or
                becomes no longer valid, after which it is not permitted to take
                advantage of the offer's benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            status:
              type: string
              enum:
                - active
                - inactive
              description: Special Offer's status, either `active` or `inactive`
              x-apidog-enum:
                - name: ''
                  value: active
                  description: Active Special Offer
                - name: ''
                  value: inactive
                  description: Inactive Special Offer
            applied_with_coupon:
              type: boolean
              description: Whether or not the offer should be applied with a valid coupon
            buy:
              type: object
              properties:
                categories:
                  type: array
                  items:
                    type: integer
                    description: >-
                      Category IDs. Get a list of Category IDs from
                      [here](https://docs.salla.dev/api-5394207)
                  description: Required if `applied_to` is set to `category`
                products:
                  type: array
                  items:
                    type: integer
                    description: >-
                      Product IDs. Get a list of Product IDs from
                      [here](https://docs.salla.dev/api-5394168)
                  description: Required if `applied_to` is set to `product`
              x-apidog-orders:
                - categories
                - products
              x-apidog-ignore-properties: []
            discounts_table:
              type: array
              items:
                type: object
                properties:
                  quantity:
                    type: string
                    description: Quantity to buy
                  discount:
                    type: string
                    description: Discount to get
                x-apidog-orders:
                  - quantity
                  - discount
                x-apidog-ignore-properties: []
              description: >-
                Tiered discount in the special offer. Required if `offer_type`
                is `discounts_table`
          x-apidog-orders:
            - name
            - applied_channel
            - offer_type
            - applied_to
            - start_date
            - expiry_date
            - status
            - applied_with_coupon
            - buy
            - discounts_table
          required:
            - name
            - applied_channel
            - offer_type
            - applied_to
            - expiry_date
          title: ''
          description: Discount Table Offer Type
          x-apidog-ignore-properties: []
        - type: object
          properties:
            name:
              type: string
              description: >-
                The title or label used to identify a specific promotional or
                discounted offer. 🌐 [Support multi-language](doc-421122)
            applied_channel:
              type: string
              description: >-
                The specific platforms, channels, or methods through which a
                promotional or special offer is made available or applied.
              enum:
                - browser
                - browser_and_application
            offer_type:
              type: string
              description: >-
                The category or nature of a particular promotional or discount
                offer, such as `cart_offer`.
              enum:
                - cart_offer
              x-apidog-enum:
                - name: ''
                  value: cart_offer
                  description: ''
            based_on:
              type: string
              description: Offer calculation based on `order_amount` or `products_count`
              enum:
                - order_amount
                - products_count
              x-apidog-enum:
                - name: ''
                  value: order_amount
                  description: ''
                - name: ''
                  value: products_count
                  description: ''
            start_date:
              type: string
              description: >-
                The date on which a promotional or discount offer start, before
                which it is not permitted to take advantage of the offer's
                benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            expiry_date:
              type: string
              description: >-
                The date on which a promotional or discount offer expires or
                becomes no longer valid, after which it is not permitted to take
                advantage of the offer's benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            status:
              type: string
              enum:
                - active
                - inactive
              description: Special Offer's status, either `active` or `inactive`
              x-apidog-enum:
                - name: ''
                  value: active
                  description: Active Special Offer
                - name: ''
                  value: inactive
                  description: Inactive Special Offer
            applied_with_coupon:
              type: boolean
              description: Whether or not the offer should be applied with a valid coupon
            options:
              type: array
              items:
                type: object
                properties:
                  discount_apply_type:
                    type: string
                    description: >-
                      Specifies whether the offer discount will be applied as a
                      percentage or fixed amount.
                    enum:
                      - percentage
                      - fixed
                    x-apidog-enum:
                      - value: percentage
                        name: ''
                        description: ''
                      - value: fixed
                        name: ''
                        description: ''
                  condition_threshold:
                    type: number
                    description: >-
                      Minimum total purchase required to apply the offer,
                      order_amount value or products_count value
                  max_customer_discount:
                    type: string
                    description: >-
                      Required if `discount_apply_type` is percentage. Specifies
                      the maximum discount amount per customer.
                  discount_amount:
                    type: string
                    description: >-
                      The discount amount depending on the `discount_apply_type`
                      it can represent a percentage or a fixed amount.
                x-apidog-orders:
                  - discount_apply_type
                  - condition_threshold
                  - max_customer_discount
                  - discount_amount
                required:
                  - discount_apply_type
                  - condition_threshold
                  - discount_amount
                x-apidog-ignore-properties: []
          x-apidog-orders:
            - name
            - applied_channel
            - offer_type
            - based_on
            - start_date
            - expiry_date
            - status
            - applied_with_coupon
            - options
          required:
            - name
            - applied_channel
            - offer_type
            - based_on
            - start_date
            - expiry_date
            - options
          title: ''
          description: Cart Offer Type
          x-apidog-ignore-properties: []
        - type: object
          properties:
            name:
              type: string
              description: >-
                The title or label used to identify a specific promotional or
                discounted offer. 🌐 [Support
                multi-language](https://docs.salla.dev/doc-421122)
            message:
              type: string
              description: >-
                A brief statement or communication that conveys the details or
                benefits of a specific promotional or discount offer. 🌐
                [Support multi-language](https://docs.salla.dev/doc-421122)
            applied_channel:
              type: string
              description: >-
                The specific platforms, channels, or methods through which a
                promotional or special offer is made available or applied.
              enum:
                - browser
                - browser_and_application
            offer_type:
              type: string
              description: >-
                The category or nature of a particular promotional or discount
                offer, such as buy-x get-y.
              enum:
                - tiered_offer
              x-apidog-enum:
                - value: tiered_offer
                  name: ''
                  description: ''
            applied_to:
              type: string
              description: >-
                The specific products, services, or items to which a particular
                promotional or discount offer is intended or allowed to be used
                or applied, specifying what the offer covers within a product or
                service catalog.
              enum:
                - order
                - product
                - category
                - paymentMethod
            start_date:
              type: string
              description: >-
                The date on which a promotional or discount offer start, before
                which it is not permitted to take advantage of the offer's
                benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            expiry_date:
              type: string
              description: >-
                The date on which a promotional or discount offer expires or
                becomes no longer valid, after which it is not permitted to take
                advantage of the offer's benefits.


                **Ensure to follow on the format of the date.**
              format: date-time
            scopes_ids:
              type: string
              description: >-
                Specifies the scopes ids for the markets which the offer applies
                to.
            countries:
              type: array
              items:
                type: integer
              description: A list of customer countries that the offer applies to.
            select_by:
              type: string
              description: >-
                Required if `countries` array is provided. Specifies whether the
                customer country should be determined based on `mobile`,
                `shipping` or `ip`
            customer_groups:
              type: string
              description: 'A list of customer groups which the offer applies to. '
            tiers:
              type: array
              items:
                type: object
                properties:
                  name:
                    type: string
                    description: Name of the tier
                  discount:
                    type: string
                    description: The discount value
                  min_purchases:
                    type: string
                    description: The minimum value to apply the discount
                  type:
                    type: string
                    description: Type of dicount whether its percentage or fixed
                    enum:
                      - fixed
                      - percentage
                    x-apidog-enum:
                      - value: fixed
                        name: ''
                        description: ''
                      - value: percentage
                        name: ''
                        description: ''
                x-apidog-orders:
                  - name
                  - discount
                  - min_purchases
                  - type
                required:
                  - name
                  - discount
                  - min_purchases
                  - type
                x-apidog-ignore-properties: []
              description: List of tiers offered.
            apply_type:
              type: string
              description: min_external_purchases or min_purchases
              enum:
                - min_purchases
                - min_external_purchases
              x-apidog-enum:
                - value: min_purchases
                  name: ''
                  description: ''
                - value: min_external_purchases
                  name: ''
                  description: ''
            with_current_cart:
              type: boolean
              description: >-
                Specifies whether the current cart value should be included in
                the calculation
            applied_with_coupon:
              type: boolean
              description: Whether or not the offer should be applied with a valid coupon
            exclude_sale_products:
              type: boolean
              description: >-
                Specifies whether the offer should be applied to sale products
                or not
            excluded_buy_products_ids:
              type: array
              items:
                type: integer
              description: >-
                Array of product Ids execluded from the offer. Get a list of
                product ids [here](https://docs.salla.dev/5394168e0)
            excluded_buy_categories_ids:
              type: array
              items:
                type: integer
              description: Array of category Ids execluded from the offer
          x-apidog-orders:
            - name
            - message
            - applied_channel
            - offer_type
            - applied_to
            - start_date
            - expiry_date
            - scopes_ids
            - countries
            - select_by
            - customer_groups
            - tiers
            - apply_type
            - with_current_cart
            - applied_with_coupon
            - exclude_sale_products
            - excluded_buy_products_ids
            - excluded_buy_categories_ids
          description: Tiered Offers
          required:
            - name
            - applied_channel
            - offer_type
            - applied_to
            - tiers
            - apply_type
          title: ''
          x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Category:
      type: object
      title: Category
      x-tags:
        - Models
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            Category ID, is a unique identifier assigned to a specific product
            category, facilitating organized classification and efficient
            management of products within a similar group. List of categories
            can be found [here](https://docs.salla.dev/api-5394207).
        name:
          type: string
          description: >-
            Category name is a descriptive label assigned to a product category,
            aiding in clear identification and organization of related products.
            🌐 [Support multi-language](doc-421122)
        image:
          type: string
          description: The category image
        urls:
          $ref: '#/components/schemas/URLs'
        parent_id:
          type: integer
          description: >-
            Category Parent ID refers to the unique identifier assigned to the
            parent category of a subcategory, establishing a hierarchical
            relationship between different levels of product classification.
        sort_order:
          type: integer
          description: 'The sequence or arrangement of categories when displayed to users. '
          nullable: true
        status:
          type: string
          description: >-
            The category status indicates whether the category is currently
            visible and accessible to users `active` or intentionally concealed
            from view `hidden`. It essentially controls whether the category is
            publicly displayed or kept private within the system.
          enum:
            - active
            - hidden
          x-apidog-enum:
            - value: active
              name: ''
              description: The category is active and visible.
            - value: hidden
              name: ''
              description: The category is inactive and invisible.
        show_in:
          type: object
          properties:
            app:
              type: boolean
              description: Whether or not to show the category in the Salla Merchant App
            salla_points:
              type: boolean
              description: Whether or not to show the category in Salla Points
          x-apidog-orders:
            - app
            - salla_points
          required:
            - app
            - salla_points
          x-apidog-ignore-properties: []
        has_hidden_products:
          type: boolean
          description: Whether or not the category has hidden products.
        update_at:
          type: string
          description: The date where the category is updated in.
        metadata:
          type: object
          properties:
            title:
              type: string
              description: >-
                Category SEO Metadata Title which is a concise label used to
                optimize search engine results and enhance the visibility of a
                category page.
            description:
              type: string
              description: >-
                A succinct summary crafted to enhance search engine optimization
                and spotlight a brand's attributes within a category.
            url:
              type: string
              description: >-
                Metadata URL is a web address that contains information designed
                to improve a webpage's search engine visibility and shareability
                on social platforms.
          x-apidog-orders:
            - title
            - description
            - url
          required:
            - title
            - description
            - url
          x-apidog-ignore-properties: []
        sub_categories:
          type: array
          items:
            type: string
          description: The subcategories list of the main category.
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                  description: Translated category name
                metadata:
                  type: object
                  properties:
                    title:
                      type: string
                      description: >-
                        Translated Category SEO Metadata Title which is a
                        concise label used to optimize search engine results and
                        enhance the visibility of a category page.
                    description:
                      type: string
                      description: >-
                        A succinct summary crafted to enhance search engine
                        optimization and spotlight a brand's attributes within a
                        Translated category.
                    url:
                      type: string
                      description: >-
                        Translated Metadata URL is a web address that contains
                        information designed to improve a webpage's search
                        engine visibility and shareability on social platforms.
                  x-apidog-orders:
                    - title
                    - description
                    - url
                  required:
                    - title
                    - description
                    - url
                  x-apidog-ignore-properties: []
              x-apidog-orders:
                - name
                - metadata
              required:
                - name
                - metadata
              description: Translation in English language.
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
          required:
            - en
          description: >-
            **You will get this object in the response if you use
            `with=translations` query parameter.** 


            Category translations are based on the store's enabled language
            locale. For instance, if the store supports both Arabic and English,
            the `translations` object will return two entries: `ar` for Arabic
            and `en` for English.
          x-apidog-ignore-properties: []
        items:
          type: array
          items: *ref_1
          description: >-
            **You will get this array in the response if you use `with=items`
            query parameter.**
      x-apidog-orders:
        - id
        - name
        - image
        - urls
        - parent_id
        - sort_order
        - status
        - show_in
        - has_hidden_products
        - update_at
        - metadata
        - sub_categories
        - translations
        - items
      required:
        - id
        - name
        - image
        - urls
        - parent_id
        - sort_order
        - status
        - show_in
        - has_hidden_products
        - update_at
        - metadata
        - sub_categories
        - translations
        - items
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
    specialOffer_response_body:
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
          $ref: '#/components/schemas/SpecialOffer'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    SpecialOffer:
      description: >-
        Detailed structure of the special offer model object showing its fields
        and data types.
      type: object
      title: SpecialOffer
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a particular promotional or
            discount offe.
        name:
          type: string
          description: >-
            A descriptive label or title given to a specific promotional offer
            to distinguish it from others. 🌐 [Support
            multi-language](doc-421122)
        message:
          type: string
          description: >-
            A brief statement or communication that conveys the details or
            benefits of a specific promotional or discount offer. 🌐 [Support
            multi-language](doc-421122)
        expiry_date:
          type: string
          description: >-
            The date when a specific promotional or discount offer expires or
            ends.
          examples:
            - '2025-01-01'
        start_date:
          type: string
          description: >-
            Special offer start date  is the date when a specific promotional or
            discount offer begins or becomes active.
        offer_type:
          type: string
          description: >-
            The category or classification that describes a particular
            promotion, discount, or deal.
          enum:
            - buy_x_get_y
            - fixed_amount
            - percentage
            - discounts_table
            - special_price
            - cart_offer
            - tiered_offer
          x-apidog-enum:
            - name: Buy X Get Y
              value: buy_x_get_y
              description: >-
                A promotion where purchasing a specified quantity (X) qualifies
                the customer to receive another item (Y) for free or at a
                discounted price.
            - name: Fixed Amount Discount
              value: fixed_amount
              description: >-
                A discount that applies a fixed monetary reduction to the order
                total or specific items.
            - name: Percentage Discount
              value: percentage
              description: >-
                A discount calculated as a percentage of the order total or the
                price of specific items.
            - name: Discounts Table
              value: discounts_table
              description: >-
                A tiered discount structure where different discount rates are
                applied based on quantity thresholds or total spend.
            - value: special_price
              name: Special Price
              description: >-
                A promotion that applies a fixed price based on quantity added
                in cart 
            - value: cart_offer
              name: Cart Offer
              description: >-
                A discount that is applied on the cart based on cart total
                amount or number of products added in cart.
            - value: tiered_offer
              name: Tiered Offer
              description: ''
        status:
          type: string
          description: >-
            The current condition of a specific discount offer, such as whether
            it is active, expired, or in a pending or inactive status.
          enum:
            - active
            - inactive
          x-apidog-enum:
            - value: active
              name: ''
              description: ''
            - value: inactive
              name: ''
              description: ''
        show_price_after_discount:
          type: boolean
          description: The option to show the price after discount.
        show_discounts_table_message:
          type: boolean
          description: >-
            Whether or not to show  information presented in a table format that
            displays various discounts.
        countries:
          type: array
          items:
            type: integer
          description: A list of customer countries that the offer applies to.
        customer_groups:
          type: array
          items:
            type: integer
          description: A list of customer groups which the offer applies to.
        select_by:
          type: string
          description: >-
            Specifies whether the customer country should be determined based on
            `mobile`, `shipping` or `ip`
          enum:
            - mobile
            - shipping
            - ip
          x-apidog-enum:
            - value: mobile
              name: ''
              description: ''
            - value: shipping
              name: ''
              description: ''
            - value: ip
              name: ''
              description: ''
        applied_to:
          type: string
          description: >-
            The specific products, services, or items to which a particular
            promotional or discount offer is intended or allowed to be used or
            applied, specifying what the offer covers within a product or
            service catalog.
          enum:
            - order
            - product
            - category
            - paymentMethod
        options:
          type: array
          items:
            type: object
            properties:
              discount_apply_type:
                type: string
                description: >-
                  Specifies whether the offer discount will be applied as a
                  percentage or fixed amount.
                enum:
                  - percentage
                  - fixed
                x-apidog-enum:
                  - value: percentage
                    name: ''
                    description: ''
                  - value: fixed
                    name: ''
                    description: ''
              condition_threshold:
                type: number
                description: >-
                  Minimum total purchase required to apply the offer,
                  order_amount value or products_count value
              max_customer_discount:
                type: string
                description: >-
                  Required if `discount_apply_type` is percentage. Specifies the
                  maximum discount amount per customer.
              discount_amount:
                type: string
                description: >-
                  The discount amount depending on the `discount_apply_type` it
                  can represent a percentage or a fixed amount.
            x-apidog-orders:
              - discount_apply_type
              - condition_threshold
              - max_customer_discount
              - discount_amount
            x-apidog-ignore-properties: []
          description: Options in case offer type is `cart_offer`
        based_on:
          type: string
          description: >-
            Offer calculation based on `order_amount` or `products_count`in case
            offer type is `cart_offer` 
          enum:
            - order_amount
            - products_count
          x-apidog-enum:
            - name: ''
              value: order_amount
              description: ''
            - name: ''
              value: products_count
              description: ''
        buy:
          type: object
          description: Specifics on items required for offer eligibility.
          properties:
            type:
              type: string
              description: >-
                Product Type to buy to be eligible for the special offer.
                Required if `offer_type = buy_x_get_y`
              enum:
                - category
                - product
              x-apidog-enum:
                - value: category
                  name: ''
                  description: 'Purchase by the type category '
                - value: product
                  name: ''
                  description: Purchase by the type product
            quantity:
              type: number
              description: >-
                Product Quantity to buy to be eligible for the special offer.
                Required if `offer_type = buy_x_get_y`
            products:
              type: array
              uniqueItems: true
              description: >-
                The Products to be purchased that are included in the special
                offer. Make sure to pass the Product IDs in an array. This field
                is mandatory when `buy.type` is set to `product`.
              items: *ref_0
            categories:
              type: array
              description: >
                The Categories included in the special offer. Make sure to pass
                the Category IDs in an array. List of Category IDs can be foun
                [here](https://docs.salla.dev/5394207e0) This field is mandatory
                when `buy.type` is set to `category`.
              items: &ref_2
                $ref: '#/components/schemas/Category1'
          x-apidog-orders:
            - type
            - quantity
            - products
            - categories
          x-apidog-ignore-properties: []
        get:
          type: object
          description: Specifics of the offer.
          properties:
            type:
              type: string
              description: The type of the offer.
            discount_type:
              type: string
              description: >-
                Discount Type to get if eligible for the special offer. Required
                if `offer_type = buy_x_get_y`
              enum:
                - 'percentage '
                - free-product
              x-apidog-enum:
                - value: 'percentage '
                  name: ''
                  description: >-
                    A discount calculated as a percentage of the order total or
                    the price of specific items.
                - value: free-product
                  name: ''
                  description: ' A promotion that allows the customer to receive a specific product for free as part of the deal'
            quantity:
              type: integer
              description: >-
                Product Quantity to get if eligible for the special offer.
                Required if `offer_type = buy_x_get_y`
            products:
              type: array
              uniqueItems: true
              description: >-
                The Products to get if eligible for the special offer that are
                included in the special offer. Make sure to pass the Product IDs
                in an array. This field is mandatory when `get.type` is set to
                `product`.
              items: *ref_0
            categories:
              type: array
              description: >
                The Categories included in the special offer. Make sure to pass
                the Product IDs in an array. This field is mandatory when
                `get.type` is set to `category`.
              items: *ref_2
          x-apidog-orders:
            - type
            - discount_type
            - quantity
            - products
            - categories
          x-apidog-ignore-properties: []
        tiers:
          type: array
          items:
            type: object
            properties:
              name:
                type: string
                description: Name of the tier
              discount:
                type: string
                description: The discount value
              min_purchases:
                type: string
                description: The minimum value to apply the discount
              type:
                type: string
                description: Type of dicount whether its percentage or fixed
                enum:
                  - fixed
                  - percentage
                x-apidog-enum:
                  - value: fixed
                    name: ''
                    description: ''
                  - value: percentage
                    name: ''
                    description: ''
            x-apidog-orders:
              - name
              - discount
              - min_purchases
              - type
            required:
              - name
              - discount
              - min_purchases
              - type
            x-apidog-ignore-properties: []
          description: Tiers, returned in case the offer type is `tiered_offer`
        apply_type:
          type: string
          description: min_external_purchases or min_purchases
          enum:
            - min_purchases
            - min_external_purchases
          x-apidog-enum:
            - value: min_purchases
              name: ''
              description: ''
            - value: min_external_purchases
              name: ''
              description: ''
        with_current_cart:
          type: boolean
          description: >-
            Specifies whether the current cart value should be included in the
            calculation
        special_price:
          type: object
          properties:
            quantity:
              type: string
              description: The required quantity for the `special price` offer to apply
            price:
              type: string
              description: >-
                The amount of the special price that the customer will get with
                the offer (tax exclusive)
          x-apidog-orders:
            - quantity
            - price
          required:
            - quantity
            - price
          x-apidog-ignore-properties: []
        applied_with_coupon:
          type: boolean
          description: Whether or not the offer should be applied with a valid coupon
        scopes:
          type: array
          items:
            type: integer
          description: The scopes ids for the markets which the offer applies to
        exclude_sale_products:
          type: boolean
          description: >-
            Specifies whether the offer will apply to sale products or not, in
            case the offer type is `tiered_offer`
        excluded_buy_products_ids:
          type: array
          items:
            type: integer
          description: >-
            Array of product Ids execluded from the offer, in case the offer
            type is `tiered_offer`
        excluded_buy_categories_ids:
          type: array
          items:
            type: integer
          description: >-
            Array of category Ids execluded from the offer,  in case the offer
            type is `tiered_offer`
      x-apidog-orders:
        - id
        - name
        - message
        - expiry_date
        - start_date
        - offer_type
        - status
        - show_price_after_discount
        - show_discounts_table_message
        - countries
        - customer_groups
        - select_by
        - applied_to
        - options
        - based_on
        - buy
        - get
        - tiers
        - apply_type
        - with_current_cart
        - special_price
        - applied_with_coupon
        - scopes
        - exclude_sale_products
        - excluded_buy_products_ids
        - excluded_buy_categories_ids
      required:
        - id
        - name
        - expiry_date
        - start_date
        - offer_type
        - status
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Category1:
      title: Category
      type: object
      properties:
        id:
          type: number
          description: ID of the category
        name:
          type: string
          description: Name of category.
        url:
          type: string
          description: Url link of the category.
      x-apidog-orders:
        - id
        - name
        - url
      required:
        - id
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

