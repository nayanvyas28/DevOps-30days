# Day 06 – Docker Fundamentals for DevOps

## What is Docker?
Docker is a containerization platform that packages applications with all dependencies.

Benefits:
- Lightweight
- Fast startup
- Portable
- Consistent environments

---

## Container vs Virtual Machine
Virtual Machine:
- Heavy
- Includes full OS
- Slow startup

Container:
- Lightweight
- Shares host OS kernel
- Fast startup

---

## Docker Architecture
Docker Components:
- Docker Client
- Docker Daemon
- Docker Image
- Docker Container
- Docker Registry (Docker Hub)

Flow:
Dockerfile → Image → Container

---

## Docker Images
Image = blueprint/template  
Images are immutable.

Commands:
docker pull nginx
docker images

---

## Docker Containers
Container = running instance of image.

Commands:
docker run nginx
docker ps
docker ps -a
docker stop <container_id>
docker rm <container_id>

---

## Dockerfile
Dockerfile defines how to build an image.

Basic Dockerfile:
FROM ubuntu
RUN apt update
CMD ["echo","Hello Docker"]

---

## Ports Mapping
Maps container port to host port.

Example:
docker run -p 8080:80 nginx

---

## Docker in DevOps
- Used in CI/CD pipelines
- Base for Kubernetes
- Used for microservices

---

## What I Learned Today
- Containers vs VMs
- Docker architecture
- Images and containers
- Dockerfile basics
- Port mapping

---

## Interview Notes
- Docker packages apps with dependencies
- Containers are lightweight
- Dockerfile builds images
- Containers run images
