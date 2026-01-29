# Apis Products  Product Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-products/Product-Details-Salla-Merchant-API-Salla-Docs](#apis-products-product-details-salla-merchant-api-salla-docs)

---

## apis-products/Product-Details-Salla-Merchant-API-Salla-Docs

# Product Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /products/{product}:
    get:
      summary: Product Details
      deprecated: false
      description: >-
        This endpoint allows you to return specific product details by passing
        the `product` as a path parameter. 


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `products.read`- Products Read Only

        </Accordion>
      operationId: Product-Details
      tags:
        - Default module/Merchant API/APIs/Products
        - Products
      parameters:
        - name: product
          in: path
          description: >-
            Unique identification number assigned to a Product. List of Product
            ID can be found [here](https://docs.salla.dev/api-5394168).
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
                $ref: '#/components/schemas/product_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 1672932878
                  promotion:
                    title: Eid Promotion
                    sub_title: Eid Offers
                  sku: 23-TD23-32
                  thumbnail: >-
                    https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/2E0Z2t6Q8FG3ca2j2PAGrqqeDROY.jpg
                  mpn: '1891251919'
                  gtin: '58636897'
                  type: product
                  name: T-Shirt
                  short_link_code: qQvmmRb
                  urls:
                    customer: https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672932878
                    admin: https://s.salla.sa/products/1672932878
                  price:
                    amount: 100
                    currency: SAR
                  taxed_price:
                    amount: 100
                    currency: SAR
                  pre_tax_price:
                    amount: 100
                    currency: SAR
                  tax:
                    amount: 0
                    currency: SAR
                  description: ''
                  quantity: 0
                  status: sale
                  is_available: true
                  views: 0
                  sale_price:
                    amount: 0
                    currency: SAR
                  sale_end: '2025-06-23'
                  require_shipping: true
                  cost_price: '35'
                  weight: 1
                  weight_type: kg
                  with_tax: true
                  url: https://salla.sa/dev-mvxlkrylzfanmuri/t-shirt/p1672932878
                  main_image: >-
                    https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/2E0Z2t6Q8FG0rwqcTY2CC2j2PAGrqqeDROY.jpg
                  images:
                    - id: 1699133464
                      url: >-
                        https://salla-dev.s3.eu-central-1.amazonaws.com/nWzD/2E0Z2G3ca620rwqcTY2CC2j2PAGrqqeDROY.jpg
                      main: false
                      three_d_image_url: ''
                      alt: image
                      video_url: ''
                      type: image
                      sort: 5
                  sold_quantity: 0
                  rating:
                    total: 0
                    count: 0
                    rate: 0
                  regular_price:
                    amount: 100
                    currency: SAR
                  max_items_per_user: 0
                  maximum_quantity_per_order: 10
                  show_in_app: true
                  notify_quantity: '10'
                  hide_quantity: false
                  unlimited_quantity: true
                  managed_by_branches: false
                  services_blocks:
                    installments: []
                  calories: '500'
                  customized_sku_quantity: false
                  channels:
                    - web
                    - app
                  metadata:
                    title: title of the item promoted
                    description: ' The item promoted is the best '
                    url: https://linkForItem
                  scoped_prices:
                    - scope_id: 566146469
                      price: 300
                      cost_price: 100
                      sale_price: null
                      sale_end: null
                      sale_start: null
                      currency: SAR
                    - scope_id: 1473353380
                      price: 25
                      cost_price: 12
                      sale_price: null
                      sale_end: null
                      sale_start: null
                      currency: KWD
                  allow_attachments: false
                  is_pinned: false
                  pinned_date: '2024-03-06 13:50:32'
                  sort: 0
                  enable_upload_image: false
                  updated_at: '2024-03-06 13:50:32'
                  options:
                    - id: 782399854
                      name: Color
                      description: ' The item promoted is the best'
                      type: radio
                      required: false
                      associated_with_order_time: 0
                      availability_range: false
                      not_same_day_order: false
                      choose_date_time: true
                      from_date_time: '2022-06-23 01:04:38'
                      to_date_time: '2025-06-23 01:04:38'
                      sort: 0
                      advance: true
                      display_type: text
                      visibility: always
                      translations:
                        ar:
                          option_name: Color
                          description: ' The item promoted is the best'
                      values:
                        - id: 422377234
                          name: Blue
                          price:
                            amount: 0
                            currency: SAR
                          formatted_price: ''
                          display_value: ''
                          advance: true
                          option_id: 782399854
                          image_url: https://linkForItem
                          hashed_display_value: ''
                          translations:
                            ar:
                              option_details_name: Blue
                          is_default: false
                          is_out_of_stock: false
                        - id: 1783843123
                          name: Red
                          price:
                            amount: 0
                            currency: SAR
                          formatted_price: ''
                          display_value: ''
                          advance: true
                          option_id: 782399854
                          image_url: https://linkForItemTag
                          hashed_display_value: ''
                          translations:
                            ar:
                              option_details_name: Red
                          is_default: false
                          is_out_of_stock: false
                    - id: 2022330687
                      name: Size
                      description: ' The item promoted is the best '
                      type: radio
                      required: false
                      associated_with_order_time: 0
                      availability_range: false
                      not_same_day_order: false
                      choose_date_time: true
                      from_date_time: '2022-06-23 01:04:38'
                      to_date_time: '2025-06-23 01:04:38'
                      sort: 0
                      advance: true
                      display_type: text
                      visibility: always
                      translations:
                        ar:
                          option_name: Size
                          description: ' The item promoted is the best '
                      values:
                        - id: 1144986140
                          name: Small
                          price:
                            amount: 0
                            currency: SAR
                          formatted_price: ''
                          display_value: ''
                          advance: true
                          option_id: 2022020687
                          image_url: https://linkForItem
                          hashed_display_value: ''
                          translations:
                            ar:
                              option_details_name: Small
                          is_default: false
                          is_out_of_stock: false
                        - id: 369375517
                          name: Large
                          price:
                            amount: 0
                            currency: SAR
                          formatted_price: ''
                          display_value: ''
                          advance: true
                          option_id: 2022020687
                          image_url: https://linkForItem
                          hashed_display_value: ''
                          translations:
                            ar:
                              option_details_name: Large
                          is_default: false
                          is_out_of_stock: false
                  skus:
                    - id: 1936825372
                      price:
                        amount: 100
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      cost_price:
                        amount: 0
                        currency: SAR
                      sale_price: {}
                      has_special_price: false
                      stock_quantity: '0'
                      unlimited_quantity: true
                      notify_low: '10'
                      barcode: abc01
                      sku: 23-TD23-32
                      mpn: '58636897'
                      gtin: '58636897'
                      related_options:
                        - 782399854
                        - 2022020687
                      related_option_values:
                        - 410377234
                        - 1144986140
                      weight: 1
                      weight_type: kg
                      weight_label: ١ كجم
                      is_user_subscribed_to_sku: false
                      is_default: false
                    - id: 1298053917
                      price:
                        amount: 100
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      cost_price:
                        amount: 0
                        currency: SAR
                      sale_price: {}
                      has_special_price: false
                      stock_quantity: '10'
                      unlimited_quantity: true
                      notify_low: '12'
                      barcode: abc01
                      sku: 23-TD23-32
                      mpn: '1891251919'
                      gtin: '58636897'
                      related_options:
                        - 782399854
                        - 2022020687
                      related_option_values:
                        - 369375517
                        - 410377234
                      weight: 1
                      weight_type: kg
                      weight_label: ١ كجم
                      is_user_subscribed_to_sku: false
                      is_default: false
                    - id: 524016158
                      price:
                        amount: 100
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      cost_price:
                        amount: 0
                        currency: SAR
                      sale_price: {}
                      has_special_price: false
                      stock_quantity: '5'
                      unlimited_quantity: true
                      notify_low: '10'
                      barcode: abc01
                      sku: 23-TD23-32
                      mpn: '58636897'
                      gtin: '58636897'
                      related_options:
                        - 782399854
                        - 2022020687
                      related_option_values:
                        - 1144986140
                        - 1783823123
                      weight: 1
                      weight_type: kg
                      weight_label: ١ كجم
                      is_user_subscribed_to_sku: false
                      is_default: false
                    - id: 1761671455
                      price:
                        amount: 100
                        currency: SAR
                      regular_price:
                        amount: 0
                        currency: SAR
                      cost_price:
                        amount: 0
                        currency: SAR
                      sale_price: {}
                      has_special_price: false
                      stock_quantity: '10'
                      unlimited_quantity: true
                      notify_low: '10'
                      barcode: abc01
                      sku: 23-TD23-32
                      mpn: '58636897'
                      gtin: '58636897'
                      related_options:
                        - 782399854
                        - 2022020687
                      related_option_values:
                        - 369375517
                        - 1783823123
                      weight: 1
                      weight_type: kg
                      weight_label: ١ كجم
                      is_user_subscribed_to_sku: false
                      is_default: false
                  categories: []
                  tags: []
          headers: {}
          x-apidog-name: Success
        '401':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error_unauthorized_401'
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Object%20Not%20Found(404)'
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: ProductDetails
      x-apidog-folder: Default module/Merchant API/APIs/Products
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394169-run
components:
  schemas:
    product_response_body:
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
          $ref: '#/components/schemas/ProductDetails'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductDetails:
      description: >-
        Detailed structure of the Product model object showing its fields and
        data types.
      type: object
      x-examples: {}
      x-tags:
        - Models
      title: ProductDetails
      properties:
        id:
          type: number
          description: A unique identifier for a specific product within a database.
        promotion:
          type: object
          description: Product promotion details
          properties:
            title:
              type: string
              description: >-
                Name of a marketing or advertising campaign, offer, or special
                event to attract and inform potential customers about the
                promotion's content or benefits. 🌐 [Support
                multi-language](doc-421122)
            sub_title:
              type: string
              description: >-
                A secondary title that provides additional context about a
                promotion, complementing the main title. 🌐 [Support
                multi-language](doc-421122)
          x-apidog-orders:
            - title
            - sub_title
          required:
            - title
            - sub_title
          x-apidog-ignore-properties: []
        sku:
          type: string
          description: >-
            Stock Keeping Unit is a unique alphanumeric code used to identify
            and manage specific products within a company's inventory.
        mpn:
          type: string
          description: >-
            Manufacturer Part Number (MPN) is a unique identifier assigned by
            manufacturers to products.
          examples:
            - '45343'
          nullable: true
        gtin:
          type: string
          description: >-
            "Global Trade Item Number" (GTIN), a unique and standardized
            identifier used to uniquely represent products in the global
            marketplace.
          examples:
            - '14643439'
          nullable: true
        type:
          type: string
          description: >-
            The categorization of a product based on its characteristics,
            features, or intended use.
          enum:
            - product
            - service
            - group_products
            - codes
            - digital
            - food
            - donating
            - booking
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
            - value: booking
              name: ''
              description: Consultancy, Medical and Tourism services etc
        name:
          type: string
          description: >-
            A label for an item, aiding in easy identification and
            categorization within a product listing. 🌐 [Supports
            multi-language](doc-421122)
        short_link_code:
          type: string
          description: >-
            A short and simplified alphanumeric code or URL used to provide a
            quick and easy way to access or share a specific product's webpage
            or information.
        urls: &ref_0
          $ref: '#/components/schemas/URLs'
        price:
          type: object
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
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        taxed_price:
          type: object
          properties:
            amount:
              type: number
              description: Product taxed price amount
            currency:
              type: string
              description: Product taxed price currency
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        pre_tax_price:
          type: object
          description: Product price details before the tax is applied.
          properties:
            amount:
              type: number
              description: Product price amount
            currency:
              type: string
              description: Product pretax price currency
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        tax:
          type: object
          description: Product tax price details
          properties:
            amount:
              type: number
              description: Product tax price amount before the tax is applied.
            currency:
              type: string
              description: Product price currency before the tax is applied..
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        description:
          type: string
          description: >-
            A detailed information about an item. 🌐 [Support
            multi-language](doc-421122)
        quantity:
          type: integer
          description: The number of items available in stock.
        unlimited_quantity:
          type: boolean
          description: Whether or not the product is of unlimited quantity.
        status:
          type: string
          description: >-
            Product status refers to the current state of availability of a
            particular item within a product catalog or inventory. 
          enum:
            - sale
            - out
            - hidden
            - deleted
          x-apidog-enum:
            - value: sale
              name: ''
              description: Product on sale, set by the Merchant from the store's dashboard
            - value: out
              name: ''
              description: >-
                Product is out of stock, set by the Merchant from the store's
                dashboard
            - value: hidden
              name: ''
              description: >-
                Product is hidden, set by the Merchant from the store's
                dashboard
            - value: deleted
              name: ''
              description: >-
                Product is deleted, set by the Merchant from the store's
                dashboard
        is_available:
          type: boolean
          description: Whether or not the product is available.
        views:
          type: integer
          description: >-
            The total number of times a specific product has been viewed by
            users.
        sale_price:
          type: object
          description: >-
            The information about the discounted price or special pricing for a
            product.
          properties:
            amount:
              type: number
              description: Product sale price amount
            currency:
              type: string
              description: Product sale price currency
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        sale_end:
          type: string
          description: >-
            The date or time when a promotional sale or discount on a product is
            scheduled to expire.
        require_shipping:
          type: boolean
          description: >-
            Whether or not the product necessitates a physical delivery process
            or can be provided digitally without shipping.
        cost_price:
          type: number
          description: >-
            The amount a business pays to acquire or manufacture a product
            before any additional expenses, such as overhead or markup, are
            applied
        weight:
          type: number
          description: >-
            The weight of the product represented in numerical form if
            applicable.
        weight_type:
          type: string
          description: >-
            The classification or unit of measurement used to specify the weight
            of an object or item, such as kilograms (kg), pounds (lb), ounces
            (oz), or grams (g).
          enum:
            - kg
            - g
            - lb
            - oz
          x-apidog-enum:
            - value: kg
              name: ''
              description: Kilograms
            - value: g
              name: ''
              description: Grams
            - value: lb
              name: ''
              description: Pound
            - value: oz
              name: ''
              description: Ounce
        with_tax:
          type: boolean
          description: Whether or not a tax applied to this product or not.
        url:
          type: string
          description: The hyperlink that leads to a specific product's page.
        images:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  product image ID  is a unique identifier or code assigned to a
                  specific product image within a database or system, enabling
                  efficient management and retrieval of images associated with a
                  product.
              url:
                type: string
                description: >-
                  The web addresses or hyperlinks that point to the online
                  locations of images associated with  the product, making it
                  possible to display those images on websites, e-commerce
                  platforms, or other online channels.
              main:
                type: boolean
                default: true
                description: Image Attribute as ma
              alt:
                type: string
                description: Product images alternative text
              video_url:
                type: string
              type:
                type: string
                description: Product images type as `image` or `video`.
                enum:
                  - image
                  - video
                x-apidog-enum:
                  - value: image
                    name: ''
                    description: Media type, being image
                  - value: video
                    name: ''
                    description: Media type, being video
              sort:
                type: number
                description: >-
                  Product images sort number,  a numerical value or order
                  assigned to product images to determine their sequence or
                  arrangement when displayed.
              three_d_image_url:
                type: string
                description: >-
                  The URL of a 3D image, A product can only has __one__ product
                  image with a 3D URL.
              main_image:
                type: string
                description: The URL of the main image of the product.
            x-apidog-orders:
              - id
              - url
              - main
              - alt
              - video_url
              - type
              - sort
              - three_d_image_url
              - main_image
            x-apidog-ignore-properties: []
          description: >-
            Visual representations or pictures of a product, to showcase its
            appearance, features, and details to potential customers.
        sold_quantity:
          type: integer
          description: >-
            The total number of items of the product that have been purchased or
            sold over a certain period.
        rating:
          type: object
          description: >-
            Product rating details, include information about the ratings and
            reviews provided by customers for a specific product.
          properties:
            total:
              type: integer
              description: >-
                Total quantity of  reviews or ratings that a specific product
                has received, which is often used as a metric to assess the
                popularity and credibility of the product.
            count:
              type: integer
              description: Counted number of ratings to the product
            rate:
              type: number
              description: >-
                The numerical evaluation or score given to a product based on
                level of satisfaction.
          x-apidog-orders:
            - total
            - count
            - rate
          required:
            - total
            - count
            - rate
          x-apidog-ignore-properties: []
        regular_price:
          type: object
          description: Product regular price details.
          properties:
            amount:
              type: number
              description: Product regular price amount.
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
        max_items_per_user:
          type: number
          description: >-
            The limit set on the number of products that an individual user is
            allowed to purchase.
        maximum_quantity_per_order:
          description: >-
            Maximum quantity per order for the customer or the maximum quantity
            for the product.
          type: number
          nullable: true
        show_in_app:
          type: boolean
          description: Whether or not to show the product in the App.
        notify_quantity:
          description: Notify quantity of the product.
          type: string
          nullable: true
        hide_quantity:
          description: Whether or not to hide the product quantity.
          type: boolean
        channels:
          type: array
          x-stoplight:
            id: nwrxrha0zd8pb
          description: The product to appear in specific channels.
          items:
            type: string
            x-stoplight:
              id: xm6mx26en8s8p
            enum:
              - app
              - web
            x-apidog-enum:
              - value: app
                name: ''
                description: Product to appea in the mobile app of the store
              - value: web
                name: ''
                description: Product to appear in the website of the store
        managed_by_branches:
          type: boolean
          description: Whether or not to indicate if the product is managed by branches.
        service_blocks:
          type: object
          description: 'External services for the prodcut. '
          properties:
            installments:
              type: array
              description: >-
                Payment gateways that supports install-mental payments, which
                have been activated by the merchant from the
                [dashboard](https://s.salla.sa/payment). 
              items:
                type: object
                properties:
                  name:
                    type: string
                    description: >-
                      Payment gateway name, the identifier of a specific payment
                      processing service or platform that facilitates online
                      transactions by securely transferring payment information
                      between a customer, a merchant, and a financial
                      institution, allowing for the authorization and settlement
                      of payments for goods or services.
                  title:
                    type: string
                    description: Payment gateway title,
                  logo:
                    type: string
                    description: >-
                      Payment gateway logo, a text string containing the URL or
                      file path to an image file that serves as the logo for a
                      particular payment gateway. 
                  details:
                    type: string
                    description: >-
                      Comprehensive information about a specific payment
                      processing service.
                x-apidog-orders:
                  - name
                  - title
                  - logo
                  - details
                x-apidog-ignore-properties: []
          x-apidog-orders:
            - installments
          required:
            - installments
          x-apidog-ignore-properties: []
        calories:
          type: string
          description: Calories amount of the product.
          examples:
            - '500.00'
          nullable: true
        starting_price:
          description: >-
            The merchant owner should activate this feature from his store from
            [here](https://s.salla.sa/settings/component/options).
          type: object
          properties:
            amount:
              type: integer
              description: >-
                Product starting price amount,the initial or base price at which
                a product is offered for sale, typically before any additional
                options, variations, or customizations are factored in, and it
                serves as the starting point for pricing.
            currency:
              type: string
              description: Currency of the starting price amount.
          x-apidog-orders:
            - amount
            - currency
          examples:
            - '500.00'
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        allow_attachments:
          type: boolean
          description: Whether or not to allow adding attachments to the prodcut details.
        is_pinned:
          type: boolean
          description: Whether or not to show if the prodcut is pinned.
        pinned_date:
          type: string
          description: The date which the product was pinned at.
        sort:
          type: number
          description: Sorting order of the product.
        active_advance:
          type: boolean
          description: Whether or not to activate advance product details.
        enable_upload_image:
          type: boolean
          description: Whether or not to allow image uploading.
        updated_at:
          type: string
          description: Product last updated date.
        options:
          type: array
          items:
            $ref: '#/components/schemas/MiniProductOption'
          description: >-
            The additional choices that can be selected to customize the product
            according to preferences. 
        skus:
          description: Product variants SKUs details
          type: array
          items:
            $ref: '#/components/schemas/ProductVariant'
        metadata:
          type: object
          properties:
            title:
              type: string
              description: >-
                Product de SEO Metadata Title which is a concise label used to
                optimize search engine results and enhance the visibility of a
                product details page. 🌐 [Support multi-language](doc-421122)
            description:
              type: string
              description: >-
                A succinct summary crafted to enhance search engine optimization
                . 🌐 [Support multi-language](doc-421122)
            url:
              type: string
              description: >-
                The web address of the Product Deatils page with embedded
                metadata (title, description, keywords) to enhance its search
                engine visibility. 🌐 [Support multi-language](doc-421122)
          x-apidog-orders:
            - title
            - description
            - url
          description: >-
            The data that describes other data, providing details on its
            creation, format, and context.
          required:
            - title
            - description
            - url
          x-apidog-ignore-properties: []
        booking_details:
          type: object
          properties:
            id:
              type: number
              description: >-
                Unique identifier or code assigned to a specific booking or
                reservation, used for tracking, reference, and management
                purposes
              examples:
                - 1521087104
            location:
              type: string
              description: >-
                The specific place or venue where a booking or reservation is
                made, such as a hotel, restaurant, event venue, or
                transportation service.
              examples:
                - Medina
            type:
              type: string
              description: >-
                Refers to the category or classification of a reservation or
                booking, indicating the nature or purpose of the booking.
                Required if `booking_details != null`
              enum:
                - date_time
                - date
              examples:
                - time
              x-apidog-enum:
                - value: date_time
                  name: ''
                  description: Booking details by date time format
                - value: date
                  name: ''
                  description: Booking details by date format
            session_duration:
              type: string
              description: >-
                Booking duration is mandatory when the booking type is set as
                `date_time`.
              format: date-time
            session_gap:
              type: number
              description: >-
                Booking session gap is necessary when the booking type is
                `date_time`, and it specifies the amount of time between
                consecutive booking sessions or appointments.
            sessions_count:
              type: number
              description: >-
                Booking Sessions Count, which is the number of sessions allowed
                for one customer . Required if `booking_details != null`
            time_strict_value:
              type: number
              description: A timeframe where it is not applicable to make reservations.
              examples:
                - 2
            time_strict_type:
              type: string
              description: >-
                The restriction on making bookings within a specific timeframe
                is measured in minutes, hours, or days.
              enum:
                - minutes
                - hours
                - days
              default: days
              x-apidog-enum:
                - value: minutes
                  name: ''
                  description: Time restriction bu the minutes
                - value: hours
                  name: ''
                  description: Time restriction bu the hours
                - value: days
                  name: ''
                  description: Time restriction bu the days
            availabilities:
              type: array
              description: >-
                Available slots for booking. Required if `booking_details !=
                null`
              items:
                type: object
                properties:
                  day:
                    type: string
                    description: Days which are available for booking.
                    enum:
                      - sunday
                      - monday
                      - tuesday
                      - wednesday
                      - thursday
                      - friday
                      - saturday
                    examples:
                      - sunday
                  is_available:
                    type: boolean
                    description: Option to enable booking availability.
                    default: true
                  times:
                    type: array
                    description: Required if `booking_details.type = date_time`
                    items:
                      type: object
                      x-stoplight:
                        id: yc1bqhdmo9gld
                      properties:
                        from:
                          type: string
                          description: "The starting time of the of available booking slot in 24 hours format. Required if `booking_details.type = date_time`\r\n"
                          examples:
                            - '14:30'
                        to:
                          type: string
                          description: "The ending time of the of available booking slot in 24 hours format. Required if `booking_details.type = date_time`\r\n"
                          examples:
                            - '17:30'
                      x-apidog-orders:
                        - from
                        - to
                      x-apidog-ignore-properties: []
                x-apidog-orders:
                  - day
                  - is_available
                  - times
                x-apidog-ignore-properties: []
            overrides:
              type: array
              description: >-
                Overwrite availability for a particular day, on a particular
                date.
              items:
                type: object
                properties:
                  id:
                    type: number
                    description: Booking Overrides ID
                    examples:
                      - 520625452
                  date:
                    type: string
                    description: >-
                      The value of specific date that has been overridden in a
                      booking 
                    examples:
                      - '2022-01-10'
                x-apidog-orders:
                  - id
                  - date
                x-apidog-ignore-properties: []
          x-apidog-orders:
            - id
            - location
            - type
            - session_duration
            - session_gap
            - sessions_count
            - time_strict_value
            - time_strict_type
            - availabilities
            - overrides
          description: >-
            The information related to a specific booking, such as date, time,
            location, and other relevant particulars
          required:
            - id
            - location
            - type
            - session_duration
            - session_gap
            - sessions_count
            - time_strict_value
            - time_strict_type
            - availabilities
            - overrides
          x-apidog-ignore-properties: []
        categories:
          type: array
          items: &ref_1
            $ref: '#/components/schemas/Category'
          description: >-
            The various sections or attributes that describe a product, such as
            name, price, description, specifications, and availability.
        brand:
          $ref: '#/components/schemas/Brand'
        tags:
          type: array
          items:
            type: object
            properties:
              id:
                type: number
                description: >-
                  A unique identifier or code assigned to a specific tag or
                  label used for categorization or classification purposes
                  within a system or database.
              name:
                type: string
                description: >-
                  The label or identifier assigned to a specific tag, used for
                  categorizing or organizing items, content, or data within a
                  system or database.
            x-apidog-orders:
              - id
              - name
            x-apidog-ignore-properties: []
        scoped_prices:
          type: object
          properties:
            scope_id:
              type: string
              description: >-
                Branch (scope) unique identification. Get a list of Scope IDs
                related to the store from
                [here](https://docs.salla.dev/15104922e0)
            price:
              type: integer
              description: Price of the item / product based on the branch (scope)
            cost_price:
              type: integer
              description: Cost price of the item / product based on the branch (scope)
            sale_price:
              type: integer
              description: Item reduced price due to sale based on the branch (scope)
            sale_end:
              type: string
              description: >-
                End of the sale of the product / item before the original price
                is back based on the branch (scope)
            sale_start:
              type: string
              description: >-
                Start of the sale of the product / item before the original
                price is back based on the branch (scope)
            currency:
              type: string
              description: Price's currency based on the branch (scope)
          x-apidog-orders:
            - scope_id
            - price
            - cost_price
            - sale_price
            - sale_end
            - sale_start
            - currency
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - promotion
        - sku
        - mpn
        - gtin
        - type
        - name
        - short_link_code
        - urls
        - price
        - taxed_price
        - pre_tax_price
        - tax
        - description
        - quantity
        - unlimited_quantity
        - status
        - is_available
        - views
        - sale_price
        - sale_end
        - require_shipping
        - cost_price
        - weight
        - weight_type
        - with_tax
        - url
        - images
        - sold_quantity
        - rating
        - regular_price
        - max_items_per_user
        - maximum_quantity_per_order
        - show_in_app
        - notify_quantity
        - hide_quantity
        - channels
        - managed_by_branches
        - service_blocks
        - calories
        - starting_price
        - allow_attachments
        - is_pinned
        - pinned_date
        - sort
        - active_advance
        - enable_upload_image
        - updated_at
        - options
        - skus
        - metadata
        - booking_details
        - categories
        - brand
        - tags
        - scoped_prices
      required:
        - id
        - promotion
        - sku
        - mpn
        - gtin
        - type
        - name
        - short_link_code
        - urls
        - price
        - taxed_price
        - pre_tax_price
        - tax
        - description
        - quantity
        - unlimited_quantity
        - status
        - is_available
        - views
        - sale_price
        - sale_end
        - require_shipping
        - cost_price
        - weight
        - weight_type
        - with_tax
        - url
        - images
        - sold_quantity
        - rating
        - regular_price
        - max_items_per_user
        - maximum_quantity_per_order
        - show_in_app
        - notify_quantity
        - hide_quantity
        - channels
        - managed_by_branches
        - service_blocks
        - calories
        - starting_price
        - allow_attachments
        - is_pinned
        - pinned_date
        - sort
        - active_advance
        - enable_upload_image
        - updated_at
        - options
        - skus
        - metadata
        - booking_details
        - categories
        - brand
        - tags
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    Brand:
      description: >-
        Detailed structure of the brand model object showing its fields and data
        types.
      type: object
      x-examples:
        Webhook V2:
          value:
            event: brand.deleted
            merchent: 674390266
            created_at: '2021-06-02 22:17:06'
            data:
              id: 1473353380
              name: زارا
              description: زارا
              banner: https://i.ibb.co/jyqRQfQ/avatar-male.webp
              logo: https://i.ibb.co/jyqRQfQ/avatar-male.webp
              ar_char: ز
              en_char: z
              metadata:
                title: Zara brand
                description: Brand awareness seo
                url: zara/item
        Webhook V1:
          value:
            id: 1473353380
            name: زارا
            description: زارا
            banner: https://i.ibb.co/jyqRQfQ/avatar-male.webp
            logo: https://i.ibb.co/jyqRQfQ/avatar-male.webp
            ar_char: ز
            en_char: z
            metadata:
              title: Zara brand
              description: Brand awareness seo
              url: zara/item
      x-tags:
        - Models
      title: Brand
      properties:
        id:
          description: A unique identifier assigned to a specific brand.
          type: number
        name:
          type: string
          description: >-
            The label given to a particular  company, to identify its products
            in the market. 🌐 [Support multi-language](doc-421122)
        label:
          type: string
          description: >-
            The label given to a particular  company, to identify its products
            in the market. 🌐 [Support multi-language](doc-421122)
        status:
          type: boolean
          description: Brand status
          nullable: true
        description:
          type: string
          description: >-
            A brief summary of a company, highlighting key attributes, values,
            and offerings to convey its identity and purpose. 🌐 [Support
            multi-language](doc-421122)
        banner:
          type: string
          description: >-
            A text or URL linking to a banner file, used as a visual identifier
            for a brand on a webpage or platform.
          nullable: true
        logo:
          type: string
          description: >-
            A text-based representation or URL link that directs to the logo
            file.
        ar_char:
          type: string
          description: Brand represented in Arabic characters.
        en_char:
          type: string
          description: Brand represented in English characters.
        channels:
          type: array
          items:
            type: string
          description: Brand channels
        metadata:
          type: object
          x-stoplight:
            id: 8d0s0tfwzpf28
          properties:
            title:
              type: string
              description: >-
                A concise metadata title used to improve search engine
                visibility and optimize a brand page’s search ranking. 🌐
                [Support multi-language](doc-421122)
              x-stoplight:
                id: bwvcv90k4e5uu
              nullable: true
            description:
              type: string
              description: >-
                Concise content enhancing search visibility and social sharing. 
                🌐 [Support multi-language](doc-421122)
              x-stoplight:
                id: idnybfvxrkyyv
              nullable: true
            url:
              type: string
              description: >-
                Web link for enhanced search engine visibility and social media
                sharing.  🌐 🌐 [Support multi-language](doc-421122)
              x-stoplight:
                id: ztu8v1b826bp3
              nullable: true
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
        - id
        - name
        - label
        - status
        - description
        - banner
        - logo
        - ar_char
        - en_char
        - channels
        - metadata
      required:
        - id
        - name
        - status
        - description
        - banner
        - logo
        - ar_char
        - en_char
        - metadata
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
        urls: *ref_0
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
    ProductVariant:
      description: >-
        Detailed structure of the product variant model object showing its
        fields and data types.
      type: object
      title: ProductVariant
      x-tags:
        - Models
      x-examples:
        Example:
          id: 1115785385
          price:
            amount: 90.5
            currency: SAR
          regular_price:
            amount: 100.33
            currency: SAR
          sale_price:
            amount: 90.5
            currency: SAR
          stock_quantity: 4
          barcode: abc01
          sku: 23-TD23-32
          mpn: 43242342
          gtin: 54353453
          related_options:
            - 512644768
            - 976327842
          related_option_values:
            - 512644768
            - 976327842
          weight: 3
          weight_type: kg
          weight_label: ٣ كجم
      properties:
        id:
          type: number
          description: >-
            A unique identifier associated with a specific variant of a product
            or item.
        price:
          type: object
          description: The price of the product variant.
          properties:
            amount:
              type: number
              description: 'The amount of the product price. Example: 96.33'
              examples:
                - 96.33
            currency:
              type: string
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        regular_price:
          type: object
          x-stoplight:
            id: uub4l1jz09qkf
          description: The regular price of the product variant.
          properties:
            amount:
              type: number
              x-stoplight:
                id: a026eri5g9k4h
            currency:
              type: string
              x-stoplight:
                id: g8gzh6e6ghf4l
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        cost_price:
          type: object
          description: The purchase price excluding any additional expenses.
          x-stoplight:
            id: 687chslg6fdqy
          properties:
            amount:
              type: number
              description: 'The value of the cost price amount. Example: 100.33'
            currency:
              type: string
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        sale_price:
          type: object
          description: The sale price of the product variant.
          properties:
            amount:
              type: number
              description: 'The value of the sale price a Example: 100.33'
            currency:
              type: string
          x-apidog-orders:
            - amount
            - currency
          required:
            - amount
            - currency
          x-apidog-ignore-properties: []
        has_special_price:
          type: boolean
          readOnly: true
          description: Whether or not the product variant has a special price.
        stock_quantity:
          type: integer
          description: >-
            The amount of the product variant total stock quantity. Only updated
            if the store feature manage product by branches is not activated.
          examples:
            - 4
        unlimited_quantity:
          type: boolean
          x-stoplight:
            id: 62evc4ca3tf7u
          description: Whether or not the product variant is of unlimit quantity.
        notify_low:
          type: integer
          x-stoplight:
            id: j71y502ca9eth
          description: >-
            Sets a threshold value to trigger notifications when inventory falls
            below.
        barcode:
          type: string
          description: The barcode value of product variant.
          examples:
            - abc01
        sku:
          type: string
          description: >-
            A unique Stock Keeping Unit (SKU) identifier assigned to a specific
            variant of a product.
          examples:
            - 23-TD23-32
        mpn:
          type: string
          x-stoplight:
            id: 1xotdb1fnb2p0
          description: >-
            Manufacturer Part Number, a unique identifier assigned by a
            manufacturer to a specific product or component.
        gtin:
          type: string
          x-stoplight:
            id: gp8b5bu8mg5y6
          description: >-
            Global Trade Item Number, a unique and standardized identifier used
            to uniquely represent products, in the global marketplace, to enable
            efficient tracking and management across supply chains and retail
            sectors. If `product_type` is set to any of the following:
            `product`, `group_products`, `codes`, `digital`, `donating` then
            value can be set. Otherwise, it can be set to `null`
        updated_at:
          $ref: '#/components/schemas/Date'
          description: The date and time product variant is updated.
        related_options:
          type: array
          x-stoplight:
            id: gwg4szqmpeyr4
          description: An array for the related options to this variant.
          items:
            x-stoplight:
              id: 2ezv3bfmmwob0
            type: integer
        related_option_values:
          type: array
          x-stoplight:
            id: ruoh1jjr3rjq6
          description: An array for the values of the related options to this variant.
          items:
            x-stoplight:
              id: 78wwfmqiyubcx
            type: integer
        weight:
          type: number
          description: >-
            The numerical value that represents the mass or weight of a specific
            variant of a product.
          examples:
            - 3
        weight_type:
          type: string
          description: Product variant weight type
          examples:
            - kg
        weight_label:
          type: string
          description: Product variant weight label representing the type of the weight.
          examples:
            - ٣ كجم
        is_user_subscribed_to_sku:
          type: boolean
          readOnly: true
          description: Whether or not the user subscribed for the sku.
        is_default:
          type: boolean
          description: >-
            Whether or not enable showing that the product variant is the
            default 
      x-apidog-orders:
        - id
        - price
        - regular_price
        - cost_price
        - sale_price
        - has_special_price
        - stock_quantity
        - unlimited_quantity
        - notify_low
        - barcode
        - sku
        - mpn
        - gtin
        - updated_at
        - related_options
        - related_option_values
        - weight
        - weight_type
        - weight_label
        - is_user_subscribed_to_sku
        - is_default
      required:
        - id
        - price
        - regular_price
        - cost_price
        - sale_price
        - has_special_price
        - stock_quantity
        - unlimited_quantity
        - notify_low
        - barcode
        - sku
        - mpn
        - gtin
        - updated_at
        - related_options
        - related_option_values
        - weight
        - weight_type
        - weight_label
        - is_user_subscribed_to_sku
        - is_default
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
    MiniProductOption:
      description: >-
        Detailed structure of the product option model object showing its fields
        and data types.
      type: object
      title: MiniProductOption
      x-tags:
        - Models
      x-examples: {}
      properties:
        id:
          type: number
          description: >-
            A unique identifier assigned to a specific product configuration or
            variant.
        name:
          type: string
          description: >-
            The label or title used to describe a specific choice or attribute
            associated with a product.
        description:
          type: string
          description: >-
            A text or content that provides detailed information about a
            specific choice associated with a product.
          nullable: true
        type:
          type: string
          description: Type of the product option, it can be a `radio` button or `checkbox`
          enum:
            - radio
            - checkbox
          x-apidog-enum:
            - value: radio
              name: ''
              description: Option type of radio.
            - value: checkbox
              name: ''
              description: Option type of checkbox.
        required:
          type: boolean
          description: Whether or not to indicate the product option is obligatory.
        associated_with_order_time:
          type: integer
          description: >-
            The product option is only relevant to order receiving time when it
            pertains to date-time selections. **ONLY** for date time options.
        sort:
          type: integer
          description: >-
            Product option sort refers to the method or criteria used to arrange
            or order product options.
          nullable: true
        display_type:
          type: string
          description: The manner in which product choices or attributes are presented.
          enum:
            - text
            - image
            - color
          x-apidog-enum:
            - value: text
              name: ''
              description: Option displayed as a text.
            - value: image
              name: ''
              description: Option displayed as an image.
            - value: color
              name: ''
              description: Option displayed as a color.
        visibility:
          type: string
          description: >-
            Product option visibility based on condition is applied exclusively
            to products categorized as 'food' or 'service', allowing certain
            choices or attributes to be shown or hidden based on specific
            criteria.
          enum:
            - always
            - on_condition
          x-apidog-enum:
            - value: always
              name: ''
              description: Always on display
            - value: on_condition
              name: ''
              description: Specific conditions to display the product
        visibility_condition_type:
          type: string
          description: Product option visiblity condition type.
          enum:
            - '>'
            - <
            - '='
            - '!='
          x-apidog-enum:
            - value: '>'
              name: ''
              description: Visibility condition of Bigger than.
            - value: <
              name: ''
              description: Visibility condition of Smaller than.
            - value: '='
              name: ''
              description: Visibility condition of Equal to.
            - value: '!='
              name: ''
              description: Visibility condition of Not equal to.
        visibility_condition_option:
          type: integer
          description: A unique identifier assigned to a specific product option.
          nullable: true
        visibility_condition_value:
          type: integer
          description: >-
            A unique identifier associated with a specific value or choice
            within a product option.
          nullable: true
        values:
          type: array
          items:
            $ref: '#/components/schemas/ProductValue'
      x-apidog-orders:
        - id
        - name
        - description
        - type
        - required
        - associated_with_order_time
        - sort
        - display_type
        - visibility
        - visibility_condition_type
        - visibility_condition_option
        - visibility_condition_value
        - values
      required:
        - id
        - name
        - description
        - type
        - required
        - associated_with_order_time
        - sort
        - display_type
        - visibility
        - visibility_condition_type
        - visibility_condition_option
        - visibility_condition_value
        - values
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    ProductValue:
      description: >-
        Detailed structure of the product value model object showing its fields
        and data types.
      type: object
      title: ProductValue
      x-tags:
        - Models
      properties:
        id:
          type: number
          description: A unique identifier assigned to a value associated with a product.
        name:
          type: string
          description: Identifying label for a product attribute.
        price:
          type: object
          description: The product price.
          properties:
            amount:
              type: number
              description: Amout of the price.
            currency:
              type: string
              description: The currency of the amount.
          x-apidog-orders:
            - amount
            - currency
          x-apidog-ignore-properties: []
        formatted_price:
          type: string
          description: >-
            The extra formatted price added when a customer selects a specific
            value.
        display_value:
          type: string
          description: >-
            The UI displays values based on the option's display type. By
            default, it shows the name when `display_value=text`. For `image`,
            use the image ID (uploaded via the attach image endpoint). For
            `color`, provide a value like `#000` for black.
        advance:
          type: boolean
          description: Is the option value is advanced or not
        option_id:
          description: A unique identifier assigned to a specific choice.
          type: number
        image_url:
          type: string
          description: The web address where the corresponding image is hosted.
        hashed_display_value:
          type: string
          description: >-
            if `option.type` = `image` then hashed display value return `image
            id`. 

            if `option.type` = `text` then hashed display value return value
            `name` 
        translations:
          type: object
          properties:
            ar:
              type: object
              properties:
                option_details_name:
                  type: string
                  readOnly: true
                  description: Option Details Name in Arabic
              x-apidog-orders:
                - option_details_name
              readOnly: true
              description: Translation provided in Arabic language.
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - ar
          readOnly: true
          description: Translation of option values in different languages
          required:
            - ar
          x-apidog-ignore-properties: []
        is_default:
          type: boolean
          description: >-
            This option will be enabled when this particular value is the
            default value.
        is_out_of_stock:
          type: boolean
          description: Whether or not the option value is out of stock.
          readOnly: true
      x-apidog-orders:
        - id
        - name
        - price
        - formatted_price
        - display_value
        - advance
        - option_id
        - image_url
        - hashed_display_value
        - translations
        - is_default
        - is_out_of_stock
      required:
        - id
        - name
        - price
        - formatted_price
        - display_value
        - advance
        - option_id
        - image_url
        - hashed_display_value
        - translations
        - is_default
        - is_out_of_stock
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

