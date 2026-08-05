# Lesson 5: Terraform State

## What is Terraform state?
Terraform state is the file that stores what Terraform already manages.

## File
```text
terraform.tfstate
```

## Why it matters
Terraform uses state to:
- track resources
- detect drift
- compare desired vs current infrastructure
- know what to update or destroy

## Local vs remote state
- Local state: okay for learning
- Remote state: best for teams and production

## Key warning
Do not commit state files to Git for production projects.
