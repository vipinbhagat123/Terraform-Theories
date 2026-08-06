# Lesson 8: Locals

## What are Locals?
Locals are named values that you define once and reuse multiple times within your Terraform configuration.

## Why Do We Need Locals?
Locals reduce repeated values and make naming conventions easier to manage.

## Using Locals
```hcl
locals {
  location = "Central India"
  rg_name  = "vipin-dev-rg"
}
```

## Use in Resources
```hcl
resource "azurerm_resource_group" "rg" {
  name     = local.rg_name
  location = local.location
}
```

## Locals Can Be Computed
```hcl
locals {
  resource_group_name = "rg-${var.environment}"
}
```

## Variables vs Locals vs Outputs
- Variables = input
- Locals = internal reusable value
- Outputs = result shown after deployment

## Best Practices
- Use locals for naming and reused expressions
- Use variables for user input
- Use outputs for useful deployment results
