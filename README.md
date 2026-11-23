# Terraform Docker Provisioner 🏗️

A DevOps project demonstrating **Infrastructure as Code (IaC)** using HashiCorp Terraform to provision local Docker containers.

## 🎯 Project Overview
This project uses Terraform to declaratively manage an Nginx web server running in a Docker container. It demonstrates the core Terraform lifecycle (`init`, `plan`, `apply`, `destroy`) without requiring cloud infrastructure costs.

## 🛠️ Tech Stack
*   **Terraform** (Infrastructure as Code)
*   **Docker** (Containerization)
*   **Nginx** (Web Server)

## 🚀 How It Works
The `main.tf` file defines two resources:
1.  **`docker_image`**: Pulls the latest Nginx image from Docker Hub.
2.  **`docker_container`**: Spins up the container, mapping local port `8080` to container port `80`.

## ⚙️ Commands Used
1.  `terraform init` - Initializes the working directory and downloads the Docker provider.
2.  `terraform plan` - Generates a preview of the resources to be created.
3.  `terraform apply` - Provisions the Nginx container.
4.  `terraform destroy` - Tears down the infrastructure safely.

## 🐛 Challenges & Solutions
*   **Provider Connectivity:** Encountered a "Docker daemon not running" error during the `plan` phase. Resolved by ensuring the Docker Desktop engine was fully initialized before running Terraform.
*   **State Security:** Implemented a `.gitignore` to ensure the `terraform.tfstate` file (which contains local infrastructure memory) is never committed to version control.