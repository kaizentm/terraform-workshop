# Challenge 1 - Deploy Resource Group and Storage Account

- Start with ensuring you have all the needed dependencies. Either use the included Dev Container or install Terraform v.1.8.3
- Ensure you have the az cli and are logged in via `az login` to an subscription that you can deploy resources to.

## Task 0

Start with the basics to ensure that you have terraform and the az cli configured correctly.

Success Criteria:

- In the src folder, you'll find a getting started template for terraform. Take a look at the folder and investigate it's contents to familiaize yourself with basic Terraform blocks.
- Run this template to see the expected outputs.
  - `terraform init -reconfigure`
  - `terraform plan -out=plan.tfplan`
  - `terraform apply plan.tfplan`
- Ensure you are logged into the az cli via `az login`

## Task 1

This task is focused on deploying a resource group with the name `tf-demo-rg`
In the solution folder, you'll find a starting point with several .tf files. 

For this task, you will need to include the provider configuration in provider.tf, the resource group resource block in main.tf, input variables in variables.tf

Success Criteria:

- A resource group named `tf-demo-rg`  should be deployed to Azure in the `East US` region.
- Ensure that resource group name and location are sourced from a variables.tf file (not hardcoded).
- Set the resource group and location values from a terraform.tfvars file.
- Run Terraform init, plan and apply. Ensure that the plan is saved to a plan file.
- Extra Credit: Run terraform plan and override the resource group name via the command line.
  
## Task 2 - Random Names

This task will change the resource group name from a hard coded name to one that includes a random prefix. See the Random Resource Provider in the resources section.

Success Criteria:

- Modify provider.tf so that the random provider is loaded per the providers documentation.
  Note: after added a second provider you will need to run `terrraform init` again.
- Modify main.tf to include a random_string resource of size 4. It should only generate alpha numeric strings with no special characters. All characters should be lower case.
- Add an output to outputs.tf to display the name of the resource group. It should be called `resource_group_name`
- Run terraform plan/apply and note the value of the output variable.
- Ensure a resource group exists with the same name.

## Task 3 - Use locals

Local values in terraform allows a name to applied to expressions , increasing reusability. This case, we will introduce a new local variable called full_resoure_group_name, which includes the randomly generated prefix.

Success criteria:

- Move the name of the resource group with prefix to a local value in locals.tf. 
- Update the azurerm_resource_group block to use the local variable.
- Run Terraform plan again and notice no changes have been made!

## Task 4 - Clean up

Success Criteria:

- Remove the deployed resources by using a terraform command. Verify that the deleted resource name is what you expect before proceeding.
  
## Resources

- [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan)
- [azurerm_resource_group](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/resource_group)
- [Terraform Random Provider](https://registry.terraform.io/providers/hashicorp/random/latest/docs)
- [Terraform Outputs](https://developer.hashicorp.com/terraform/language/values/outputs)
- [Local Values](https://developer.hashicorp.com/terraform/language/values/locals)
- [Terraform Destroy](https://developer.hashicorp.com/terraform/cli/commands/destroy)