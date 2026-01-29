# Getting Started

## Table of Contents

- [additional-resources/Troubleshooting-Salla-CLI-Salla-Docs](#additional-resources-troubleshooting-salla-cli-salla-docs)
- [additional-resources/Upgrade-and-Version-Salla-CLI-Salla-Docs](#additional-resources-upgrade-and-version-salla-cli-salla-docs)
- [apis/Abandoned-Carts](#apis-abandoned-carts)
- [apis/Advertisements](#apis-advertisements)
- [apis/Affiliates](#apis-affiliates)
- [apis/Branch-Delivery-Zones](#apis-branch-delivery-zones)
- [apis/Branches](#apis-branches)
- [apis/Branches-Allocations](#apis-branches-allocations)
- [apis/Brands](#apis-brands)
- [apis/Cancel-Subscription-Salla-Merchants-APIs-Salla-Docs](#apis-cancel-subscription-salla-merchants-apis-salla-docs)
- [apis/Categories](#apis-categories)
- [apis/Charge-Subscription-Salla-Merchants-APIs-Salla-Docs](#apis-charge-subscription-salla-merchants-apis-salla-docs)
- [apis/Cities](#apis-cities)
- [apis/Countries](#apis-countries)
- [apis/Coupons](#apis-coupons)
- [apis/Currencies](#apis-currencies)
- [apis/Custom-URLs](#apis-custom-urls)
- [apis/Customer-Groups](#apis-customer-groups)
- [apis/Customer-Wallet](#apis-customer-wallet)
- [apis/Customers](#apis-customers)
- [apis/DNS-Records](#apis-dns-records)
- [apis/Digitals-Product](#apis-digitals-product)
- [apis/Employees](#apis-employees)
- [apis/Feedbacks](#apis-feedbacks)
- [apis/Languages](#apis-languages)
- [apis/Loyalty-Points](#apis-loyalty-points)
- [apis/Merchant](#apis-merchant)
- [apis/Order-Assignment](#apis-order-assignment)
- [apis/Order-Histories](#apis-order-histories)
- [apis/Order-Invoice](#apis-order-invoice)
- [apis/Order-Items](#apis-order-items)
- [apis/Order-Options](#apis-order-options)
- [apis/Order-Reservations](#apis-order-reservations)
- [apis/Order-Status](#apis-order-status)
- [apis/Payments](#apis-payments)
- [apis/Product-Images](#apis-product-images)
- [apis/Product-Option-Templates](#apis-product-option-templates)
- [apis/Product-Option-Values](#apis-product-option-values)
- [apis/Product-Options](#apis-product-options)
- [apis/Product-Tags](#apis-product-tags)
- [apis/Product-Variants](#apis-product-variants)
- [apis/Reviews](#apis-reviews)
- [apis/SEO](#apis-seo)
- [apis/Settings](#apis-settings)
- [apis/Shipments](#apis-shipments)
- [apis/Shipping-Companies](#apis-shipping-companies)
- [apis/Shipping-Routes](#apis-shipping-routes)
- [apis/Shipping-Zones](#apis-shipping-zones)
- [apis/Special-Offers](#apis-special-offers)
- [apis/Taxes](#apis-taxes)
- [apis/Transactions](#apis-transactions)
- [apis/Update-Payment-Method](#apis-update-payment-method)
- [apis/Webhooks](#apis-webhooks)
- [getting-started/Create-Salla-Theme-Twilight-Documentation-Salla-Docs](#getting-started-create-salla-theme-twilight-documentation-salla-docs)
- [getting-started/Develop-a-Theme-Twilight-Documentation-Salla-Docs](#getting-started-develop-a-theme-twilight-documentation-salla-docs)
- [getting-started/Publish-a-Theme-Twilight-Documentation-Salla-Docs](#getting-started-publish-a-theme-twilight-documentation-salla-docs)
- [getting-started/Setup-Themes-Twilight-Documentation-Salla-Docs](#getting-started-setup-themes-twilight-documentation-salla-docs)
- [settings/App-Setting-Details-Partners-Apps-APIs-Salla-Docs](#settings-app-setting-details-partners-apps-apis-salla-docs)
- [settings/Update-App-Settings-Partners-Apps-APIs-Salla-Docs](#settings-update-app-settings-partners-apps-apis-salla-docs)

---

## additional-resources/Troubleshooting-Salla-CLI-Salla-Docs

# Troubleshooting

In the course of using the Salla CLI, you may encounter various issues or error messages. These can stem from a variety of causes, from minor misconfigurations to deeper problems requiring more thorough investigation. This section presents a range of common errors and their corresponding troubleshooting steps to guide you in resolving these issues efficiently. Remember, each problem is an opportunity to better understand the workings of the Salla CLI.

## Identifying and Resolving Common Issues
The key to working effectively on any technical task is understanding how to troubleshoot and resolve issues. Here are some of the common error messages you might encounter, along with explanations and suggested solutions for each:

| Common Error Messages | Description | Suggested Solutions |
| --- | --- | --- |
| Preview Error | While previewing the Twilight theme during development using your browser, it seems to not be replacing assets url with `localhost:8000/assets/...`. | Select the preview browser when prompting the Salla CLI [`preview`](doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK) command. |
|Preview Error 404|The Theme preview encounters an error with code number 404.| You can preview the store froma different demo store. <TipInfo>Read more about Demo Store theme preview [here](https://salla.dev/blog/themes-preview-on-demo-stores/) </TipInfo>
| Non-existent Theme ID | The theme ID doesn't exist in your developer account. | Re-login through the CLI using the command [salla login](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK). |
| CLI Request Failure | The CLI failed to request a preview for the theme. | Reconnect your [Github](https://github.com/) account to Salla and give all authorizations. |
| Web Socket Issue | There's an issue with the web socket. | Contact support via [Telegram](https://t.me/SallaSupportBot). |
| Token Authorization | There's a problem with token authorization. | Personal Accesss Token is used as an alternative to passwords for authentication to Github with Salla CLI. This step is required for creating themes using Salla CLI. Read more [here](https://docs.salla.dev/doc-422769?nav=01HNA8QHCPJTCY5VSEZ616JCAK).  |
| Bad CPU Type in executable | Users with Apple devices running on the Apple Silicon chip processors will face a problem, which is caused by the package used, [cloudflare](https://www.npmjs.com/package/cloudflare). The package is not compatible *yet* with Apple devices using the new Apple Silicon chip. | Installing Rosetta by following this [guide](https://docs.salla.dev/doc-422761?nav=01HNA8QHCPJTCY5VSEZ616JCAK). 






## Preventing Salla CLI Errors

:::tip[Note]
Remember, troubleshooting is a systematic process. If the first solution doesn't resolve the problem, don't be discouraged. Move on to the next step, and continue the process until the issue is resolved.
:::

To mitigate issues with the Salla CLI, consider these preventative measures:

-   Ensure proper login to your [Salla Partners Account](https://salla.partners/) and local GitHub account for secure interactions.
-   Regularly [update](https://docs.salla.dev/doc-422763?nav=01HNA8QHCPJTCY5VSEZ616JCAK) your Salla CLI to benefit from bug fixes and feature improvements.
-   Familiarize yourself with the options of each Salla CLI command for greater control and efficiency.

Adopting these best practices can lead to a smoother, trouble-free experience with the Salla CLI.

---

## additional-resources/Upgrade-and-Version-Salla-CLI-Salla-Docs

# Upgrade and Version

As a part of maintaining a good performance for the Apps and Themes in Salla, the developers continuously enhance their products with new features that require updating. This article shows the commands that the developer can use to perform the upgrade and check the current version of Salla CLI.


## 📙 What you'll learn

- [Upgrade](#upgrade)
- [Version](#version)
<hr>

## Upgrade

To upgrade the [Salla CLI](https://github.com/SallaApp/Salla-CLI) package globally, you need to run:

```bash title = "Terminal"
npm install @salla.sa/cli@latest -g
```

## Version

To check the version of Salla Apps and Themes

```bash title = "Terminal"
salla --version
```

---

## apis/Abandoned-Carts

# Abandoned Carts

## Docs

- [List Abandoned Carts](https://docs.salla.dev/5394138e0.md): This endpoint allows you to list abandoned carts that contain all the needed data that you can use to help customers continue the purchasing process.
- [Abandoned Cart Details](https://docs.salla.dev/5394139e0.md): This endpoint allows you to return the complete details for a specific abandoned cart by passing the `cart-id` as a path parameter.

---

## apis/Advertisements

# Advertisements

## Docs

- [Create Advertisement](https://docs.salla.dev/5394264e0.md): This endpoint allows you to create an advertisement post of the store on its pages.
- [List Advertisements](https://docs.salla.dev/5394265e0.md): This endpoint allows you to list all of the advertisement posts of the store.
- [Advertisement Details](https://docs.salla.dev/5394266e0.md): This endpoint allows you to list an existing advertisement post by passing the `advertisement_id` as a path parameter. 
- [Update Advertisement](https://docs.salla.dev/5394267e0.md): This endpoint allows you to update an existing advertisement post by passing the `advertisement_id` as a path parameter. 
- [Delete Advertisement](https://docs.salla.dev/5394268e0.md): This endpoint allows you to delete an existing advertisement post by passing the `advertisement_id` as a path parameter.

---

## apis/Affiliates

# Affiliates

## Docs

- [List Affiliates](https://docs.salla.dev/5394270e0.md): This endpoint allows you to fetch a list of marketing affiliates.
- [Affiliate Details](https://docs.salla.dev/5394271e0.md): This endpoint allows you to fetch details regarding an affiliate by passing the `affiliate_id` as a path parameter.
- [List Affiliate Links](https://docs.salla.dev/13902666e0.md): This endpoint allows you to fetch links for  a specific affiliate by passing the `affiliate_id` as a path parameter.
- [Create Affiliate](https://docs.salla.dev/5394269e0.md): This endpoint allows you to create a marketing affiliate.
- [Update Affiliate](https://docs.salla.dev/5394272e0.md): This endpoint allows you to update details regarding an affiliate by passing the `affiliate_id` as a path parameter.
- [Delete Affiliate](https://docs.salla.dev/5394273e0.md): This endpoint allows you to delete an affiliate by passing the `affiliate_id` as a path parameter.

---

## apis/Branch-Delivery-Zones

# Branch Delivery Zones

## Docs

- [List Branch Delivery Zones](https://docs.salla.dev/22300545e0.md): This endpoint is used to retrieve delivery zone configurations for specific branches. It helps determine which geographical areas (zones) each branch can serve for deliveries
- [Branch Delivery Zone Details](https://docs.salla.dev/22300546e0.md): This Endpoint is used to show a branch’s delivery zo, including the area defined by either a radius or a polygon.
- [Create Branch Delivery Zone](https://docs.salla.dev/22300547e0.md): This endpoint is using for creating a new delivery zone and defining a branch’s delivery coverage by specifying its status and setting the area using either a radius or polygon coordinates
- [Update Branch Delivery Zone](https://docs.salla.dev/22300548e0.md): This endpoint allows modifying an existing branch’s delivery coverage, such as changing its status, adjusting the radius, or updating polygon coordinates to keep the service area accurate and up to date
- [Delete Branch Delivery Zone](https://docs.salla.dev/22300549e0.md): This endpoint is used for removing an existing delivery coverage configuration from a branch

---

## apis/Branches

# Branches

## Docs

- [Create Branch](https://docs.salla.dev/5394223e0.md): This endpoint allows you to create a new branch and return the created branch id and its details.
- [List Branches](https://docs.salla.dev/5394224e0.md): This endpoint allows you to list all branches related to your store directly from this endpoint.
- [Branch Details](https://docs.salla.dev/5394225e0.md): This endpoint allows you to return the complete details for a specific branch by passing the `branch` as a path parameter. 
- [Update Branch](https://docs.salla.dev/5394226e0.md): This endpoint allows you to update branch details by passing the `branch` as a path parameter. 
- [Delete Branch](https://docs.salla.dev/5394227e0.md): This endpoint allows you to delete a specific branch by passing the `branch` as a path parameter.

---

## apis/Branches-Allocations

# Branches Allocations

> These endpoints are used to assign shipping companies to specific branches based on location, so customers only see relevant options when ordering. 

## Docs

- [Branch Allocation Details](https://docs.salla.dev/18877324e0.md): This endpoint allows you to show the allocated branch details by passing the `id`of the allocated branch as a path parameter; the response includes the assigned shipping companies based on branch coordinates.
- [Create Branches Allocations](https://docs.salla.dev/18495510e0.md): This endpoint allows you to define allocation rules for a branch, including assigning couriers and setting coverage areas.
- [Update Branches Allocations](https://docs.salla.dev/18495548e0.md): This endpoint allows you to update a branch’s configuration by passing the `id`of the allocated branch as a path parameter, including its courier and area allocation rules.
- [Delete Branches Allocations](https://docs.salla.dev/18495551e0.md): This endpoint allows you to delete a specific allocation branch.
- [Allocation Branch Settings](https://docs.salla.dev/22349439e0.md): This endpoint provides the configuration for how orders are assigned to branches and defines the strategy for deducting stock from branch inventories
- [List Branches Allocations](https://docs.salla.dev/18495252e0.md): This endpoint allows you to fetch a list of allocated branches with their rules, showing which shipping companies are assigned based on branch location.

---

## apis/Brands

# Brands

## Docs

- [Create Brand](https://docs.salla.dev/5394212e0.md): This endpoint allows you to create a new brand in the store
- [List Brands](https://docs.salla.dev/5394213e0.md): This endpoint allows you to list all brands related to your store directly from this endpoint. Also, it allows you to filter them using a keyword, the endpoint would return any brand which name matches this keyword.
- [Brand Details](https://docs.salla.dev/5394214e0.md): This endpoint allows you to return the complete details for a specific brand by passing the `brand` as a path parameter. 
- [Update Brand](https://docs.salla.dev/5394215e0.md): This endpoint allows you to update brand details by passing the `brand` as a path parameter. 
- [Delete Brand](https://docs.salla.dev/5394216e0.md): This endpoint allows you to delete a specific brand by passing the `brand` as a path parameter.

---

## apis/Cancel-Subscription-Salla-Merchants-APIs-Salla-Docs

# Cancel Subscription

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /admin/v2/subscriptions/{subscription_id}:
    delete:
      summary: Cancel Subscription
      deprecated: false
      description: >-
        Cancel an active subscription immediately. This stops all future
        automatic charges. Existing orders/invoices remain unchanged. A webhook
        `subscription.cancelled` is emitted.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `subscriptions.read_write` - Subscriptions Read & Write

        </Accordion>
      tags:
        - Recurring Payment Apps/APIs
      parameters:
        - name: subscription_id
          in: path
          description: >-
            Unique identifier of the subscription to retrieve. Must refer to a
            valid subscription created via checkout or API.
          required: true
          example: '814202285'
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
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
                  data:
                    type: object
                    properties:
                      code:
                        type: integer
                        description: Response Code
                      message:
                        type: 'null'
                        description: Response Message
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
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
          headers: {}
          x-apidog-name: Success
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
          headers: {}
          x-apidog-name: validation_error
      security:
        - bearer: []
      x-apidog-folder: Recurring Payment Apps/APIs
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-21076365-run
components:
  schemas:
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

## apis/Categories

# Categories

## Docs

- [Create Category](https://docs.salla.dev/5394206e0.md): This endpoint allows you to create a new category and return the category ID and its details.
- [List Categories](https://docs.salla.dev/5394207e0.md): This endpoint allows you to list all categories related to your store directly from this endpoint. Also, it allows you to filter them using a keyword, the endpoint would return any category which name matches this keyword.
- [Category Details](https://docs.salla.dev/5394208e0.md): This endpoint allows you to return the complete details for a specific category by passing the `category` as a path parameter. 
- [Update Category](https://docs.salla.dev/5394209e0.md): This endpoint allows you to update category details by passing the `category` as a path parameter. 
- [Delete Category](https://docs.salla.dev/5394210e0.md): This endpoint allows you to delete a specific category by passing the `category` as a path parameter. 
- [Category Children](https://docs.salla.dev/5394211e0.md): This endpoint allows you to return specific category children by passing the `category` as a path parameter. 
- [Categories Search](https://docs.salla.dev/10309545e0.md): This endpoint allows you to search through existing categories using keywords *(a.k.a name of the category)* as well as an array of Category IDs
- [List Category Products](https://docs.salla.dev/11055135e0.md): This endpoint allows you to list all the products and their sort order that are related in a specified category by passing the `id` as a path parameter..

---

## apis/Charge-Subscription-Salla-Merchants-APIs-Salla-Docs

# Charge Subscription

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /admin/v2/subscriptions/{subscription_id}/charge:
    post:
      summary: Charge Subscription
      deprecated: false
      description: >-
        Manually trigger a charge for an active subscription. On success, it
        creates a cart from the subscription items, generates an invoice,
        processes payment via the configured gateway, creates a final order, and
        emits webhooks.


        <Accordion title="Scopes" defaultOpen={true} icon="lucide-key-round">

        `subscriptions.read_write` - Subscriptions Read & Write

        </Accordion>
      tags:
        - Recurring Payment Apps/APIs
      parameters:
        - name: subscription_id
          in: path
          description: >-
            The unique identifier of the active subscription to be charged. This
            ID must reference a valid and active subscription that belongs to
            the store.
          required: true
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
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
                  data:
                    type: object
                    properties:
                      code:
                        type: integer
                        description: Response Code
                      message:
                        type: 'null'
                        description: Response Message
                      subscription_id:
                        type: integer
                        description: >-
                          Unique identifier of the subscription that was
                          charged.
                    required:
                      - code
                      - message
                      - subscription_id
                    x-apidog-orders:
                      - code
                      - message
                      - subscription_id
                    x-apidog-ignore-properties: []
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
          headers: {}
          x-apidog-name: Success
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
          headers: {}
          x-apidog-name: validation_error
      security:
        - bearer: []
      x-apidog-folder: Recurring Payment Apps/APIs
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-21070946-run
components:
  schemas:
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

## apis/Cities

# Cities

## Docs

- [List Cities](https://docs.salla.dev/5394230e0.md): This endpoint allows you to list all available cities for a specific country by passing the `country` as a path parameter.

---

## apis/Countries

# Countries

## Docs

- [List Countries](https://docs.salla.dev/5394228e0.md): This endpoint allows you to list all available countries. 
- [Country Details](https://docs.salla.dev/5394229e0.md): This endpoint allows you to return the details for a specific country by passing the `country` as a path parameter.

---

## apis/Coupons

# Coupons

## Docs

- [Create Coupon](https://docs.salla.dev/5394274e0.md): 
- [List Coupons](https://docs.salla.dev/5394275e0.md): This endpoint allows you to return a list of coupons.
- [Coupon Details](https://docs.salla.dev/5394276e0.md):  This endpoint allows you to fetch details regarding a coupon by passing the `coupon_id` as a path parameter.
- [Update Coupon](https://docs.salla.dev/5394277e0.md): This endpoint allows you to update details regarding a coupon by passing the `coupon_id` as a path parameter.
- [Delete Coupon](https://docs.salla.dev/5394278e0.md):  This endpoint allows you to delete a coupon by passing the `coupon_id` as a path parameter.
- [List Coupon Codes](https://docs.salla.dev/9185252e0.md): This endpoint allows you to return all the child coupons of the parent coupon by passing the `coupon_id` as a query parameter.

---

## apis/Currencies

# Currencies

## Docs

- [Activate Currencies](https://docs.salla.dev/5394256e0.md): This endpoint allows activating either a single currency or a group of currencies.
- [List Currencies](https://docs.salla.dev/5394257e0.md): This endpoint allows you to fetch a list of all currencies alongside their details, such as `name`, `code`, `symbol` and `status`.
- [List Available Currencies](https://docs.salla.dev/5394258e0.md): This endpoint allows you to fetch a list of available currencies alongside their details, such as `name`, `code`, `symbol` and `status`.

---

## apis/Custom-URLs

# Custom URLs

## Docs

- [Import Custom URLs](https://docs.salla.dev/10393771e0.md): This endpoint allows you to import custom URLs to the store.

---

## apis/Customer-Groups

# Customer Groups

## Docs

- [Create Customer Group](https://docs.salla.dev/5394128e0.md): This endpoint allows you to create a customer group by providing a required group name, along with conditions *(shared traits among members)* and the features that will apply to the group.
- [List Customer Groups](https://docs.salla.dev/5394129e0.md): This endpoint allows you to list all the customer groups in your store.
- [Add Customers To Group Customer](https://docs.salla.dev/5394130e0.md): This endpoint allows you to add customers to a specific customer groups.
- [Update Default Customer Group](https://docs.salla.dev/5394131e0.md): This endpoint allows you to update the default customer group from this Endpoint. Each new customer is added automatically to the default customer group. 
- [Update Customer Group](https://docs.salla.dev/5394132e0.md): This endpoint allows you to update a customer group by passing the `group` as a path parameter. 
- [Delete Customer Group](https://docs.salla.dev/5394133e0.md): This endpoint allows you to delete a customer group by passing the `group` as a path parameter.

---

## apis/Customer-Wallet

# Customer Wallet

## Docs

- [Deposit to Wallet](https://docs.salla.dev/24839928e0.md): This endpoint allows you to deposit a specific amount in the customer wallet.
- [Withdraw from Wallet](https://docs.salla.dev/24850516e0.md): This endpoint allows you to withdraw a specific amount from the customer wallet.

---

## apis/Customers

# Customers

## Docs

- [Create Customer](https://docs.salla.dev/5394120e0.md): This endpoint allows you to create Customers within your store at Salla by providing the required data in this endpoint. 
- [List Customers](https://docs.salla.dev/5394121e0.md): This endpoint lets you list all customers associated with your store and filter them using a keyword. It retrieves customers whose `"mobile number"`, `"email"`, or `"name"` match the keyword you provide.
- [Customer Details](https://docs.salla.dev/5394122e0.md): This endpoint allows you to return a specific customer's details by passing the `customer` as a path parameter. 
- [Update Customer](https://docs.salla.dev/5394123e0.md): This endpoint allows you to update customer details by passing the `customer` as a path parameter. 
- [Delete Customer](https://docs.salla.dev/5394124e0.md): This endpoint allows you to delete a customer from the store customers list by passing the `customer` as a path parameter. 
- [Ban Customer](https://docs.salla.dev/5394125e0.md): This endpoint allows you to ban, aka Add to blacklist, one of your customers by passing the `customer` as a path parameter. 
- [Un-Ban customer](https://docs.salla.dev/5394126e0.md): This endpoint allows you to ub-ban (remove from blacklist) one of banned customers by passing the `customer` as a path parameter. 
- [Import Customers](https://docs.salla.dev/5394127e0.md): This endpoint allows you to import customers from an Excel file.

---

## apis/DNS-Records

# DNS Records

## Docs

- [List DNS Records](https://docs.salla.dev/5394251e0.md): This endpoint allows you to retrieve all of the DNS records, such as A, CNAME, MX, and TXT records.
- [Create DNS Record](https://docs.salla.dev/5394252e0.md): This endpoint allows you to create DNS records such as A, CNAME, MX, and TXT records.
- [Delete DNS Record](https://docs.salla.dev/5394253e0.md): This endpoint allows you to delete DNS records such as A, CNAME, MX, and TXT records, by passing the `dns_id` as a path parameter.

---

## apis/Digitals-Product

# Digitals Product

## Docs

- [Attach Digital Code](https://docs.salla.dev/5394181e0.md): This endpoint allows you to add digital codes to a specific product by passing the `product` as a path parameter. 
- [Attach Digital File](https://docs.salla.dev/5394182e0.md): This endpoint allows you to add digital files to a specific digital product by passing the `product` as a path parameter. 
- [Delete Digital File](https://docs.salla.dev/5394183e0.md): This endpoint allows you to delete a specific digital file, by passing the `file` as a path parameter.

---

## apis/Employees

# Employees

## Docs

- [List Employees](https://docs.salla.dev/5394259e0.md): This endpoint allows you to fetch a list of your store employees.

---

## apis/Feedbacks

# Feedbacks

## Docs

- [List Feedbacks](https://docs.salla.dev/5394279e0.md): This endpoint allows you to list product feedbacks, general product, blog,and shipping ratings as well as Merchant store feedbacks.
- [Feedback Details](https://docs.salla.dev/5394280e0.md): This endpoint allows you to fetch a specific review by passing the `feedback_id` as a path parameter. 
- [Update Feedback](https://docs.salla.dev/5394281e0.md): This endpoint allows you to update a specific feedback by passing the `feedback_id` as a path parameter. 
- [Store Feedback](https://docs.salla.dev/12250711e0.md): 
- [Feedback Reply](https://docs.salla.dev/11160591e0.md): This endpoint allows you to add a specific reply feedback by passing the `feedback_id` as a path parameter. 
- [Update Feedback Reply](https://docs.salla.dev/11160744e0.md): This endpoint allows you to update a specific reply feedback by passing the `feedback_reply_id` as a path parameter.

---

## apis/Languages

# Languages

## Docs

- [Add Language](https://docs.salla.dev/5394254e0.md): This endpoint allows you to add one or more languages to the store. 
- [List Languages](https://docs.salla.dev/5738815e0.md): This endpoint allows you to fetch a list of languages associated with your Salla Store.
- [Update Language](https://docs.salla.dev/5738833e0.md): This endpoint allows you to update a specific language by passing the `locale` as the path parameter.

---

## apis/Loyalty-Points

# Loyalty Points

## Docs

- [Customer Loyalty Points](https://docs.salla.dev/12250577e0.md): This endpoint allows you to fetch the history of a customer's loylty points that is assocaited with the store.
- [Update Customer Loyalty Points](https://docs.salla.dev/12250579e0.md): This endpoint enables you to add loyalty points to customers, helping to enhance engagement and reward customer loyalty.

---

## apis/Merchant

# Merchant

## Docs

- [User Information Details](https://docs.salla.dev/9466620e0.md): This endpoint allows you to fetch User information based on the [Access Token](https://docs.salla.dev/doc-421118) you have received, with a detailed response showcasing Store information.
- [Store Information](https://docs.salla.dev/5394261e0.md): This endpoint allows you to return the Store's detail information.

---

## apis/Order-Assignment

# Order Assignment

## Docs

- [List Auto Assignment Rules](https://docs.salla.dev/5576999e0.md): This endpoint allows you to retrieve all the orders auto-assignment rules per employee.
- [Order Assigned Employees Details](https://docs.salla.dev/6930855e0.md): This endpoint allows you to fetch the assigned employees' details for a specific order by passing the `order_id` as a path parameter. 
- [Update Auto Assignment Rule](https://docs.salla.dev/5581833e0.md): This endpoint allows you to update the order rules per employee by passing the `rule_id` as the path parameter.
- [Create Auto Assignment Rules](https://docs.salla.dev/5677301e0.md): This endpoint allows you to create multiple order auto assignment rules.

---

## apis/Order-Histories

# Order Histories

## Docs

- [List Order Histories](https://docs.salla.dev/5394162e0.md): This endpoint allows you to return the order history of previous and current order statuses for a specific order by passing the `order_id` as a path parameter. 
- [Create Order History](https://docs.salla.dev/5394163e0.md): This endpoint allows you to append a `note` to the Order History, by passing the `order_id` as a path parameter.

---

## apis/Order-Invoice

# Order Invoice

## Docs

- [Create Invoice](https://docs.salla.dev/5394156e0.md): This endpoint allows you to create an invoice to a specific order from your side. 
- [List Invoices](https://docs.salla.dev/5394157e0.md): This endpoint allows you to fetch a list of order invoices.
- [Invoice Details](https://docs.salla.dev/5394158e0.md): This endpoint allows you to fetch a specific order invoice details by passing the `invoice_id` as a path parameter. 
- [Send Order Invoice](https://docs.salla.dev/6336820e0.md): This endpoint allows you to send the order invoice to the customer's email by passing the `order_id` as a path parameter. 
- [Create Order Invoice](https://docs.salla.dev/6339631e0.md): This endpoint allows you to create / print the Order Invoice by passing the `order_id` as the path parameter.

---

## apis/Order-Items

# Order Items

## Docs

- [List Order Items](https://docs.salla.dev/5565737e0.md): This endpoint allows you to retrieve the complete details of specific Order items by passing the `order_id` as query parameter.
- [Create Order Item](https://docs.salla.dev/5751402e0.md): This endpoint allows you to create an order item for a specific order by passing its ID in the body request.
- [Update Order Item](https://docs.salla.dev/5751555e0.md): This endpoint allows you to update a specific Order item by passing the `item_id` as a path parameter. 
- [Delete Order Item](https://docs.salla.dev/5751557e0.md): This endpoint allows you to delete an order item by passing the `item_id` as a path parameter.

---

## apis/Order-Options

# Order Options

## Docs

- [List Order Options](https://docs.salla.dev/5394154e0.md): This endpoint allows you to list all available order options.
- [Order Option Details](https://docs.salla.dev/13121125e0.md): This endpoint allows you to list a specific order option details
- [Create Order Option](https://docs.salla.dev/5394153e0.md): This endpoint allows you to create an order option associated with an order. 
- [Update Order Option ](https://docs.salla.dev/12918611e0.md): This endpoint allows you to update a specific order option associated with an order.
- [Delete Order Options](https://docs.salla.dev/5394155e0.md): This endpoint allows you to delete a particular option from a specific order by passing the `id` as a path parameter for the order and the `option_id` as a path parameter for the tag.

---

## apis/Order-Reservations

# Order Reservations

## Docs

- [List Order Reservations](https://docs.salla.dev/5579097e0.md): This endpint allows you to retrieve all the current order reservations.

---

## apis/Order-Status

# Order Status

## Docs

- [Update Order Status](https://docs.salla.dev/5394148e0.md): This endpoint allows you to update the status of a specific order by passing the `order_id` as a path parameter. 
- [Create Custom Order Status](https://docs.salla.dev/5394149e0.md): This endpoint allows you to create a custom order status using the parameters available to be sent as body request.
- [List Order Statuses](https://docs.salla.dev/5394150e0.md): This endpoint allows you to fetch a list of all order statuses and sub-statuses.
- [Order Status Details](https://docs.salla.dev/5394151e0.md): This endpoint allows you to fetch details about specific order status by passing the `status_id` as a path parameter. 
- [Update Custom Order Status](https://docs.salla.dev/5394152e0.md): This endpoint allows you to update a custom order status by passing the `status_id` as a path parameter.
- [Update Bulk Orders Statuses](https://docs.salla.dev/5588886e0.md): This endpoint allows you to update orders' statuses in bulk by uploading an Excel file with the `xlsx` file extension.
- [Sort Orders Statuses](https://docs.salla.dev/5607770e0.md): This endpoint allows you to sort the orders statuses on the Merchant dashboard.

---

## apis/Payments

# Payments

## Docs

- [Available Payment Methods](https://docs.salla.dev/5394164e0.md): This endpoint allows you to list all available payment methods.
- [List Banks](https://docs.salla.dev/5394165e0.md): This endpoint allows you to list all banks associated with the store to receive payments.
- [Payment Bank Details](https://docs.salla.dev/5394166e0.md): This endpoint allows you to fetch the details of the bank associated with the store to recieve payments by passing the `bank_id` as a path parameter.

---

## apis/Product-Images

# Product Images

## Docs

- [Attach Image by SKU](https://docs.salla.dev/5394184e0.md): This endpoint allows you to attach an image by passing the `sku` as a path parameter. 
- [Attach Video by SKU](https://docs.salla.dev/5394185e0.md): This endpoint allows you to attache a video by passing the `sku` as a path parameter. 
- [Attach Youtube Video](https://docs.salla.dev/5394186e0.md): This endpoint allows you to add unlimited videos to a specific product by passing the `product` as a path parameter. 
- [Attach Image](https://docs.salla.dev/5394187e0.md): This endpoint allows you to add up to __10__ images to a specific product by passing the `product` as a path parameter. 
- [Update Image](https://docs.salla.dev/5394188e0.md): This endpoint allows you to update a specific product's image by passing the `image_id` as a path parameter. The updating of the image can be done either via providing a URL link to the image or uploading an image via `multipart/form-data` media type.
- [Delete Image](https://docs.salla.dev/5394189e0.md): This endpoint allows you to delete a specific image by passing the `image` as a path parameter.

---

## apis/Product-Option-Templates

# Product Option Templates

## Docs

- [List Option Templates](https://docs.salla.dev/9633869e0.md): This endpoint allows you to list all option templates related to the product.
- [Option Template Details](https://docs.salla.dev/9634609e0.md): This endpoint allows you to fetch the product options' templates by passing the `id` as a path parameter.
- [Delete Option Template](https://docs.salla.dev/9634526e0.md): This endpoint allows you to delete a specific product option template by passing the `id` as a path parameter.
- [Update Option Template](https://docs.salla.dev/9634567e0.md): This endpoint allows you to update a specific product option template by passing the `id` as a path parameter.
- [Create Option Template](https://docs.salla.dev/9634676e0.md): This endpoint allows you create a new option template.

---

## apis/Product-Option-Values

# Product Option Values

## Docs

- [Create Product Option Value](https://docs.salla.dev/5394198e0.md): This endpoint allows you to create new values in specific option for a specific product by passing the `option` as a path parameter. 
- [Product Option Value Details](https://docs.salla.dev/5394199e0.md): This endpoint allows you to return value details in specific option for a specific product by passing the `value` as a path parameter. 
- [Update Product Option Value](https://docs.salla.dev/5394200e0.md): This endpoint allows you to update value details in a specific option for a specific product by passing the `value` as a path parameter. 
- [Delete Product Option Value](https://docs.salla.dev/5394201e0.md): This endpoint allows you to delete value from a specific option for a specific product by passing the `value` as a path parameter.

---

## apis/Product-Options

# Product Options

## Docs

- [Create Product Option](https://docs.salla.dev/5394194e0.md): This endpoint allows you to create a new option for a specific product by passing the `product` as a path parameter. 
- [Product Option Details](https://docs.salla.dev/5394195e0.md): This endpoint allows you to return specific option details for a specific product by passing the `option` as a path parameter. 
- [Update Product Option](https://docs.salla.dev/5394196e0.md): This endpoint allows you to update specific option details for a specific product by passing the `option` as a path parameter. 
- [Delete Product Option](https://docs.salla.dev/5394197e0.md): This endpoint allows you to delete a particular option for a specific product including its related data (values and variants) by passing the `option` as a path parameter.

---

## apis/Product-Tags

# Product Tags

## Docs

- [Create Product Tag](https://docs.salla.dev/5394179e0.md): This endpoint allows you to create Product Tags within your store at Salla by providing the required data.
- [List Product Tags](https://docs.salla.dev/5394180e0.md): This endpoint allows you to list all available product tags related to your store.

---

## apis/Product-Variants

# Product Variants

## Docs

- [List Product Variants](https://docs.salla.dev/5394202e0.md): This endpoint allows you to list all product variants directly from this endpoint by passing the `product` as a path parameter. 
- [Product Variant Details](https://docs.salla.dev/5394203e0.md): This endpoint allows you to return the complete details for a specific variant by passing the `variant` as a path parameter. 
- [Update Product Variant](https://docs.salla.dev/5394204e0.md): This endpoint allows you to update variant details by passing the `variant` as a path parameter. 
- [Update Product Variant Quantity](https://docs.salla.dev/5394205e0.md): This endpoint allows you to update a specific product variant quantity by passing the `variant` as a path parameter.

---

## apis/Reviews

# Reviews

## Docs

- [List Reviews](https://docs.salla.dev/16603963e0.md): This endpoint allows you to list product review, general product, and shipping ratings as well as Merchant store reviews.
- [Review Details ](https://docs.salla.dev/16603964e0.md): This endpoint allows you to fetch a specific review by passing the `id` as a path parameter. 
- [Update Review](https://docs.salla.dev/16603966e0.md): This endpoint allows you to update a specific review by passing the `id` as a path parameter.

---

## apis/SEO

# SEO

## Docs

- [List SEO Settings](https://docs.salla.dev/5394262e0.md): This endpoint allows you to show your Store's SEO Settings, such as Title, Keywords, and Description.
- [Update SEO Settings](https://docs.salla.dev/5394263e0.md): This endpoint allows you to update your Store's SEO Settings, such as Title, Keywords, and Description.

---

## apis/Settings

# Settings

## Docs

- [Settings List](https://docs.salla.dev/6965777e0.md): This endpoint allows you to fetch the list of the main settings associated with the store to enable / disable / show / hide store features based on a specific entity
- [Update Setting Slug](https://docs.salla.dev/6965780e0.md): This endpoint allows you to update a specific Setting slug based on a specific entity, where the payload will be changed based on the passed body parameter values 
- [Setting Details](https://docs.salla.dev/6965781e0.md): This endpoint allows you to fetch settings details for a specific slug by passing the `slug` as a path parameter.

---

## apis/Shipments

# Shipments

## Docs

- [Create Shipment](https://docs.salla.dev/5394231e0.md): This endpoint allows you to create a shipment related to your store directly from this endpoint.
- [List Shipments](https://docs.salla.dev/5394232e0.md): This endpoint allows you to list all shipments related to your store directly from this endpoint.
- [Update Shipment Details](https://docs.salla.dev/5394233e0.md): This endpoint allows you to update specific shipment details by passing the `shipment_id` as a path parameter. 
- [Shipment Details](https://docs.salla.dev/5394234e0.md): This endpoint allows you to return the complete details for a specific shipment by passing the `shipment_id` as a path parameter. 
- [Cancel Shipment](https://docs.salla.dev/5394235e0.md): This endpoint allows you to cancel specific Shipment by passing the `shipment_id` as a path parameter. 
- [Return Shipment](https://docs.salla.dev/5394236e0.md): This endpoint allows you to return specific shipment by passing the `shipment_id` as a path parameter. 
- [Shipment Tracking](https://docs.salla.dev/5394237e0.md): This endpoint allows you to fetch tracking details for a specific shipment by passing the `shipment_id` as a path parameter.

---

## apis/Shipping-Companies

# Shipping Companies

## Docs

- [Create Shipping Company](https://docs.salla.dev/5394238e0.md):  This endpoint allows you to create a **custom** shipping company.
- [Shipping Company Options](https://docs.salla.dev/8817101e0.md): This endpoint is used to show the shipping company's options when issuing an AWB for an order
- [List Shipping Companies](https://docs.salla.dev/5394239e0.md): This endpoint allows you to list all active shipping companies associated with the store. 
- [Shipping Company Details](https://docs.salla.dev/5394240e0.md): This endpoint allows you to fetch details of a speicifc shipping company associated with the store by passing the `company_id` as a path parameter. 
- [Update Shipping Company](https://docs.salla.dev/5394241e0.md): This endpoint allows you to update a **custom** shipping company associated with the store by passing the `company_id` as a path parameter. 
- [Delete Shipping Company](https://docs.salla.dev/5394242e0.md): This endpoint allows you to delete a **custom** shipping company associated with the store, by passing the `company_id` as a path parameter. 
- [List Estimate Rates](https://docs.salla.dev/6899590e0.md): This endpoint allows you to fetch all of the shipping companies' estimate rates, based on the customer's order address

---

## apis/Shipping-Routes

# Shipping Routes

## Docs

- [  Routes List](https://docs.salla.dev/19357016e0.md): This endpoint allows you to fetch all shipping routes configured for the store.
- [Route Details](https://docs.salla.dev/19357556e0.md): This endpoint allows you to fetch detailed information about a specific shipping route, including
- [Create Route](https://docs.salla.dev/19358856e0.md): This endpoint allows you to create a new shipping route with configurable behavior, type, and conditions.
- [Update Route](https://docs.salla.dev/19370925e0.md): This endpoint allows you to update the details of an existing shipping route by passing its `id` as a path parameter.
- [Default Route](https://docs.salla.dev/19370978e0.md): This endpoint allows you to view or update the default shipping route.
- [Delete Route](https://docs.salla.dev/19371255e0.md): This endpoint allows you to update an existing shipping route by passing its `id` as a path paraneter.

---

## apis/Shipping-Zones

# Shipping Zones

## Docs

- [Create Shipping Zone](https://docs.salla.dev/5394246e0.md): This endpoint allows you to create a __Custom__ Shipping Zone.
- [List Shipping Zones](https://docs.salla.dev/5394247e0.md): This endpoint allows you to list all __Custom__ Shipping Zones.
- [Shipping Zone Details](https://docs.salla.dev/5394248e0.md): This endpoint allows you to fetch a specific __Custom__ Shipping Zone by passing the `zone_id` as a path parameter. 
- [Update Shipping Zone](https://docs.salla.dev/5394249e0.md): This endpoint allows you to update a specific __Custom__ Shipping Zone, by passing the `zone_id` as a path parameter. 
- [Delete Shipping Zone](https://docs.salla.dev/5394250e0.md): This endpoint allows you to delete a specific __Custom__ Shipping Zone, by passing the `zone_id` as a path parameter.

---

## apis/Special-Offers

# Special Offers

## Docs

- [Create Special Offer](https://docs.salla.dev/5394217e0.md): This endpoint allows you to create a new special offer in the store.
- [List Special Offers](https://docs.salla.dev/5394218e0.md): This endpoint allows you to list all special offers related to the store.
- [Special Offer Details](https://docs.salla.dev/5394219e0.md): This endpoint allows you to return the complete details for a specific special offer by passing the `specialoffer` as a path parameter. 
- [Update Special Offer](https://docs.salla.dev/5394220e0.md): This endpoint allows you to update special offer details by passing the `specialoffers` as a path parameter. 
- [Delete Special Offer](https://docs.salla.dev/5394221e0.md): This endpoint allows you to delete a specific special offer by passing the `specialoffer` as a path parameter. 
- [Change Special Offer Status](https://docs.salla.dev/5394222e0.md): This endpoint allows you to update specific special offer status by passing the `offer` as a path parameter.

---

## apis/Taxes

# Taxes

## Docs

- [Create Tax](https://docs.salla.dev/5394140e0.md): This endpoint allows you to create a new tax and return the corresponding tax id.
- [List Taxes](https://docs.salla.dev/5394141e0.md): This endpoint allows you to list all available taxes for your store.
- [Tax Details](https://docs.salla.dev/5394142e0.md): This endpoint allows you to return the complete details for specific tax by passing the `tax` as a path parameter. 
- [Update Tax](https://docs.salla.dev/5394143e0.md): This endpoint allows you to update an existing tax by passing the `tax` as a path parameter. 
- [Delete Tax](https://docs.salla.dev/5394144e0.md): This endpoint allows you to delete an existing tax by passing the `tax` as a path parameter.

---

## apis/Transactions

# Transactions

## Docs

- [List Transactions](https://docs.salla.dev/8382471e0.md): This endpoints allows you to list all of the Store Owner's payment transactions
- [Transaction Details](https://docs.salla.dev/8385183e0.md): This endpoint allows you to fetch transaction details by passing the `transaction_id` as a path parameter. 
- [Print Transaction Invoice](https://docs.salla.dev/11716492e0.md): This endpoint allows you to print the transaction invoice by passing the `transaction_id` as a path parameter.
- [Update Transaction](https://docs.salla.dev/8385232e0.md): This endpoint allows you to `refund`, `void`, or `reverse` a transaction by passing the `transaction_id` as a path parameter.

---

## apis/Update-Payment-Method

# Update Payment Method

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /admin/v2/subscriptions/{subscription_id}:
    put:
      summary: Update Payment Method
      deprecated: false
      description: Updates payment method for an active subscription
      tags:
        - Recurring Payment Apps/APIs
      parameters:
        - name: subscription_id
          in: path
          description: ''
          required: true
          schema:
            type: string
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: integer
                  success:
                    type: boolean
                  data:
                    type: object
                    properties:
                      code:
                        type: integer
                      message:
                        type: 'null'
                      checkout_url:
                        type: string
                    required:
                      - code
                      - message
                      - checkout_url
                    x-apidog-orders:
                      - code
                      - message
                      - checkout_url
                    x-apidog-ignore-properties: []
                required:
                  - status
                  - success
                  - data
                x-apidog-orders:
                  - status
                  - success
                  - data
                x-apidog-ignore-properties: []
          headers: {}
          x-apidog-name: Success
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
          x-apidog-name: not_found
      security:
        - bearer: []
      x-apidog-folder: Recurring Payment Apps/APIs
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-24950109-run
components:
  schemas:
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

## apis/Webhooks

# Webhooks

## Docs

- [Register Webhook](https://docs.salla.dev/5394134e0.md): This endpoint allows you to register a new webhook. 
- [Update Webhook](https://docs.salla.dev/10312606e0.md): This endpoint allows you to update an existing webhook by passing the `id` as path parameter
- [List Active Webhooks](https://docs.salla.dev/5394135e0.md): This endpoint allows you to list all available, registered, and active webhooks related to the store.
- [List Events](https://docs.salla.dev/5394136e0.md): This endpoint allows you to list all the available events that can be used in registering webhooks from this endpoint.
- [Deactivate Webhook](https://docs.salla.dev/5394137e0.md): This endpoint allows you to unsubscribe/deactivate a webhook from the active webhooks list at your store.

---

## getting-started/Create-Salla-Theme-Twilight-Documentation-Salla-Docs

# Create a theme

Now that you have the necessary skills to begin creating fantastic [**Twilight**](https://github.com/SallaApp/theme-raed) themes for [Salla's Store](https://salla.sa/), you can move on to the next phase and construct your theme.


:::info[A thing to know!]
- [Salla Partners Portal](https://salla.partners) and [Salla CLI](https://github.com/SallaApp/Salla-CLI) are two alternatives tools provided by Salla for creating and setting up Twilight Themes for the developers.
- [Salla CLI documentation](project-451700?nav=01HNA8QHCPJTCY5VSEZ616JCAK) provides a full guide for Salla CLI commands.
:::


## 📙 What you'll learn

By the end of this article, you will have successfully created a theme using [Salla Partners Portal](https://salla.partners). 

Creating a Theme via [Salla Partners Portal](https://salla.partners), includes:
  - [Prerequisites](#prerequisites)
  - [Initiating a theme](#initiating-a-theme)
  - [Connecting with GitHub](#connecting-with-GitHub)
    - [Create a new theme](#create-a-new-theme)
    - [Import an existing theme](#import-an-existing-theme)

<hr>

## Creating Theme via Salla Partners Portal

Developers can use the [Salla Partners Portal](https://salla.partners/) to integrate their themes with Salla's [eCommerce Platform](https://salla.sa/). It gives them the ability to create custom themes for Salla Merchants by giving them a set of tools to help them explore their creativity.

By using this tool, developers will be able to build big projects on the platform in a simple, organized, and monitored way. Learn more about Salla Partners Portal by visiting this [blog](https://salla.dev/blog/welcome-to-salla-partners-portal/).

### Prerequisites
- [Salla partner account](https://salla.partners/) account.
- [Github](https://github.com/) account, to sync the theme's files that are being developed with the [Salla partner account](https://salla.partners/).

### Initiating a theme
On [Salla Partners Portal](https://salla.partners/) dashboard, click on *My Themes* on the main navigation menu. The page will be redirected to the theme management page. From there, click on *Create your first theme*. If you have already created your first theme, click on the *Create theme* button.
<!--
focus: false
-->
![Salla Partners Portal](https://cdn.salla.network/docs/twilight/1/create-theme-01.png?=)


:::info[A thing to know!]

[**Salla CLI**](https://github.com/SallaApp/Salla-CLI), is a command-line tool developed by Salla team, can be used to [create](https://docs.salla.dev/doc-422775?nav=01HNA8QHCPJTCY5VSEZ616JCAK) Salla themes.
:::

### Connecting with GitHub
This step is crucial in order for **Twilight** to access a [GitHub](https://github.com/) account and start crafting the theme's files there, it needs to verify the developer's GitHub identity. This requires going through the authorization process in order to authorize interactions with the data on GitHub on the developer's behalf. 
<!--
focus: false
-->
![GitHub](https://cdn.salla.network/docs/twilight/1/create-theme-02.png?v)

After setting the [GitHub](https://github.com/) authorization, the page will give two options:

- Create a New Theme
- Import a Theme

Both methods will be explained respectively. 


#### Create a new theme
By clicking on *Create theme* button, the theme setting file will be created. More about theme's files [here](https://docs.salla.dev/doc-421918?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

<!--
focus: false
-->
![Create theme options](https://cdn.salla.network/docs/twilight/1/create-theme-03.png?=N)
 
Next, fill in the new theme basic information:

<br>

<!--
focus: false
-->
![Theme information](https://cdn.salla.network/docs/twilight/1/create-theme-04.png?n)

Then, click on *Create theme*. The table below explains the new theme details required in the above photo.

|||
|--|--|
|1- Theme icon for the new theme| Icon is an image that describes your theme.|
|2- Name| The name of the theme|
|3- Theme Category (optional)|This option allows the theme to be categorized in the available categories for ease of access by merchants. |
|4- Theme website (optional)| This option provides the theme website for the merchant to display the theme.|
|5- Support email|Email address to support the theme.|


🎉 **Well done!** You have successfully created a theme using *create theme* on [Salla Partners Portal](https://salla.partners/). 


Next, we'll create a theme by importing it.


#### Import an existing theme
The other method for creating a theme from the [Salla Partners Portal](https://salla.partners) is to import an existing theme that already exists in the developer's GitHub account. This method will detect the theme setting file [twilight.json](doc-421921?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) and craft the new theme based on it. Here is a complete article about the [twilight.json](doc-421921?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) file.

On the theme management page click on *import theme* button.

<!--
focus: false
-->
![Import theme](https://cdn.salla.network/docs/twilight/1/create-theme-05.png?)

<br/>

Next, fill in these details:


<!--
focus: false
-->
![Import information](https://cdn.salla.network/docs/twilight/1/create-theme-06.png?=i)

Then, click on *import theme*. The following table explains the information required from the developer to create the theme using import theme option.
|||
|--|--|
|1- Icon for the imported theme| Icon is an image that describes your theme.|
|2- The Github account |The GitHub account linked to the partners account. |
|3- The theme repository |Imported theme repository, from the developer's remote GitHub account. |
|4- Theme Categories| The Theme category |
|5- Theme screenshots (optional)| Images of the theme, up to three images.|

🎉**Congratulations!** You have successfully created a theme using *import theme* on [Salla Partners Portal](https://salla.partners/).

<!--
:::note[]
**Next**, we'll go through the [**Theme Development**](https://docs.salla.dev/doc-421878?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) workflow in detail.
:::
-->
<br/>

---

## getting-started/Develop-a-Theme-Twilight-Documentation-Salla-Docs

# Develop a theme

Developers are empowered to develop and customize themes for Salla Stores in a swift, effortless, and robust way. These customizations might range from minor tweaks to complete redesigns. Build extraordinary theme customizations through the [Partners Portal](https://salla.partners/) and, then, publish them to the [Store Themes Marketplace](https://s.salla.sa/marketplace/themes/tag-all).


:::info[A thing to know!]
✅ Read and understand the [Directory Structure](doc-421918?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) for proper use of the Theme.
:::

## 📙 What You'll Learn

In this article, the developer will learn how to develop a theme in a local development environment and how to preview the new customization. The main outline will be:

- [Theme Development Workflow](#theme-development-workflow)
- [Twilight Watcher Plugin](#twilight-watcher-plugin)

## Theme Development Workflow

The previous step includes the [creation](doc-421877?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) of a new theme files, which means that a local directory has been created for theme's files, which were cloned from the synced GitHub repository to a local development environment on the local machine. 


:::tip[Tip]
If the theme was created using the [Partner Portal](https://salla.partners/), the developer will need to:
- Manually `git clone` the theme files from the synced GitHub repository to a local development environment on the local machine.
- Run the command `npm install` to download and install the dependencies listed in the package file 'package.json'.
- Ensure that you have full administrative access to your local files to successfully complete the installation process.
:::

Next is to step inside the theme's directory and to run the [Salla CLI command `preview`](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK), and open the given starter theme with an IDE:
<Tabs>
    <Tab>
```shell title="Command Line"
> cd theme_folder_name
> npm install
> salla theme preview
```
  </Tab>
    </Tabs>
    
Salla has developed an **interactive development environment** that is launched with the command, `salla theme preview`. During the development process, the [`preview`](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK) command will automatically handle the process of building and deploying the theme to a local server and preview browser. This will involve the following steps:

- Running a local development server to serve the local assets' directory.
- Opening a local preview browser with a selected demo store.
- Watching theme file changes. 
- Hot reloading the current previewed page each time changes in assets or views are detected. 
- Managing the preview environment including committing the changes to the synced GitHub repository if required. 
The following image shows the development workflow:

![image](https://cdn.salla.network/docs/twilight/1/develop-theme-01.png)

<br/>

This amazing workflow enables the developer to develop the theme just like any other client-side applications. This means that the developer has complete control over every step of the development process, starting with editing the theme's source code and quickly previewing any changes in the local browser.

## Twilight Watcher Plugin

The *Twilight Engine* provides a *Watcher* plugin, which performs the task of tracking any changes in the theme's files and delivering these changes to the CLI in order to be reflected into the current preview. The Watcher plugin is included in the [Webpack](https://webpack.js.org/plugins/install-webpack-plugin/#usage), which is simply a static module bundler for modern client-side applications.

When it processes the theme's files, [Webpack](https://webpack.js.org/plugins/install-webpack-plugin/#usage) creates an internal dependency structure from one or more entry points. The theme's files are then combined into one or more bundles, which are static assets that provide the theme's content by combining each module into a single file. 

The developer needs to make sure the Twilight Watcher plugin is added to the `webpack.config.js` file. This file can be found in the root theme's directory. More information about Webpack can be found [here](https://webpack.js.org/plugins/install-webpack-plugin/#usage).


:::info[Information]
The developer has the option to use any other static module bundler other than the Webpack.
:::


The **Twilight Watcher Plugin** can be added as follows:
<Tabs>
    <Tab>
        
```js title=".\webpack.config.js"
const ThemeWatcher = require('@salla.sa/twilight/watcher');
module.exports = {
    ...
  plugins: [
    ...
    new ThemeWatcher()
  ],
}
```
</Tab>
</Tabs>

<br/>

<!-- 

⏭️ **Next**, we will explore the [**Theme Setup**](doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) step which includes managing the theme's basic information, screenshots, settings, features, custom components, and price.

> ### Development Workflow
>  ✅ `git clone`  the theme's files from the synced GitHub repository. <br/>
>  ✅ [`salla preview`](doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK) command to offline preview the theme's changes as per the local files during the development process. <br/>

Optional
>  ✅ `git push` the customized theme's files from the local environment to the synced GitHub repository. <br/>
>  ✅ (*Optional*) Preview the theme's files via the [Partners Portal](https://salla.partners/) to see the custom theme from the synced GitHub repository. This step is in case the developer needs to preview the theme using a demo or a live store.
-->

---

## getting-started/Publish-a-Theme-Twilight-Documentation-Salla-Docs

# Publish a theme

Show the world what you have built and publish it to the [Theme Marketplace](https://s.salla.sa/marketplace/themes/tag-all) for [Salla Merchants](https://salla.partners/) to start using it. As the Theme has been [tested and previewed](https://docs.salla.dev/doc-422776?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), it is time to submit the publication request for Salla Team to approve it.


:::tip[A thing to know!]
- 🖥️ [**Salla CLI**](https://github.com/SallaApp/Salla-CLI), which is a command-line tool developed by Salla team, can be used to [publish](https://docs.salla.dev/doc-422968?nav=01HNA8QHCPJTCY5VSEZ616JCAK) a theme.
- ✅ The developer can decide whether a theme is installed in all stores or just some of them by setting the theme's availability during the [theme setup](https://docs.salla.dev/doc-421879?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
:::


## 📙 What you'll learn
By the end of this article, you will have successfully requested to publish your theme via [Salla Partners Portal](https://salla.partners). You will learn:
- [Theme Publication](#theme-publication)
- [Withdraw Theme Publication](#withdraw-theme-publication)

<hr>

### Theme Publication
Once all information has been provided, the developer can submit the request for publication by scrolling down to the Theme Publication section in the Partners Portal. Click on "Complete Theme publication" button.

<!--
focus: false
-->
![Send Publication Request](https://cdn.salla.network/docs/twilight/1/publish-theme-01.png?=ve)

This will redirect you to the Listing Details page where details about the theme should be provided as shown below.
|Item|Description|
|--|--|
|Theme Screenshots| Images of how the Theme would appear on the store|
|Preview Stores| Details about the demo store that will be used as preview store|
|Theme Price| The them price and discount details if applicable|
|Support Details| The contact details for Theme support|


## Listing Information
This is the second part of Theme Setup, where the developer can prepare the Theme for publishing.

#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">1</span> Theme Screenshots

If not added previously, the developer can add high-quality screenshots, so as to make the theme more attractive and more user-friendly. There should be at least 3 images, with  the resolution of 1366x768.

<!--
focus: false
-->
![Theme Screenshots](https://cdn.salla.network/docs/twilight/1/set-up-theme-02.png?=ve)



#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">2</span> Preview Stores

To showcase Themes for Merchants in a live demonstration by using one of your Demo Stores.
<!--
focus: false
-->
![](https://i.imgur.com/0pLtemN.png)

To add a Demo Store as a preview store follow these steps:
a- Click "Add New Store"
![image](https://i.imgur.com/IE0V9OA.png)
b- Fill in the details
![image](https://i.imgur.com/hbSFL5v.png)

And the details are as follow:

| Item  |Description   |
|---|---|
|1-Preview Store |Select the Demo Store from the List.|
|2- Theme Category| Select the Theme Category from the drop down list|
|3- Color|Choose the store Color|
|4- Thumbnail| Add a Thumbnail image for your Preview Store|
|5- Default Store|Tick here if you wish to have this Demo Store as the default preview store|
|6- Save|Click "Save" to save the changes|

Once you finish these steps, you will find the Demo Store listed in the Preview Stores, and a notification will be displayed on the upper right of the page


#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">3</span> Theme Price

Set the one-time price of the Theme, which will be used to purchase the Theme from the Merchant. Perhaps add a discount to encourage more Merchants to install and use the Theme.

<!--
focus: false
-->
![Theme Price](https://cdn.salla.network/docs/twilight/1/setup-theme-19.png?ss)

:::tip[Note]
Price your theme at a minimum of *SAR250* to align with our platform's pricing policy and ensure fair compensation for your effort.
:::


#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">4</span> Support Details

For the Merchants to continue using the Theme, having detailed support ways would help greatly.

![image](https://cdn.salla.network/docs/twilight/1/setup-theme-14.png?new)

After completing the Listing Information details, click on the "Send publication request" button.

![](https://cdn.salla.network/docs/twilight/1/publish-theme-06.png)

A pop-up window will appear requesting Theme Category and Changelog details. Fill in the details and click "Send publication request" button to continue.
![](https://cdn.salla.network/docs/twilight/1/publish-theme-05.png)


:::check[Important]
To update your theme, you must submit a new publishing request which will go through the Salla team’s review process, even if the theme is private.
:::

:::warning[Alert]
Always pay attention to any warnings received in the theme's [Github](https://www.github.com) repository's latest commit update text. Follow the directions given to fix any problems and keep enjoying the Twilight experience.

![Image](https://cdn.salla.network/docs/twilight/1/publish-theme-03.png?v=1-10-202)
:::
 
### Withdraw Theme Publication
The developer may need to withdraw the theme in order to make some modifications. The theme publication can be withdrawn by clicking on the "Withdraw" button at the top of the screen.

<!--
focus: false
-->
![Withdraw Request](https://i.imgur.com/yH67JlW.png)

---

## getting-started/Setup-Themes-Twilight-Documentation-Salla-Docs

# Setup a theme

Using the [Partners Portal](https://salla.partners/), the developer has the ability to manage the theme's setup. This includes managing the theme's basic information, screenshots, settings, features, custom components, and price. Besides that, the developer can `preview`, `delete`, `publish`, or *withdraw* any theme.

## 📙 What You'll Learn

In this article, you will learn how to setup a theme using the [Partners Portal](https://salla.partners/). We will also go through the following:

- [Setting up twilight.json](#setting-up-twilight.json)
- [Setup via the Partners Portal](#setup-via-the-partners-portal)

<hr>

## Setting up twilight.json

:::info[About twilight.json]
The Theme's setup can be modified directly from the [twilight.json](https://docs.salla.dev/doc-421921?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) file, which is synced in the [Github](https://github.com/) account connected with the [Partners Portal](https://salla.partners/). Explore more on the **twilight.json** file by reading this [guide](https://docs.salla.dev/doc-421921?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).
:::


Upon [creating / importing a theme](https://docs.salla.dev/doc-421877?nav=01HNFTD5Y5ESFQS3P9MJ0721VM), the [twilight.json](doc-421877?nav=01HNFTD5Y5ESFQS3P9MJ0721VM) file will be existed in the root directory. Within that file, a developer is able to specify Theme Features, which are the [pre-defined](https://docs.salla.dev/doc-421921?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#theme-features) theme components, and Theme Components, which are the [custom](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#components) components that are built by the developer. As changes are made to the file, they can be easily synced in the [Github](https://github.com/) account connected to the [Partners Portal](https://salla.partners/). Explore more about *twilight.json* [here](https://docs.salla.dev/doc-421918?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).

## Setup via the Partners Portal
On the [Salla Partners Portal](https://salla.partners) dashboard, the developer needs to click on *My Themes* in the main navigation menu. This will show the list of available themes. The developer needs to first select a theme and then start with the setup process.

There are two parts for Theme setup which are Basic Settings and Listing Information



![](https://cdn.salla.network/docs/twilight/1/theme-set-up-01.png?=ve)

## Basic Settings

The Basic Settings will be explained in the coming sections and Listing Information will be further explained in the Theme Publish [article](https://docs.salla.dev/doc-421880?nav=01HNFTD5Y5ESFQS3P9MJ0721VM).



#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">1</span> Basic Information
To start click on edit Theme Name to edit Theme name and category
<!--focus: false-->

![image](https://cdn.salla.network/docs/twilight/1/theme-set-up.png)
<br>

Here you can also update basic information about the Theme, such as Theme icon, name and category.

<!--focus: false-->

![image](https://cdn.salla.network/docs/twilight/1/theme-set-up-011.png?=ve)


#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">2</span> Theme Settings

Personalize the experience via the Theme Settings section by adding custom fields and parameters, which allow for significant control over the Theme.

<!--
focus: false
-->
![Settings Page](https://cdn.salla.network/docs/twilight/1/set-up-theme-12new.png)

In there, the drag & drop four fields (String, Numeric, Boolean, and List) bring a unified, straightforward experience for Salla Merchants. A fifth field is Collection, which allows for creating a group of fields that has a mix of the four fields.

<!--
focus: false
-->
![Settings Page Details](https://cdn.salla.network/docs/twilight/1/set-up-theme-13new.png)



#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">3</span> Theme Features

Mark the Theme features' checkboxes that make up the theme. That said, it is to be customizable from the Merchant side. Explore more about Theme Features [here](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#theme-features-and-theme-components).

<!--
focus: false
-->

![Theme Features](https://cdn.salla.network/docs/twilight/1/set-up-theme-14new.png)

#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">4</span> Extra Features

If the developed Theme provides extra features, add each of them in a separate line in the field available.
<!--
focus: false
-->
![Extra Features](https://cdn.salla.network/docs/twilight/1/set-up-theme-15new.png)


#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">5</span> Theme Components

Add a [custom component](doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#components) by clicking on "Add Custom Component". This kind of component is developed by the developer.

<!--
focus: false
-->
![Hi](https://cdn.salla.network/docs/twilight/1/set-up-theme-16new.png)

Provide the details of the custom component in terms of the title, icon, and file path of the component.
<!--
focus: false
-->
![Add Component](https://cdn.salla.network/docs/twilight/1/set-up-theme-17new.png)

That will result in having the [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#components) added.
<!--
focus: false
-->
![Result](https://cdn.salla.network/docs/twilight/1/set-up-theme-18new.png)

Edit and update the previously inputted basic information of the [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#components), such as the title, icon, and file path. The pop dialog will showcase the fields to be updated.
<!--
focus: false
-->
![Custom Component Basic Info](https://cdn.salla.network/docs/twilight/1/set-up-theme-19new.png)

By going to the Settings page of the [custom component](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#components), several setting fields can be added for that specific component.
<!--
focus: false
-->
![Settings Page](https://cdn.salla.network/docs/twilight/1/set-up-theme-20new.png)

The custom components setting page will appear as follows, where it is easy to add the fields that customize the component in a drag & drop way, each with its own properties and functionalities that will be reflected on the Merchant side.

<!--
focus: false
-->
![Settings Page Details](https://cdn.salla.network/docs/twilight/1/set-up-theme-21new.png)


#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">6</span> Theme Preview

The [Partners Portal](https://salla.partners) provides this feature to preview the themes in a demo store for quality assurance, before submitting a publication request. Explore what is suitable and enjoy the progress so far while developing the theme.

<!--
focus: false
-->
![Test & Preview Options](https://cdn.salla.network/docs/twilight/1/setup-theme-15.png?)

Create a new [demo store](https://salla.partners/demo-stores), unless one is already created, and click on the "Preview Theme".

<!--
focus: false
-->
![Preview Theme](https://cdn.salla.network/docs/twilight/1/setup-theme-16.png?)

On the demo dashboard, the theme will then be in the preview mode to which all the changes made to the theme, in terms of components, [pre-defined](https://docs.salla.dev/doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#theme-features-and-theme-components) and [custom](doc-422558?nav=01HNFTD5Y5ESFQS3P9MJ0721VM#theme-features-and-theme-components), and settings, will be reflected.



:::tip[A thing to know!]
🖥️ [**Salla CLI**](https://github.com/SallaApp/Salla-CLI), which is a command-line tool developed by Salla team, can be used to [preview](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK) a theme.
:::



#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">7</span> Theme Details

Write details about the Theme to grab the attention of the Merchants, which will be apparent in the [Store Themes Marketplace](https://s.salla.sa/marketplace/themes/tag-all).
<!--
focus: false
-->
![](https://cdn.salla.network/docs/twilight/1/Theme-details.png)
#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">8</span> Theme Preview in Live Store

You can preview the theme on live stores by adding the store link then clicking on "sending the installation request" button.

<!--
focus: false
-->
![Theme Details](https://cdn.salla.network/docs/twilight/1/theme-set-up-live.png)

#### <span style="background-color: #85dbb3; padding:3px; font-weight: bold">9</span> Theme Installation

The developer can decide the Theme installation methods as follows:

a. By ticking this option, the devloper indicates that the theme is public an available for all stores.
b. By ticking this option,the theme is beta and under development.
c. By ticking this option, the theme is private and can only be installed by.installation link
d. In this box, the developer can copy the theme installation link for store to install it via installation link


![Live Store Request](https://cdn.salla.network/docs/twilight/1/setup-theme-18.png?eh)

By getting here you have successfully completed theme setup.

---

## settings/App-Setting-Details-Partners-Apps-APIs-Salla-Docs

# App Setting Details

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /apps/{app_id}/settings:
    get:
      summary: App Setting Details
      deprecated: false
      description: >-
        This endpoint allows you to fetch details of App Settings per [Salla
        Store](http://s.salla.sa/).


        :::warning[Important]

        The App Settings are custom-made parameters by the Salla App Developer.
        Read [here](https://salla.dev/blog/how-to-build-app-settings-form/) for
        more on App Settings.

        :::
      operationId: get-apps-app_id-settings
      tags:
        - Partner Apps APIs/Settings
        - Settings
      parameters:
        - name: app_id
          in: path
          description: >-
            Salla Application ID. [Salla Partners](https://salla.partners) > My
            Apps > Your App
          required: true
          example: 513499943
          schema:
            type: integer
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AppSettingsBodyResponse'
              example:
                status: 200
                success: true
                data:
                  app_id: '513499943'
                  app_slug: allrights
                  settings:
                    email: test@store.sa
                    password: '123456789'
                    contract_no.: 50
                    fast_delivery: true
          headers: {}
          x-apidog-name: Success
        '403':
          description: ''
          content:
            application/json:
              schema: &ref_0
                $ref: '#/components/schemas/NotFoundResponse'
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: ليس لديك صلاحية لتعديل الخدمة
          headers: {}
          x-apidog-name: Unauthorized
        '404':
          description: ''
          content:
            application/json:
              schema: *ref_0
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: لايوجد اعدادت للتطبيق
          headers: {}
          x-apidog-name: Not Found
        x-404:Not Found:
          description: ''
          content:
            application/json:
              schema: *ref_0
              example:
                status: 404
                success: false
                error:
                  code: error
                  message: الخدمة غير موجودة
          headers: {}
          x-apidog-name: Not Found
      security:
        - bearer: []
      x-apidog-folder: Partner Apps APIs/Settings
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5401096-run
components:
  schemas:
    AppSettingsBodyResponse:
      title: UpdateAppSettingsBodyResponse
      type: object
      x-examples:
        Example:
          status: 200
          success: true
          data:
            app_id: '513499943'
            app_slug: allrights
            email: test@store.sa
            password: '123456789'
            contract_no.: 50
            fast_delivery: true
      properties:
        status:
          type: number
          description: Response Status Code
          examples:
            - 200
        success:
          type: boolean
          description: Whether or not the response is successful
          default: true
        data:
          type: object
          properties:
            app_id:
              type: string
              description: Salla App ID, provided by Salla
              examples:
                - '513499943'
            app_slug:
              type: string
              description: Salla App Slug, provided by Salla
              examples:
                - allrights
            settings:
              type: object
              properties:
                email:
                  type: string
                  description: Custom App Setting Parameter
                  examples:
                    - test@store.sa
                password:
                  type: string
                  description: Custom App Setting Parameter
                  examples:
                    - '123456789'
                contract_no.:
                  type: number
                  description: Custom App Setting Parameter
                  examples:
                    - 50
                fast_delivery:
                  type: boolean
                  description: Custom App Setting Parameter
                  default: true
              x-apidog-orders:
                - email
                - password
                - contract_no.
                - fast_delivery
              x-apidog-ignore-properties: []
          x-apidog-orders:
            - app_id
            - app_slug
            - settings
          x-apidog-ignore-properties: []
      x-apidog-orders:
        - status
        - success
        - data
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    NotFoundResponse:
      type: object
      title: NotFoundResponse
      properties:
        status:
          type: number
          description: Response status Code
        success:
          type: boolean
          description: Response flag
        error:
          type: object
          properties:
            code:
              type: integer
              description: Response code
            message:
              type: string
              description: Response message
          x-apidog-orders:
            - code
            - message
          x-apidog-ignore-properties: []
      x-examples:
        Example:
          success: false
          status: 404
          error:
            code: 404
            message: The content you are trying to access is no longer available
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

## settings/Update-App-Settings-Partners-Apps-APIs-Salla-Docs

# Update App Settings

## OpenAPI Specification

```yaml
openapi: 3.0.1
info:
  title: ''
  description: ''
  version: 1.0.0
paths:
  /apps/{app_id}/settings:
    post:
      summary: Update App Settings
      deprecated: false
      description: >-
        This endpoint allows you to update App Settings per [Salla
        Store](http://s.salla.sa/).


        :::warning[Important]

        - The App Settings are custom-made parameters by the Salla App
        Developer. Read
        [here](https://salla.dev/blog/how-to-build-app-settings-form/) for more
        on App Settings.

        - You **must** pass all Settings even if you need to update just *one*
        setting to avoid any data loss. Passing only the key you need to update
        will cause other values to become `null`.

        :::
      operationId: post-apps-app_id-settings
      tags:
        - Partner Apps APIs/Settings
        - Settings
      parameters:
        - name: app_id
          in: path
          description: >-
            Salla Application ID. [Salla Partners](https://salla.partners) > My
            Apps > Your App
          required: true
          example: 513499943
          schema:
            type: integer
      requestBody:
        content:
          application/json:
            schema: &ref_0
              $ref: '#/components/schemas/UpdateAppSettingsBodyRequest'
            example:
              email: test@salla.sa
              password: '3534543534'
              fast_delivery: true
              contact_no: 50
      responses:
        '200':
          description: ''
          content:
            application/json:
              schema: *ref_0
              example:
                status: 200
                success: true
                data:
                  app_id: '513499943'
                  app_slug: allrights
                  settings:
                    email: test@store.sa
                    password: '3534543534'
                    fast_delivery: true
                    contract_no.: 50
          headers: {}
          x-apidog-name: Success
        '403':
          description: ''
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/NotFoundResponse'
              example:
                status: 403
                success: false
                error:
                  code: error
                  message: ليس لديك صلاحية لتعديل الخدمة
          headers: {}
          x-apidog-name: Error
      security:
        - bearer: []
      x-apidog-folder: Partner Apps APIs/Settings
      x-apidog-status: released
      x-run-in-apidog: https://app.apidog.com/web/project/451700/apis/api-5401097-run
components:
  schemas:
    UpdateAppSettingsBodyRequest:
      title: UpdateAppSettingsBodyRequest
      type: object
      properties:
        email:
          type: string
          description: Custom App Setting Parameter
          examples:
            - test@salla.sa
        password:
          type: string
          description: Custom App Setting Parameter
          examples:
            - '3534543534'
        fast_delivery:
          type: boolean
          description: Custom App Setting Parameter
          default: true
        contact_no:
          type: number
          description: Custom App Setting Parameter
          examples:
            - 50
      x-examples:
        Example:
          email: test@salla.sa
          password: '3534543534'
          fast_delivery: true
          contact_no: 50
      x-apidog-orders:
        - email
        - password
        - fast_delivery
        - contact_no
      x-apidog-ignore-properties: []
      x-apidog-folder: ''
    NotFoundResponse:
      type: object
      title: NotFoundResponse
      properties:
        status:
          type: number
          description: Response status Code
        success:
          type: boolean
          description: Response flag
        error:
          type: object
          properties:
            code:
              type: integer
              description: Response code
            message:
              type: string
              description: Response message
          x-apidog-orders:
            - code
            - message
          x-apidog-ignore-properties: []
      x-examples:
        Example:
          success: false
          status: 404
          error:
            code: 404
            message: The content you are trying to access is no longer available
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

