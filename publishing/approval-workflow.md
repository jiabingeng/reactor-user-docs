# Approval Workflow

**Tip**: The available actions depend on the state of the library and your permission levels.

## Permissions

The following levels of permission are important for the approval workflow:

* **The develop right:** Includes the ability to create libraries, build for development, and submit for approval.
* **The approve right:** Includes the ability to build for staging and approve.
* **The publish right:** Includes the ability to publish an approved library.

The rights are not inclusive. To complete the workflow, you must be granted all three rights in a property.

## Library state

A library can be in one of the following states:

* [Development](approval-workflow.md#development)
* [Submitted](approval-workflow.md#submitted)
* [Approved](approval-workflow.md#approved)
* [Published](approval-workflow.md#published)

![](../.gitbook/assets/library-state.png)

Specific actions must be taken to move a library between these states, and these states are represented as columns in the **Publishing** tab.

### Development

Libraries are created in Development, and any changes to a library must be made while the library is in Development. The library is submitted after development and testing are completed.

Available actions for a library in Development state are:

* **Edit**

  In the library Edit page, you can add or remove components from a library.

* **Build for Development**

  Create a build for the library. The build is compiled and deployed to the environment to which the library is assigned.   
  
  **Important**: If the library has not been assigned to an environment, this step will fail.   

* **Submit for Approval**

  Unassigns the library from its development environment and moves the library to the submitted column for an Approver to edit or update.

### Submitted

An Approver tests the library in a staging environment. After testing is completed, the library is approved or rejected. Rejected builds return to Development so changes can be made, and the approval flow starts again.

Available actions for a library in Submitted state are:

* **Open**

  You can view the contents of the library, but changes are not allowed. If changes are needed, reject the library. This way, the library returns to Development, which allows you to make the necessary changes. 

* **Build for Staging**

  Assigns the library to the staging environment and deploys the library.

* **Approve for Publishing**

  Moves the library to the **Approved** column, so that the Publisher can publish it. 

* **Reject**

  Unassigns the library from the staging environment and moves the library to the **Development** column for changes.

### Approved

The library is waiting to be published. A Publisher can publish or reject the library. Rejected builds return to Development so that changes can be made, and the approval flow begins again.

Available actions for a library in Approved state are:

* **Open**

  View the contents of the library, but canges are not allowed. If changes are required, the library should be rejected so changes can be made in Development.

* **Build and Publish to Production**

  Unassigns the library from the staging environment, assigns the library to the production environment, and deploys it.

  **Important**: When this option is selected, your library becomes live in your production environment, so be sure before you click the button.

* **Reject**

  Unassigns the library from the staging environment and moves the library to the **Development** column for changes.

### Published

The library is live in the production environment. This column shows which libraries have been published and their publish dates. You can look at these libraries, but you cannot make changes. To make changes in your production environment, create a new library and push it through the approval process.

