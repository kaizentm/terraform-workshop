# Challenge 2 - Remote State

## Task 1 - Deploy Storage Account

Using the az cli deploy a storage account that will be used to hold remote state. Note this can be done via terraform with the state imported in, but it is an advanced scenario and will be part of extra credit.

Success Criteria:

- Deploy a storage account using the az cli to hold remote state files.
- The file scripts/deploy-state-storage.sh has been provided for your convenience.
- Note the values in the console output.
  
## Task 2 - Remote State Configuration

This task requires that you modify the provider block in providers tf to use remote state.

Success Criteria:

- Modify providers.tf so that a backend attribute exists and set to azurerm.
  Note: It should be an empty block without values.
- Add a new file called backend.tfvars and set the correct values based on azurerm documentation and using the state resource names created in task1.
- If you have a file named `terraform.tfstate` delete the local file and re-run `terraform init -reconfigure`. Note you should pass the path to backend.tfvars. If you are prompted for a container name, then you are not using the backend.tfvars file. You should not be prompted for any values.
- Deploy the resource group again via plan/apply.
- Note there is no local state file.
- Examine the state storage account and specifically look at the blob container for state.

## Resources

- [Store Terraform state in Azure Storage](https://learn.microsoft.com/en-us/azure/developer/terraform/store-state-in-azure-storage?tabs=azure-cli)
- [Terraform Backend Configuration](https://developer.hashicorp.com/terraform/language/settings/backends/configuration)
- [AzureRM backend](https://developer.hashicorp.com/terraform/language/settings/backends/azurerm)