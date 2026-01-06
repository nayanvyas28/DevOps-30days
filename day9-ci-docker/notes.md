# Day 09 – CI/CD Docker Build & Push

## CI with Docker
CI pipelines often:
- Build Docker images
- Run tests inside containers
- Push images to registry

---

## Docker Image Registry
A registry stores Docker images.

Examples:
- Docker Hub
- AWS ECR
- GitHub Container Registry

---

## GitHub Secrets
Secrets are encrypted variables used in workflows.

Used for:
- Docker Hub credentials
- Cloud access keys
- Tokens

Secrets are referenced as:
${{ secrets.SECRET_NAME }}

---

## CI Flow for Docker
1. Developer pushes code
2. GitHub Actions starts
3. Docker image is built
4. Image pushed to Docker Hub
5. Deployment uses the image

---

## What I Learned Today
- CI pipeline for Docker
- Secure secret handling
- Docker image build automation
- Registry usage

---

## Interview Notes
- CI builds Docker images
- Registries store images
- Secrets keep credentials safe
- Pipelines automate releases
 