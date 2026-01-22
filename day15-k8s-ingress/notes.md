# Day 15 – Kubernetes Ingress (Traffic Routing)

## Why Ingress?
Ingress provides HTTP/HTTPS routing to Kubernetes services.

Problems without Ingress:
- NodePort exposes random ports
- Multiple services need multiple ports
- No central routing

Ingress solves this with:
- Single entry point
- Host & path-based routing
- TLS termination

---

## Ingress vs Service
Service:
- Exposes pods
- L4 (TCP/UDP)

Ingress:
- Routes HTTP/HTTPS
- L7 (application layer)
- Works on top of Services

---

## Ingress Controller
Ingress is just rules.
Ingress Controller implements the rules.

Popular controllers:
- NGINX Ingress
- Traefik
- HAProxy

We use NGINX Ingress.

---

## Installing Ingress Controller (Minikube)
minikube addons enable ingress

Verify:
kubectl get pods -n ingress-nginx

---

## Ingress YAML Structure
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: app-ingress
spec:
  rules:
    - host: app.local
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: app-service
                port:
                  number: 80

---

## Host-Based Routing
Different domains → different services

Example:
- app.local → frontend
- api.local → backend

---

## Path-Based Routing
Same domain → different paths

Example:
- / → frontend
- /api → backend

---

## What I Learned Today
- Purpose of Ingress
- Ingress Controller concept
- HTTP routing rules
- Production-style traffic handling

---

## Interview Notes
- Ingress manages HTTP/HTTPS traffic
- Works at L7
- Requires Ingress Controller
- Replaces NodePort in production
