# Terraform Workshop

This workshop will help you learn Terraform and best practices around using the tool.

Work through the challenges in order. Ensure that you look at resources for each challenge as they include tips and useful resources on solving the challenge.

This workshop is modeled after a Microsoft OpenHack. The solution is not provided and it's expected that some exploration would take place as part of the learning process.

## Scenario

You are tasked with creating infrastructure for a simple website that will run as static website using Azure Storage.

This workshop will have you work with mainly the AzureRM Terraform provider, but will make sure of Hashicorp's Random Provider.

## Setup

This workshop utilizes includes a dev container for easily setting up dependencies needed.
In order to use the Dev Container please ensure that VSCode and Docker desktop are installed.

You will need access to an Azure subscription where you can deploy resources to.

## Challenges

- [Challenge 1 - Deploy Resource Group and Storage Account](./Challenge-1.md)
- [Challenge 2 - Configure Remote State](./Challenge-2.md)
- [Challenge 3 - Deploy Storage Account](./Challenge-3.md)
- [Challenge 4 - Add Tests](./Challenge-4.md)

## Resources

- [Terraform Provider for Azure (AzureRM) Documentation](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
-[Terraform on Azure](https://learn.microsoft.com/en-us/azure/developer/terraform/overview)
- [Terraform Random Provider](https://registry.terraform.io/providers/hashicorp/random/latest/docs)
- [VS Code Dev Container](https://code.visualstudio.com/docs/devcontainers/create-dev-container)