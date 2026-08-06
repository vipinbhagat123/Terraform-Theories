# Lesson 7: Outputs

## What are Outputs?
An output is a value that Terraform displays after creating or updating your infrastructure.

## Why do we need Outputs?
Outputs help you see useful values like IDs, names, and IP addresses without searching in the Azure Portal.

## Creating an Output
```hcl
output "resource_group_name" {
  value = azurerm_resource_group.demo.name
}
```

## Another Example
```hcl
output "resource_group_id" {
  value = azurerm_resource_group.demo.id
}
```

## Sensitive Outputs
```hcl
output "connection_string" {
  value     = azurerm_storage_account.demo.primary_connection_string
  sensitive = true
}
```

## terraform output
```bash
terraform output
terraform output resource_group_name
```

## Best Practices
- Keep outputs in outputs.tf
- Output only useful values
- Mark secrets as sensitive
