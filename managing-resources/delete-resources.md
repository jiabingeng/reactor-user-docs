# Delete Resources

To delete a resoucrce, select the resource and click **Delete**.

## Prepare a resource for deletion

**Important**: Before you delete a resource, verify that it is in a state where it can be deleted.

Resources exist in different states, and they depend on one another. In some cases, you must resolve conflicts before you can delete a resource. In other cases, although you can delete the resource, you have to update the other resources that are dependent on this resource.

For example:

* Deleting a data element affects the behavior of any rules that reference the data element.
* Deleting an extension affects any data elements and any rules that include components provided by the extension.

## Update dependent resources

If you want to delete an extension or a data element, you must update dependent resources. You can do this before or after you delete.

### Update dependent resources for an extension

Modify any rules that use components provided by the extension. Any data elements provided by the extension will be broken.

### Update dependent resources for a data element

1. Update any rule components that reference the data element.
2. Modify any extension configurations that reference the data element.

## Delete a resource that was published in Prod

1. Disable the resource.
2. Publish that change through to **Prod**.
3. Click **Delete**.

## Delete a resource from a library in Dev

1. Remove the resource from the library.
2. Click **Delete**.

## Delete a resource from a library in Stage

1. Reject the library to move it back to **Dev**.
2. Remove the resource from the library.
3. Click **Delete**.

