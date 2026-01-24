# Day 17 – Kubernetes StatefulSets

## Stateless vs Stateful Applications

Stateless applications:
- Do not store data locally
- Can be restarted anytime
- Easy to scale

Examples:
- Frontend
- REST APIs

Stateful applications:
- Store persistent data
- Need stable identity
- Require careful startup/shutdown

Examples:
- Databases
- Message queues

---

## Why Deployments Are Not Enough
Deployments:
- Create pods with random names
- Do not guarantee pod order
- Do not guarantee dedicated storage

This is risky for databases.

---

## What is a StatefulSet?
A StatefulSet is a Kubernetes workload used for stateful applications.

Key features:
- Stable pod names
- Stable persistent storage
- Ordered deployment and scaling
- Predictable network identity

---

## Stable Pod Identity
Pods are created with fixed names:
- mysql-0
- mysql-1
- mysql-2

Pod names never change, even after restart.

---

## Stable Storage
Each pod gets its own PersistentVolume.

Example:
- mysql-0 → pvc-mysql-0
- mysql-1 → pvc-mysql-1

Deleting a pod does NOT delete its data.

---

## Ordered Operations
StatefulSet ensures:
- Pods start one by one
- Pods stop in reverse order

This prevents data corruption.

---

## Headless Service
StatefulSets use a headless service:
- clusterIP: None
- No load balancing
- Direct DNS to pods

Example DNS:
mysql-0.mysql.default.svc.cluster.local

---

## StatefulSet YAML Structure
Important fields:
- kind: StatefulSet
- serviceName
- volumeClaimTemplates
- replicas

---

## Example StatefulSet YAML
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: mysql
spec:
  serviceName: mysql
  replicas: 3
  selector:
    matchLabels:
      app: mysql
  template:
    metadata:
      labels:
        app: mysql
    spec:
      containers:
        - name: mysql
          image: mysql:8
          volumeMounts:
            - name: data
              mountPath: /var/lib/mysql
  volumeClaimTemplates:
    - metadata:
        name: data
      spec:
        accessModes: ["ReadWriteOnce"]
        resources:
          requests:
            storage: 1Gi

---

## What I Learned Today
- Difference between Deployment and StatefulSet
- Why databases need StatefulSets
- Stable identity and storage
- Role of headless services

---

## Interview Notes
- StatefulSets are used for databases
- They provide stable pod identity
- They ensure persistent storage
- They support ordered scaling
