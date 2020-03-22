# S3 Terraform Module

This module was created to keep the S3 bucket creation as simples as it is.

# Providers

| Name | Version |
|------|---------|
| aws | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| block\_public\_acls | Whether Amazon S3 should block public ACLs for this bucket | `bool` | `false` | no |
| block\_public\_policy | Whether Amazon S3 should block public bucket policies for this bucket | `bool` | `false` | no |
| ignore\_public\_acls | Whether Amazon S3 should ignore public ACLs for this bucket | `bool` | `false` | no |
| is\_versioned | This variable when set to `true` enabled versioning feature on S3 | `bool` | `false` | no |
| name | Name that will be used by this given bucket | `string` | n/a | yes |
| restrict\_public\_buckets | Whether Amazon S3 should restrict public bucket policies for this bucket | `bool` | `false` | no |

## Outputs

No output.


## Usage Example

Most single usage 
```
module "my_new_bucket"{
    source = "git::git@github.com:CovidZero/terraform-modules.git//aws/s3?ref=v0.0.1"

    name = "my-bucket"
}
```

```
module "my_new_bucket"{
    source = "git::git@github.com:CovidZero/terraform-modules.git//aws/s3?ref=v0.0.1"

    name               = "my-bucket"
    versioning_enabled = true

    block_public_acls       = true
    block_public_policy     = true
    ignore_public_acls      = true
    restrict_public_buckets = true
}
```
