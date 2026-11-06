# DeployCraft CI/CD Automation ⚙️

## Project Overview

This project demonstrates how to automate Docker image building and application testing using GitHub Actions.

DeployCraft helps developers and small teams reduce manual deployment work through automated CI workflows.

Whenever relevant application code is pushed to the `main` branch or a pull request targets `main`, GitHub Actions automatically executes the workflow.

## Technology Stack

- GitHub Actions
- Docker
- Nginx Alpine
- Ubuntu GitHub-hosted runner
- Git and GitHub

## Project Architecture

```text
deploycraft-portfolio/
│
├── .github/
│   └── workflows/
│       └── docker-ci.yml
│
├── docker-service/
│   ├── app/
│   │   └── index.html
│   ├── Dockerfile
│   └── README.md
│
└── cicd-service/
    └── README.md
```

## CI Pipeline Workflow

The pipeline performs the following steps:

1. **Trigger:** Detects relevant pushes to `main` and pull requests targeting `main`.
2. **Checkout:** Retrieves the repository source code.
3. **Docker Build:** Builds a Docker image using the Dockerfile.
4. **Container Execution:** Starts the application inside a Docker container.
5. **Automated Testing:** Uses curl to verify the HTTP response and checks for the DeployCraft application content.
6. **Cleanup:** Removes the test container after execution.

## Workflow Configuration

The GitHub Actions workflow is located at:

`.github/workflows/docker-ci.yml`

It uses:

- Ubuntu latest runner
- Docker CLI
- GitHub Actions checkout
- Automated HTTP testing
- Automatic container cleanup

## How to Run the Pipeline

### 1. Clone the repository

```bash
git clone https://github.com/Avinash-0009/deploycraft-portfolio.git

cd deploycraft-portfolio
```

### 2. Make an application change

Edit:

`docker-service/app/index.html`

### 3. Commit and push

```bash
git add docker-service/app/index.html

git commit -m "Update application"

git push origin main
```

### 4. Monitor the pipeline

Open the GitHub Actions tab:

https://github.com/Avinash-0009/deploycraft-portfolio/actions

Select the **DeployCraft Docker CI** workflow to inspect execution logs and test results.

## Verification

The workflow validates:

- Docker image builds successfully.
- Container starts successfully.
- Application responds over HTTP.
- Expected DeployCraft content is present.
- Test container is cleaned up.

## Current Implementation Scope

This project implements Continuous Integration (CI) and automated Docker build validation.

It does not yet include production deployment, container registry publishing, or automated infrastructure provisioning.

These capabilities can be introduced in future pipeline iterations.

## Business Application

DeployCraft provides CI/CD pipeline configuration and automation assistance for developers, startups, and small software teams.

Our objective is to help customers automate repetitive development and testing workflows.

---

**DeployCraft — Build. Automate. Deploy.**