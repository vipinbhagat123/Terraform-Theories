# Lesson 2: Installation and Project Structure

## Typical Terraform project structure
```text
terraform-project/
├── main.tf
├── providers.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
└── terraform.tfstate
```

## Common commands
- `terraform init`
- `terraform validate`
- `terraform plan`
- `terraform apply`
- `terraform destroy`

## Important note
Terraform loads all `.tf` files in a directory, so filenames are for organization, not strict requirement.
