# Apis Brands  Brand Details Salla Merchant Api Salla Docs

## Table of Contents

- [apis-brands/Brand-Details-Salla-Merchant-API-Salla-Docs](#apis-brands-brand-details-salla-merchant-api-salla-docs)
- [apis-brands/Create-Brand-Salla-Merchant-API-Salla-Docs](#apis-brands-create-brand-salla-merchant-api-salla-docs)
- [apis-brands/Delete-Brand-Salla-Merchant-API-Salla-Docs](#apis-brands-delete-brand-salla-merchant-api-salla-docs)

---

## apis-brands/Brand-Details-Salla-Merchant-API-Salla-Docs

# Brand Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /brands/{brand}:
    get:
      summary: Brand Details
      deprecated: false
      description: >
        This endpoint allows you to return the complete details for a specific
        brand by passing the `brand` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `brands.read`- Brands Read Only

        </Accordion>
      operationId: Brand-Details
      tags:
        - Default module/Merchant API/APIs/Brands
        - Brands
      parameters:
        - name: brand
          in: path
          description: >-
            Unique identifier assigned to the Brand. List of Brand IDs can be
            found [here](https://docs.salla.dev/api-5394213)
          required: true
          example: 0
          schema:
            type: integer
        - name: with
          in: query
          description: Use `with=translations` to fetch list of brands with translations
          required: false
          example: translations
          schema:
            type: string
            enum:
              - translations
            x-apidog-enum:
              - name: ''
                value: translations
                description: List of brands with translations
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/brand_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 510571718
                  name: hayat
                  description: Al Hayat Brand
                  banner: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  logo: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  ar_char: حياه
                  en_char: Hayat
                  metadata:
                    title: Zara brand
                    description: Brand awareness seo
                    url: zara/item
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
                    brand.read
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
          x-apidog-name: Record Not Found
        x-200:With translations:
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/brandWithTranslations_response_body'
              example:
                status: 200
                success: true
                data:
                  id: 510571718
                  name: زارا
                  description: ماركه زارا
                  banner: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  logo: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  ar_char: ه
                  en_char: h
                  metadata:
                    title: Zara brand
                    description: Brand awareness seo
                    url: zara/item
                  translations:
                    ar:
                      name: زارا
                      description: زارا brand
                      metadata:
                        title: Meta AR
                        description: description AR
                        url: linkAR
                    en:
                      name: Zara EN
                      description: Zara brand
                      metadata:
                        title: Meta EN
                        description: description EN
                        url: linkEN
          headers: {}
          x-apidog-name: With translations
      security:
        - bearer: []
      x-salla-php-method-name: retrieve
      x-salla-php-return-type: Brand
      x-apidog-folder: Default module/Merchant API/APIs/Brands
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394214-run
components:
  schemas:
    brand_response_body:
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
          $ref: '#/components/schemas/Brand'
      x-apidog-orders:
        - status
        - success
        - data
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
    brandWithTranslations_response_body:
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
          $ref: '#/components/schemas/BrandWithTranslation'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    BrandWithTranslation:
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
      title: BrandWithTranslation
      properties:
        id:
          description: >-
            Brand ID is a unique identifier assigned to a specific brand, aiding
            in precise tracking and management of products associated with that
            brand.
          type: number
        name:
          type: string
          description: >-
            Brand name is the distinctive label given to a particular
            manufacturer or company, helping to identify and differentiate its
            products in the market. 🌐 [Support multi-language](doc-421122)
        description:
          type: string
          description: >-
            Brand description is a brief overview that highlights key
            attributes, values, and qualities associated with a particular
            manufacturer or company, providing insights into its identity and
            offerings. 🌐 [Support multi-language](doc-421122)
        banner:
          type: string
          description: >-
            A text-based representation or URL link that directs to an image
            file, used as a visual symbol to identify and represent a brand on a
            webpage or platform.
        logo:
          type: string
          description: >-
            A text-based representation or URL link that directs to an image
            file, used as a visual symbol to identify and represent a brand on a
            webpage or platform.
        ar_char:
          type: string
          description: Brand represented in Arabic character
        en_char:
          type: string
          description: Brand represented in English character
        metadata:
          type: object
          x-stoplight:
            id: 8d0s0tfwzpf28
          properties:
            title:
              type: string
              x-stoplight:
                id: bwvcv90k4e5uu
              description: >-
                Metadata Title which is a concise label used to optimize search
                engine results and enhance the visibility of a Brand page. 🌐
                [Support multi-language](doc-421122)
            description:
              type: string
              x-stoplight:
                id: idnybfvxrkyyv
              description: >-
                SEO Metadata Description:Concise content enhancing search
                visibility and social sharing. 
            url:
              type: string
              x-stoplight:
                id: ztu8v1b826bp3
              description: >-
                SEO Metadata URL: Web link for enhanced search engine visibility
                and social media sharing.  🌐 [doc-421122)
          x-apidog-orders:
            - title
            - description
            - url
          required:
            - title
            - description
            - url
          x-apidog-ignore-properties: []
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                metadata:
                  type: object
                  x-stoplight:
                    id: 8d0s0tfwzpf28
                  properties:
                    title:
                      type: string
                      x-stoplight:
                        id: bwvcv90k4e5uu
                      description: >-
                        Metadata Title which is a concise label used to optimize
                        search engine results and enhance the visibility of a
                        Brand page. 🌐 [Support multi-language](doc-421122)
                    description:
                      type: string
                      x-stoplight:
                        id: idnybfvxrkyyv
                      description: >-
                        SEO Metadata Description:Concise content enhancing
                        search visibility and social sharing.  🌐 [doc-421122)
                    url:
                      type: string
                      x-stoplight:
                        id: ztu8v1b826bp3
                      description: >-
                        SEO Metadata URL: Web link for enhanced search engine
                        visibility and social media sharing.  🌐 [doc-421122)
                  x-apidog-orders:
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
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
          required:
            - en
          description: >-
            Brand translations are based on the store's enabled language locale.
            For instance, if the store supports both Arabic and English, the
            `translations` object will return two entries: `ar` for Arabic and
            `en` for English.
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - id
        - name
        - description
        - banner
        - logo
        - ar_char
        - en_char
        - metadata
        - translations
      required:
        - id
        - name
        - description
        - banner
        - logo
        - ar_char
        - en_char
        - metadata
        - translations
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

## apis-brands/Create-Brand-Salla-Merchant-API-Salla-Docs

# Create Brand

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /brands:
    post:
      summary: Create Brand
      deprecated: false
      description: |
        This endpoint allows you to create a new brand in the store

        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">
        `brands.read_write`- Brands Read & Write
        </Accordion>
      operationId: Create-Brand
      tags:
        - Default module/Merchant API/APIs/Brands
        - Brands
      parameters:
        - name: Content-Type
          in: header
          description: multipart/form-data
          required: false
          example: ''
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/brand_rquest_body'
            example: |-
              {
                  "name": "ابل",
                  "logo": "",
                  "banner": "",
                  "description": "شركه ابل",
                  "metadata_title": "ابل",
                  "metadata_description": "شركه ابل",
                  "metadata_url": "apple",
                  "translations": {
                      "en": {
                          "name": "Apple",
                          "description": "Apple brand",
                          "metadata_title": "Apple",
                          "metadata_description": "Apple brand",
                          "metadata_url": "apple",
                      }
                  }
              }
      responses:
        '201':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/brand_response_body'
              example:
                status: 201
                success: true
                data:
                  id: 1283560901
                  name: salamaBrand
                  description: Al Salama Brand
                  banner: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  logo: https://i.ibb.co/jyqRQfQ/avatar-male.webp
                  ar_char: س
                  en_char: s
                  metadata:
                    title: Zara brand
                    description: Brand awareness seo
                    url: zara/item
          headers: {}
          x-apidog-name: New brand created successfully.
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
                    brands.read_write
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
                    name:
                      - حقل اسم الماركة مطلوب.
          headers: {}
          x-apidog-name: Error Validation
      security:
        - bearer: []
      x-salla-php-method-name: create
      x-salla-php-return-type: Brand
      x-apidog-folder: Default module/Merchant API/APIs/Brands
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394212-run
components:
  schemas:
    brand_rquest_body:
      type: object
      properties:
        name:
          type: string
          description: >-
            The unique name or label associated with a specific company,
            manufacturer, or producer of products or services. 🌐 [Support
            multi-language](https://docs.salla.dev/doc-421122)
        logo:
          type: string
          description: >-
            Brand logo (string or file) is the visual representation of a brand,
            either in the form of an image or a file, with recommended
            dimensions typically set at 100x80** pixels
          format: binary
        banner:
          type: string
          description: >-
            A text-based representation or URL link that directs to an image
            file, used as a visual symbol to identify and represent a brand on a
            webpage or platform.
          format: binary
        description:
          type: string
          description: >-
            Brand description is a brief overview that highlights key
            attributes, values, and qualities associated with a particular
            manufacturer or company, providing insights into its identity and
            offerings. 🌐 [Support
            multi-language](docs/1.%20Introduction/1.6.Multi-Language-Support.md)
          x-stoplight:
            id: 0x3bxwmxd52n7
        metadata_title:
          type: string
          x-stoplight:
            id: izkrff02wewq2
          description: >-
            Metadata Title which is a concise label used to optimize search
            engine results and enhance the visibility of a Brand page.
            [🌐Support multi-language](doc-421122)
        'metadata_description ':
          type: string
          description: >-
            SEO Metadata Description:Concise content enhancing search visibility
            and social sharing.  🌐 [Support multi-language](doc-421122)
          x-stoplight:
            id: d5qb0j3q2nib8
        metadata_url:
          type: string
          x-stoplight:
            id: asooh6qvtuqg1
          description: >-
            SEO Metadata URL: Web link for enhanced search engine visibility and
            social media sharing.  🌐 [Support multi-language](doc-421122)
        translations:
          type: object
          properties:
            en:
              type: object
              properties:
                name:
                  type: string
                metadata:
                  type: object
                  x-stoplight:
                    id: 8d0s0tfwzpf28
                  properties:
                    title:
                      type: string
                      x-stoplight:
                        id: bwvcv90k4e5uu
                      description: >-
                        Metadata Title which is a concise label used to optimize
                        search engine results and enhance the visibility of a
                        Brand page. 🌐 [Support multi-language](doc-421122)
                    description:
                      type: string
                      x-stoplight:
                        id: idnybfvxrkyyv
                      description: >-
                        SEO Metadata Description:Concise content enhancing
                        search visibility and social sharing.  🌐 [doc-421122)
                    url:
                      type: string
                      x-stoplight:
                        id: ztu8v1b826bp3
                      description: >-
                        SEO Metadata URL: Web link for enhanced search engine
                        visibility and social media sharing.  🌐 [doc-421122)
                  x-apidog-orders:
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
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - en
          required:
            - en
          description: >-
            Brand translations are based on the store's enabled language locale.
            For instance, if the store supports both Arabic and English, the
            `translations` object will return two entries: `ar` for Arabic and
            `en` for English.
          x-apidog-ignore-properties: []
      required:
        - name
        - logo
      x-apidog-orders:
        - name
        - logo
        - banner
        - description
        - metadata_title
        - 'metadata_description '
        - metadata_url
        - translations
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    brand_response_body:
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
          $ref: '#/components/schemas/Brand'
      x-apidog-orders:
        - status
        - success
        - data
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

## apis-brands/Delete-Brand-Salla-Merchant-API-Salla-Docs

# Delete Brand

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /brands/{brand}:
    delete:
      summary: Delete Brand
      deprecated: false
      description: >-
        This endpoint allows you to delete a specific brand by passing the
        `brand` as a path parameter. 



        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `brands.read_write`- Brands Read & Write

        </Accordion>
      operationId: Delete-Brand
      tags:
        - Default module/Merchant API/APIs/Brands
        - Brands
      parameters:
        - name: brand
          in: path
          description: >-
            Unique identifier assigned to the Brand. List of Brand IDs can be
            found [here](https://docs.salla.dev/api-5394213)
          required: true
          example: 0
          schema:
            type: integer
      responses:
        '202':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/delete_success'
              example:
                status: 202
                success: true
                data:
                  message: The Object has been removed successfully
                  code: 202
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
                    brands.read_write
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
      x-apidog-folder: Default module/Merchant API/APIs/Brands
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5394216-run
components:
  schemas:
    delete_success:
      type: object
      properties:
        status:
          type: number
          description: >-
            Response status code, a numeric or alphanumeric identifier used to
            convey the outcome or status of a request, operation, or transaction
            in various systems and applications, typically indicating whether
            the action was successful, encountered an error, or resulted in a
            specific condition.Response status Code
        success:
          type: boolean
          description: >-
            Response flag, boolean indicator used to signal a particular
            condition or state in the response of a system or application, often
            representing the presence or absence of certain conditions or
            outcomes.
        data:
          $ref: '#/components/schemas/DeleteSuccess'
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    DeleteSuccess:
      type: object
      properties:
        message:
          type: string
          description: >-
            A message or data structure that is generated or returned when a
            deletion operation is successful.
        code:
          type: number
          description: >-
            A numerical or alphanumeric code that is used in various software
            and web development contexts to convey information about the outcome
            of a request or operation.
      x-apidog-orders:
        - message
        - code
      required:
        - message
        - code
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

