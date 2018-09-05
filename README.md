# Overview

Launch is the next generation of website tag and mobile SDK management capabilities from Adobe. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences. For mobile, Launch provides capabilities to dynamically configure, publish and delpoy changes to their SDK.

Launch empowers anyone to build and maintain their own integrations with Launch, called Extensions. These extensions are available to both web and mobile Launch customers in an app-store like experience so they can quickly install, configure, and deploy their integrations.

## Key benefits

Here are the key benefits to using Launch:

* Faster time to value
* Trustworthy data through centralized collection, organization, and delivery using data elements
* Compelling experiences through the integration of data and marketing technology using rule builder

## Key features

Here are some of the key features in Launch:

### Extensions

An extension is a package of code \(JavaScript, HTML, and CSS\) that extends the Launch UI and client functionality. You can build, manage, and update your integrations using a virtually self-service interface. You can think of Launch as an operating system, and extensions are the apps you use to achieve your tasks.

Mobile extensions are comprised of the Launch UI configuration options and native SDK components that work with the core Adobe Cloud Platform SDKs to deliver functionality to mobile apps.

### Extension Catalog

You can browse, configure, and deploy marketing/advertising tools built and maintained by independent software vendors.

### Rule Builder

You can create robust rules that combine multiple events, sequenced in the way that you determine using if/then logic with conditions and exceptions.

Extensions provide options for:

* Events
* Conditions
* Exceptions
* Actions

The rule builder includes real-time error checking and syntax highlighting for your custom code. When the criteria outlined in your rules are met and conditions are satisfied, the actions you define are executed in order.

### Data Elements

You can collect, organize, and deliver data across marketing and advertising technologies.

### Enterprise Publishing

The publishing process enables teams to publish code to pages or SDK configuration options to mobile apps. Different users can create an implementation, approve it, and publish.

The publishing process provides the following features:

* Changes to your code or configuration are encapsulated in libraries you define.​
* You specify where and when you want your code deployed. ​
* Multiple libraries can be built in parallel by different teams. ​
* Unlimited development environments. ​
* Deliberate, permissioned process for merging libraries. ​

### Open APIs

Automate implementations of individual technologies, or a group of technologies.

* Launch interacts with the Reactor APIs ​
* Deployments can be automated through APIs ​
* Integrate the Launch APIs with your own internal systems ​
* You can build your own user interface, if desired ​

### Light, Modular Container Tag

The Launch container tag is 60 percent lighter than DTM and 40 percent lighter than Google Tag Management. The content of your container is minified, including your custom code. Everthing is modular. If you do not need an item, it is not included in your library. The result is an implentation that is fast and compact. For more information, see Minification.

## Other Highlights

Launch provides several improvements over similar systems, including:

* No use of `document.write ()`, where Chrome does not allow it.​
* The Page Top and Page Bottom rules are bundled into the main library to minimize unnecessary HTTP calls. ​ ​
* Custom action scripts within a rule can be loaded in parallel, but are executed sequentially. ​
* If you avoid Page Top and Page Bottom rules, the code is mostly asynchronous, with a path to getting fully async. ​

## Requirements

Launch requires the following:

* You must be an Adobe Experience Cloud customer.
* For web, you must deploy the Launch or DTM embed code on your web pages.
* For mobile, you must integrate the Adobe Experience Cloud Mobile SDKs into your application.

## Adobe Launch FAQ

Here are some frequently asked questions about the new tag management capabilities that was announced in March 2017.

#### What is Launch?

Launch is the next-generation of the Adobe tag-management capability, built into the Adobe Cloud Platform. Launch enables clients to:

* Deploy client-side web products using integrations called _extensions_
* Consistently capture, define, manage, and share data between marketing and advertising products from other vendors and from Adobe

Launch is an advanced JavaScript delivery system that evaluates conditions and executed actions to efficiently and effectively deploy client-side libraries and products. It provides a highly scalable approach to managing and building extensions, together with a robust set of APIs for programmatic interaction with the Adobe Cloud Platform.

#### Is Launch just an updated DTM?

No. Launch is an entirely new product with a new code base. The system has been redesigned from scratch using modern front-end development practices and an API-first approach. Everything is built on a robust set of APIs, which makes the system very powerful and highly flexible.

#### Will the current DTM product remain available?

Yes, legacy DTM \(the existing production version\) will continue to be supported for the foreseeable future. Adobe will continue to fix any significant bugs and ensure consistent performance. At this time, no major feature enhancements are planned for legacy DTM.

Many customers see Launch implementations as an opportunity to start from scratch and clean up many issues they have with current implementations. If this does not describe you, you can copy an existing DTM property into Launch and save yourself a bunch of effort. For more information, see [Upgrade FAQ](upgrade-from-dtm-to-launch/upgrade-faq.md).

#### How much does Launch cost?

There is no additional charge for Launch. It is available for any Adobe Experience Cloud customer.

#### Will I have to change the embed codes in my current DTM implementation?

If you are currently using the existing \(legacy\) DTM system, no, you will not have to change your production embed codes. You can continue to work in your current DTM Company and Web Properties. You can link your DTM Production embed code with your Launch Production embed code so that you do not have to change your page tags. For more information, see [Link DTM Embed Code](upgrade-from-dtm-to-launch/link-dtm-embed-code.md).

#### I heard there are plug-ins now. What's that about?

We call them [Extensions](./#extensions). Launch is built into the Adobe Cloud Platform, and it is fully extensible. Customers, Adobe Partners, agencies, and marketing or advertising technology vendors will soon be able to build Launch extensions that add new functionality or modify existing functionality. The system allows partners and clients to build, manage, and update their own integrations. This is just one way Adobe is opening up the Adobe Cloud Platform so that customers and partners can build products and businesses on the Platform, and so that everyone can more easily connect Adobe technology to the marketing and advertising technologies from other vendors.

#### Will all third-party extensions be available right away?

Extensions are available for all Adobe solutions and for a growing number of independent vendors. New extensions are always under development and more are added to the catalog every week. Each extension developer maintains their own roadmap and schedule for their extensions, and the Launch team does not have control or influence over this process.

#### When will clients or partners be able to build extensions?

Anyone can build an extension now. To get started, read the [developer docs](https://developer.adobelaunch.com/guides/extensions/). Currently all extensions are open to all Launch users, but later this year we will add the ability to build an extension that can only be seen by your company and a whitelist of others that you specify.

#### Will Launch meet my company's security standards?

Launch is SOC-2 and Gramm-Leach-Bliley Act ready. Launch also offers the capability of being self-hosted. The JavaScript libraries can be served from your own servers, or the CDN of your choice. This gives your IT and security teams the ability to run automated testing, to check the files into your own version control system, and to fully comply with any internal production migration processes, security-related or otherwise.

#### I have a project coming up very soon. Should I use Launch or DTM?

Launch. Any new deployments done with DTM will need to be migrated eventually as DTM reaches its sunset phase.

#### Does Launch support single page apps \(SPAs\) and my favorite framework?

Yes. Launch has capabilities to give users and extension developers flexibility in collecting, managing, and distributing data in single-page application experiences or Ajax-heavy pages or sites. This applies regardless of your development framework preferences, including Angular, React.js, Ember, Meteor, and so on.

For more information about the benefits of using Launch for your SPAs, go to the [Launch blog](https://medium.com/launch-by-adobe/the-top-5-reasons-that-launch-is-better-for-single-page-applications-5a7b9880939f).

#### Does Launch support dynamic data layers?

Yes. Launch includes an extension that specializes in listening for changes in dynamic data layers.

#### Which event types does Launch support?

Event types are available through extensions. The Launch Core extension includes 30 built-in event types. Other extensions add additional event types. For example, the YouTube extension includes the following video event types: 

* Play
* Pause
* End
* Time played

Through extensions, Launch can support any other browser event types or synthetic event types, such as specific visitor activity sequences.

#### Will the new Launch speed up \(or slow down\) my web site?

Performance is very important to us. Launch is designed to deliver and run marketing and advertising technologies on your web site as efficiently as possible using today's best practices. Adobe technologies deployed together through Launch are faster than any other deployment method. You can read more about performance and our perspective in the [Performance Whitepaper](https://medium.com/launch-by-adobe/adobe-web-browser-technology-performance-477c2bfeaa98).

#### Which browsers will Launch support?

Browser support in the Launch client-side libraries:

* Chrome \(latest\)
* Safari \(latest\)
* Firefox \(latest\)
* Internet Explorer \(10 and above\)
* iOS Safari \(latest\)
* Android Chrome \(latest\)

Browser support in the Launch application interface:

* Chrome \(latest\)
* Safari \(latest\)
* Firefox \(latest\)
* Internet Explorer \(11 and above\)

Legacy DTM supported older versions of Internet Explorer, but over the last few years, the percentage of overall web users with older, outdated browsers has dropped to a small segment for our clients. Most Adobe clients now leverage more modern web platform features in current browsers and create better user experiences, including single-page applications, interactive Ajax-heavy web sites, and pages. As most clients move to more modern approaches with their sites, they demand a solution like Launch that enables those approaches.

#### Does the new Launch work on native mobile apps?

Adobe continues to recommend the [Mobile Services App SDK](http://www.adobe.com/solutions/digital-marketing/mobile-services/app-sdk.html) to implement data collection and delivery in a native mobile app environment. With Adobe mobile services, the process is streamlined with one SDK that works with multiple Adobe Cloud Platform solutions. Going forward, you will see additional tag management-like functionality in the Mobile Services interface as the Launch and Mobile teams continue working closely together for more seamless Cloud Platform access and user experiences.

#### What if I have other questions?

These are the questions that we have received most often from customers and partners since the Launch announcement. If you have other questions, go to the Adobe Community on the main Launch page at [https://adobe.com/go/launchme](https://adobe.com/go/launchme).

Launch is just one example of where our platform is headed: more open, more integrated and as always dedicated to customer success.

