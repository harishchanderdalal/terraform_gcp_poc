# terraform_gcp_poc
POC of terraform which create VPC Subnet LB Autoscaling with Webserver
# Terraform GCP POC
## Harish Chander Editor, +91 8529142143

Terraform POC which Helps You to create below components:- 
- New VPC with CIDR
- Autoscaling Group with Webserver
- Traffic Handle By LoadBalancer

## Prerequisite
1 - Google Cloud Account - GCP
2 - Service Account to Access from Remote ( API )
3 - Terraform will be in HOST MACHINE

## Install Google CLI
```
curl https://sdk.cloud.google.com | bash
gcloud init
```
## How to install Terraform - macOS

```
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
terraform -version
```


## Update below file terraform.tfvars
```
# Application Definition
app_name        = "timpoc" #do NOT enter any spaces
app_environment = "tim" # 
app_domain      = "timcloud.com"
app_project     = "PROJECT NAME FROM THE GCP XXXXXXXXXX"
app_node_count  = 1

# GCP Settings
gcp_region_1  = "asia-south1"
gcp_zone_1    = "asia-south1-a"
gcp_auth_file = "SERVICE FILE YOU DOWNLOAD FROM.json"

# GCP Netwok
private_subnet_cidr_1  = "10.10.0.0/16"
```
# NOTE:- keep the service.json file in git clone folder

 CMD to RUN :- 
```sh
git clone https://github.com/harishchanderdalal/terraform_gcp_poc.git
cd terraform_gcp_poc
terraform init
terraform plan -var-file="terraform.tfvars"
terraform apply -var-file="terraform.tfvars"
```

- ✨Magic ✨
