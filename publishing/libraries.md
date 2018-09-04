# Libraries

A library is a set of instructions for how extensions, data elements, and rules will interact with each other after they are deployed. When you create a library, specify the changes that you want to make to your library. At build time, these changes are combined with everything that has been submitted and was approved or published in previous libraries.

Remember the following information about libraries:

* Libraries contain the addition or removal of:  
  * Rules 
  * Elements 
  * Extension configruation
* Libraries must be assigned to an environment before they can be compiled in a build.
* Libraries are approved or rejected as a whole.  You cannot approve or reject individual items in a library.
* A library moves between several environments as it makes its way through the publishing workflow.

## Create a library

1. Open the **Publishing** tab.

   The Publishing page lists the Dev libraries and provides the means to submit them for approval, move them to staging, or publish them to production.

2. In **Development**, click **+** to add a new library.

   ![](../.gitbook/assets/library-create.jpg)

3. Name the library.
4. Assign the library to a Dev environment.
5. Add a change to the library. 
6. To add an item, click **Add a Resource** and choose the items you want to add.  
   Items that have been edited or deleted are available to add to the selected library.

   ![](../.gitbook/assets/library-add-change.jpg)

   You can add the following items to your library:

   * Rules
   * Data elements
   * Extension configurations

7. To add any resources that have changed, click **Add All Changed Resources**.
8. Click **Save** or **Save & Build for Development**.

   Deploying compiles a build and deploys it to the assigned environment.

After the library is created, use the drop-down menu for that library to select one of the following options:

* **Edit**

  Changes the library configuration.

* **Build for Development**

  Compiles a build and deploy it to the assigned environment.

* **Submit for Approval**

  Makes the library available for an Approver to move it to the next step in the publishing process

* **Delete**

  Removes the library from the publishing process.

![](../.gitbook/assets/library-menu.png)

## Add to a library

1. Install the [extensions](../managing-resources/extensions.md) you want to add.
2. Create the [data elements](../managing-resources/data-elements.md) and rules you want to add.
3. Open the Publishing tab.
4. Select the [library](libraries.md) you want to change, then click Edit.
5. Use the rules, data elements, and extensions buttons to select the items you want to add to the library.
6. Click **Save**.

Changes to the library are shown in the Library Contents change log.

Note: Data elements can depend upon extensions. Rules can depend on both data elements and extensions. If you do not include all the necessary components in your library, the build will fail at build time and you'll need to add the necessary components before you complete a successful build. A future release will check dependencies when making changes to a library.

## Remove from a library

To remove something from a library, you must deactivate it and then publish the deactivated state.

1. Disable the extensions you want to remove, along with any data elements and rules that depend on those extensions.
2. Disable the data elements and rules you want to remove.
3. Open the **Publishing** tab.
4. Select the library you want to change.
5. Use the rules, data elements, and extensions buttons to select the disabled items you want to remove from the library.
6. Click **Save**.

## Manage library changes

1. Click on a library and select **Edit** to view library changes.  
   All changes are shown in the Library Contents list.

   ![](../.gitbook/assets/library-contents.jpg)

2. Click a change to view and select a revision.

   ![](../.gitbook/assets/library-contents-revision.jpg)

3. Select whether to show all items or changed items.
4. Click the revision and click **Select Revision**.
5. Click **Add a Change** or **Add All Changed Resources**.

## Active Library

Libraries encapsulate a set of changes you'd like to make to your deployed code. Active Library makes this easier, allowing you to rapidly iterate through changes and see the impact.

You can save new and existing extensions, rules, and data elements directly to the library on which you are working and immediately kick off a build. You can also create a new library from the **Active Library** drop down.

1. [Create a new library](libraries.md#create-a-library).
2. Go to [Rules](../managing-resources/rules.md), [Data Elements](../managing-resources/data-elements.md), or [Extensions](../managing-resources/extensions.md).
3. Select your Active Library.
4. Make your changes, then save and build the library.
5. Test your changes, and repeat these steps as needed.

