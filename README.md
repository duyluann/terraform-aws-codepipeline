# 🚧 Terraform on AWS CodePipeline Project

![Terraform Validation](https://codebuild.ap-southeast-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiMWxNWFp1TVVjVFE0N0VIeFB2SFNaRCt4clVzallPSWxCYWY2SWtmQ01NelFnbVpVd1RmYnZiN3N4aGRaR0M5Qmh4R1I3a0tpaXdqRTU0L29yOEpZejlVPSIsIml2UGFyYW1ldGVyU3BlYyI6Ilp3dnlVeHk4RTRzT1BPcWIiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=main)

This repository provides a structured template for Terraform projects, enabling consistent and scalable infrastructure deployments. The template is equipped with best practices, CI/CD integration, and environment-specific configurations to streamline your infrastructure management.

## 📁 Repository Structure

```bash
.
├── CODEOWNERS                      # 👥 Defines code owners for the repository
├── LICENSE                         # 📜 License for the repository
├── README.md                       # 📖 This file
├── backend.tf                      # 🗄️ Configuration for Terraform backend
├── environments                    # 🌐 Environment-specific variable files
│   ├── dev
│   │   └── dev.tfvars              # 🛠️ Development environment variables
│   ├── prod
│   │   └── prod.tfvars             # 🚀 Production environment variables
│   └── qa
│       └── qa.tfvars               # 🧪 QA environment variables
├── locals.tf                       # 📍 Local values for the Terraform configuration
├── main.tf                         # 🔧 Main Terraform configuration file
├── modules                         # 📦 Directory for reusable Terraform modules
│   └── module1
│       ├── main.tf                 # 🔧 Module-specific configuration
│       ├── outputs.tf              # 📤 Module-specific outputs
│       └── variables.tf            # 📥 Module-specific variables
├── providers.tf                    # 🌐 Provider configurations
├── templates                       # 📝 Build specifications and validation scripts
│   ├── buildspec-apply.yaml        # 🛠️ Buildspec for applying Terraform configurations with AWS CodeBuild
│   ├── buildspec-destroy.yaml      # 💣 Buildspec for destroying resources with AWS CodeBuild
│   ├── buildspec-plan.yaml         # 🔄 Buildspec for generating a Terraform execution plan using AWS CodeBuild
│   ├── buildspec-validate.yaml     # ✅ Buildspec for validating the Terraform code with AWS CodeBuild
│   └── scripts
│       └── tf-validation.sh        # 🛡️ Shell script to validate Terraform configurations
└── variables.tf                    # 📥 Input variables for the Terraform configuration
```

## 🚀 Getting Started

### 🧰 Prerequisites

- Terraform: Ensure you have Terraform installed.
- Docker: Required for the development container setup.
- VSCode: Recommended for development, with the Dev Containers extension.

### 🖥️ Development Environment

To get started with development, you can use the pre-configured development container:

1. Open in VSCode:

- Install the Dev Containers extension.
- Open the repository in VSCode.
- You should see a prompt to reopen the project in the dev container.

2. Build and Run:

- The dev container is pre-configured with all the necessary tools and extensions.
- You can start writing and testing your Terraform configurations immediately.

### 🛠️ Terraform Configuration

- Backend Configuration: The `backend.tf` file configures the remote state storage for Terraform.
- Environment Variables: The `environments/` directory contains environment-specific variable files (`.tfvars`).
- Modules: Reusable Terraform modules are stored in the `modules/` directory.

### 🔄 CI/CD

This repository uses `AWS CodeBuild` projects with the `buildspec` files under `templates` folder to configure.

### Terraform CodePipeline Deployment

This repository contains the necessary CloudFormation template to create a Terraform-based AWS CodePipeline. Follow the instructions below to deploy the stack directly into your AWS account.

#### Deploy the Stack

To deploy the stack directly into your AWS account, click the button below:

[![Launch Stack](https://devops4life-cloudformation-templates.s3.ap-southeast-1.amazonaws.com/launch-stack-aws.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=MyTerraformPipelineStack&templateURL=https://devops4life-cloudformation-templates.s3.ap-southeast-1.amazonaws.com/terraform-aws-codepipeline/cf-codepipeline.yaml)

#### Parameters
- **GitHubAccountName**: Input your GitHub account name.
- **GitHubRepositoryName**: Input your repository name.

Make sure to update the parameters when deploying to match your GitHub repository.

### ✅ Pre-Commit Hooks

Pre-commit hooks are set up to ensure code quality and consistency. To install the pre-commit hooks:

```bash
pre-commit install
```

## 🤝 Contributing

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with a detailed description of the changes.

## 📜 License

This project is licensed under the [MIT License](LICENSE).

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
