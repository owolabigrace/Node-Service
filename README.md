# Node.js CI/CD Pipeline with Terraform, Ansible & GitHub Actions

## Project Overview

This project demonstrates a complete CI/CD pipeline for deploying a Node.js application to an AWS EC2 instance.

The infrastructure is provisioned using Terraform, the server is configured using Ansible, and deployments are automated using GitHub Actions over SSH.

The goal of this project is to automate everything from server creation to application deployment.

---

## Architecture

GitHub Repository
        │
        ▼
GitHub Actions
        │
        ▼
SSH into EC2 Instance
        │
        ▼
Pull Latest Code
        │
        ▼
Install Dependencies
        │
        ▼
Restart Application (PM2)
        │
        ▼
Node.js Application

Infrastructure

Terraform
        │
        ▼
AWS EC2 Instance
        │
        ▼
Ansible Configuration
        │
        ▼
Node.js + Nginx + PM2

---

## Technologies Used

- AWS EC2
- Terraform
- Ansible
- GitHub Actions
- Node.js
- Express.js
- PM2
- Nginx
- Git
- SSH

---

## Features

- Infrastructure as Code using Terraform
- Automated server configuration using Ansible
- Automatic deployment on every push to the main branch
- Process management using PM2
- Secure deployment using SSH keys and GitHub Secrets
- Repeatable and automated deployment pipeline

---

## Project Structure

```
.
├── terraform/
│   ├── main.tf
│   └── outputs.tf
│
├── ansible-server-setup/
│   ├── roles/
│   │   ├── base/
│   │   ├── nginx/
│   │   ├── app/
│   │   └── ssh/
│   ├── inventory.ini
│   └── setup.yml
│
├── node-service/
│   ├── index.js
│   ├── package.json
│   └── .github/
│       └── workflows/
│           └── deploy.yml
```

---

## Deployment Workflow

1. Terraform provisions an EC2 instance.
2. Terraform generates an Ansible inventory.
3. Terraform executes the Ansible playbook.
4. Ansible installs:
   - Node.js
   - npm
   - Git
   - Nginx
   - PM2
5. Ansible clones the Node.js application.
6. PM2 starts the application.
7. GitHub Actions automatically deploys new changes whenever code is pushed to the `main` branch.

---

## Lessons Learned

During this project I gained practical experience with:

- Infrastructure as Code
- Configuration Management
- CI/CD pipelines
- SSH authentication
- GitHub Actions
- Linux server administration
- Process management with PM2
- Debugging deployment issues
- AWS networking and security groups

---

## Future Improvements

- HTTPS with Let's Encrypt
- Custom domain
- Docker deployment
- Monitoring with Prometheus and Grafana
- Zero-downtime deployments
- Load balancing
- Multi-environment deployments (Development, Staging, Production)
