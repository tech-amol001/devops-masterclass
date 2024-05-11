# Terraform Resources

## Overview

- Each resource block describes one or more infrastructure objects, such as virtual networks, compute instances, or higher-level components such as DNS records.

## Syntax

```
resource "resource _type" "resource_label" {
  argument = expression
  argument = expression
}
```

## Examples

In this example, we are creating EC2 Instance

```
resource "aws_instance" "linux_server" {
  ami                    = "ami-12456335335"
  instance_type          = "t2.micro"
  key_name               = "key_pair_name"
  tags = {
    Name = "Lab-WebServer"
    Environment   = "Production"
  }
}
```

## [References](https://developer.hashicorp.com/terraform/language/resources)
