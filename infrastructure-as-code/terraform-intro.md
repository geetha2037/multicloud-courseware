# Terraform Introduction

* A tool for building, changing, and versioning infrastructure
* Almost any infrastructure type can be represented as a resource
* Cloud-specific provider is responsible for understanding API interactions and exposing resources
* Configuration files describe the components needed, for an application or for an entire data centre
* Execution plan describes what to is the desired state, not how to reach it
* Sample VM template for different cloud providers:

```text
# Aws
resource "aws_instance" "web-server" {
  ami           = "ami-0dacb0c129b49f529" <-- AWS AMI ID
  instance_type = "t2.micro" <-- Instance type
}
```

```text
# Azure
resource "azurerm_virtual_machine" "web-server" {
  name                  = "web-server"
  location              = "Central US"
  resource_group_name   = "online-store-resource-group"
  vm_size               = "Standard_DS1_v2"
}
```

```text
# GCP
resource "google_compute_instance" "web-server" {
  name         = "web-server"
  machine_type = "n1-standard-1"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }
}
```

