# Module 3 – Lesson 15: Dynamic Blocks

## What are Dynamic Blocks?
Dynamic blocks let you generate repeated nested blocks inside a resource automatically.

They are useful when a resource has a nested block that may need to appear multiple times.

## Why use them?
- Avoid repeating the same nested block many times
- Make configurations cleaner
- Handle variable-length nested settings

## Syntax
```hcl
resource "..." "..." {
  dynamic "block_name" {
    for_each = ...
    content {
      # nested block arguments
    }
  }
}
```

## Example
```hcl
variable "security_rules" {
  default = [
    {
      name = "ssh"
      port = 22
    },
    {
      name = "http"
      port = 80
    }
  ]
}

resource "example" "demo" {
  dynamic "rule" {
    for_each = var.security_rules
    content {
      name = rule.value.name
      port = rule.value.port
    }
  }
}
```

## Real-world Azure use cases
- Network Security Group rules
- Application Gateway listeners
- Storage network rules
- Multiple IP configurations

## Important note
Dynamic blocks are for nested blocks only. Do not use them to create top-level resources.

## Best practices
- Keep dynamic blocks simple
- Use locals to prepare complex data before the block
- Use them only when repetition is actually needed

## Interview questions
1. What is a dynamic block?
2. When should you use it?
3. Is it used for top-level resources or nested blocks?
