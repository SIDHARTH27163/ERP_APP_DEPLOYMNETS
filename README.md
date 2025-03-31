ERP_APP_DEPLOYMENTS – GitHub Repository Description
Description:
This repository contains Dockerized deployment configurations and scripts for the ERP Application, including Jenkins pipelines, Docker Compose, Amazon Corretto-based builds, and Terraform configurations. It simplifies the process of building, testing, and deploying the ERP application across multiple environments using containerized infrastructure.

 Tech Stack:

Backend: Java (Spring Boot)

Database: MySQL

Deployment: Docker, Docker Compose, Terraform

CI/CD: Jenkins (in Docker with plugins for Spring app)

Java Runtime: Amazon Corretto 21
Key Features:

Dockerfile with Amazon Corretto 21 base image for optimized Java performance.

Jenkins in Docker with pre-installed Spring Boot plugins for seamless integration.

Docker Compose for multi-container orchestration.

Terraform configurations for infrastructure as code (IaC) management.

Volume management for persistent data storage.

Environment-specific configurations for flexible and consistent deployments.
Usage:

Clone the repo and build Docker images.

Use docker-compose up -d for local deployment.

Run Terraform scripts for infrastructure provisioning.

Configure Jenkins pipelines for automated CI/CD workflows.
Contributions and Issues: