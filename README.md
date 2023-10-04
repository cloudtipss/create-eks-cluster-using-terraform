## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 5.19.0 |
| <a name="provider_random"></a> [random](#provider\_random) | 3.5.1 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_eks"></a> [eks](#module\_eks) | terraform-aws-modules/eks/aws | 19.16.0 |
| <a name="module_irsa-ebs-csi"></a> [irsa-ebs-csi](#module\_irsa-ebs-csi) | terraform-aws-modules/iam/aws//modules/iam-assumable-role-with-oidc | 4.7.0 |
| <a name="module_vpc"></a> [vpc](#module\_vpc) | terraform-aws-modules/vpc/aws | 5.1.2 |

## Resources

| Name | Type |
|------|------|
| [aws_eks_addon.ebs-csi](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eks_addon) | resource |
| [random_string.suffix](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/string) | resource |
| [aws_iam_policy.ebs_csi_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_ami_type"></a> [ami\_type](#input\_ami\_type) | Ami Type for Ec2 instances created in Cluster | `string` | `"AL2_x86_64"` | no |
| <a name="input_aws_availability_zones"></a> [aws\_availability\_zones](#input\_aws\_availability\_zones) | AWS availability zones | `list` | <pre>[<br>  "us-east-1a",<br>  "us-east-1b",<br>  "us-east-1c"<br>]</pre> | no |
| <a name="input_aws_profile"></a> [aws\_profile](#input\_aws\_profile) | Set this variable if you use another profile besides the default awscli profile called 'default'. | `string` | `"default"` | no |
| <a name="input_aws_region"></a> [aws\_region](#input\_aws\_region) | Set this variable if you use another aws region. | `string` | `"us-east-1"` | no |
| <a name="input_cidr"></a> [cidr](#input\_cidr) | Cird block for your VPC | `string` | `"10.0.0.0/16"` | no |
| <a name="input_cluster_version"></a> [cluster\_version](#input\_cluster\_version) | kubernetes cluster version | `string` | `"1.27"` | no |
| <a name="input_env"></a> [env](#input\_env) | it would be a prefix for you cluster name created, typically specified as dev or test | `string` | `"dev"` | no |
| <a name="input_private_subnets"></a> [private\_subnets](#input\_private\_subnets) | private subnets to create, need to have 1 for each AZ | `list` | <pre>[<br>  "10.0.1.0/24",<br>  "10.0.2.0/24",<br>  "10.0.3.0/24"<br>]</pre> | no |
| <a name="input_public_subnets"></a> [public\_subnets](#input\_public\_subnets) | public subnets to create, need to have 1 for each AZ | `list` | <pre>[<br>  "10.0.4.0/24",<br>  "10.0.5.0/24",<br>  "10.0.6.0/24"<br>]</pre> | no |
| <a name="input_vpc_name"></a> [vpc\_name](#input\_vpc\_name) | Vpc name that would be created for your cluster | `string` | `"EKS_vpc"` | no |

## Outputs

No outputs.
