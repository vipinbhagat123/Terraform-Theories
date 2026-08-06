# Lesson 9: Data Sources

## What is a Data Source?
A data source allows Terraform to read information about an existing resource instead of creating a new one.

## Resource vs Data Source
- Resource = create/manage something
- Data Source = read something that already exists

## Example
```hcl
data "azurerm_resource_group" "rg" {
  name = "production-rg"
}
```

## Using Data Source Values
```hcl
data.azurerm_resource_group.rg.name
```

## Real Azure Example
```hcl
data "azurerm_resource_group" "rg" {
  name = "production-rg"
}

resource "azurerm_storage_account" "storage" {
  name                = "vipinstorage123"
  location            = data.azurerm_resource_group.rg.location
  resource_group_name = data.azurerm_resource_group.rg.name
  account_tier        = "Standard"
  account_replication_type = "LRS"
}
```

## Best Practices
- Use resource when Terraform should create infrastructure
- Use data when infrastructure already exists
- Avoid duplicate shared resources
