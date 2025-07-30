# Website On Azure

## Overview
This project is a custom-built website deployed on **Microsoft Azure** using **Infrastructure as Code (IaC)** with an ARM template and a CI/CD pipeline via **Azure DevOps**.

## Architecture
- **IaC**: Azure Resource Manager (ARM) template stored in an **Azure Repo**  
- **CI/CD**: Automated deployment via **Azure DevOps Pipelines**  
- **Hosting**: Azure App Service
- **Secrets Management**: Azure Key Vault

## Deployment Process
1. The yaml pipeline **creates a new resource group** in Azure.
2. Deploys infrastructure using the **ARM template**.
3. Stores **connection strings & SAS tokens** in **Azure Key Vault** for the Web App to reference securely.
4. Configures **custom domain settings** inside Key Vault for the Web App.

## Next Steps
1. Enhance ARM Template Tagging
  - Add environment parameters to template.json
  - Apply tags to all resources (Key Vault, App Service Plan, Web App)
2. Create Environment-Specific Parameter Files
  - Rename current parameters file to `dev.parameters.json` & `prod.parameters.json`
  - Add environment-specific tag values to each parameter file
