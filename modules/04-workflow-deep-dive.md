# Lesson 4: Terraform Workflow Deep Dive

## Workflow
```text
terraform init
terraform validate
terraform plan
terraform apply
terraform destroy
```

## What each command does
- `init` downloads providers and initializes the project
- `validate` checks syntax
- `plan` previews changes
- `apply` creates or updates infrastructure
- `destroy` deletes managed infrastructure

## Important concept
Terraform is idempotent, so running `apply` again without changes should not recreate everything.
