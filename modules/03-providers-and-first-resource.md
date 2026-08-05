# Lesson 3: Providers and Your First Azure Resource

## What is a provider?
A provider is a plugin that lets Terraform talk to a platform like Azure.

## Azure provider example
```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 4.0"
    }
  }
}

provider "azurerm" {
  features {}
}
```

## First Azure resource group
```hcl
resource "azurerm_resource_group" "demo" {
  name     = "rg-demo"
  location = "Central India"
}
```

## Best practice
Reference resources using Terraform expressions instead of hardcoding values.
