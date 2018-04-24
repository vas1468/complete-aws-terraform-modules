# terragrunt-infra-modules-complete

This repo, along with the [terragrunt-infra-live-complete](https://github.com/vas1468/terragrunt-infra-live-complete), show a complete example of file/folder structure you can use with [Terragrunt](https://github.com/gruntwork-io/terragrunt) to keep your [Terraform](https://www.terraform.io) code DRY. For background information, check out the [Keep your Terraform code DRY](https://github.com/gruntwork-io/terragrunt#keep-your-terraform-code-dry) section of the Terragrunt documentation.

This repo contains the following modules:

* Modules will get listed here as they are added.

Note: This code is solely for training-demonstration purposes at this point. This is not production-ready code, so use at your own risk.


## Quick start!! How do you use these modules?

1. [Install Terraform](https://www.terraform.io/intro/getting-started/install.html).

To use a module, create a  `terraform.tfvars` file that specifies the module you want to use as well as values for the
input variables of that module:

```hcl
# Use Terragrunt to download the module code
terragrunt = {
  terraform {
    source = "git::git@github.com:vas1468/terragrunt-infra-modules-complete.git//path/to/module?ref=v0.0.1"
  }
}

# Fill in the variables for that module
foo = "bar"
baz = 3
```

(*Note: the double slash (`//`) in the `source` URL is intentional and required. It's part of Terraform's Git syntax 
for [module sources](https://www.terraform.io/docs/modules/sources.html).*)

You then run [Terragrunt](https://github.com/gruntwork-io/terragrunt), and it will download the source code specified 
in the `source` URL into a temporary folder, copy your `terraform.tfvars` file into that folder, and run your Terraform 
command in that folder: 

```
> terragrunt apply
[terragrunt] Reading Terragrunt config file at terraform.tfvars
[terragrunt] Downloading Terraform configurations from git::git@github.com:vas1468/terragrunt-infra-modules-complete.git//path/to/module?ref=v0.0.1
[terragrunt] Copying files from . into /tmp/terragrunt/infrastructure-modules/path/to/module
[terragrunt] Running command: terraform apply
[...]
```

Check out the [terragrunt-infra-live-complete repo](https://github.com/vas1468/terragrunt-infra-live-complete) for examples and the [Keep your Terraform code DRY documentation](https://github.com/gruntwork-io/terragrunt#keep-your-terraform-code-dry) for more info.



