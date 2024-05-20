# Challenge 3 - Storage Account


## Task 1 - Deploy a Storage Account

Success Criteria:

- Add a resource block to main.tf to deploy a storage account to hold our static website. Note it should be in the resource group defined in previous challenges.
- Storage account name should be in a local value with the same random prefix as the resource group, followed by storage. For example if the random value is `abcd` the resource group name should be `abcdstorage` (Note storage account names should be all lowercase and include no special characters or dashes!)
- Add an output to show the value of the randomly generated storage account name
- Deploy the storage via plan and apply.
  Note for this task, you only need to deploy the storage account. Not any containers in the account.
  
## Task 2 - Static Website configuration

Success Criteria:

- Add a static_website block to the azurerm_storage_account resource.
- Re-run plan and apply.
- Browse to the storage account in azure and verify that a container called $web exists.

## Task 3 - Add a index.html as a blob

Success Criteria:

- In main.tf add another resource block for azurerm_storage_blob and ensure that it is in the storage account we have created.
- Ensure the content type is set to `"text/html"`
- The blob should be named index.html and it's source is `web/index.html`
- Add an output to show the static website url . Note the storage account property for the static website url is `primary_blob_internet_host `
- Re-run plan/apply.
  
## Task 4 - Move to module

Terraform modules are a great way to organize and reuse terraform configurations. In this task we will move the storage account to it's own module under the modules folder for better reuse.

Success Criteria:

- Create a folder under the modules folder called storage_account
- Add the following empty files to the storage_account folder (main.tf, variables.tf, outputs.tf)
- Move the two storage account resource blocks to storage_account/main.tf
- Add variables for resource_group_name, location and storage_account_name to storage_accounts/variables.tf.
- Add outputs to storage_accounts/outputs.tf 
- Modify the root folders main.tf to reference the newly module instead of the azurerm_storage_account resource block.
- Modify the root folders output to reference the module outputs.
- Re-run the terraform init command (with backend)
- Run plan/apply

## Task 5 - Add a second module instance!

Now that we have a reusable module, we can easily create a second website using the same configuration code!

Success Criteria:

- In the root main.tf, add a second utilization of our storage account module.
- Ensure you create a new local value name for the second storage account.
- Update the outputs to show the urls for both storage accounts.
- Update the second module utilization to point to index2.html instead of index.html
- Re-run the terraform init command (with backend)
- Run plan/apply

## Resources

- [Store Terraform state in Azure Storage](https://learn.microsoft.com/en-us/azure/developer/terraform/store-state-in-azure-storage?tabs=azure-cli)
- [Terraform Backend Configuration](https://developer.hashicorp.com/terraform/language/settings/backends/configuration)
- [AzureRM backend](https://developer.hashicorp.com/terraform/language/settings/backends/azurerm)
- [AzureRM Storage Blob](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/storage_blob)
- [Terraform Modules](https://developer.hashicorp.com/terraform/language/modules)