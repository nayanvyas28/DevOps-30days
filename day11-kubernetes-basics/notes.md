# Day 11 – Kubernetes Fundamentals for DevOps

## What is Kubernetes?
Kubernetes is a container orchestration platform used to manage containerized applications at scale.

It automates:
- Deployment
- Scaling
- Load balancing
- Self-healing

---

## Why Kubernetes?
Docker alone cannot:
- Restart failed containers automatically
- Scale containers easily
- Manage multiple containers across servers

Kubernetes solves these problems.

---

## Kubernetes Cluster
A cluster is a group of machines running Kubernetes.

Two main parts:
- Control Plane (Master)
- Worker Nodes

---

## Control Plane Components
- API Server – entry point for commands
- Scheduler – assigns pods to nodes
- Controller Manager – ensures desired state
- etcd – key-value store (cluster data)

---

## Worker Node Components
- kubelet – communicates with control plane
- container runtime – Docker/containerd
- kube-proxy – networking

---

## What is a Pod?
A Pod is the smallest unit in Kubernetes.

- Contains one or more containers
- Containers in a pod share:
  - Network
  - Storage

---

## Kubernetes Objects
- Pod – runs containers
- Deployment – manages pods
- Service – exposes pods
- Namespace – logical isolation

---

## kubectl
kubectl is the CLI tool for Kubernetes.

Used to:
- Create resources
- View cluster status
- Debug issues

---

## What I Learned Today
- Kubernetes basics
- Cluster architecture
- Pods & nodes
- Core Kubernetes components
- kubectl fundamentals

---

## Interview Notes
- Kubernetes orchestrates containers
- Pods are smallest unit
- Control plane manages cluster
- Kubernetes provides self-healing & scaling
