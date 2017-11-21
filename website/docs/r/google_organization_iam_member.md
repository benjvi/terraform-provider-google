---
layout: "google"
page_title: "Google: google_organization_iam_member"
sidebar_current: "docs-google-organization-iam-member"
description: |-
 Allows management of a single member for a single binding on the IAM policy for a Google Cloud Platform Organization.
---

# google\_organization\_iam\_member

Allows creation and management of a single member for a single binding within
the IAM policy for an existing Google Cloud Platform Organization.

~> **Note:** This resource __must not__ be used in conjunction with
   `google_organization_iam_binding` for the __same role__ or they will fight over
   what your policy should be.

## Example Usage

```hcl
resource "google_organization_iam_member" "binding" {
  org_id = "0123456789"
  role    = "roles/editor"
  member  = "user:jane@example.com"
}
```

## Argument Reference

The following arguments are supported:

* `org_id` - (Required) The numeric ID of the organization in which you want to create a custom role.

* `role` - (Required) The role that should be applied.

* `member` - (Required) The user that the role should apply to.
    
## Attributes Reference

In addition to the arguments listed above, the following computed attributes are
exported:

* `etag` - (Computed) The etag of the organization's IAM policy.