# Day 07 – Docker Compose for DevOps

## What is Docker Compose?
Docker Compose is a tool to define and run multi-container Docker applications.

Uses:
- Run multiple containers together
- Define services, networks, volumes
- Start/stop entire stack easily

Command:
docker compose up

---

## docker-compose.yml
This YAML file defines all services.

Main sections:
- version
- services
- ports
- volumes
- networks
- environment

---

## Example Architecture
Application Stack:
- Web (Nginx)
- App (Node/Python)
- DB (MySQL/PostgreSQL)

All run using one file.

---

## Basic docker-compose.yml Example
version: "3.8"

services:
  web:
    image: nginx
    ports:
      - "8080:80"

---

## Multi-Container Example (App + DB)
version: "3.8"

services:
  app:
    image: node:18
    ports:
      - "3000:3000"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: root

---

## Docker Compose Commands
- docker compose up
- docker compose up -d
- docker compose down
- docker compose ps
- docker compose logs

---

## Volumes
Volumes persist data.

Example:
volumes:
  - db_data:/var/lib/mysql

---

## Networking
All services communicate using service names.

Example:
app connects to db using hostname: db

---

## Docker Compose in DevOps
- Used in development
- Used in CI pipelines
- Used for testing before Kubernetes

---

## What I Learned Today
- Docker Compose basics
- docker-compose.yml structure
- Running multi-container apps
- Volumes & networking
- Managing stack with one command

---

## Interview Notes
- Docker Compose manages multi-container apps
- Services talk via service names
- Used before Kubernetes in DevOps lifecycle
