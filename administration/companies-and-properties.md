---
description: >-
  A property, or web property, is a collection of rules, data elements,
  configured extensions, environments, and libraries. There is only one publish
  embed code per property.
---

# Companies and Properties

A property can be any grouping of one or more domains and subdomains. You can manage and track these assets similarly. For example, if you have multiple websites based on one template, and you want to track the same assets on all of them. You can apply one property to multiple domains.

A web property can be any grouping of one or more domains and subdomains. You can manage and track these assets similarly. For example, suppose that you have multiple websites based on one template, and you want to track the same assets on all of them. You can apply one property to multiple domains, but keep in mind there is only one publish embed code per property.

A mobile property type can contain multiple applications. For example, in a mobile property you can manage the same set of rules and extensions across multiple iOS and Android applications.

For a video tutorial, see [Creating your first property](../getting-started/videos.md).

## Companies

In Launch, there is a one-to-one relationship between your companies and your Experience Cloud organizations.

You can have one or several Launch company accounts. Companies contain properties, and you can have any number of properties in a company account. In a property, you can have any number of domains or subdomains. Some customers have one company that contains all of their properties. Some have a company that contains many properties, one for each domain. Some have a company that contains several properties, one for each type of site they manage.

## Separating the Launch environment for multiple entities

In Launch, there are a few ways to handle multiple-geo markets, business units, applications, domains, and subdomains. For example, you might have three properties in your company account where one property contains all of your blog sites, a second property contains all of your ecommerce sites, and the third property contains all of your lead-generation sites.

**Tip**: Each property requires its own embed codes in your page templates. Any domains or subdomains that you want to include in a property will have the same embed codes in the page templates when Dynamic Tag Management is first installed on your site. For example, you might have four properties within your company account where one contains all of your blog sites, another contains all of your ecommerce sites, a the third contains all of your lead-generation sites, and a fourth contains all of your mobile applications.

### Can we use separate instances for each?

As described above, you can use separate company accounts for your three entities, or you can combine the entities into one company account and split the domains/subdomains into different properties in that company account.

### Is there a clear way to separate domains and settings in the same Launch instance?

In a company account, you can use multiple properties to separate domains and settings, or you can put multiple domains in the same property.

### What are the pros and cons for using one Launch instance?

With one property that contains multiple domains and subdomains, you will eventually add conditional logic to separate unique data collection and tracking needs that only apply to individual domains, subdomains, or subsets of domains/subdomains.

### What is the approach recommended by Adobe: one or separate companies?

Multiple Launch companies are not recommended. Adobe strongly suggests multiple properties in one company.

## Best practices for planning properties

Each implementation can be different in Launch, with a wide variety of data-collection needs, variable usage, extensions, third-party tags, other systems and technologies, people, teams, geographic regions, and so on. Using the flexible User Management features and properties, you can create a configuration that matches your workflow and processes.

If the scenarios you are tracking, the data you are collecting, the extensions you are deploying, and the variables you are setting are similar across all or some of your domains and subdomains, it is easier to have those domains and subdomains grouped into the same property in Launch. If those are unique for each domain and subdomain, it is easier to have those domains and subdomains in their own property. If you choose to group domains and subdomains into one property now, you can always change your mind and later create several web properties.

Considering the following when planning properties:

#### Data

**For all of your websites or applications, is the data you are going to collect very similar, somewhat similar, or unique?**

If the data you need to collect is similar across everything, it might make sense to group those sites or applications into one property to avoid duplicating rules or copying rules from one property to another.

If your data collection needs are unique for each site or application, it might make sense to separate them into their own properties. This method lets you control the data collection more specifically, without using large amounts of conditional logic in custom scripts.

#### Variables

**Similar to data, for all of your websites, are the variables you are going to set in your Analytics and other extensions very similar, somewhat similar, or unique?**

For example, if eVar27 is used for the same source value across all of your websites, it might make sense to group those sites together so you can set those common variables across your sites in just one property.

If your variable usage is unique for each site, it might make more sense to separate those sites into their own properties so you can control the variables more specifically for each site without using large amounts of conditional logic in custom scripts.

#### Extensions, Tags, and Systems

**Are the extensions, tags and systems you are going to deploy through Launch very similar, somewhat similar, or unique?**

If the extensions, tags, and systems you are going to deploy through Launch are very similar across your sites, you might want to include those sites in the same property.

If you are deploying Adobe Analytics on only one site, and your other extensions and tags are also unique to certain sites, you might want to create separate properties for those sites so you can control those specific extensions in one property.

For example, If you are deploying Adobe Analytics, Target, and the same 3rd-party tags and extensions across your sites, that is a reason to group sites together.

#### People

**For the individuals, teams, and organizations that are working in Launch, will they need access to all of your websites, some of them, or just one of your domains or sub-domains?**

The User Management features allow you to assign different roles to different people for all of your properties or on a per-property basis. If someone has sufficient rights, that person can perform administrative actions across all the properties in that Launch company. All the other roles can be assigned on a per-property basis. You can even hide a property from certain users \(non-admins\) by not giving them any role in that property.

## Deactivating a property

The ability to deactivate a property is planned for a future release.

## Properties page

A property is a collection of rules, data elements, configured extensions, environments, and libraries. There is only one publish embed code per property.

A property can be any grouping of one or more domains and subdomains. You can manage and track these assets similarly. For example, suppose that you have multiple websites based on one template, and you want to track the same assets on all of them. You can apply one property to multiple domains.

The left side of the screen shows the companies in your organization. This is particularly useful if you manage multiple accounts. Select a company to see the properties and audit logs for that company.

Each property is shown in the Properties list.

The **Properties** list shows the following information:

* **Property name**
* **Status**

Click a property to see an overview of that property. The overview shows any activity performed on the property. It also lists the metrics and extensions for the property.

## Create a Web property

Create a Web property in Launch.

Note: Only a user with sufficient rights can create a property. See [User Management](https://github.com/jiabingeng/mobile-launch/tree/99e9070fe9a3f19319363a0299dd4c8ead31fb10/administration/users.md).

Before beginning, review the [Best practices for planning properties](companies-and-properties.md#best-practices-for-planning-properties) for properties.

1. Navigate to your company page, then click Add New Property.

   ![](../.gitbook/assets/property-create.jpg)

2. Fill in the fields:

   **Name:** The name of your property.

   **URL:** The base URL of the property

3. \(Optional\) Configure Advanced Settings.

   **Return an empty string for undefined values of Data Elements:** Select this check box if you want undefined values to be empty, rather than to assign default values.

   **Tracking Cookie Name:** Overrides the default tracking cookie name. You can customize the name that Launch uses to track your opt-out status for receiving other cookies.

   **Anchor Delay \(Milliseconds\):** Specifies how long Launch waits for tags to fire on clicked links before moving to the next page. The default value is 100 milliseconds. Longer delays improve tracking accuracy. Adobe recommends a delay of 500 milliseconds or less, which the user will not perceive. Launch will wait up to the time specified, but if the beacon fires sooner, the delay is cut short. \(That is, user won't always wait the full length of the delay.\)

4. Click Save.

   The extension is automatically installed into the new property.

## Create a Mobile property

Create a Mobile property in Launch.

Note: Only a user with sufficient rights can create a property. See [User Management](https://github.com/jiabingeng/mobile-launch/tree/99e9070fe9a3f19319363a0299dd4c8ead31fb10/administration/users.md).

Before beginning, review the [Best practices for planning properties](companies-and-properties.md#best-practices-for-planning-properties) for properties.

1. Navigate to your company page, then click Add New Property.

   ![](../.gitbook/assets/mobile-property.png)

2. Fill in the fields:

   **Name:** The name of your property.

   **Privacy:** Privacy defaults to "Opted In". This setting determines if the app should send identifying data by default. Note that function calls to the SDK can be made to stop sending data and to delete any data already collected.

   **Use HTTPS:** Check this box on or off depending on how you would like the SDK to transfer data from the application.

3. Click Save.

## Delete a property

Delete a property from Launch.

Note: Property removal cannot be reversed. The requestor must be an admin-level user. This request cannot be undone.

1. In the Properties list, select the property you want to delete.

   You can select multiple properties to delete.

2. Click Delete, then confirm the removal of the property.

