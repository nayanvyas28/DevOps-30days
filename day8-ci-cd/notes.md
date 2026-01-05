# Day 08 – CI/CD with GitHub Actions

## What is CI/CD?
CI/CD automates building, testing, and deploying applications.

CI (Continuous Integration):
- Code is integrated frequently
- Automated build & test

CD (Continuous Deployment):
- Code is deployed automatically after CI

---

## Why CI/CD is Important
- Faster releases
- Fewer bugs
- No manual deployment
- Consistent process

---

## What is GitHub Actions?
GitHub Actions is a CI/CD tool built into GitHub.

It uses workflows written in YAML.

Workflow triggers:
- push
- pull_request
- schedule
- manual trigger

---

## Workflow Structure
A workflow file lives in:
.github/workflows/

Main components:
- name
- on (trigger)
- jobs
- steps

---

## Example Workflow Flow
1. Developer pushes code
2. GitHub Actions starts workflow
3. Job runs on virtual machine
4. Steps execute commands
5. Build/test results shown

---

## Runners
Runners are machines that execute jobs.

Common runner:
- ubuntu-latest

---

## GitHub Actions in DevOps
- Build Docker images
- Run tests
- Deploy to AWS
- Automate infrastructure

---

## What I Learned Today
- CI/CD concepts
- GitHub Actions basics
- Workflow YAML structure
- Automated jobs on git push

---

## Interview Notes
- CI detects bugs early
- CD automates deployment
- GitHub Actions uses YAML workflows
- Pipelines trigger from Git events
