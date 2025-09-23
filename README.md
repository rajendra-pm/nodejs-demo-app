# nodejs-demo-app
# Node.js CI/CD Pipeline with Docker

## Overview
This repository demonstrates a complete **CI/CD pipeline** for a Node.js application using **GitHub Actions** and **Docker**.  
Whenever code is pushed to the `main` branch, the pipeline automatically:

1. Builds the Node.js application
2. Runs tests (if any)
3. Builds a Docker image
4. Pushes the image to **DockerHub**

---

## Repository Structure

ci-cd-docker-nodejs/
│
├── .github/
│ └── workflows/
│ └── main.yml # GitHub Actions workflow
├── Dockerfile # Docker build instructions
├── docker-entrypoint.sh # Optional entrypoint script
├── index.js # Node.js application entry point
├── package.json # Node.js dependencies
├── package-lock.json # Dependency lock file
└── README.md # This file


---

## How CI/CD Works

### Continuous Integration (CI)
- Checkout the repository
- Install Node.js dependencies
- Run tests (if any)

### Continuous Deployment (CD)
- Log in to DockerHub using GitHub Secrets
- Build Docker image with:
  - `latest` tag
  - Commit SHA tag
- Push Docker image to DockerHub repository

---

## DockerHub Image

- **Repository:** `1rajendrapm/nodejs-demo-app`  
- **Pull latest image:**
```bash
docker pull 1rajendrapm/nodejs-demo-app:latest
Run container locally:

docker run -p 3000:3000 1rajendrapm/nodejs-demo-app:latest


Open your browser at http://localhost:3000 to see the app running.

GitHub Secrets

DOCKERHUB_USERNAME → DockerHub username

DOCKERHUB_TOKEN → DockerHub Personal Access Token (with write access)

Note: Do not hardcode credentials in the workflow. Use GitHub Secrets to keep them secure.
