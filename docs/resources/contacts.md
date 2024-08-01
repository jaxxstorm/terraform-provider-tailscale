---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tailscale_contacts Resource - terraform-provider-tailscale"
subcategory: ""
description: |-
  The contacts resource allows you to configure contact details for your Tailscale network. See https://tailscale.com/kb/1224/contact-preferences for more information.
  Destroying this resource does not unset or modify values in the tailscale control plane, and simply removes the resource from Terraform state.
---

# tailscale_contacts (Resource)

The contacts resource allows you to configure contact details for your Tailscale network. See https://tailscale.com/kb/1224/contact-preferences for more information.

Destroying this resource does not unset or modify values in the tailscale control plane, and simply removes the resource from Terraform state.

## Example Usage

```terraform
resource "tailscale_contacts" "sample_contacts" {
  account {
    email = "account@example.com"
  }

  support {
    email = "support@example.com"
  }

  security {
    email = "security@example.com"
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `account` (Block Set, Min: 1, Max: 1) Configuration for communications about important changes to your tailnet (see [below for nested schema](#nestedblock--account))
- `security` (Block Set, Min: 1, Max: 1) Configuration for communications about security issues affecting your tailnet (see [below for nested schema](#nestedblock--security))
- `support` (Block Set, Min: 1, Max: 1) Configuration for communications about misconfigurations in your tailnet (see [below for nested schema](#nestedblock--support))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--account"></a>
### Nested Schema for `account`

Required:

- `email` (String) Email address to send communications to


<a id="nestedblock--security"></a>
### Nested Schema for `security`

Required:

- `email` (String) Email address to send communications to


<a id="nestedblock--support"></a>
### Nested Schema for `support`

Required:

- `email` (String) Email address to send communications to

## Import

Import is supported using the following syntax:

```shell
# ID doesn't matter.
terraform import tailscale_contacts.sample_contacts contacts
```