# Sample repo for Null Provider

See [this page](https://registry.terraform.io/providers/hashicorp/null/latest/docs) for the reference


# Prerequisite

Install and configure Terraform as per [official documentation](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

# How To

## Clone the repository

```
git clone https://github.com/dmitryuchuvatov/null-provider.git
```

## Go into the directory

```
cd null-provider
```

## Initialize Terraform

```
terraform init
```

You should see the following output:

```
Initializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/null...
- Installing hashicorp/null v3.2.1...
- Installed hashicorp/null v3.2.1 (signed by HashiCorp)

Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

## Run Terraform Apply

```
terraform apply
```
Enter **yes** and hit **Enter** to apply the changes:

```
Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following
symbols:
  + create

Terraform will perform the following actions:

  # null_resource.null will be created
  + resource "null_resource" "null" {
      + id = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

null_resource.null: Creating...
null_resource.null: Provisioning with 'local-exec'...
null_resource.null (local-exec): Executing: ["/bin/sh" "-c" "echo 'Hello World'"]
null_resource.null (local-exec): Hello World
null_resource.null: Creation complete after 0s [id=8174626668123780454]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```
## Clean Up

```
terraform destroy
```
Enter **yes** and hit **Enter** to destroy the resources:

```
null_resource.null: Refreshing state... [id=8174626668123780454]

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following
symbols:
  - destroy

Terraform will perform the following actions:

  # null_resource.null will be destroyed
  - resource "null_resource" "null" {
      - id = "8174626668123780454" -> null
    }

Plan: 0 to add, 0 to change, 1 to destroy.

Do you really want to destroy all resources?
  Terraform will destroy all your managed infrastructure, as shown above.
  There is no undo. Only 'yes' will be accepted to confirm.

  Enter a value: yes

null_resource.null: Destroying... [id=8174626668123780454]
null_resource.null: Destruction complete after 0s

Destroy complete! Resources: 1 destroyed.
```


