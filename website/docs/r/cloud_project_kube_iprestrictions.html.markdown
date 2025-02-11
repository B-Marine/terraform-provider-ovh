---
layout: "ovh"
page_title: "OVH: cloud_project_kube_iprestrictions"
sidebar_current: "docs-ovh-resource-cloud-project-kube-iprestrictions-x"
description: |-
  Apply IP restrictions to an OVHcloud Managed Kubernetes cluster.
---

# ovh_cloud_project_kube_iprestrictions

Apply IP restrictions to an OVHcloud Managed Kubernetes cluster.

## Example Usage

```hcl
resource "ovh_cloud_project_kube_iprestrictions" "vrack_only" {
  service_name = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
  kube_id      = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx"
  ips          = ["10.42.0.0/16"]
}
```

## Argument Reference

The following arguments are supported:

* `service_name` - (Optional) The id of the public cloud project. If omitted,
    the `OVH_CLOUD_PROJECT_SERVICE` environment variable is used.

* `kube_id` - The id of the managed Kubernetes cluster.

* `ips` - List of CIDR authorized to interact with the managed Kubernetes cluster.

## Attributes Reference

No additional attributes than the ones provided are exported.

## Import

OVHcloud Managed Kubernetes Service cluster IP restrictions can be imported using the `service_name` and the `id` of the cluster, separated by "/" E.g.,

```bash
$ terraform import ovh_cloud_project_kube_iprestrictions.iprestrictions service_name/kube_id
```
