# GitHub Action for Terraform deployments

GitHub Action to deploy infrastructure using Terraform.

Features:
* Allows change of working directory
* Terraform Validation
* Supports `-backend-config` arg in `terraform init`
* Supports `-var-file` arg in `terraform apply`

## GitHub Action

You can use the terraform GitHub Action by adding the below to your workflow:
```yaml
- name: Deploy infrastructure
  uses: ellogroup/terraform-action@v1
  with:
    working-directory: infrastructure
    workspace: dev
    backend-config-arg: -backend-config=.env/dev.hcl -backend-config="key=dev/dev_terraform.tfstate"
    var-file-arg: -var-file=.env/dev.tfvars
  env:
    TF_VAR_example: value
```
