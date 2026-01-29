# Twilight Themes Command

## Table of Contents

- [twilight-themes-command/Create-Theme-Salla-CLI-Salla-Docs](#twilight-themes-command-create-theme-salla-cli-salla-docs)
- [twilight-themes-command/Delete-Theme-Salla-CLI-Salla-Docs](#twilight-themes-command-delete-theme-salla-cli-salla-docs)
- [twilight-themes-command/List-Themes-Salla-CLI-Salla-Docs](#twilight-themes-command-list-themes-salla-cli-salla-docs)
- [twilight-themes-command/Publish-Theme-Salla-CLI-Salla-Docs](#twilight-themes-command-publish-theme-salla-cli-salla-docs)
- [twilight-themes-command/Theme-Preview-Salla-CLI-Salla-Docs](#twilight-themes-command-theme-preview-salla-cli-salla-docs)
- [twilight-themes-command/overview-and-introduction-to-the-Salla-CLI-Theme-Commands-Salla-CLI-Salla-Docs](#twilight-themes-command-overview-and-introduction-to-the-salla-cli-theme-commands-salla-cli-salla-docs)

---

## twilight-themes-command/Create-Theme-Salla-CLI-Salla-Docs

# Create

With over thousands of stores in Salla, it's a big plus to stand out visually where customers can see the uniqueness that sets one store apart from another. Salla themes allows making detailed changes to the store's look-and-feel, with the help of [Salla CLI](https://github.com/SallaApp/Salla-CLI) which can be leveraged by the developers to design the themes. Within this article, an explanation of how a developer can create themes by using the `create` command will be provided.

## 📙 What you'll learn

[Create Theme Methods](#create-theme-methods):
- [Create A New Theme](#create-a-new-theme)
- [Import A Theme](#import-a-theme)

<hr>

### Create Theme Methods
The developer has two alternatives when it comes to creating themes using [Salla CLI](https://github.com/SallaApp/Salla-CLI): one is to create a theme using the console, and the other is to import a theme from GitHub. To see the theme creation choices, the developer must be be logged into [Salla Partners Account](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) and into his Github Account using [PAT](https://docs.salla.dev/doc-422774?nav=01HNA8QHCPJTCY5VSEZ616JCAK), use the command `salla theme create`, which can be abbreviated to `salla theme c`:



```shell title = "Terminal"
salla theme create

# Alias command for create
salla theme c
```

After executing the command, the following choices will be displayed on the terminal; Read the next section to know more about each option:

<!--
focus: false
-->
![Theme Create Command](https://cdn.salla.network/docs/cli/theme_create_command.gif?new_version)

#### Create A New Theme

In the case where the option "Create a theme" is selected, the developer will be prompted to fill in a few details about the theme.

Theme details are as shown below:
|Requirement|Description|
|--|--|
|Theme Name| Name the developer wishes to call their theme.|
|Theme Description| Short description of what the theme is.|
|Theme URL| URL link of the theme.|
|Author email address| Developer's email account.|
|Select your Github repo| Developer's list of GitHub repo.|

After entering all the required information, a local folder will be created in the developer environment for the newly created theme. It will also get [Twilight Themes](https://docs.salla.dev/doc-421877?nav=01HNA8QHCPJTCY5VSEZ616JCAK) source code from GitHub and install it locally. 
At the same time, the `preview` command will be triggered. The theme details can be found in the file `twilight.json`. [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `preview` is explained in this [article](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK). 


:::note
Please keep in mind that the newly created theme will be created as a **private repository** in your GitHub account! 
:::

If you do not have access to that private repository or if you are located in a [region](https://docs.github.com/en/site-policy/other-site-policies/github-and-trade-controls) does not support accessing private repositories, you may encounter the error `Error occurred while making the request` when attempting to import the theme from the GitHub repository. In case you encountered this issue, you may create the theme manually by following the below steps:

- Go to https://github.com/SallaApp/theme-raed.
- Click on ["Use this template"](https://github.com/SallaApp/theme-raed/generate) and create a new repository.
- From your [Salla Partners Portal](https://salla.partners/) account, create a theme and then select "Import Theme" to import the newly created repository as your Salla theme.


#### Import A Theme
In the other option, when the developer chooses "Import theme", a list of themes that are currently in the developer's GitHub account will be displayed. After choosing the theme the developer wishes to import, the process will proceed to create a local folder for the theme, install the packages, and run the `preview` command to view how the theme looks on the store. [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `preview` is explained in this [article](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

---

## twilight-themes-command/Delete-Theme-Salla-CLI-Salla-Docs

# Delete

The developer can delete the theme that has been created by them using [Salla CLI](https://github.com/SallaApp/Salla-CLI). This article will guide the developer on using the `delete` command to delete a theme.

## 📙 What you'll learn

- [Delete](#delete) command

<hr>

### Delete
Initially the developer needs to login to [Salla Partners](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) and to the Github Account using [PAT](https://docs.salla.dev/doc-422774?nav=01HNA8QHCPJTCY5VSEZ616JCAK). Next, the developer can run the following command to delete the theme:


```shell title = "Terminal"
salla theme delete

# Alias command for preview
salla theme d
```
A list of themes that are connected to the developer [Salla Partners](https://salla.partners) account will be displayed for the developer to choose the theme they want to delete. After choosing the theme, a success message will be displayed.

<!--
focus: false
-->
![Salla Theme Delete Command](https://cdn.salla.network/docs/cli/theme_delete_command.gif)

---

## twilight-themes-command/List-Themes-Salla-CLI-Salla-Docs

# List

The developer has the ability to design various themes that can be used across multiple stores. The `list` command in [Salla CLI](https://github.com/SallaApp/Salla-CLI) assists the developer in listing the Themes associated with their [Salla Partners](https://salla.partners/) account. To learn more about this command, keep reading.

## 📙 What you'll learn
- [List](#list) command 

<hr>

### List
The developer should be logged into [Salla Partners Account](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) and into his Github Account using [PAT](https://docs.salla.dev/doc-422774?nav=01HNA8QHCPJTCY5VSEZ616JCAK). Then, the command `list` is used to show the list of the developer's Themes:



```shell title = "Terminal"
salla theme list

# Alias command for list
salla theme l
```

As shown bellow:

<!--
focus: false
-->
![List of the themes](https://cdn.salla.network/docs/cli/theme_list_command.gif?version3)

---

## twilight-themes-command/Publish-Theme-Salla-CLI-Salla-Docs

# Publish

Following the creation of [Salla theme](https://docs.salla.dev/doc-422775), the developer may publish it to the [Store Themes Marketplace](http://salla.sa/design), to be ready for installation by the [stores' owners](https://s.salla.sa). This is accomplished with the [Salla CLI](https://github.com/SallaApp/Salla-CLI) theme command `publish`.

## 📙 What you'll learn

- [Publish](#publish) command.
<hr>


### Publish Theme
When a theme connected to a GitHub repository is published, the connection between the repository and the theme is maintained.

:::check
To run the `publish` command, the developer must be in the theme's root folder.
:::

To publish the theme, the developer must be logged in [Salla Partners](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) and into Github Account using [PAT](https://docs.salla.dev/doc-422774?nav=01HNA8QHCPJTCY5VSEZ616JCAK). After that, they need to do the following:


On the terminal, enter the command:


```shell title = "Terminal"
> cd theme_folder_name
> salla theme publish
```

As a result, the system will do the following:

- Recheck the codes for errors and enhance them.
- Commits changes to the theme.
- Request for theme publishing.

<!--
focus: false
-->
![Salla Theme Publish Command](https://cdn.salla.network/docs/cli/Theme_publish_command.gif)

---

## twilight-themes-command/Theme-Preview-Salla-CLI-Salla-Docs

# Preview

The [Salla CLI](https://github.com/SallaApp/Salla-CLI) allows the developer to preview the theme as they are being developed. This article will walk the developer through the process of using the `preview` command in the [Salla CLI](https://github.com/SallaApp/Salla-CLI).

## 📙 What you'll learn

- [Preview](#preview) command

<hr>


### Preview

The `preview` command helps the developer to get a look at the theme in live mode.


:::info
- To run the preview command, the developer must be in the theme's root folder. 
- The developer must be logged into [Salla Partners Account](https://docs.salla.dev/doc-422762?nav=01HNA8QHCPJTCY5VSEZ616JCAK) and logged in to his Github Account using [PAT](https://docs.salla.dev/doc-422774?nav=01HNA8QHCPJTCY5VSEZ616JCAK).
:::


```shell title = "Terminal"
> cd theme_folder_name
> salla theme preview
# Alias command for preview
salla theme p
```

The demo stores of the developer will be listed for the developer to choose from to preview the theme on, after which
an interactive development environment designed by Salla will be launched with the help of `preview` command, this command will also automatically handle the process building and deploying the theme to a local server and preview browser during the development process.

This includes the following steps:

- Running a local development server to serve the local assets' directory.
- Launching a local preview browser with a selected demo store.
- Watching theme file changes.
- Hot reloading the current previewed page, each time changes in assets or views are detected.
- Managing the preview environment including committing the changes to the synced GitHub repository if required.

This is a fantastic option for developers who want to see live updates to their themes appearing on the demo store right away.


:::caution
The developer will be in the preview mode until they exit the CLI using "Ctrl+c".
:::


<!--
focus: false
-->

![Salla Theme Preview Command](https://cdn.salla.network/docs/cli/Theme_preview_command.gif)

Additionally, `preview` command allows further options to simplify previewing a theme in the development environment:

<Tabs>
  <Tab title="Store Name">

``` Store-Name
salla theme preview --store=sweet_store  --with-editor --browser=chrome
```

  </Tab>
  <Tab title="Store ID">

``` Store-ID
salla theme preview store=3346 --browser=firefox 
```

  </Tab>
</Tabs>

|Options|Description|
|---|---|
|`--store=<store>`|Opens the development browser with a selected demo store. The developer needs to provide the demo store name or ID, which can be retrieved by the command `salla store list`. If the developer does not provide the name of the demo store, he or she will be asked to select one later.|
|`--with-editor`|Opens the development browser along with an editor for theme customization. The developer will be asked about this option later, in case it was not provided with the previous command. |
|`--browser=<browser-name>`|Opens the development browser using a specific user browser. By default, the user's browser will be "Google Chrome".|

There are more options for the `preview` command that make it easier to see a preview of the theme in the development environment:

In the case of having an existing project in the developer’s local environment, the `preview` command will request the developer to commit recent changes to the remote repo file in GitHub. Which is equivalent to the `git push` command.
As a best practice, the developer should accept to commit changes to ensure a smooth preview experience.

<!--
focus: false
-->
![Salla Git push Command](https://cdn.salla.network/docs/cli/theme_preview_gitPush.gif.gif)


In rather uncommon situations, the developer may receive an error message as shown below:

``` shell title = "Terminal"
INFO Syncing files in progress..

ERROR Oops! Something went wrong
Error: connect ETIMEDOUT ****
```
This is due to the IP being blocked resulting from exceeding the number of **allowed** requests. 

To resolve this issue:

✅&nbsp;The developer needs to avoid enabling any auto-save option in the IDE. Such features work automatically and send too many requests to the server. <br>
✅&nbsp;Check the network connection. <br>
✅&nbsp;Reboot the network router in order to get a new IP address.<br>

---

## twilight-themes-command/overview-and-introduction-to-the-Salla-CLI-Theme-Commands-Salla-CLI-Salla-Docs

# Overview

This section contains an overview and introduction to the [Salla CLI](https://github.com/SallaApp/Salla-CLI) Theme Commands. These commands allow the developer to create a Salla theme, view a live preview, list the themes, and delete theme.


:::info
Salla Themes are meticulously detailed in the [Twilight Themes Documenation](https://docs.salla.dev/doc-421877).
:::

## 📙 What you'll learn

- [Create a Personal Access Token](#create-a-personal-access-token).
- The different [Salla theme commands](#the-different-salla-theme-commands).


<hr>

## Create a Personal Access Token

[Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#using-a-token-on-the-command-line) or PAT are used as an alternative to passwords for authentication to Github with Salla CLI and GitHub APIs. This step is required for creating themes using Salla CLI. To create a PAT you need to do the following:

1. Login to your [Github](https://github.com/login) account.
2. Verify your email (if not done already)
3. On the upper-right corner of any page, click your profile photo, then click **Settings**.
4. In the left sidebar, click **<> Developer settings**.
5. In the left sidebar, click **Personal access tokens**. 
6. Click on **Generate new token**. 
7. Give your token a **descriptive name**.
8. Add an Expiration date for your token by clicking on **Expiration** drop-down menu then choose default or enter the date using calendar option.
9. Select the scopes, or permissions, you'd like to grant this token. To use your token to access repositories from the command line, select repo.
10. Click **Generate token**. 
Find out more about Personal Access Token [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#using-a-token-on-the-command-line).

:::warning
The Token is to be treated as a password, that means you don't share it publicly and use the token as environment variables instead of hardcoding them into your programs when working with API.
:::


### The different Salla theme commands

- [Create](#create)
- [Preview](#preview)
- [List](#list)
- [Delete](#delete)
- [Publish](#publish)

| ِAction             | Command   | Alias |
| ------------------- | --------- | ----- |
| [Create](https://docs.salla.dev/doc-422775?nav=01HNA8QHCPJTCY5VSEZ616JCAK)   | `create`  | `c`   |
| [Preview](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK) | `preview` | `p`   |
| [List](https://docs.salla.dev/doc-422777?nav=01HNA8QHCPJTCY5VSEZ616JCAK)       | `list`    | `l`   |
| [Delete](https://docs.salla.dev/doc-422778?nav=01HNA8QHCPJTCY5VSEZ616JCAK)   | `delete`  | `d`   |
| [Publish](https://docs.salla.dev/doc-422968?nav=01HNA8QHCPJTCY5VSEZ616JCAK) | `publish` | `p`   |

:::check
For a seamless command execution, it is essential for the developer to:
• Execute the [`Salla login`](https://docs.salla.dev/doc-422762) command to manage [Salla Apps](https://docs.salla.dev/doc-422767) and [Themes](#overview).
• Connect own **Partners Portal** account with GitHub account using [Personal Accesss Token](#create-a-personal-access-token).

:::


### Create 
It is relatively simple to create a Salla theme using the [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `create`. To create the theme, the developer has two options: create a new theme or import an existing one from GitHub. This [article](https://docs.salla.dev/doc-422775?nav=01HNA8QHCPJTCY5VSEZ616JCAK) goes into greater detail about this command.

### Preview 
The developer could also preview the theme to see how it will appear in [Salla stores](https://salla.sa). The [Salla CLI](https://github.com/SallaApp/Salla-CLI) command `preview` allows the developer to do that. More information about the `preview` command can be found [here](https://docs.salla.dev/doc-422776?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

### List
Using the `list` command, the developer is able to view a list of the themes that are associated with their [Salla Partners](https://salla.partners) account. Continue reading [here](https://docs.salla.dev/doc-422777?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

### Delete
The [Salla CLI](https://github.com/SallaApp/Salla-CLI) also gives users the ability to delete any themes they have created. Find further information in this [article](https://docs.salla.dev/doc-422778?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

### Publish
The `publish` command gives the developer the ability to publish the theme they have created to the [Store Themes Marketplace](https://s.salla.sa/design), to be available for installation. More information on the publishing theme is found [here](https://docs.salla.dev/doc-422968?nav=01HNA8QHCPJTCY5VSEZ616JCAK).

---

