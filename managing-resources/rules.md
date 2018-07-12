# Rules

Launch is a rule-based system. It looks for user interaction and associated data. When the criteria that are outlined in your rules are met, the rule triggers the extension, script, or HTML that you identified.

Build rules to integrate the data and functionality of marketing and ad tech that unifies disparate products into one solution.

For an introductory video, see [Rule builder](../getting-started/videos.md).

Events are where the majority of interactions on sites take place. You can measure and react to these interactions in real-time, without the need for JavaScript.

**Events \(If\):** The event is what you want the rule to look for. This is defined by choosing an event, any applicable conditions, and any exceptions.

**Actions \(Then\):** Triggers occur after a rule's events take place and all conditions are satisfied. A rule in Launch can trigger as many discrete actions as you want, and you can control the order in which these actions occur. For example, a rule for an e-commerce _**Thank You**_ page can trigger your analytics tools and third-party tags from one rule. You do not need to create separate rules for each extension or tag.

You can add more event types. Multiple events are joined with an OR, so the rule's conditions will be evaluated if any of the events are met.

**Important**: Changes do not take effect until they are [published](../publishing/).

## Events, conditions, and exceptions \(if\)

Events, with any conditions and exceptions, are the _If_ portion of a rule.

If a specified event occurs, the conditions and exceptions are evaluated, the specified actions take place if necessary.

* Events

  Specify one or more events that must take place to trigger the rule. Multiple events are joined by an OR. Any of the specified events will trigger the rule.

* Conditions

  Narrow the event by configuring any conditions that must be true for an event to trigger the rule.

* Exceptions

  Specify any exceptions that would keep the rule from firing, even if the events and conditions are met.

The events that are available depend on which extensions are installed. For information about the events in the Core extension, see [Core extension event types](../extension-reference/web/core-extension.md#core-extension-event-types).

**Important**: DTM provided page load, event-based, and direct call event types. This is no longer true in Launch. Rather than event types, Launch extensions configure different individual events.

Only events are required, and the conditions and exceptions are optional.

## Actions \(then\)

Actions are the _Then_ portion of a rule. When an event is triggered, if conditions evaluate to true and exceptions evaluate to false, the actions are performed. You can drag and drop actions to specify the order.

The action, or _then_ , part of the formula determines what happens when the event takes place and all conditions and exclusions are met.

## Create a rule

Create a rule by specifying what actions occur when a condition is met.

1. Open the **Rules** tab and click **Create New Rule**.

   ![](../.gitbook/assets/rule-create.png)

2. Name the rule.
3. Click the **Events Add** icon.
4. Select your extension and one of the event types that are available for that extension and configure the properties for the event.   
  
   **Tip**: The available event types are defined by the extension.

   ![](../.gitbook/assets/rule-event-config.png)

   Some events do not have any properties that need to be configured.

5. Set the **Order parameter** and click **Keep Changes**.

   The default order for all rule components is 50. If you want one to run sooner, give it a number less  than 50.

   * Order of execution is the numerical order, for example, 1 comes before 3, and 3 comes before 10. 10 comes before 100, and so on.
   * Rules that have the same order run in no particular order.
   * Rules are fired in order, but do not necessarily finish in the same order.   
     If Rule A and Rule B share an event, and you assign an order so that Rule A comes first, if Rule A does something asynchronously, there is no guarantee that Rule A will finish before Rule B starts.

     If you want Rule A to run later, give it a number higher than 50. For more information about ordering, see [Rule ordering](rules.md#rule-ordering).

6. Click the **Conditions Add** icon,  choose a condition type, and configure the properties for your condition. 
7. Click **Keep Changes**.

   You can add other conditions, and multiple conditions are joined with an OR. The rule's exceptions will be evaluated if any of the events are met with their conditions.

8. Click the **Exceptions Add** icon and choose an exception type and configure the properties for your exception. 
9. Click **Keep Changes**.

   You can add other exceptions, and multiple exceptions are joined with an OR. The rule's actions will be evaluated if any of the events are met with their conditions and exceptions.

10. Click the **Actions Add** icon, select your extension and an action type, configure the properties for the action, and click **Keep Changes**.   
  
    **Tip**: The available action types are defined by the extension.

    ![](../.gitbook/assets/rule-action-config.jpg)

    You can add more event types, and multiple events are joined with an OR. The rule's conditions will be evaluated if any of the events are met.

11. Review your rule and click **Save Rule**.

    When you [publish](../publishing/), you can add this rule to a library and deploy it.

When you edit or update an existing rule, a new version of the rule is created, which you can deploy. 

When creating or editing rules, you can save and build to your [active library](../publishing/libraries.md#active-library). This step immediately saves your change to your library and executes a build. The status of the build is displayed.

## Rule ordering

Rule ordering allows you to control the order of execution for rules that share an event, and it might sometimes be important to have your rules fire in a specific order.

Here are some examples: 

1. You have several rules that conditionally set Analytics variables, and you need to ensure that the rule with `Send Beacon` goes last.
2. You have a rule that fires Target and another rule that fires Analytics and you want the Target rule to run first.

Ultimately, the responsibility for executing actions in order lie with the extension developer of the event type that you are using. For Adobe extensions, Adobe makes sure this works properly. For third-party extensions, Adobe can only provide the necessary guidance, but it is up to the developers to implement everything correctly.

Adobe strongly recommends that you order your rules with positive numbers between 1 and 100. \(The default value is 50.\) 

**Tip**: Remember you have to maintain your order. 

However, Adobe recognizes there might be edge cases where this recommendation might feel limiting, so you can use other numbers. Launch supports negative numbers to a **minimum** of  -1.79 \* 10^308, 0, and positive numbers to a **maximum** of 1.79 \* 10^308. You can also use up to 17 decimal places.

### Scenarios

Here are a some sample scenarios:

* Five rules share an event.  All have default priority, and I want one of rules  to run last. I just need to edit that one Rule Component and give it a number higher than 50 \(60 for example\).
* Five rules share an event.  All have default priority. I want one of them to run first. I just need to edit that one Rule Component and give it a number lower than 50 \(40 for example\).

### Client-side rule handling

The load order for rules depends on whether the rule action is configured with JavaScript or HTML, and whether the rules uses a page bottom or top event, or a different type of event.

You can use `document.write` within your custom scripts regardless of the events configured for the rule.

You can order different custom code types among each other. For example, you can now have a JavaScript custom code action, then an HTML custom code action, then a JavaScript custom code action. Launch ensures that they are executed in that order.

### Rules with page bottom or page top event

* **Javascript:** The JavaScript is embedded in the main Launch library. The custom script is wrapped in a script tag and written to the document using `document.write`. If the rule has multiple custom scripts, they're written in order.
* **HTML:** The HTML is embedded in the main Launch library. `document.write` is used to write the HTML to the document. If the rule has multiple custom scripts, they're written in order.

### Rules with any other event

* **JavaScript:** The JavaScript is loaded from the server as regular text, wrapped in a script tag, and added to the document using Postscribe. If the rule has multiple JavaScript custom scripts, they will be loaded in parallel from the server, but executed in the same order that was configured in the rule.
* **HTML:** The HTML is loaded from the server and added to the document using Postscribe. If the rule has multiple custom HTML scripts, they will be loaded in parallel from the server, but executed in the same order that was configured in the rule.

