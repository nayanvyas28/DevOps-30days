# Day 20 – Kubernetes Architecture & Control Loop

## Kubernetes Philosophy
Kubernetes is a declarative system.

You define:
- Desired state (YAML)

Kubernetes ensures:
- Actual state matches desired state

This is called reconciliation.

---

## Kubernetes Cluster Architecture
A Kubernetes cluster has:
- Control Plane (brain)
- Worker Nodes (muscle)

---

## Control Plane Components

### API Server
- Entry point to Kubernetes
- All commands go through API Server
- kubectl → API Server

---

### etcd
- Distributed key-value store
- Stores entire cluster state
- Single source of truth

If etcd is lost → cluster is lost.

---

### Scheduler
- Assigns pods to nodes
- Decides WHERE a pod runs
- Considers CPU, memory, constraints

---

### Controller Manager
- Runs controllers
- Watches cluster state
- Fixes differences between desired and actual state

Examples:
- Deployment controller
- Node controller
- ReplicaSet controller

---

## Worker Node Components

### kubelet
- Runs on each node
- Talks to API Server
- Ensures containers are running

---

### Container Runtime
- Docker / containerd
- Pulls images
- Runs containers

---

### kube-proxy
- Handles networking
- Routes traffic to pods
- Implements Services

---

## Controllers & Reconciliation Loop
Controller logic:
1. Watch desired state
2. Watch current state
3. Compare both
4. Take action to fix mismatch

This runs continuously.

Example:
Desired replicas: 3  
Current replicas: 2  
→ Kubernetes creates 1 pod

---

## Why Kubernetes is Self-Healing
- Pod crashes → controller recreates it
- Node fails → pods rescheduled
- Config changes → rollout happens

All due to reconciliation loop.

---

## What I Learned Today
- Kubernetes architecture
- Control plane internals
- Controller manager role
- Reconciliation loop concept
- How Kubernetes self-heals

---

## Interview Notes
- Kubernetes is a desired-state system
- API Server is the entry point
- etcd stores cluster state
- Controllers enforce desired state
- Reconciliation loop enables self-healing
