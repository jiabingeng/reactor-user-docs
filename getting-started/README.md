# Getting Started

Launch is the next-generation of Adobe's website tag and mobile SDK management technology, built on the Adobe Cloud Platform. It is built from the ground up to support an open and sustainable ecosystem where anyone can build their own integrations that Adobe customers can deploy to their websites and mobile applciations. It is an API first application so anything you can do through the UI you can also do programmatically through an API.

The basic Launch workflow:

1. [Set up groups and users](./#1-set-up-groups-and-users).
2. [Log in](./#2-log-in).
3. [Create a property](./#3-create-a-property).
4. [Install extensions](./#4-install-extensions).
5. [Create data elements and rules](./#5-create-data-elements-and-rules).
6. [Test in your dev environment](./#6-test-in-your-dev-environment).
7. [Promote to production](./#7-promote-to-production).

For an introductory video, see [Introduction to Launch, by Adobe](videos.md).

## 1. Set up groups and users

Launch is fully integrated with your Adobe ID. User permissions are managed through the Admin Console with other Adobe products and solutions from the Creative Cloud, Document Cloud, and Experience Cloud.

Unlike DTM, which has a role-based user management, Launch has rights-based user management. This means that instead of getting a role that implies a certain set of rights, individual rights must be explicitly granted. These rights are assigned to groups, and to gain access, users are added to the appropriate groups. Even if your company has access to Launch, users cannot complete any tasks until an Org Administrator explicitly grants them some rights.

For more information about how to create groups and add users for Launch, see [Users](https://github.com/jiabingeng/mobile-launch/tree/99e9070fe9a3f19319363a0299dd4c8ead31fb10/administration/users.md).

## 2. Log in

After Launch rights have been added to your Adobe ID, you need to log in to Launch by going to [https://launch.adobe.com](https://launch.adobe.com) or by logging in to the [Experience Cloud \(https://experiencecloud.adobe.com\)](https://experiencecloud.adobe.com), navigating to the Activation page, and clicking on Launch.

## 3. Create a property

In Launch, your first task is to create a property. 

A property is a container that you fill with extensions, rules, data elements, and libraries to deploy tags to your site and configuration parameters to your mobile apps. Some users create a property for each website \(or group of closely related sites\) where they want to deploy the same set of tags. For mobile applications, a new property can contain multiple applications or one application depending on the need for different configurations.

For more about creating properties, see [Create a property](../administration/companies-and-properties.md#create-a-property).

## 4. Install extensions

Extensions are one of the core features of Launch. An extension is an integration built by Adobe or an Adobe partner that adds new and endless options for the tags that you can deploy to your sites. If you think of Launch as an operating system, extensions are the apps that you install so that Launch can do the things you need it to do.

All new properties come with the [Core extension](https://github.com/jiabingeng/mobile-launch/tree/99e9070fe9a3f19319363a0299dd4c8ead31fb10/extension-reference/core-extension.md) installed. This extension is built by the Launch team to provide a robust default set of data element types for your data layer and event types for your rules. Most of the actions that you want to perform, including get an Experience Cloud ID, send Adobe Analytics beacons, load the Target global mbox, and so on, will come from extensions that you install from the catalog.

What makes Launch truly unique among other tag and mobile SDK management systems is that these extensions can be built by anyone. Do you need to drop a Facebook remarketing pixel on your site? Check out the extension that Facebook built. Do you want the same for Twitter or LinkedIn? Use those extensions. Do you need to run a survey? Look at Question Pro or Foresee. Do you need to manage privacy and consent from your end users to help out with GDPR? Take a good look at Evidon and Trust Arc. Would you like to see really granular insight into the behavior of individual users on your site? Maybe take a look at Clicktale. For mobile attribution, check out Branch. For more information, see [Add a new extension](../managing-resources/extensions.md#add-a-new-extension).

## 5. Create data elements and rules

**Data elements** are pointers to the information that you want to collect and send to different places on your page and include the following:

* A defined data layer in JSON
* DOM elements
* Cookies
* Session and local storage
* Just about everything else

Once defined in a data element, you can use the element anywhere in Launch for any extension. For more information, see [Data Elements](../managing-resources/data-elements.md).

**Rules** are at the logical core of your implementation and control the what, when, where, and how. With rules, you can define an event, set conditions and exceptions, define the actions and order, and publish your changes to see the results. For more information, see [Rules](../managing-resources/rules.md).

## 6. Test in your Dev environment

### Libraries and builds

Nothing in Launch is published automatically. Each set of changes you make is encapsulated into a [library](../publishing/libraries.md). Each library you create automatically inherits anything upstream \(published, approved, or submitted\) as a baseline, so all you need to do is define the changes that you want to make. This library serves as the blueprint for a [build](../publishing/builds.md). A build for a web property is the actual set of JavaScript files that are deployed and used on your site. A build for a mobile property is the JSON file used to configure your SDK and a manifest file that can be used with a dependency manager such as Maven, Carthage, or CocoaPods to bundle in extensions.

![](../.gitbook/assets/loop.png)

Here is an overview of the process:

1. Launch publishes a build to your host server.

   As mentioned above, a build is the actual JavaScript file\(s\) that Launch produces. This relationship between Launch and your host location is defined by an adapter. For more information about adaptors, see [Adapters](./#adapters) below. 

2. Launch provides an embed code `<script>` tag that goes on your site.

   When you create an environment and attach an adapter, the environment provides this `<script>` tag to put on your pages.

3. When a user browses your site, the Embed Code `<script>` tag retrieves the build from your host server and performs your defined actions in the browser.

### Adapters

An adapter is a connection between Launch and your hosting location. Launch currently supports an Akamai adapter and an SFTP adapter. When you generate a build, Launch connects to the server that is defined by your adapter.

If you want to self-host, you can have Launch push directly to your servers through SFTP or you can push the build to Akamai and download it by using your environment's Archive option. For more information, see [Adapters](../administration/adapters.md).

### Environments

Each library is created in an environment, and an environment defines how you want your build to look after it is published.   
  
You can specify the following types of environments:

* **Adapter** Each environment needs an adapter that determines where Launch will push the builds that were created in this environment.
* **Archive** The default is to deploy your build as a minified .js file, or if you are using custom code, multiple files that reference each other. You can have wrap all these files together in a zip file and encrypt it.

After you save your environment, it generates the embed code that you can copy and paste into your website. 

**Important**: The embed code will not work until you have created a library and produced a build. For more information, see [Environments](../administration/environments.md).

### Publish a Build to Dev

Now that you understand the basic components, the publishing process should make more sense.

To publish, you need to complete the following tasks:

1. Create an adapter.
2. Create a dev environment by using the adapter you created.
3. Deploy the embed code from your dev environment to your dev test site.
4. Create a library and assign it to the dev environment you created.
5. Build your library.

## 7. Promote to production

After you test your build in your dev environment, the promotion process is simple. Before you try it out, ensure that you create your stage and production environments and put the embed codes in the necessary places. 

**Tip**: You can reuse existing adapters.

Promoting a library all the way through to production will typically require coordination among the following roles:

1. A **Developer** has Develop rights and submits the library, which moves the library to the Submitted state.
2. An **Approver** has Approve rights, can build the library to the stage environment, and approve it after testing. This process moves the library to the approved state, but only one library can be submitted and approved at a time.
3. A **Publisher** has Publish rights and can build the library to the production environment.

You can assign all these rights to one person. For more information about the different states and options that are available during the publishing process, see [Approval Workflow](../publishing/approval-workflow.md).

## Additional Resources

To learn more about Launch, see the following resources:

* [**Launch Community**](https://forums.adobe.com/community/experience-cloud/platform/launch)**:** Ask and answer questions, submit ideas, vote on the ideas of others. Log in with your Adobe ID.
* [**Launch Webinars**](https://adobe.com/go/launchme)**:** Sign up for upcoming webinars and watch recordings of past webinars.
* [**Developer Docs**](http://developer.adobelaunch.com/)**:** Get involved with the Launch developer community to build extensions or use the Launch APIs
* [**Videos**](https://github.com/Adobe-Marketing-Cloud/reactor-user-docs/tree/67a59a7519514467a713016adfe46d999fe330d8/getting-started/videos.html)

  These videos introduce you to Launch concepts and tasks.

