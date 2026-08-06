# Lesson 10: Expressions and Functions

## What are Expressions?
An expression is anything Terraform evaluates to produce a value.

## String Interpolation
```hcl
locals {
  rg_name = "rg-${var.environment}"
}
```

## Built-in Functions
- upper()
- lower()
- length()
- join()
- split()
- contains()
- lookup()
- coalesce()

## Example Functions
```hcl
upper("terraform")
lower("AZURE")
length(["dev", "test", "prod"])
join("-", ["web", "dev", "01"])
contains(["dev", "test", "prod"], "dev")
```

## Conditional Expressions
```hcl
condition ? true_value : false_value
```

## Real Azure Example
```hcl
locals {
  storage_name = lower("${var.project_name}${var.environment}storage")
}
```

## Best Practices
- Use functions to avoid hardcoding values
- Keep complex expressions in locals
- Use conditionals instead of duplicated code
