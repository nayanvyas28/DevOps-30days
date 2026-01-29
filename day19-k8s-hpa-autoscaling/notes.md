# Day 19 – Kubernetes Horizontal Pod Autoscaler (HPA)

## What is Auto Scaling?
Auto scaling automatically adjusts the number of pods based on load.

Benefits:
- Handles traffic spikes
- Improves availability
- Saves infrastructure cost

---

## What is HPA?
HPA (Horizontal Pod Autoscaler) automatically scales pods in a Deployment,
ReplicaSet, or StatefulSet.

HPA works by:
- Monitoring metrics (CPU/Memory)
- Increasing or decreasing replicas

---

## Horizontal vs Vertical Scaling
Horizontal Scaling:
- Add/remove pods
- Used by Kubernetes HPA

Vertical Scaling:
- Increase CPU/RAM of pod
- Requires pod restart

Kubernetes primarily uses horizontal scaling.

---

## Metrics Used by HPA
Common metrics:
- CPU utilization
- Memory utilization
- Custom metrics (advanced)

Example:
Target CPU = 50%
If usage > 50% → scale up
If usage < 50% → scale down

---

## Metrics Server
HPA requires Metrics Server.

Metrics Server:
- Collects CPU & memory usage
- Provides metrics to Kubernetes API
- HPA reads metrics from it

Without Metrics Server:
HPA will NOT work.

---

## How HPA Works (Flow)
1. Metrics Server collects pod metrics
2. HPA controller checks metrics
3. Compares with target value
4. Scales replicas up/down
5. Kubernetes creates or deletes pods

---

## HPA YAML Structure
Key fields:
- scaleTargetRef
- minReplicas
- maxReplicas
- metrics

---

## Example HPA YAML
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: nginx-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: nginx-deployment
  minReplicas: 2
  maxReplicas: 10
  metrics:
    - type: Resource
      resource:
        name: cpu
        target:
          type: Utilization
          averageUtilization: 50

---

## What I Learned Today
- Why auto-scaling is needed
- How HPA works
- Role of Metrics Server
- CPU-based scaling logic
- Production scaling strategy

---

## Interview Notes
- HPA performs horizontal scaling
- Uses metrics like CPU & memory
- Requires Metrics Server
- Prevents overloading applications
