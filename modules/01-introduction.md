# Lesson 1: Introduction to Terraform

Terraform is an Infrastructure as Code tool used to create, update, and manage infrastructure using code.

## Why Terraform?
- Repeatable
- Version controlled
- Less manual work
- Easier team collaboration

## Example
```hcl
resource "azurerm_resource_group" "demo" {
  name     = "rg-demo"
  location = "Central India"
}
```

## Commands
```bash
terraform init
terraform plan
terraform apply
```

## Key idea
Instead of clicking in a portal again and again, you write infrastructure once and reuse it.
