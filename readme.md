# Terraform Workshop

This Terraform project creates a basic infrastructure on AWS that includes a VPC, public subnet, internet gateway, route table, security group, and two EC2 instances with a Cloud-Init configuration.

## Project Structure

- `main.tf`: Defines AWS resources such as VPC, subnet, internet gateway, route table, security group, and EC2 instances.
- `variables.tf`: Defines the variables used in the project.
- `provider.tf`: Configures the AWS provider.
- `scripts/add-ssh-web-app.yaml`: Cloud-Init script to configure the EC2 instances.

## Requirements

- [Terraform](https://www.terraform.io/downloads.html) >= 1.2.0
- Configured AWS credentials

## Usage

1. Clone this repository:

    ```sh
    git clone https://github.com/ronaldorodriguezbermudez/terraform-workshop.git
    cd terraform-workshop
    ```

2. Generate the SSH key pair:

    ```sh
    ssh-keygen -t rsa -C "terraform-cs@test.com" -f ./tf-cloud-init
    ```

3. Replace the content of `ssh_authorized_keys` in the `add-ssh-web-app.yaml` file with the content of `tf-cloud-init.pub`:


4. Initialize the Terraform project:

    ```sh
    terraform init
    ```

5. Review the execution plan:

    ```sh
    terraform plan
    ```

6. Apply the Terraform plan:

    ```sh
    terraform apply
    ```

7. Once completed, you will get the public IP addresses of the EC2 instances:

    ```sh
    terraform output public_ip
    ```

## Cleanup

To destroy the resources created by Terraform, run:

```sh
terraform destroy
```

## Acknowledgements

This project was created using the [terraform-workshop](https://github.com/falconcr/terraform-workshop) repository as a guide.