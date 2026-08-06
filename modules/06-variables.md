# Lesson 6: Variables

## What are Variables?
A variable is a placeholder that allows you to pass different values into your Terraform configuration without changing the code.

## Why use Variables?
Variables make Terraform code reusable, cleaner, and easier to maintain.

## Declaring a Variable
```hcl
variable "location" {
  description = "Azure region"
  type        = string
}
```

## Using a Variable
```hcl
location = var.location
```

## Supplying Values
### terraform.tfvars
```hcl
location = "Central India"
resource_group_name = "rg-demo"
```

### Command Line
```bash
terraform apply -var="location=East US"
```

### Environment Variables
```bash
export TF_VAR_location="Central India"
```

## Variable Types
- string
- number
- bool
- list(string)
- map(string)

## Default Values
```hcl
variable "location" {
  type    = string
  default = "Central India"
}
```

## Validation
```hcl
variable "environment" {
  type = string

  validation {
    condition     = contains(["dev", "test", "prod"], var.environment)
    error_message = "Environment must be dev, test, or prod."
  }
}
```

## Best Practices
- Keep declarations in variables.tf
- Put values in terraform.tfvars
- Avoid hardcoding
- Do not store secrets in tfvars
