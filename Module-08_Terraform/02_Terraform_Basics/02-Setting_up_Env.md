# Setting-up environment for Terraform

## Section-01: Install Terraform CLI

1.  Windows

    - [Download Terraform Binary](https://www.terraform.io/downloads.html)
    - Unzip the package
    - Create new folder 'tf-binary' somewhere in 'C' drive
    - Copy the terraform.exe to a 'tf-binary' directory
    - Set the PATH from system's Environment variables section to 'tf-binary' directory path

2.  Linux
    - [Download Terraform Binary](https://www.terraform.io/downloads.html)
    - [Install Terraform on Linux Distributions](https://learn.hashicorp.com/tutorials/terraform/install-cli)

```
# Install yum-config-manager to manage your repositories.
sudo yum install -y yum-utils

# Use yum-config-manager to add the official HashiCorp Linux repo
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo

# Install terraform
sudo yum -y install terraform

# After the TF installation, check the installed version of TF
terraform --version
```

## Section-02: Install AWS CLI

- Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)

- Create a new IAM User with programmatic access and download the keys for configuring AWS CLI

- Now, go to your local system >> Command Prompt >> `aws configure` >> Enter Access Key, Secret Key, Default Region (us-west-1) and Output format (json/yaml)

## Section-03: Download and Install Editor (Visual Studio Code)

- For downloading the latest version of the VS Code editor, [click here >>](https://code.visualstudio.com/download)

- After successful installation, open VS Code editor >> go to 'Extensions' section and install below two extensions:
  1. Terraform
  2. Prettier - Code Formatter

## Section-04: Download and Install Git (VCS)

- For downloading the latest version of the Git, [click here >>](https://git-scm.com/downloads)
