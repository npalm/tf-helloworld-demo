# Terraform Hello World demo

## Introduction
This repo contains terraform scripts to demo Terraform. It creates a EC2 Instance, Security Group and add a simple web application to the EC2 instance.
The tool tfenv is used to fix the terraform version, see .terraform-version
for the currect version.

## Setup
To run the terraform scripts you need to have AWS keys. The easiest way is to provide them to docker via a file containing the keys as key value pair.
Example file:
```
AWS_ACCESS_KEY_ID=...
AWS_SECRET_ACCESS_KEY=...
```

## Terraform commands
Terraform commands to manage the ECS cluster

### Initialize
Update `terraform.tfvars` and generate key files using `init.sh`.
```
docker run -it --env-file <AWS_KEYS_FILE>  -v $(pwd):/data -w /data \
  hashicorp/terraform:0.10.4 init
```

### Plan
```
docker run -it --env-file <AWS_KEYS_FILE>  -v $(pwd):/data -w /data \
  hashicorp/terraform:0.10.4 plan
```

### Apply
```
docker run -it --env-file <AWS_KEYS_FILE>  -v $(pwd):/data -w /data \
  hashicorp/terraform:0.10.4 apply
```

### Destroy
```
docker run -it --env-file <AWS_KEYS_FILE>  -v $(pwd):/data -w /data \
  hashicorp/terraform:0.10.4 destroy
```
