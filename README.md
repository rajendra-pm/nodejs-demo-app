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

Screenshots
## Screenshots

### Pipeline Success
![Pipeline](screenshots/pipeline.png)
<img width="1892" height="832" alt="image" src="https://github.com/user-attachments/assets/eb6a2d88-db5f-4c8e-9d80-43a220be52ba" />

### DockerHub Image
![DockerHub](screenshots/dockerhub.png)
<img width="1881" height="682" alt="image" src="https://github.com/user-attachments/assets/390d7889-9c77-4d41-b7ea-8e57b0291dd6" />

### Running App
![App](screenshots/app.png)
<img width="1908" height="961" alt="image" src="https://github.com/user-attachments/assets/648745e5-7ff4-42f0-ad7a-f0f9739c8f22" />

Summary

This project shows a fully automated CI/CD pipeline for a Node.js application with Docker.
It can be extended for production deployment or used as a template for future projects.






