# Day 18 – Kubernetes Networking Basics

## Kubernetes Networking Model
Kubernetes follows these rules:
1. Pods can communicate with each other without NAT
2. Pods can communicate across nodes
3. Services provide stable access to pods

---

## Pod-to-Pod Communication
- Each Pod gets a unique IP
- Pods can talk directly using IP
- Pod IPs change when pods restart

Therefore:
Pod IPs are NOT reliable

---

## What is a Service?
A Service provides a stable endpoint to access pods.

Why Services exist:
- Pods die & restart
- Pod IPs change
- Clients need stable access

Service uses labels to select pods.

---

## Service Types

### ClusterIP (Default)
- Internal access only
- Used for backend services

Example:
frontend → backend

---

### NodePort
- Exposes service on node IP and port
- Used for testing and demos
- Not recommended for production

---

### LoadBalancer
- Exposes service using cloud load balancer
- Used in cloud environments
- Costs money

---

## kube-proxy
kube-proxy runs on every node.

Responsibilities:
- Maintains network rules
- Routes traffic to pods
- Load balances requests

---

## DNS in Kubernetes
Kubernetes provides built-in DNS.

Service DNS format:
service-name.namespace.svc.cluster.local

Example:
backend.default.svc.cluster.local

---

## Service Discovery
Pods discover services using DNS.

Applications connect using:
- Service name
- Not pod IP

---

## Headless Service
Headless service:
- clusterIP: None
- No load balancing
- Direct pod DNS

Used with:
- StatefulSets
- Databases

---

## What I Learned Today
- Kubernetes networking basics
- Role of services
- Service types and use cases
- DNS & service discovery
- kube-proxy role

---

## Interview Notes
- Services provide stable networking
- Pod IPs are ephemeral
- ClusterIP is default service
- DNS enables service discovery
