# terraform-dlm-snapshot
Leverage AWS Data Lifecycle Manager to take EC2 snapshots. This code will look for a `target_tag` value on your EC2 instances to identify those 
in need of snapshotting. By default this will be the key `Snapshot` with a string value of `true`.

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0.1 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | ~> 4.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | ~> 4.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_dlm_lifecycle_policy.dlm_daily_snapshots](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/dlm_lifecycle_policy) | resource |
| [aws_iam_role.dlm_lifecycle_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role_policy_attachment.dlm_lifecycle_policy_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_caller_identity.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |
| [aws_iam_policy_document.dlm_lifecycle_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_environment"></a> [environment](#input\_environment) | Environment name, EG. Development | `any` | n/a | yes |
| <a name="input_service"></a> [service](#input\_service) | Name of service to use this module. EG. SuperCaliFragiListic | `any` | n/a | yes |
| <a name="input_state"></a> [state](#input\_state) | State for the DLM policy. Valid values are `ENABLED` and `DISABLED` | `string` | `"ENABLED"` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | Map of tags to apply | `map(any)` | n/a | yes |
| <a name="input_target_tags"></a> [target\_tags](#input\_target\_tags) | Map of tags to look for in order to create a snapshot | `map` | <pre>{<br>  "Snapshot": "true"<br>}</pre> | no |

## Outputs

No outputs.
<!-- END_TF_DOCS -->
