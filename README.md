# terraform-aag
# Deploy Azure Application Gateway to Azure

## Setup terraform in Azure Cloud Shell
1. Determine Terraform version in Azure Cloud Shell
```bash
terraform version
```
2. If not the latest version, copy URL for Linux AMD64 from [Terraform downloads page](https://www.terraform.io/downloads.html)
3. In Azure Cloud Shell download the latest version using curl  
```bash
curl -O <terraform_download_url>
```
4. Unzip the downloaded archive
```bash
unzip <terraform_zip_package_downloaded>
```
5. Create a directory named `bin`
```bash
mkdir bin
```
6. Move extracted `terraform` binary to `bin` folder
```bash
mv terraform bin/
```
7. Remove archive
```bash
rm <terraform_zip_package_downloaded>
```
8. Close and restart Cloud Shell
9. Verify that the downlaoded version of Terraform is first in the path
```bash
terraform version
```

## Deploy Terraform plan from repository
1. Create a directory to hold your projects and change to that directory
```bash
mkdir projects
cd projects
```
2. Clone your git repository containing Terraform code into the `project` directory
```bash
git clone <git_repository_url>
```
3. Change to directory holding clone repository
```bash
cd <git_repository_name>
```
4. Initialize Terraform project
```bash
terraform init
```
5. Create an execution plan
```bash
terraform plan -out main.tfplan
```
6. Apply execution plan
```bash
terraform apply main.tfplan
```
7. Destroy deployed plan
```bash
terraform plan -destroy -out main.destroy.tfplan
terraform apply main.destroy.tfplan
```
