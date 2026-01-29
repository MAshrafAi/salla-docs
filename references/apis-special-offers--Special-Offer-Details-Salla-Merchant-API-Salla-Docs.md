# Apis Special Offers  Special Offer Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-special-offers/Special-Offer-Details-Salla-Merchant-API-Salla-Docs](#apis-special-offers-special-offer-details-salla-merchant-api-salla-docs)

---

## apis-special-offers/Special-Offer-Details-Salla-Merchant-API-Salla-Docs

# Special Offer Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /specialoffers/{specialoffer}:
    get:
      summary: Special Offer Details
      deprecated: false
      description: >-
        This endpoint allows you to return the complete details for a specific
        special offer by passing the `specialoffer` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `specialoffers.read`- Special Offers Read Only

        </Accordion>
      operationId: Special-Offer-Details
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
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/specialOffer_response_body'
              examples:
                '1':
                  summary: Buy X get Y
                  value:
                    status: 200
                    success: true
                    data:
                      id: 374680268
                      name: Buy one get one
                      message: >-
                        اشتري قطعتين واحصل على قطعة واحدة مجاناً من المنتجات
                        التالية
                      expiry_date: '2026-04-25 11:14:45'
                      start_date: '2026-01-30 11:15:21'
                      offer_type: buy_x_get_y
                      status: inactive
                      show_price_after_discount: false
                      show_discounts_table_message: false
                      countries: []
                      customer_groups:
                        - 909470991
                        - 1281032
                      applied_to: product
                      select_by: ''
                      options: []
                      based_on: null
                      buy:
                        type: product
                        quantity: 2
                        products:
                          - id: 187002438
                            sku: ''
                            name: iphone pro
                            price: 81
                            currency: SAR
                            description: null
                            options: ''
                            type: product
                            store_id: 67593
                            brand_id: null
                            quantity: 1397
                            status: sale
                            rand_token: ''
                            views: 0
                            created_at: '2025-12-16T11:53:13.000000Z'
                            updated_at: '2026-01-11T18:01:01.000000Z'
                            minimum_order_time: '0'
                            maximum_daily_order: null
                            maximum_quantity_per_order: null
                            allow_attachments: 0
                            pinned: 0
                            pinned_date: '2025-12-16 14:53:13'
                            sale_price: null
                            sale_end: null
                            source: '24'
                            require_shipping: 0
                            cost_price: null
                            digital_download_limit: null
                            digital_download_expiry: null
                            from_instagram: 0
                            weight: null
                            with_tax: true
                            hide_quantity: false
                            min_amount_donating: null
                            max_amount_donating: null
                            subtitle: null
                            active_advance: 1
                            enable_upload_image: false
                            searchable_at: null
                            promotion_title: null
                            extra_attributes:
                              tax_reason_code: null
                              has_custom_fields: false
                            sort: 0
                            enable_note: false
                            thumbnail: >-
                              https://cdn.salla.sa/NKZOK/53f66e65-fe61-42ef-b2e1-e8641d49c101-357.14285714286x500-tQmmx9Tk6iNRFk1eQ44rfskE6UIHsKtnzWT94FfP.jpg
                            thumbnail_alt_seo: ''
                            target_donating_enable: false
                            unlimited_quantity: false
                            managed_by_branches: 1
                            notify_quantity: null
                            show_in_app: true
                            child: 0
                            customized_sku_quantity: 1
                            starting_price: 70
                            custom_url: null
                            calories: null
                            minimum_notify_quantity: null
                            subscribers_percentage: null
                            mpn: null
                            gtin: null
                            real_weight: null
                            weight_type: kg
                            show_in_mahly_app: 0
                            mahly_category_id: null
                            spam_status: 0
                            show_in_web: true
                            minimum_quantity_per_order: 1
                            shipping_international: null
                            shipping_box_id: null
                            scoped_prices: []
                            sale_start: null
                            manufacture_country_id: null
                            show_in_landing_page: false
                      get:
                        type: product
                        discount_type: free-product
                        quantity: 1
                        products:
                          - id: 1537458321
                            type: group_products
                            promotion:
                              title: null
                              sub_title: null
                            quantity: null
                            status: sale
                            is_available: true
                            sku: ''
                            name: Test advanced bundle
                            price:
                              amount: 0
                              currency: SAR
                            sale_price:
                              amount: 0
                              currency: SAR
                            currency: SAR
                            url: >-
                              https://mozdanastore.com/ar/test-advanced-bundle/p1537458321
                            thumbnail: >-
                              https://cdn.salla.sa/NKZOK/b8771dc7-04fe-4001-b5cf-42c200466940-375x500-bzf6rtjVLWFkpkEXVsaGgkTN4vycHnleV656t6Xd.webp
                            has_special_price: false
                            regular_price:
                              amount: 0
                              currency: SAR
                            calories: null
                            mpn: null
                            gtin: null
                            description: ''
                            has_preorder_campaign: false
                            preorder: null
                            favorite: null
                            features:
                              availability_notify: null
                              show_rating: true
                            activePreorderCampaign: null
                      tiers: []
                      apply_type: null
                      with_current_cart: false
                      special_price: null
                      applied_with_coupon: false
                      scopes:
                        - 1473353380
                        - 289292369
                      exclude_sale_items: false
                      excluded_buy_products_ids: []
                      excluded_buy_categories_ids: []
                '2':
                  summary: Fixed Amount Offer
                  value:
                    status: 200
                    success: true
                    data:
                      id: 843056940
                      name: Fixed Amount Offer
                      message: اشتري قطعة واحصل على خصم 5 ر.س من المنتجات التالية
                      start_date: '2024-12-08 16:00:00'
                      expiry_date: '2025-12-10 16:00:00'
                      offer_type: fixed_amount
                      status: inactive
                      show_price_after_discount: false
                      show_discounts_table_message: false
                      countries: []
                      customer_groups: []
                      applied_to: order
                      select_by: ''
                      options: []
                      based_on: null
                      buy:
                        min_amount: 0
                        min_items: 50
                      get:
                        discount_amount: '10.00'
                      tiers: []
                      apply_type: null
                      with_current_cart: false
                      special_price: null
                      applied_with_coupon: false
                      scopes: []
                      exclude_sale_items: false
                      excluded_buy_products_ids: []
                      excluded_buy_categories_ids: []
                '3':
                  summary: Percentage Offer
                  value:
                    status: 200
                    success: true
                    data:
                      id: 204285485
                      name: Percentage Offer
                      message: اشتري قطعة واحصل على خصم %5 من المنتجات التالية
                      start_date: '2024-12-08 16:00:00'
                      expiry_date: '2025-12-10 16:00:00'
                      offer_type: percentage
                      status: inactive
                      show_discounts_table_message: false
                      countries: []
                      customer_groups: []
                      applied_to: order
                      select_by: ''
                      options: []
                      based_on: null
                      buy:
                        min_amount: 10
                        min_items: 0
                        products: []
                      get:
                        discount_amount: '5.00'
                      tiers: []
                      apply_type: null
                      with_current_cart: false
                      special_price: null
                      applied_with_coupon: false
                      scopes: []
                      exclude_sale_items: false
                      excluded_buy_products_ids: []
                      excluded_buy_categories_ids: []
                '4':
                  summary: Discounts Table Offer
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1145030649
                      name: Discount Table Offer
                      message: ''
                      expiry_date: '2026-07-22 16:20:34'
                      start_date: '2026-01-22 16:23:59'
                      offer_type: discounts_table
                      status: inactive
                      show_price_after_discount: false
                      show_discounts_table_message: false
                      countries: []
                      customer_groups:
                        - 1354073706
                      applied_to: product
                      select_by: ''
                      options: []
                      based_on: null
                      buy:
                        products:
                          - id: 1298176905
                            sku: P-0267
                            name: product 01
                            price: 123
                            currency: SAR
                            description: ''
                            options: ''
                            type: product
                            store_id: 67593
                            brand_id: null
                            quantity: 0
                            status: sale
                            rand_token: ''
                            views: 0
                            created_at: '2026-01-18T23:27:56.000000Z'
                            updated_at: '2026-01-21T12:12:26.000000Z'
                            minimum_order_time: '0'
                            maximum_daily_order: null
                            maximum_quantity_per_order: null
                            allow_attachments: 0
                            pinned: 0
                            pinned_date: '2026-01-19 02:27:56'
                            sale_price: null
                            sale_end: null
                            source: null
                            require_shipping: 1
                            cost_price: null
                            digital_download_limit: null
                            digital_download_expiry: null
                            from_instagram: 0
                            weight: 4.0539818069
                            with_tax: true
                            hide_quantity: false
                            min_amount_donating: null
                            max_amount_donating: null
                            subtitle: null
                            active_advance: 0
                            enable_upload_image: false
                            searchable_at: null
                            promotion_title: null
                            extra_attributes:
                              tax_reason_code: null
                            sort: 0
                            enable_note: false
                            thumbnail: null
                            thumbnail_alt_seo: null
                            target_donating_enable: false
                            unlimited_quantity: true
                            managed_by_branches: 1
                            notify_quantity: 0
                            show_in_app: true
                            child: 0
                            customized_sku_quantity: 0
                            starting_price: null
                            custom_url: null
                            calories: null
                            minimum_notify_quantity: null
                            subscribers_percentage: null
                            mpn: null
                            gtin: null
                            real_weight: 143
                            weight_type: oz
                            show_in_mahly_app: 0
                            mahly_category_id: null
                            spam_status: 0
                            show_in_web: true
                            minimum_quantity_per_order: 1
                            shipping_international: null
                            shipping_box_id: null
                            scoped_prices: []
                            sale_start: null
                            manufacture_country_id: null
                            show_in_landing_page: false
                          - id: 1444615766
                            sku: P-8362
                            name: product 02
                            price: 34
                            currency: SAR
                            description: null
                            options: ''
                            type: product
                            store_id: 67593
                            brand_id: null
                            quantity: 838
                            status: sale
                            rand_token: ''
                            views: 0
                            created_at: '2025-12-11T11:06:00.000000Z'
                            updated_at: '2026-01-11T18:01:01.000000Z'
                            minimum_order_time: '0'
                            maximum_daily_order: null
                            maximum_quantity_per_order: null
                            allow_attachments: 0
                            pinned: 0
                            pinned_date: '2025-12-11 14:06:00'
                            sale_price: null
                            sale_end: null
                            source: '24'
                            require_shipping: 0
                            cost_price: null
                            digital_download_limit: null
                            digital_download_expiry: null
                            from_instagram: 0
                            weight: 15.42214058
                            with_tax: true
                            hide_quantity: false
                            min_amount_donating: null
                            max_amount_donating: null
                            subtitle: null
                            active_advance: 1
                            enable_upload_image: false
                            searchable_at: null
                            promotion_title: null
                            extra_attributes:
                              tax_reason_code: null
                              has_custom_fields: false
                            sort: 17
                            enable_note: false
                            thumbnail: null
                            thumbnail_alt_seo: null
                            target_donating_enable: false
                            unlimited_quantity: false
                            managed_by_branches: 1
                            notify_quantity: null
                            show_in_app: true
                            child: 0
                            customized_sku_quantity: 1
                            starting_price: 34
                            custom_url: null
                            calories: null
                            minimum_notify_quantity: null
                            subscribers_percentage: null
                            mpn: null
                            gtin: null
                            real_weight: 34
                            weight_type: lb
                            show_in_mahly_app: 0
                            mahly_category_id: null
                            spam_status: 0
                            show_in_web: true
                            minimum_quantity_per_order: 1
                            shipping_international: null
                            shipping_box_id: null
                            scoped_prices: []
                            sale_start: null
                            manufacture_country_id: null
                            show_in_landing_page: false
                      discounts_table:
                        - quantity: '2'
                          discount_amount: '10'
                        - quantity: '4'
                          discount_amount: '20'
                      source: null
                      tiers: []
                      apply_type: null
                      with_current_cart: false
                      special_price: null
                      applied_with_coupon: false
                      scopes: []
                      exclude_sale_items: false
                      excluded_buy_products_ids: []
                      excluded_buy_categories_ids: []
                '5':
                  summary: Cart Offer
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1601705172
                      name: Basket Offer
                      message: ''
                      expiry_date: '2026-02-28 00:00:00'
                      start_date: '2026-01-29 00:00:00'
                      offer_type: cart_offer
                      status: inactive
                      show_price_after_discount: null
                      show_discounts_table_message: false
                      countries: []
                      customer_groups: []
                      applied_to: null
                      select_by: ''
                      options:
                        - id: 0
                          discount_apply_type: percentage
                          condition_threshold: 10
                          max_customer_discount: 50
                          discount_amount: 20
                      based_on: products_count
                      buy:
                        min_amount: 0
                        min_items: 0
                      get:
                        discount_amount: null
                      tiers: []
                      apply_type: null
                      with_current_cart: false
                      special_price: null
                      applied_with_coupon: false
                      scopes: []
                      exclude_sale_items: false
                      excluded_buy_products_ids: []
                      excluded_buy_categories_ids: []
                '6':
                  summary: Special Price Offer
                  value:
                    status: 200
                    success: true
                    data:
                      id: 2065846998
                      name: Special Price Offer
                      message: This message describes the offer
                      expiry_date: '2026-04-26 00:00:00'
                      start_date: '2026-01-26 00:00:00'
                      offer_type: special_price
                      status: inactive
                      show_price_after_discount: false
                      show_discounts_table_message: false
                      countries: []
                      customer_groups:
                        - 1354073706
                      applied_to: product
                      select_by: ''
                      options: []
                      based_on: null
                      buy:
                        min_amount: 0
                        min_items: 0
                        products:
                          - id: 1298176905
                            sku: P-7636
                            name: product 01
                            price: 123
                            currency: SAR
                            description: ''
                            options: ''
                            type: product
                            store_id: 67593
                            brand_id: null
                            quantity: 0
                            status: sale
                            rand_token: ''
                            views: 0
                            created_at: '2026-01-18T23:27:56.000000Z'
                            updated_at: '2026-01-21T12:12:26.000000Z'
                            minimum_order_time: '0'
                            maximum_daily_order: null
                            maximum_quantity_per_order: null
                            allow_attachments: 0
                            pinned: 0
                            pinned_date: '2026-01-19 02:27:56'
                            sale_price: null
                            sale_end: null
                            source: null
                            require_shipping: 1
                            cost_price: null
                            digital_download_limit: null
                            digital_download_expiry: null
                            from_instagram: 0
                            weight: 4.0539818069
                            with_tax: true
                            hide_quantity: false
                            min_amount_donating: null
                            max_amount_donating: null
                            subtitle: null
                            active_advance: 0
                            enable_upload_image: false
                            searchable_at: null
                            promotion_title: null
                            extra_attributes:
                              tax_reason_code: null
                            sort: 0
                            enable_note: false
                            thumbnail: null
                            thumbnail_alt_seo: null
                            target_donating_enable: false
                            unlimited_quantity: true
                            managed_by_branches: 1
                            notify_quantity: 0
                            show_in_app: true
                            child: 0
                            customized_sku_quantity: 0
                            starting_price: null
                            custom_url: null
                            calories: null
                            minimum_notify_quantity: null
                            subscribers_percentage: null
                            mpn: null
                            gtin: null
                            real_weight: 143
                            weight_type: oz
                            show_in_mahly_app: 0
                            mahly_category_id: null
                            spam_status: 0
                            show_in_web: true
                            minimum_quantity_per_order: 1
                            shipping_international: null
                            shipping_box_id: null
                            scoped_prices: []
                            sale_start: null
                            manufacture_country_id: null
                            show_in_landing_page: false
                          - id: 1444615766
                            sku: P-8726
                            name: product 02
                            price: 34
                            currency: SAR
                            description: null
                            options: ''
                            type: product
                            store_id: 67593
                            brand_id: null
                            quantity: 838
                            status: sale
                            rand_token: ''
                            views: 0
                            created_at: '2025-12-11T11:06:00.000000Z'
                            updated_at: '2026-01-11T18:01:01.000000Z'
                            minimum_order_time: '0'
                            maximum_daily_order: null
                            maximum_quantity_per_order: null
                            allow_attachments: 0
                            pinned: 0
                            pinned_date: '2025-12-11 14:06:00'
                            sale_price: null
                            sale_end: null
                            source: '24'
                            require_shipping: 0
                            cost_price: null
                            digital_download_limit: null
                            digital_download_expiry: null
                            from_instagram: 0
                            weight: 15.42214058
                            with_tax: true
                            hide_quantity: false
                            min_amount_donating: null
                            max_amount_donating: null
                            subtitle: null
                            active_advance: 1
                            enable_upload_image: false
                            searchable_at: null
                            promotion_title: null
                            extra_attributes:
                              tax_reason_code: null
                              has_custom_fields: false
                            sort: 17
                            enable_note: false
                            thumbnail: null
                            thumbnail_alt_seo: null
                            target_donating_enable: false
                            unlimited_quantity: false
                            managed_by_branches: 1
                            notify_quantity: null
                            show_in_app: true
                            child: 0
                            customized_sku_quantity: 1
                            starting_price: 34
                            custom_url: null
                            calories: null
                            minimum_notify_quantity: null
                            subscribers_percentage: null
                            mpn: null
                            gtin: null
                            real_weight: 34
                            weight_type: lb
                            show_in_mahly_app: 0
                            mahly_category_id: null
                            spam_status: 0
                            show_in_web: true
                            minimum_quantity_per_order: 1
                            shipping_international: null
                            shipping_box_id: null
                            scoped_prices: []
                            sale_start: null
                            manufacture_country_id: null
                            show_in_landing_page: false
                      get:
                        discount_amount: '0.00'
                      tiers: []
                      apply_type: null
                      with_current_cart: false
                      special_price:
                        quantity: 3
                        price: 90
                      applied_with_coupon: false
                      scopes: []
                      exclude_sale_items: false
                      excluded_buy_products_ids: []
                      excluded_buy_categories_ids: []
                '7':
                  summary: Tiered Offer
                  value:
                    status: 200
                    success: true
                    data:
                      id: 1890762705
                      name: Tiered Offer
                      message: Tiered Offer Description
                      expiry_date: '2026-03-26 11:24:13'
                      start_date: '2026-02-26 11:24:13'
                      offer_type: tiered_offer
                      status: inactive
                      show_price_after_discount: false
                      show_discounts_table_message: false
                      countries: []
                      customer_groups: []
                      applied_to: order
                      select_by: ''
                      options: []
                      based_on: null
                      buy:
                        min_amount: 0
                        min_items: 0
                      get:
                        discount_amount: '0.00'
                      tiers:
                        - name: Tier One
                          min_purchases: 200
                          type: percentage
                          discount: 20
                        - name: Tier Two
                          min_purchases: 1000
                          type: percentage
                          discount: 50
                      apply_type: min_purchases
                      with_current_cart: true
                      special_price: null
                      applied_with_coupon: true
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
                    specialoffers.read
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
      x-salla-php-return-type: SpecialOffer
      x-apidog-folder: Default module/Merchant API/APIs/Special Offers
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394219-run
components:
  schemas:
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
              items: &ref_0
                $ref: '#/components/schemas/ProductCard'
            categories:
              type: array
              description: >
                The Categories included in the special offer. Make sure to pass
                the Category IDs in an array. List of Category IDs can be foun
                [here](https://docs.salla.dev/5394207e0) This field is mandatory
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
              items: *ref_1
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
    Category:
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

