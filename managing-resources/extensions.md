---
description: >-
  An extension is a packaged set of code that extends the Launch interface and
  the library or mobile SDK functionality.
---

# Extensions

Launch is the platform, and extensions are like mini-apps that run on the platform. Adding an extension may add new data elements and new options for creating rules.

**Tip**: Extensions are similar to _tools_ in the previous Dynamic Tag Management.

Extensions determine the elements that are available when building properties, rules, and data elements and provide the following:

* Events, conditions, and exceptions
* Data elements
* JavaScript
* SDK code for mobile apps

Use the links at the top of the Extensions list to view installed extensions, the extensions catalog, or updates.

To view and change the extension's settings, select an extension and click **Configure**. For information about extension options, see [Add a new extension](extensions.md#add-a-new-extension) .

**Important**: Changes do not take effect until they are [published](../publishing/).

By default, Adobe provides extensions that support common integrations. Extensions can be modified with custom configurations, and configurations are provided through the extensions. To create a configuration, click the extension card and click **Add New Configuration**.

For a video introduction, see [Extensions](../getting-started/videos.md).

## Extension catalog

Use the extension catalog to browse, configure, and deploy marketing and advertising technology built and maintained by independent software vendors, as well as extensions for Adobe solutions.

The Extensions page provides the following views:

* **Installed**, which shows all of your installed extensions.
* **Catalog**, which shows all available extensions.
* **Updates**, which shows updates to installed extensions.

Click **Extensions** to see all your installed extensions. You can also use the catalog to see a list of all available extensions and the extensions that that you can update. For more information about the Adobe-owned extensions, see [Extensions Reference](../extension-reference/) .

## Add an extension

Launch is highly extendible, so you can easily add core functionality.

**Tip**: A common use of extensions is to create integrations with other applications. In the previous version of Launch, known as Dynamic Tag Management, extensions were called _tools_.

1. From a property's overview page, click the **Extensions** tab.
2. Select an extension, for example, **Mobile Core**.

   ![](../.gitbook/assets/extensions.png)

3. Select an extension from the extensions catalog.
4. Mouse over an extension in your list to configure or disable it.
5. Add other extensions from the catalog as necessary.

   The **Mobile Core** extension is the starting point for your new extension, and the default extension provides the following features:

   * Default event
   * Default conditions and exceptions
   * Default JavaScript

   These defaults are the basis for the custom rules that you will build to create your extension.

   **Important**: You should also install the **Identity**, **Analytics**, and **Profile** extensions.

When creating or editing elements, you can save and build to your [active library](../publishing/libraries.md#active-library). This step immediately saves your change to your library and executes a build, and you can monitor the build status. You can also create a new library from the **Active Library** drop down.

## Configure an extension

Mouse over an installed extension and click **Configure**.

**Tip**: Some extensions do not require configuration and do not offer configuration options.

Each configurable extension has unique options. For information about the options available for each Adobe extension, see [Extensions Reference](../extension-reference/).

