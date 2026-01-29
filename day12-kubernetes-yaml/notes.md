# Day 12 – Kubernetes YAML (Pods, Deployments, Services)

## Imperative vs Declarative

Imperative:
- Tell Kubernetes HOW to do things
- Example: kubectl create deployment

Declarative:
- Tell Kubernetes WHAT you want
- Kubernetes figures out HOW
- Uses YAML files

Production uses declarative approach.

---

## Kubernetes YAML Structure

Common fields:
- apiVersion
- kind
- metadata
- spec

Example:
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
    - name: nginx
      image: nginx

---

## Pod
Pod is the smallest unit in Kubernetes.

- Runs one or more containers
- Shares network and storage
- Not self-healing alone

---

## Pod YAML Example

apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
    - name: nginx
      image: nginx
      ports:
        - containerPort: 80

---

## Deployment
Deployment manages Pods.

Features:
- Replica management
- Self-healing
- Rolling updates

---

## Deployment YAML Example

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx
          ports:
            - containerPort: 80

---

## Service
Service exposes Pods to network.

Types:
- ClusterIP (internal)
- NodePort (external via node)
- LoadBalancer (cloud)

---

## Service YAML Example

apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  type: NodePort
  selector:
    app: nginx
  ports:
    - port: 80
      targetPort: 80

---

## kubectl with YAML
- kubectl apply -f file.yaml
- kubectl get all
- kubectl delete -f file.yaml

---

## What I Learned Today
- Declarative Kubernetes
- Writing YAML manifests
- Pods, Deployments, Services
- Applying and updating resources

---

## Interview Notes
- YAML defines desired state
- Deployment manages pods
- Services expose pods
- Declarative approach is production standard
