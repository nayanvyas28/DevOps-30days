# Day 10 – Continuous Deployment to AWS EC2

## What is Continuous Deployment?
Continuous Deployment (CD) automatically deploys applications after CI passes.

Benefits:
- Faster releases
- No manual errors
- Consistent deployments

---

## Deployment Strategy (Basic)
1. Build Docker image
2. Push image to registry
3. SSH into server
4. Pull latest image
5. Stop old container
6. Run new container

---

## SSH-Based Deployment
SSH allows GitHub Actions to run commands on EC2 securely.

We use:
- SSH private key
- EC2 public IP
- GitHub Secrets

---

## Required Secrets
- EC2_HOST → Public IP
- EC2_USER → ubuntu
- EC2_KEY → Private SSH key
- DOCKER_USERNAME → Docker Hub user

---

## Docker Deployment Commands
docker pull image
docker stop container
docker rm container
docker run -d -p 80:80 image

---

## What I Learned Today
- CI vs CD difference
- Automated EC2 deployment
- SSH-based remote execution
- Real production-style workflow

---

## Interview Notes
- CD deploys automatically
- SSH used for remote deployment
- Docker ensures consistency
- Pipelines reduce downtime
