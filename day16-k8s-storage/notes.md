# Day 16 – Kubernetes Volumes, PV & PVC

## Stateless vs Stateful Apps
Stateless:
- No data stored locally
- Easy to scale
Examples: frontend apps, APIs

Stateful:
- Data must persist
Examples: databases, file uploads

---

## Volumes in Kubernetes
Volumes provide storage to Pods.

Key point:
- Volume lifetime is tied to Pod
- If Pod is deleted, volume data may be lost (depends on type)

---

## PersistentVolume (PV)
PV represents actual storage in the cluster.

- Created by admin
- Cluster-wide resource
- Has size & access mode

---

## PersistentVolumeClaim (PVC)
PVC is a request for storage by an application.

- Created by developer
- Binds to a suitable PV
- Decouples app from storage details

---

## PV → PVC Flow
1. Admin creates PV
2. Developer creates PVC
3. Kubernetes binds PVC to PV
4. Pod uses PVC

---

## Access Modes
- ReadWriteOnce (RWO)
- ReadOnlyMany (ROX)
- ReadWriteMany (RWX)

---

## What I Learned Today
- Need for persistent storage
- Difference between Volume, PV, PVC
- How Kubernetes binds storage
- How apps retain data across restarts

---

## Interview Notes
- Containers are ephemeral
- PV provides storage
- PVC requests storage
- Volumes mount storage into pods
