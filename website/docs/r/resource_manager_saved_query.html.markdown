---
subcategory: "Resource Manager"
layout: "alicloud"
page_title: "Alicloud: alicloud_resource_manager_saved_query"
description: |-
  Provides a Alicloud Resource Manager Saved Query resource.
---

# alicloud_resource_manager_saved_query

Provides a Resource Manager Saved Query resource. Saved Query Requests.

For information about Resource Manager Saved Query and how to use it, see [What is Saved Query](https://www.alibabacloud.com/help/zh/resource-management/developer-reference/api-resourcecenter-2022-12-01-createsavedquery).

-> **NOTE:** Available since v1.212.0.

## Example Usage

Basic Usage

```terraform
variable "name" {
  default = "terraform-example"
}

provider "alicloud" {
  region = "cn-hangzhou"
}

resource "alicloud_resource_manager_saved_query" "default" {
  description      = var.name
  expression       = "select * from resources limit 1;"
  saved_query_name = var.name

}
```

## Argument Reference

The following arguments are supported:
* `description` - (Optional) Query Description.
* `expression` - (Required) Query Expression.
* `saved_query_name` - (Required) The name of the resource.

## Attributes Reference

The following attributes are exported:
* `id` - The ID of the resource supplied above.
* `create_time` - The creation time of the resource.

## Timeouts

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/docs/configuration-0-11/resources.html#timeouts) for certain actions:
* `create` - (Defaults to 5 mins) Used when create the Saved Query.
* `delete` - (Defaults to 5 mins) Used when delete the Saved Query.
* `update` - (Defaults to 5 mins) Used when update the Saved Query.

## Import

Resource Manager Saved Query can be imported using the id, e.g.

```shell
$ terraform import alicloud_resource_manager_saved_query.example <id>
```