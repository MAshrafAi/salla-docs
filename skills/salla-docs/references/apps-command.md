# Apps Command

## Table of Contents

- [apps-command/App-Serve-Salla-CLI-Salla-Docs](#apps-command-app-serve-salla-cli-salla-docs)
- [apps-command/Apps-Commands-Overview-Salla-CLI-Salla-Docs](#apps-command-apps-commands-overview-salla-cli-salla-docs)
- [apps-command/Create-App-Salla-CLI-Salla-Docs](#apps-command-create-app-salla-cli-salla-docs)
- [apps-command/Create-Webhook-Salla-CLI-Salla-Docs](#apps-command-create-webhook-salla-cli-salla-docs)
- [apps-command/Delete-App-Salla-CLI-Salla-Docs](#apps-command-delete-app-salla-cli-salla-docs)
- [apps-command/Link-Salla-App-Salla-CLI-Salla-Docs](#apps-command-link-salla-app-salla-cli-salla-docs)
- [apps-command/salla-app-list-Salla-Storefront-Twilight-Documentation-Salla-Docs](#apps-command-salla-app-list-salla-storefront-twilight-documentation-salla-docs)

---

## apps-command/App-Serve-Salla-CLI-Salla-Docs

# Serve

Developers can test the App and get the Apps information such as Remote URL, Local URL, Webhook URL, and OAuth Callback URL. `Salla app serve` command can be accessed via the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command. Read this article to learn more about the `serve`.

## 📙 What you'll learn

- [Serve App](#serve-app)

<hr>

### Serve App

The developer can run and test an existing Salla App. He needs to login to [Salla Partners Portal](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) account to show the Apps linked to his account using the following command:

```bash title = "Terminal"
salla app serve
```

A result summary will be displayed on the terminal after running the command.

<!--
focus: false
-->

![Salla App Serve Command](https://cdn.salla.network/docs/cli/app_serve_command.gif?version2)

---

## apps-command/Apps-Commands-Overview-Salla-CLI-Salla-Docs

# Overview

This section is about Salla Apps commands. In this overview, developers can find a brief guide to the commands [Salla CLI](https://github.com/SallaApp/Salla-CLI#:~:text=version%20with%20this-,command,-%3A) made for the Apps.

## 📙 What you'll learn

- [Salla Apps' various commands](#salla-apps-various-commands)

### Salla Apps' various commands

- [Create App](#create-app)
- [Create Webhook](#create-webhook)
- [Delete](#delete)
- [Link](#link)
- [Listing and information](#listing-and-information)
- [Serve](#serve)
<hr>

### Create App
This article explains the steps of creating Salla Apps using Salla CLI. The developer can find more information on developing an app [here](https://docs.salla.dev/doc-422767?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

### Create Webhook
Webhooks and notifications are tools that allow developers to track events that occur between their apps and Salla stores, Webhooks can be created in the Apps using Salla CLI. More information on creating webhooks can be found [here](https://docs.salla.dev/doc-422768?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

### Delete
Developers can delete their own apps using the Salla CLI. More information about the Delete App can be found [here](https://docs.salla.dev/doc-422770?nav=01HNA8QHCPJTCY5VSEZ616JCAK).


### Link
To link the App with [Salla Partners Portal](https://salla.partners), the developer needs to follow the steps mentioned in this [article](https://docs.salla.dev/doc-422771?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

### Listing and information
The developer can list the Apps created and get details about the app. This [article](https://docs.salla.dev/doc-422772?nav=01HNA8QHCPJTCY5VSEZ616JCAK) gives complete information for listing and gives more information about the Apps.

### Serve
The developer can test the App and view certain details, such as remote URL, local URL, and other app's attributes. More information is available [here](https://docs.salla.dev/doc-422773?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

---

## apps-command/Create-App-Salla-CLI-Salla-Docs

# Create  App

Developers create [Salla Apps](https://salla.partners/), which are primarily used in [Salla stores](https://salla.sa) to provide functionality and other services. This article demonstrates how to use the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `salla app create` to create Salla Apps.

:::info[Information]
The article linked below discusses using the Salla CLI to set up a webhook server with Laravel, simplifying development and integration for developers.

🔗 https://salla.dev/blog/salla-cli-webhook-server-laravel/
:::



## 📙 What you'll learn

- How to [Create Salla App](#create-salla-app)
<hr>

### Create Salla App
Creating [Salla App](https://salla.partners/) is much easier with [Salla CLI](https://github.com/SallaApp/Salla-CLI). Run the following command to go through the wizard that would help create the app, in either `Public`, `Private` or `Shipping` types:


```bash title = "Terminal"

salla app create

```

The terminal will display a list of existing Apps associated with the developer [Salla Partners](https://salla.partners/) account, as well as an option to create an App on [Salla Partners Portal](https://salla.partners/). Afterwards, a list of easy-to-fill-in information will be displayed on the terminal to complete creating the App.

<!--
focus: false
![App Create](https://cdn.salla.network/docs/cli/App_create_command.gif)
-->



![salla-create-app.gif](https://api.apidog.com/api/v1/projects/451700/resources/344774/image-preview)

---

## apps-command/Create-Webhook-Salla-CLI-Salla-Docs

# Create Webhook

Webhook simplifies the way Apps communicate with each other, as it is triggered by an event in a source system. For instance, a Salla Merchant Store and / or Salla Apps Store sends the data payload to a destination system, for example the Developer's App.



<TipInfo>More information is available at the [Official Docs](https://docs.salla.dev/doc-421119).</TipInfo>
<br>
 
This article guides the developer to stream or create a webhook for the App using the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `salla app create-webhook`. The article will also explain how to add [custom webhook headers](https://salla.dev/blog/custom-webhook-header-is-now-available/).

## 📙 What you'll learn

- [Streaming webhook](#streaming-webhook)
- [Add custom webhook header](#custom-webhook-header)
<hr>

### Streaming webhook
For the utmost flexibility, the developer can stream a webhook for any event they want to receive by passing the [event name](https://docs.salla.dev/doc-421119), which can also be fetched from the [Webhook endpoint](https://docs.salla.dev/api-5394136). Run the following command to create a webhook:

```bash title = "Terminal"
salla app create-webhook <event.name>
```

Once the command is executed, a success message will be displayed below.

<!--
focus: false
-->

![Salla App Create-Webhook Command](https://cdn.salla.network/docs/cli/app_create_webhook_command.gif?updated)

### Custom webhook header

Customizing webhook headers, which is done via the [Salla Partners Portal](https://salla.partners), can help the developer define the headers to show specific information about the events happening between their Apps and Salla stores. 
To add a custom webhook header:

- Login to [Salla Partners Portal](https://salla.partners/).

  <!--
  focus: false
  -->
  ![Partners Login](https://cdn.salla.network/docs/cli/partners_login.png?s)

- Click on the item *My App* menu on the left of the page. ![](https://i.imgur.com/XEVy1dL.png) 

- Choose the App to add the Custom Webhook Header to.

  <!--
  focus: false
  -->
  ![Selected App](https://i.imgur.com/UX2Co8W.png)

- Scroll down to the Webhook and Notification section.
![](https://i.imgur.com/OkS75kb.png)
- Click on the Custom webhook header to display the custom header form.
![](https://i.imgur.com/kg3KFRN.png)


<TipInfo>Read more about managing custom webhook headers [here](https://salla.dev/blog/custom-webhook-header-is-now-available/).</TipInfo>
<br>
- Add the Key and Value and click save. 
  ![](https://i.imgur.com/GgyCoih.png)

:::tip[Note]
The developer can add up to **10** custom webhook headers. 
:::

---

## apps-command/Delete-App-Salla-CLI-Salla-Docs

# Delete

Using [Salla CLI](https://github.com/SallaApp/Salla-CLI) commands, developers can quickly delete the apps they created. This article explains how to delete an app using the command `salla app delete`.

## 📙 What you'll learn

- [Delete App](#delete-app)
<hr>

### Delete App
To delete the App directly via Salla CLI, the developer needs login to [Salla Partners Portal](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) (If not already) and run:

```bash title = "Terminal"
salla app delete
```

Once the command is executed, the developer will be asked to select the App to be deleted and confirm the deletion. As shown below, a success message will be displayed to confirm that the App has been deleted.

<!--
focus: false

![Salla App Delete Command](https://cdn.salla.network/docs/cli/App_delete_command.gif?new_version)
-->


![salla-app-delete.gif](https://api.apidog.com/api/v1/projects/451700/resources/344776/image-preview)

---

## apps-command/Link-Salla-App-Salla-CLI-Salla-Docs

# Link

Developers can link an App with their Salla Partners account to manage the Apps that they created. The developer can use the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command to link a local app to the Partners account.

## 📙 What you'll learn

- [Link Salla App](#link-salla-app)
<hr>

### Link Salla App

To link the local App with [Salla Partners](https://salla.partners/), the developer needs to login to [Salla Partners Portal](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) (in case he didn't) and run:

```bash title = "Terminal"
salla app link
```

The terminal will display a list of existing apps associated with the developer account. The developer will need to choose the application they wish to link to the local App.

<!--
focus: false
-->

![Salla App Link Command](https://s11.gifyu.com/images/SBPqS.gif)

---

## apps-command/salla-app-list-Salla-Storefront-Twilight-Documentation-Salla-Docs

# List and Info

Salla's skilled developers are continuously creating amazing Apps for Salla. To keep track and check the Apps created by the developers, they can easily use the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `salla app list` to display the Apps associated with their [Salla Parnters](https://salla.partners/) account, as explained later in this article.


## 📙 What you'll learn

- [List and Info Salla App](#list-and-info)
<hr>

### List and Info

To list all the Apps created by the developer, he'll need to login to [Salla Partners Portal](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) and use this command:

```bash title = "Terminal"
salla app list
```

After executing this command line, a list of the Apps and their information will be displayed in the terminal.

![salla-app-list.gif](https://api.apidog.com/api/v1/projects/451700/resources/344775/image-preview)

---

